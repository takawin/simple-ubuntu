FROM ubuntu:22.04

SHELL ["/bin/bash", "-c"]

RUN apt-get update \
    && apt-get install -y git vim curl zip unzip sudo \
    && groupadd --gid 1000 sudogroup \
    && useradd --uid 1000 --shell /bin/bash --gid 1000 -m vscode \
    && echo %sudogroup ALL=\{ALL\} NOPASSWD: ALL > /etc/sudoers.d/sudogroup

RUN su vscode --command \
    'curl -s "https://get.sdkman.io" | bash \
    && source "${HOME}/.sdkman/bin/sdkman-init.sh" \
    && sdk install java "18.0.2-amzn" \
    && sdk install gradle "7.5"'