# FFMPEG Streaming

## Poišči ime input device-a

`ffmpeg -list_devices true -f dshow -i dummy`

## Nastavitve input device-a

`ffmpeg -list_options true -f dshow -i video="DEVICE_NAME"`

## Start stream

`ffmpeg -f dshow -video_size 1920x1080 -rtbufsize 2147.48M -framerate 30 -i video="DEVICE_NAME":audio="DEVICE_NAME" -tune zerolatency -framerate 30 -video_size 1920x1080 -c:v libx264 -c:a mp3 -f mpegts udp://127.0.0.1:10000`

- [ffmpeg dshow command examples](http://trac.ffmpeg.org/wiki/DirectShow)
- [ffmpeg dshow device options list](http://ffmpeg.org/ffmpeg-devices.html#dshow)
- [ffmpeg streaming commands](http://trac.ffmpeg.org/wiki/StreamingGuide)
- [ffmpeg encoding for stream](http://trac.ffmpeg.org/wiki/EncodingForStreamingSites)
- [ffmpeg *H.264* Encoding](https://trac.ffmpeg.org/wiki/Encode/H.264)
- [ffmpeg formats](https://ffmpeg.org/ffmpeg-formats.html)

## OBS

- dodaj `media source`
- input = `udp://127.0.0.1:10000`
- file format = `mpegts`


