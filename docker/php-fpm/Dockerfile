FROM php:8.2-fpm-alpine

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions xdebug

COPY --from=composer:2.8.0 /usr/bin/composer /usr/bin/composer

COPY php-fpm/99-xdebug.ini /usr/local/etc/php/conf.d/99-php-overrides-dev.ini

USER www-data

WORKDIR /var/www