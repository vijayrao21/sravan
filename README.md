<?xml version="1.0" encoding="UTF-8"?>
<project xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xmlns="http://maven.apache.org/POM/4.0.0"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.automation</groupId>
    <artifactId>AdeptQA_Automation</artifactId>
    <version>1.0-SNAPSHOT</version>

    <name>AdeptAutomation</name>
    <url>http://www.acordsolutions.com</url>



    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.target>1.8</maven.compiler.target>
        <maven.compiler.source>1.8</maven.compiler.source>
    </properties>
    <repositories>
        <repository>
            <snapshots>
                <enabled>false</enabled>
            </snapshots>
            <id>bintray-epam-reportportal</id>
            <name>bintray</name>
            <url>http://dl.bintray.com/epam/reportportal</url>
        </repository>
    </repositories>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-resources-plugin</artifactId>
                <version>3.0.2</version>
            </plugin>

            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-surefire-plugin</artifactId>
                <version>2.19.1</version>
                <configuration>
                    <testFailureIgnore>true</testFailureIgnore>
                    <suiteXmlFiles>
                        <!--suppress UnresolvedMavenProperty -->
                        <suiteXmlFile>${suiteXmlFile}</suiteXmlFile>
                    </suiteXmlFiles>
                </configuration>
            </plugin>

            <plugin>
                <groupId>net.masterthought</groupId>
                <artifactId>maven-cucumber-reporting</artifactId>
                <version>5.0.0</version>
                <executions>
                    <execution>
                        <id>execution</id>
                        <phase>verify</phase>
                        <goals>
                            <goal>generate</goal>
                        </goals>
                        <configuration>
                            <projectName>Adept Automation Project</projectName>
                            <!-- optional, per documentation set this to "true" to bypass generation of Cucumber Reports entirely, defaults to false if not specified -->
                            <skip>false</skip>
                            <!-- output directory for the generated report -->
                            <outputDirectory>${project.build.directory}/cucumber_reports</outputDirectory>
                            <buildNumber>1</buildNumber>
                            <!-- optional, defaults to outputDirectory if not specified -->
                            <jsonFiles>
                                <!-- supports wildcard or name pattern -->
                                <param>**/*.json</param>
                            </jsonFiles>
                            <!-- optional, defaults to outputDirectory if not specified -->

                            <!--                            <parallelTesting>false</parallelTesting>-->
                            <!-- optional, set true to group features by its Ids -->
                            <mergeFeaturesById>false</mergeFeaturesById>
                            <!-- optional, set true to get a final report with latest results of the same test from different test runs -->
                            <mergeFeaturesWithRetest>false</mergeFeaturesWithRetest>
                            <!-- optional, set true to fail build on test failures -->
                            <checkBuildResult>true</checkBuildResult>
                        </configuration>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>

    <dependencies>

        <!--        <dependency>-->
        <!--            <groupId>com.json.comparison</groupId>-->
        <!--            <artifactId>json-comparison</artifactId>-->
        <!--            <version>1.2</version>-->
        <!--        </dependency>-->

        <dependency>
            <groupId>com.google.code.gson</groupId>
            <artifactId>gson</artifactId>
            <version>2.8.6</version>
        </dependency>

        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.10.1</version>
        </dependency>

        <dependency>
            <groupId>io.rest-assured</groupId>
            <artifactId>rest-assured</artifactId>
            <version>4.3.0</version>
            <scope>compile</scope>
        </dependency>

        <dependency>
            <groupId>org.apache.logging.log4j</groupId>
            <artifactId>log4j-api</artifactId>
            <version>2.11.2</version>
        </dependency>
        <dependency>
            <groupId>org.apache.logging.log4j</groupId>
            <artifactId>log4j-core</artifactId>
            <version>2.11.2</version>
        </dependency>
        <dependency>
            <groupId>javax.xml.soap</groupId>
            <artifactId>javax.xml.soap-api</artifactId>
            <version>1.3.5</version>
        </dependency>

        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi</artifactId>
            <version>4.1.2</version>
        </dependency>

        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-ooxml</artifactId>
            <version>4.1.2</version>
        </dependency>

        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-ooxml-schemas</artifactId>
            <version>4.1.2</version>
        </dependency>

        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-scratchpad</artifactId>
            <version>4.1.2</version>
        </dependency>

        <dependency>
            <groupId>org.apache.poi</groupId>
            <artifactId>poi-excelant</artifactId>
            <version>4.1.2</version>
        </dependency>


        <dependency>
            <groupId>org.assertj</groupId>
            <artifactId>assertj-core</artifactId>
            <version>3.14.0</version>
        </dependency>

        <dependency>
            <groupId>org.influxdb</groupId>
            <artifactId>influxdb-java</artifactId>
            <version>2.12</version>
        </dependency>
        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-dbcp2</artifactId>
            <version>2.5.0</version>
        </dependency>
        <dependency>
            <groupId>ru.yandex.qatools.ashot</groupId>
            <artifactId>ashot</artifactId>
            <version>1.5.3</version>
        </dependency>

        <dependency>
            <groupId>io.github.bonigarcia</groupId>
            <artifactId>webdrivermanager</artifactId>
            <version>4.2.2</version>
        </dependency>

        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-server</artifactId>
            <version>3.141.59</version>
        </dependency>

        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-remote-driver</artifactId>
            <version>3.141.59</version>
        </dependency>

        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-java</artifactId>
            <version>3.141.59</version>
        </dependency>

        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-api</artifactId>
            <version>3.141.59</version>
        </dependency>

        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-support</artifactId>
            <version>3.141.59</version>
        </dependency>

        <dependency>
            <groupId>javax.mail</groupId>
            <artifactId>mail</artifactId>
            <version>1.4</version>
        </dependency>

        <dependency>
            <groupId>com.opencsv</groupId>
            <artifactId>opencsv</artifactId>
            <version>5.2</version>
        </dependency>

        <dependency>
            <groupId>com.googlecode.json-simple</groupId>
            <artifactId>json-simple</artifactId>
            <version>1.1.1</version>
        </dependency>

        <dependency>
            <groupId>commons-collections</groupId>
            <artifactId>commons-collections</artifactId>
            <version>3.0</version>
        </dependency>

        <dependency>
            <groupId>commons-lang</groupId>
            <artifactId>commons-lang</artifactId>
            <version>2.6</version>
        </dependency>

        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-lang3</artifactId>
            <version>3.8.1</version>
        </dependency>

        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-log4j12</artifactId>
            <version>1.8.0-beta4</version>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>8.0.12</version>
        </dependency>

        <dependency>
            <groupId>com.github.yev</groupId>
            <artifactId>screenshot</artifactId>
            <version>1.1</version>
        </dependency>

        <dependency>
            <groupId>commons-configuration</groupId>
            <artifactId>commons-configuration</artifactId>
            <version>1.10</version>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>io.cucumber</groupId>
            <artifactId>cucumber-java</artifactId>
            <version>6.5.1</version>
        </dependency>

        <dependency>
            <groupId>io.cucumber</groupId>
            <artifactId>cucumber-core</artifactId>
            <version>6.5.1</version>
        </dependency>

        <dependency>
            <groupId>io.cucumber</groupId>
            <artifactId>cucumber-picocontainer</artifactId>
            <version>6.5.1</version>
        </dependency>

        <dependency>
            <groupId>net.masterthought</groupId>
            <artifactId>cucumber-reporting</artifactId>
            <version>5.3.0</version>
        </dependency>

        <dependency>
            <groupId>io.cucumber</groupId>
            <artifactId>cucumber-gherkin</artifactId>
            <version>6.5.1</version>
        </dependency>

        <dependency>
            <groupId>io.cucumber</groupId>
            <artifactId>cucumber-plugin</artifactId>
            <version>6.5.1</version>
        </dependency>

        <!--        <dependency>-->
        <!--            <groupId>junit</groupId>-->
        <!--            <artifactId>junit</artifactId>-->
        <!--            <version>4.12</version>-->
        <!--            <scope>compile</scope>-->
        <!--        </dependency>-->

        <!--        <dependency>-->
        <!--            <groupId>com.vimalselvam</groupId>-->
        <!--            <artifactId>cucumber-extentsreport</artifactId>-->
        <!--            <version>3.1.1</version>-->
        <!--        </dependency>-->

        <dependency>
            <groupId>io.cucumber</groupId>
            <artifactId>cucumber-junit</artifactId>
            <version>6.5.1</version>
        </dependency>

        <dependency>
            <groupId>com.aventstack</groupId>
            <artifactId>extentreports-cucumber4-adapter</artifactId>
            <version>1.0.12</version>
            <exclusions>
                <exclusion>
                    <groupId>io.cucumber</groupId>
                    <artifactId>cucumber-java</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>io.cucumber</groupId>
                    <artifactId>cucumber-core</artifactId>
                </exclusion>
            </exclusions>
        </dependency>

        <dependency>
            <groupId>org.testng</groupId>
            <artifactId>testng</artifactId>
            <version>7.3.0</version>
        </dependency>

        <dependency>
            <groupId>org.apache.pdfbox</groupId>
            <artifactId>pdfbox</artifactId>
            <version>2.0.21</version>
        </dependency>

        <dependency>
            <groupId>io.cucumber</groupId>
            <artifactId>cucumber-testng</artifactId>
            <version>6.5.1</version>
        </dependency>

        <dependency>
            <groupId>tech.grasshopper</groupId>
            <artifactId>extentreports-cucumber6-adapter</artifactId>
            <version>2.5.0</version>
        </dependency>

        <dependency>
            <groupId>com.aventstack</groupId>
            <artifactId>extentreports</artifactId>
            <version>4.0.9</version>
        </dependency>

        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.12.1</version>
        </dependency>

        <dependency>
            <groupId>xmlunit</groupId>
            <artifactId>xmlunit</artifactId>
            <version>1.4</version>
        </dependency>

        <dependency>
            <groupId>net.javacrumbs.json-unit</groupId>
            <artifactId>json-unit-assertj</artifactId>
            <version>2.24.0</version>
        </dependency>

        <dependency>
            <groupId>org.skyscreamer</groupId>
            <artifactId>jsonassert</artifactId>
            <version>1.5.0</version>
        </dependency>

        <dependency>
            <groupId>org.json</groupId>
            <artifactId>json</artifactId>
            <version>20201115</version>
        </dependency>

        <dependency>
            <groupId>com.google.zxing</groupId>
            <artifactId>core</artifactId>
            <version>3.3.0</version>
        </dependency>

        <dependency>
            <groupId>com.google.zxing</groupId>
            <artifactId>javase</artifactId>
            <version>3.3.0</version>
        </dependency>

        <dependency>
            <groupId>org.jboss.aerogear</groupId>
            <artifactId>aerogear-otp-java</artifactId>
            <version>1.0.0</version>
        </dependency>

    </dependencies>

    <distributionManagement>
        <repository>
            <id>github</id>
            <name>GitHub eBay Apache Maven Packages</name>
            <url>https://maven.pkg.github.com/eBay/json-comparison</url>
        </repository>
    </distributionManagement>
</project>
