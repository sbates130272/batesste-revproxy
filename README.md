# batesste-revproxy: A Ngnix-based Reverse Proxy Service

## Introduction

This repository is a docker-based implementation of an
[NGNIX][ngnix-ref] based [reverse proxy][rev-proxy-ref] that can be
run on a host Linux server. This service ties in with
[systemd][systemdref] and [docker-compose][dc-ref].

The docker-compose file in this repo is *heavily* based on the
great work by the team at [NGNIX Proxy
Manager][https://nginxproxymanager.com/].

## Install

The repo contains a batesste-revproxy.service file for systemd. You
need to perform the following steps in order to install it
sucessfully on Linux based systems.

1. Make sure docker and docker-compose are installed.
1. ```sudo mkdir -p /opt/batesste-revproxy/```
1. ```sudo mkdir -p /opt/batesste-revproxy/data```
1. ```sudo mkdir -p /opt/batesste-revproxy/letsencrypt```
1. ```sudo ln -s /opt/batesste-revproxy/batesste-revproxy-compose.yml <path to this repo's compose file>```
1. ```sudo cp batesste-revproxy.service /usr/lib/systemd/system/```
1. ```sudo systemctl daemon-reload```
1. ```sudo systemctl enable batesste-revproxy```
1. ```sudo systemctl start batesste-revproxy```

## Usage

Once you have performed the steps above you should be able to see the
revproxy service exposed via the hostname of the physical host you
are running on (on port 81).

I suggest you then head over to [this site][] for information on how
to login to the service and start implementing your reverse proxy!

[ngnix-ref]: https://www.nginx.com/
[rev-proxy-ref]: https://en.wikipedia.org/wiki/Reverse_proxy
[npm-ref]: https://nginxproxymanager.com/
[dc-ref]: https://docs.docker.com/compose/reference/
[systemdref]: https://manpages.ubuntu.com/manpages/jammy/man5/systemd.service.5.html
