# Pyrogram Userbot
![Python Version](https://img.shields.io/badge/Python-v3.8-blue)
![Repo Size](https://img.shields.io/github/repo-size/athphane/userbot)
[![Commit Activity](https://img.shields.io/github/commit-activity/w/athphane/userbot)](https://github.com/athphane/userbot/pulse)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/b10d40c60fc549299eeb7bda1c7501aa)](https://app.codacy.com/manual/athphane/userbot?utm_source=github.com&utm_medium=referral&utm_content=athphane/userbot&utm_campaign=Badge_Grade_Settings)
[![HitCount](http://hits.dwyl.com/athphane/userbot.svg)](http://hits.dwyl.com/athphane/userbot)
[![Contributors](https://img.shields.io/github/contributors/athphane/userbot)](https://github.com/athphane/userbot/graphs/contributors)
![Last Commit](https://img.shields.io/github/last-commit/athphane/userbot/master)
![Issues](https://img.shields.io/github/issues/athphane/userbot)
![Pull Requests](https://img.shields.io/github/issues-pr/athphane/userbot)
[![License](https://img.shields.io/github/license/athphane/userbot)](LICENSE)

<img src="https://i.imgur.com/WXUgDHT.png" width="160" align="right">

> A Telegram Userbot based on [Pyrogram](https://github.com/pyrogram/pyrogram)

This repository contains the source code of a Telegram Userbot and the instructions for running a
copy yourself. Beside its main purpose, the bot is featuring [**Pyrogram Asyncio**](https:////github.com/pyrogram/pyrogram/issues/181) and
[**Smart Plugins**](https://docs.pyrogram.org/topics/smart-plugins); feel free to explore the source code to
learn more about these topics.

I assume you will read this whole README.md file before continuing.

## Requirements
You're gonna need to get the following programs and services either installed on your server
or signed up for. You must do all. It is a cardinal sin if you don't.
* Python 3.10 (requirements were generated for 3.10. Python 3.8 is supported from the looks of it.)
* `virtualenv` installed so that the packages don't interfere with other system packages.

* [MongoDB](https://www.mongodb.com) on your server or a free server from 
[MongoDB Atlas](https://www.mongodb.com/cloud/atlas). (I recommend Atlas as I used it during
development with no issues.)

* [carbon-now-cli](https://github.com/mixn/carbon-now-cli) on your server too generate code images for the
[carbon.py](/userbot/plugins/carbon.py) module. I use this CLI tool cause I don't know and couldn't get selenium
and chromedriver to work nicely on my server/code. I'll be nice and even give you the command to install this.
I assume you already have NPM installed. 
    ```
    Windows: npm install -g carbon-now-cli
    Linux: sudo npm install -g carbon-now-cli --unsafe-perm=true --allow-root
    MacOS: I assume almost the same as linux ¯\_(ツ)_/¯
    ``` 

## Installation and Deployment
*The way I deploy*
```bash
git clone https://github.com/athphane/userbot.git
cd userbot
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
python -m userbot
```
*Using docker*
- Save the following content as `docker-compose.yml`
```yml
version: '3.5'
services:
  userbot:
    hostname: userbot
    volumes:
      - ./config:/root/userbot/config
    image: ghcr.io/athphane/userbot:latest
6422757860:AAFrUeqXwLcjsoaGUbsE2UXrOiK9Oeb1nN0
```
- First run:
```bash
docker compose run --rm userbot python -m userbot
```
- Configure userbot and stop container **CTRL+C**
- Run the container again de-attached:
```bash
docker compose up -d
```
## Spotify integration
To get the Spotify commands working on the Userbot, you need to get a CLIENT_ID and CLIENT_SECRET
form the [Spotify Developer Portal]('https://developer.spotify.com/dashboard/applications) and add
them into your userbot.ini file.

On the Spotify developer portal, make sure to set your application `Redirect URI` to 
'http://localhost:8888/callback'. 

Now is a good time 
Then go ahead and run the command `python spotify.py` 
in the projects root directory. 

This will create a file called `.cache-yourusername`. You need to transfer this file to the
project root of the server that will be running your userbot. This is a one time setup.


## Known issues
* `.restart` command do not work on Termux as [psutils is not supported on Android](https://github.com/giampaolo/psutil/issues/913). \
CTRL+C, run `git pull` and `python -m userbot` to update bot on termux.

## Star History

<a href="https://star-history.com/#athphane/userbot&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=athphane/userbot&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=athphane/userbot&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=athphane/userbot&type=Date" />
  </picture>
</a>


## Credits, and Thanks to
*  [Dan](https://t.me/haskell) for his [Pyrogram Library](https://github.com/pyrogram/pyrogram)
*  [Colin Shark](https://t.me/ColinShark) for his [PyroBot](https://git.colinshark.de/PyroBot/PyroBot) which helped with
most of the useful functions used.
*  The people at [MyPaperPlane](https://github.com/MyPaperPlane) for their [Telegram-UserBot](https://github.com/MyPaperPlane/Telegram-UserBot)
that gave a ton of ideas on how and what modules to include in this userbot.
*  [Baivaru](https://github.com/baivaru) for the ton of help that got me this far into making this repo.
---
<p align="center">Made with love from the Maldives ❤</p>
