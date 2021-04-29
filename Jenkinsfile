node
{

def mavenHome = tool name: "maven3.6.2"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

stage('Checkout')
{
 git branch: 'development', credentialsId: 'ca3e7044-a865-4143-8535-b4811d25e74a', url: 'https://github.com/raviinjam123/maven-web-application.git'
}

stage('Build with Maven')
{
 sh "${mavenHome}/bin/mvn clean package"
}

/*
stage('ExecuteSonarqube Report')
{
 sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifacts Into Nexus')
{
 sh "${mavenHome}/bin/mvn deploy"
}

stage ('DeployApp Into TomcatServer')
{
sshagent(['d3b8ec8f-77d9-411a-a078-1ced27412aa5']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@15.206.123.81://opt/apache-tomcat-9.0.45/webapps/"
}
}

stage ('EmailNotification')
{
emailext body: '''Build is over!!!

Regards,
Ravi Injam,
9502497958.
''', subject: 'Build is over!!!', to: 'raviinjam1991@gmail.com'
}

*/

}
