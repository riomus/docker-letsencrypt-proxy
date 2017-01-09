# docker-compose for [docker-letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion)

Because of docker-compose [v2 bug](https://github.com/jwilder/nginx-proxy/issues/502), network hack must be done. 

Create proxy network:

```bash
 docker network create service-proxy
 ```

Add to your each proxied service:
```yml
networks:
  - default
  - service-proxy
```

and to your each *.yml with proxied services:

```yml
networks:
    service-proxy:
       external: true
```


