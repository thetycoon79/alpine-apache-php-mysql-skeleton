FROM httpd:alpine3.14
LABEL maintainer="Mohd Zulfadzly <mzulfadzly@yahoo.com>"

RUN  apk update && apk upgrade && \
     apk add openrc --no-cache && \
     apk add --no-cache bash && \
     apk add --no-cache vim && \
     apk add --no-cache lsof && \
     rm -rf /var/cache/apk/*

COPY php-fpm.conf /usr/local/apache2/conf/php-fpm.conf
RUN sed -i '/LoadModule rewrite_module/s/^#//g' /usr/local/apache2/conf/httpd.conf && \
sed -i '/^Listen 80/a Listen 81' /usr/local/apache2/conf/httpd.conf && \
echo "Include /usr/local/apache2/conf/php-fpm.conf" \
    >> /usr/local/apache2/conf/httpd.conf