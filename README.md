# Publish-library-To-Repository


```gradle

plugins {
	id 'org.springframework.boot' version '2.6.4'
	id 'io.spring.dependency-management' version '1.0.11.RELEASE'
	id 'java'
	<b>id 'maven-publish'</b>
}

group = 'com.tirmizee'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'

repositories {
	mavenCentral()
}

dependencies {
	implementation 'org.springframework.boot:spring-boot-starter'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

tasks.named('test') {
	useJUnitPlatform()
}

publishing {
	publications {}
	repositories {
		maven {
			name = "Private" //  optional target repository name
			url = "http://my.org.server/repo/url"
			credentials {
				username = 'alice'
				password = 'my-password'
			}
		}
	}
}


```
