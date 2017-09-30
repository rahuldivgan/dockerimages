FROM alpine:3.6

MAINTAINER Rahul Divgan <rahuldivgan@gmail.com>

RUN apk add --no-cache python py-pip python-dev libffi-dev build-base openssl-dev openssl openssl-dev gcc musl-dev openssh curl linux-headers jq \
    && pip install --upgrade pip \
	&& pip install awscli netaddr requests

#ADD https://releases.hashicorp.com/terraform/0.10.6/terraform_0.10.6_linux_amd64.zip /
ADD lib/terraform_0.10.6_linux_amd64.zip /

RUN unzip terraform_0.10.6_linux_amd64.zip -d /usr/bin \
	&& rm /terraform_0.10.6_linux_amd64.zip \
    && apk del build-base

ENTRYPOINT ["terraform"]
CMD ["--version"]
