FROM golang:1.12
LABEL io.tyk.vendor="Tyk" \
      version="1.0" \
      description="Base image for builds"

ENV GOPATH=/go

RUN apt-get update && apt-get dist-upgrade -y && \
    apt-get install -y ca-certificates \
                       git \
                       curl \
                       jq \
                       build-essential \
                       libluajit-5.1-2 \
                       luarocks \
                       python3-setuptools \
                       python3-dev \
                       python3-pip
RUN luarocks install lua-cjson
RUN pip3 install grpcio protobuf
RUN mkdir -p $GOPATH