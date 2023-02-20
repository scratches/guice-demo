Build with AOT:

```
$ ./mvnw -P native package
```

Run it. It should print a `Spam` and exit:

```
$ java -Dspring.aot.enabled=true -jar target/demo-0.0.1-SNAPSHOT.jar
...
2023-02-20T16:40:24.211Z  INFO 920971 --- [           main] com.example.demo.DemoApplication         : Starting AOT-processed DemoApplication v0.0.1-SNAPSHOT using Java 17.0.5 with PID 920971 (/home/dsyer/dev/scratch/guice-demo/target/demo-0.0.1-SNAPSHOT.jar started by dsyer in /home/dsyer/dev/scratch/guice-demo)
2023-02-20T16:40:24.214Z  INFO 920971 --- [           main] com.example.demo.DemoApplication         : No active profile set, falling back to 1 default profile: "default"
2023-02-20T16:40:24.618Z  INFO 920971 --- [           main] com.example.demo.DemoApplication         : Started DemoApplication in 0.777 seconds (process running for 1.184)
com.example.demo.Spam@50caa560
```

Build a native image:

```
$ ./mvnw -P native native:compile
```

Run it:

```
$ ./target/demo 

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v3.0.2)

2023-02-20T16:43:08.928Z  INFO 925472 --- [           main] com.example.demo.DemoApplication         : Starting AOT-processed DemoApplication using Java 17.0.5 with PID 925472 (/home/dsyer/dev/scratch/guice-demo/target/demo started by dsyer in /home/dsyer/dev/scratch/guice-demo)
2023-02-20T16:43:08.928Z  INFO 925472 --- [           main] com.example.demo.DemoApplication         : No active profile set, falling back to 1 default profile: "default"
2023-02-20T16:43:08.940Z  INFO 925472 --- [           main] com.example.demo.DemoApplication         : Started DemoApplication in 0.035 seconds (process running for 0.041)
com.example.demo.Spam@67c15c86
```