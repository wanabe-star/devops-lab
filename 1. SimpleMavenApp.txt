/***********creating a maven based application using terminal

1. open terminal and type
mvn archetype:generate -DgroupId=com.example -DartifactId=MyMavenApp -DarchetypeArtifactiId=maven-archetype-quickstart -DinteractiveMode=false

2. get into the directory
 cd MyMavenApp
 /MyMAvenApp/gedit pom.xml
// add dependencies from maven central repository
goto chrome --> maven central repository --> search for a particular dependency --> type junit--> it shows the dependency --> scroll up --> click on the recent version and copy the dependency available and paste it in pom.xml under dependencies tag 

// add  plugins to generate jar file and to compile and intimate where to start the application from 

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.example</groupId>
  <artifactId>MyMavenApp</artifactId>
  <packaging>jar</packaging>
  <version>1.0-SNAPSHOT</version>
  
  
  <name>MyMavenApp</name>
  <url>http://maven.apache.org</url>
  
  <!-- Properties: Customize Java version or plugin versions -->
<properties>
<maven.compiler.source>11</maven.compiler.source>
<maven.compiler.target>11</maven.compiler.target>
</properties>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
  
  <!-- Build: Configuring plugins and build settings -->
<build>
<plugins>
<!-- Example: Maven Compiler Plugin to compile Java code -->
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-compiler-plugin</artifactId>
<version>3.8.1</version>
<configuration>
<source>1.7</source>
<target>1.7</target>
</configuration>
</plugin>

<!-- Example: Maven Surefire Plugin to run tests -->
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-surefire-plugin</artifactId>
<version>2.22.2</version>
</plugin>


<plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-jar-plugin</artifactId>
            <version>3.1.0</version>
            <configuration>
                <archive>
                    <manifestEntries>
                        <Main-Class>com.example.App</Main-Class>
                    </manifestEntries>
                </archive>
            </configuration>
        </plugin>
        
</plugins>
</build>
</project>

3. mvn compile  // compiles the application
4. mvn test
5. mvn package   // generates the jar file
6. java -jar target/MyMaven.....    // run the App.java file and displays the output

OR

mvn clean install
java -jar target/MyMaven.....jar 




