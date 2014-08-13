## Description

This docker image setup supervisord, used a a base for images that run multiple services on the same container.

*Note*:

The docker philosphy is to run only one service by container, but in some cases (development env, POC), having a
fullstack container with ssh server, database services, etc is useful.
The downside is that you will loose great scaling possibility offered by docker... so you many not use this in prod ;)

## Dependency

This image is based on `trobz/ubuntu`, please check the [specific readme of this image](https://registry.hub.docker.com/u/trobz/ubuntu/).

## Features

### Supervisord

Install and run supervisord as the main docker process.

- supervisord is configured to listen on `8011` port for the web management interface.
- user/password for the web interface and the command line tool are defined based on `USERNAME` and `PASSWORD`,
these environment variables defined for `trobz/ubuntu` image (same as default system user).

## Build

Same as `trobz/ubuntu`, `./build.sh` is used to generated a Dockerfile for each ubuntu version.