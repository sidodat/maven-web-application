// Powered by Infostretch 

timestamps {

node () {

	stage ('mtn project - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'gitHubCredentials', url: 'https://github.com/sidodat/maven-web-application']]]) 
	}
	stage ('mtn project - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.timestamper.TimestamperBuildWrapper". Please verify and convert manually if required.		// Maven build step
	withMaven(maven: 'maven3.8.6') { 
 			if(isUnix()) {
 				sh "mvn clean install " 
			} else { 
 				bat "mvn clean install " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven3.8.6') { 
 			if(isUnix()) {
 				sh "mvn sonar:sonar " 
			} else { 
 				bat "mvn sonar:sonar " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven3.8.6') { 
 			if(isUnix()) {
 				sh "mvn deploy " 
			} else { 
 				bat "mvn deploy " 
			} 
 		} 
	}
}
}