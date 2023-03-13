# Micronaut-Quarkus-SpringBoot
This contains Hello World project for benchmark purposes. Projects are using Micronaut 3.8.6 vs Quarkus 2.16 vs Spring Boot 3.0.4 on JDK 17. 

### Setup

To setup all dependencies first:

```
node install request
``` 

Then you can measure time to first response with:

```
node time.js [PATH_TO_JAR or PATH_TO_EXEC]
```

### Third Party tools used:

*How was memory measured?*

Using the `ps` command to obtain the RSS memory:

```
ps x -o rss,vsz,command | grep [java or myexecutable]
```

*How was req/sec measured?*

Using `ab` (ApacheBench) with keep alive connections:

```
ab -k -c 20 -n 10000 http://localhost:8080/hello
```

Using `wrk`:

```
wrk -t12 -c400 -d30s http://localhost:8080/hello
```
