# FIXME: tutum/debian will be deprecated soon: https://github.com/tutumcloud/tutum-debian/blob/master/README.md
FROM tutum/debian:jessie

RUN rm /etc/apt/apt.conf.d/docker-clean && apt-get update && apt-get install -y sudo net-tools wget sysvinit-core sysvinit sysvinit-utils curl vim man faketime unzip iptables iputils-ping logrotate && apt-get remove -y --purge --auto-remove systemd

RUN mkdir -p /opt/xenon
COPY *.jar /opt/xenon

RUN echo "deb http://http.debian.net/debian jessie-backports main" >> /etc/apt/sources.list
RUN apt-get update
RUN apt install -t jessie-backports -y openjdk-8-jre-headless ca-certificates-java
RUN apt-get install -y openjdk-8-jre
