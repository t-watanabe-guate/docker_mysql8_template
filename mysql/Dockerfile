FROM mysql:8.0.33-debian

COPY ./conf.d/my.cnf /etc/mysql/conf.d/

# mysqlコンテナ日本語化
RUN apt-get update && apt-get install -y locales
RUN sed -i -E 's/# (ja_JP.UTF-8)/\1/' /etc/locale.gen && locale-gen

ENV LC_ALL ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV TZ Asia/Tokyo

CMD ["mysqld", "--character-set-server=utf8mb4", "--collation-server=utf8mb4_general_ci"]