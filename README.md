## Spring cloud service proxy

This project is used for proof of concept only. Of course, you can contribute, you just need to fork
and PR your feature.

### Usage

Start the container :

```
docker run -p 8080:8080 sipf/proxy-service
```

You can then log to [http://127.0.0.1:8080](http://127.0.0.1:8080) to use the service.

### Default Configuration

#### application.yml

```
zuul:
  routes:
    organisms:
      path: /organisms/**
      url: https://organism-ws.herokuapp.com
```

#### bootstrap.yml

```
spring:
  application:
    name: proxy
  profiles:
    active: development
  cloud:
    config:
      uri: https://supervisor:supervisor@config-service-ws.herokuapp.com
```

### Building the container

```
docker build -t sipf/proxy-service .
```

### License & Authors

* License : MIT
* Authors : Leonard TAVAE (leonard.tavae@informatique.gov.pf)