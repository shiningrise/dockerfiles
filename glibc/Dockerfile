FROM xataz/alpine:3.4
MAINTAINER xataz <https://github.com/xataz>

ARG GLIBC_VER=2.23-r3
ARG GLIBC_URL=https://github.com/andyshinn/alpine-pkg-glibc/releases/download/unreleased

LABEL description="Glibc image based on alpine" \
      tags="latest 2.23-r3 2.23 2" \
      build_ver="2016072701"

RUN BUILD_DEPS="wget \
            ca-certificates" \
    && apk add -U ${BUILD_DEPS} \
    && wget ${GLIBC_URL}/glibc-${GLIBC_VER}.apk -O /tmp/glibc-${GLIBC_VER}.apk \
    && wget ${GLIBC_URL}/glibc-bin-${GLIBC_VER}.apk -O /tmp/glibc-bin-${GLIBC_VER}.apk \
    && apk add --allow-untrusted /tmp/glibc-${GLIBC_VER}.apk /tmp/glibc-bin-${GLIBC_VER}.apk \
    && apk del ${BUILD_DEPS} \
    && rm -rf /var/cache/apk/* /tmp/*
