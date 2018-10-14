FROM php:7.2-fpm

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install libmcrypt-dev zlib1g-dev libicu-dev g++ \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN docker-php-ext-configure intl
RUN docker-php-ext-install intl pdo_mysql mbstring

RUN mkdir /var/logs
RUN touch /var/logs/access.log
RUN touch /var/logs/error.log

WORKDIR "/var/www/html"
