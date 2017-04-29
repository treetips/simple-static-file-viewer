# Simple static file viewer

This is the simple web server which can read a static files.

これは、静的リソースを簡単に閲覧する事ができるWEBサーバです。

## Description

I cannot confirm the latest static resource when I manage the static resources such as html or the image in git if there is not git environment.

I made Simple static file viewer to solve it.

I use Alpine linux-based nginx and can use it in familiar UI by autoindex.

It is lightweight and is simple and can easily customize it by nginx which got used to treating it.

gitでhtmlや画像等の静的リソースを管理していると、git環境が無いと最新の静的リソースを確認する事ができません。

それを解決するため、Simple static file viewerを作りました。

Alpine linuxベースのnginxを利用しており、autoindexによる見慣れたUIで使う事ができます。

非常に軽量でシンプルで、扱い慣れたnginxによって簡単にカスタマイズする事も可能になっています。

## Features

- Dcoker v17
- docker-compose v1.11
- Alpine linux v1.12.0
- nginx v1.12.0

## Requirement

- Docker
- docker-compose

Change the version of docker-compose.yml from 3 to 2 when you use docker which does not support v3 of docker-compose.

もしdocker-composeのv3に対応していないdockerを使用している場合、docker-compose.ymlのversionを3から2に変更して下さい。

## Usage

1. docker-compose up -d
2. copy static files to htdocs directory.
3. browse http://localhost:8081/

## Installation

    $ git clone https://github.com/treetips/simple-static-file-viewer.git

## Change Lang

Edit docker-compose.yml.

    environment:
      - LANG=ja_JP.UTF-8

## Change timezone

Edit docker-compose.yml.

    environment:
      - TZ=Asia/Tokyo

# Customie nginx

Customize default.conf freely.

default.conf is read as follows by nginx.conf.

default.confを自由にカスタマイズして下さい。

default.confは以下のようにnginx.confによって読み込まれます。

    include /etc/nginx/conf.d/*.conf;

## Known issue for macOS

In Docker for mac, xhyve is used for virtualization, but the problem that the same period of the time cannot perform during sleep of macOS is reported.

Docker for macは仮想化にxhyveが使われていますが、macOSのスリープ中に時刻の同期が行えていない問題が報告されています。

[Time drift in Moby VM and containers caused by system sleep #17
](https://github.com/docker/for-mac/issues/17)

## License

[MIT](http://b4b4r07.mit-license.org)