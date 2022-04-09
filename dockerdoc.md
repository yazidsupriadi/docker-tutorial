##### docker pull
----
```
docker pull image-name
```

##### check existing images
```
docker images
```

#### run docker images
----------

```
docker run images_name
```


#### check container running

```
docker ps
```

#### start specific container

```
docker start id-container
```

#### stop run docker container

```
docker stop id-container
```

#### list running and stop container

```
docker ps -a
```

#### pull images and run

```
docker run images:tag
```
example
```
docker run redis:4.0
```

#### check images docker

```
docker images
```

#### check logs container

```
docker logs container-id
```

```
docker logs container-name
```

#### run docker images with specific number and port

```
docker run -d -p6001:6374 --name specific-name image-name
```

```
docker run -d -p6001:6374 --name redis-older redis
```


####docker list network

```
docker network ls
```

#### docker create network

```
docker network create network-name
```
example


```
docker network create mongo-network
```


### Project example


* first pull mongo and mongo-express

* then create network
 ```
  docker network create mongo-network
 ```

* start mongo db
 ```
 docker run -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=password123 --net mongo-network --name mongodb mongo
 ```

 start mongo-express
 ```
 docker run -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password123 --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express
 ```

 if you want to start with docker compose
 ```
 docker-compose -f docker-compose-file-name.yaml up
 ```

create docker file
* run docker file 
    ```
    docker build -t app-name:version
    ```