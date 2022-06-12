FROM node:16.15.1-alpine3.16

RUN apk add --update \
            udev \
            ttf-freefont \
            chromium

RUN mkdir /noto

ADD https://noto-website.storage.googleapis.com/pkgs/NotoSansCJKjp-hinted.zip /noto 

WORKDIR /noto

RUN unzip NotoSansCJKjp-hinted.zip && \
    mkdir -p /usr/share/fonts/noto && \
    cp *.otf /usr/share/fonts/noto && \
    chmod 644 -R /usr/share/fonts/noto/ && \
    fc-cache -fv

WORKDIR /
RUN rm -rf /noto

RUN npm install -g @angular/cli @vue/cli

ENV CHROME_BIN="/usr/bin/chromium-browser"

WORKDIR /workspace

ENTRYPOINT [""]
CMD ["sh"]

