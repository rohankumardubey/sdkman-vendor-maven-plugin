## Maven Plugin for SDKMAN!

The [SDKMAN!](http://sdkman.io) Maven Plugin.

### Creating a candidate release

Usage in a `pom.xml`:

```
<plugin>
  <groupId>io.sdkman</groupId>
  <artifactId>sdkman-maven-plugin</artifactId>
  <version>1.0-SNAPSHOT</version>
  <execution>
    <goals>
      <goal>release</goal>
    </goals>
    <phase>deploy</phase>
    <configuration>
      <candidate>the-candidate</candidate>
      <version>the-version</version>
      <url>the-url</url>
    </configuration>
  </execution>
</plugin>
```

The `consumerKey` and `consumerToken` could also be specified in the `configuration` tag but these should not be there. These
values have corresponding properties that should be used from the command line or configured in the `settings.xml`.

Usage from command line:

```
mvn -e io.sdkman:sdkman-maven-plugin:1.0-SNAPSHOT:release \ 
    -Dsdkman.consumer.key=${my_key} \
    -Dsdkman.consumer.token=${my_token} \
    -Dsdkman.candidate=${my_candidate} \
    -Dsdkman.version=${my_version} \
    -Dsdkman.url=${my_url}
```
