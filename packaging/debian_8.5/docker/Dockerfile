FROM debian:8.5

RUN apt-get update
RUN apt-get install -y make
RUN apt-get install -y dpkg-dev
RUN apt-get install -y debhelper
RUN apt-get install -y dh-systemd
RUN apt-get install -y golang

COPY src.tgz /

RUN tar -xzmf /src.tgz

CMD cd /jobber-* && \
    make -C packaging/debian_8.5 pkg-local DESTDIR=/pkgs && \
    cd /pkgs && tar -cf /pkgs.tar ./*
