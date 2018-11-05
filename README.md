# Java Spring MVC Demo Instruction

*Group: LetterA*

this demo is runs on IntelliJ IDE


## What you'll need for run the demo

### Basic requirements

 - IntelliJ IDE
 - JDK 6 or later


### Install SDK

SDKMAN! (The Software Development Kit Manager) can be used for managing multiple versions of various binary SDKs,
including Groovy and the Spring Boot CLI. Get SDKMAN!
from: https://sdkman.io

    $curl -s "https://get.sdkman.io" | bash

Source sdk

    $source "/Users/Alex/.sdkman/bin/sdkman-init.sh"

### Install Spring
Install Spring Boot by using the following commands:

    $ sdk install springboot

### Install Maven

Building Java Projects with Maven
This guide walks you through using Maven to build a simple Java project.

What you’ll build
You’ll create an application that provides the time of day and then build it with Maven.

To skip the basics, do the following:

Maven is downloadable as a zip file at http://maven.apache.org/download.cgi.

Only the binaries are required, so look for the link to apache-maven-{version}-bin.zip or apache-maven-{version}-bin.tar.gz.

Once you have downloaded the zip file, unzip it to your computer. Then add the bin folder to your path.

To test the Maven installation, run mvn from the command-line:

    $mvn -v


If systems are setted, your server should be presented with following information about the Maven installation. It will look similar to: (although perhaps slightly different from)

    Apache Maven 3.5.2 (138edd61fd100ec658bfa2d307c43b76940a5d7d; 2017-10-18T00:58:13-07:00)
    Maven home: /usr/local/Cellar/maven/3.5.2/libexec
    Java version: 1.8.0_161, vendor: Oracle Corporation
    Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_161.jdk/Contents/Home/jre
    Default locale: en_CA, platform encoding: UTF-8
    OS name: "mac os x", version: "10.13.3", arch: "x86_64", family: "mac"

Congratulations! You now have Maven installed.


### Install Tomcat(Java Servlet)

Download apache-tomcat-9.0.5.tar from
include: http://tomcat.apache.org/

    $cd ./apache-tomcat-9.0.5/bin
    $sudo chmod 755 ./*.sh
    $./startup.sh

Edit the application file by:

    $vi tomcat

As:

    #!/bin/bash
    case $1 in
    start)
    sh /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/bin/startup.sh
    ;;
    stop)
    sh /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/bin/shutdown.sh
    ;;
    restart)
    sh /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/bin/shutdown.sh
    sh /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/bin/startup.sh
    ;;
    *)
    echo “Usage: start|stop|restart”
    ;;
    esac
    exit 0

After that for Setup the command in terminal, we need add ./tomcat's path in ~/.bash_profile
by:

    $vi ~/.bash_profile

Add following (Decide by the path where you download tomcat):

    export JAVA_HOME=$(/usr/libexec/java_home)
    export PATH=$PATH:/Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/bin

Start Tomcat:

    $tomcat start

If it is successes, then you can see:

    Using CATALINA_BASE:   /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5
    Using CATALINA_HOME:   /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5
    Using CATALINA_TMPDIR: /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/temp
    Using JRE_HOME:        /Library/Java/JavaVirtualMachines/jdk1.8.0_161.jdk/Contents/Home
    Using CLASSPATH:       /Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/bin/bootstrap.jar:/Users/Alex/Desktop/CMPT470/apache-tomcat-9.0.5/bin/tomcat-juli.jar
    Tomcat started.

## Ready to run the demo

By new project from existing source, and open *pom.xml* file. Import it, build with spring and run it with Tomcat.

Finally you can see the "Hello from letter A" from the localhost port, which port number is decide by your setting from Tomcat! :)