FROM nginx:alpine
MAINTAINER tana3n
RUN apk update
RUN apk add git nano perl-fcgi imagemagick-perlmagick perl-cryptx perl-net-ssleay
COPY nginx.conf /etc/nginx/nginx.conf
RUN git clone https://github.com/nabe-abk/adiary /var/www/html/adiary 
RUN mv /var/www/html/adiary/adiary.conf.cgi.sample /var/www/html/adiary/adiary.conf.cgi
CMD /docker-entrypoint.sh nginx -g 'daemon off;' & /var/www/html/adiary/adiary.fcgi /var/www/html/adiary/adiary.sock