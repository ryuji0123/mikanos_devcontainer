# See here for image contents: https://github.com/sarisia/mikanos-docker
ARG VARIANT=latest
FROM ghcr.io/sarisia/mikanos:${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && \
    export DEBIAN_FRONTEND=noninteractive && \
    apt-get -y install --no-install-recommends \
        curl lsof git tmux tree vim wget zsh && \
    apt-get clean && \
	rm -rf /var/lib/apt/lists/* && \
	rm -rf /var/cache/apk/*

# settings
USER vscode
ENV HOME /home/vscode
ENV SETTING_PATH $HOME/settings
COPY settings $SETTING_PATH
WORKDIR $SETTING_PATH
RUN sh $SETTING_PATH/setup.sh