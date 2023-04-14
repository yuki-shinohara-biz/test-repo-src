#イメージのベースを指定
FROM php:7.4-fpm

# Set php.ini
COPY ./php.ini /usr/local/etc/php/

#composerのインストール
COPY --from=composer:2.2 /usr/bin/composer /usr/bin/composer

#パッケージ管理ツールapt-getの更新と必要パッケージのインストール
RUN apt-get update \
&& apt-get install -y \
git \
zip \
unzip \
libpq-dev \
libonig-dev \
libzip-dev \
zlib1g-dev \
poppler-utils

RUN pecl install xdebug-3.1.6 && docker-php-ext-enable xdebug