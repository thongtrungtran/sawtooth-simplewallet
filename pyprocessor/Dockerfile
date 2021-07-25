# Copyright 2018 Intel Corporation
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# -----------------------------------------------------------------------------

FROM ubuntu:bionic

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && \
    apt install sudo && \
    sudo apt-get install software-properties-common -y && \
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 8AA7AF1F1091A5FD && \
    sudo add-apt-repository 'deb [arch=amd64] http://repo.sawtooth.me/ubuntu/chime/stable bionic universe' && \
    sudo apt update && \
    sudo apt-get install -y -q \
#    apt-transport-https \
#    build-essential \
#    ca-certificates \
    python3-sawtooth-sdk \
    python3-protobuf \
    python3-pandas  && \
    sudo apt-get clean && \
    sudo rm -rf /var/lib/apt/lists/*

EXPOSE 4004/tcp

WORKDIR /project/simplewallet/pyprocessor
ENV PATH "$PATH:/project/simplewallet/pyprocessor"

CMD bash -c './simplewallet-tp'
