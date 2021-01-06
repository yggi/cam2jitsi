# cam2jitsi

Directly stream a webcam into a jitsi room.

Intended to run headless on a Raspberry Pi

## Requirements

* Hardware: Raspberry Pi
  * Runs fine with a 720p cam on a Pi 2
* OS: Raspberry Pi OS Lite

* Software:
  * chromium
  * chromium-codecs-ffmpeg
  * npm
  * puppeteer

* Script:
  * stream.js (from this repo)


## Installation
Run on Pi:

```
sudo apt-get update
sudo apt-get install chromium chromium-codecs-ffmpeg npm git
npm i puppeteer
git clone https://github.com/yggi/cam2jitsi.git
```

## Configuration

Set the default jitsi link and screen name in stream.js:

```
vi cam2jitsi/stream.js
````

## Execution

### Manual Start

```
node cam2jitsi/stream.js <JITSI-LINK> <NAME>
````

### Autostart

Add to rc.local (before final "exit 0" line):

```
node /home/pi/cam2jitsi/stream.js <JITSI-LINK> <NAME> &
```

## References

* [Original puppeteer script](https://code.saghul.net/2017/09/streaming-a-webcam-to-a-jitsi-meet-room/) by saghul
* [Running puppeteer on raspian](https://samiprogramming.medium.com/puppeteer-on-raspbian-nodejs-3425ccea470e) by Sami C.
* [Jitsi url options](https://github.com/jitsi/jitsi-meet/blob/master/react/features/base/config/configWhitelist.js#L11)

## License

Released as Public Domain under CC0-License
