FROM ubuntu:18.04

MAINTAINER HUNGNV

RUN apt-get update

RUN apt-get -y upgrade

RUN apt-get install -y apache2 && apt-get clean

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid

EXPOSE 80

# update default apache site with config 
# ADD apache-config.conf /etc/apache2/sites-enabled/000-default.conf

CMD ["apachectl", "-D", "FOREGROUND"]
