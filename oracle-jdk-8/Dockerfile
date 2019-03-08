FROM centos:centos7
MAINTAINER rohithn

ENV JAVA_VERSION=8u131 \
    JAVA_VERSION_BUILD=11

# Update and download
# RUN yum update -y && \
RUN yum install -y wget && \
wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" \
http://download.oracle.com/otn-pub/java/jdk/$JAVA_VERSION-b$JAVA_VERSION_BUILD/d54c1d3a095b4ff2b6607d096fa80163/jdk-$JAVA_VERSION-linux-x64.rpm

RUN rm -f jdk-${JAVA_VERSION}-linux-x64.rpm && \
rm -rf /var/cache/yum

RUN alternatives --install /usr/bin/java jar /usr/java/latest/bin/java 200000 && \
 alternatives --install /usr/bin/javaws javaws /usr/java/latest/bin/javaws 200000 && \
 alternatives --install /usr/bin/javac javac /usr/java/latest/bin/javac 200000

ENV JAVA_HOME /usr/java/latest