FROM httpd:2.4

RUN sed -i \
  -e 's/#LoadModule rewrite_module/LoadModule rewrite_module/' \
  -e 's/#LoadModule proxy_module/LoadModule proxy_module/' \
  -e 's/#LoadModule proxy_fcgi_module/LoadModule proxy_fcgi_module/' \
  /usr/local/apache2/conf/httpd.conf

# PHPファイルをPHP-FPMにプロキシする設定とDirectoryIndexを追加
COPY ./my.conf /usr/local/apache2/conf/extra/my.conf
RUN echo "Include conf/extra/my.conf" \
  >> /usr/local/apache2/conf/httpd.conf
