pipeline{
    agent any
   stages {
       stage ('Set Java version') {
           steps {
               withEnv(['JAVA_HOME=C:\\\\Program Files\\\\Java\\\\jdk1.8.0_192']) {
                   //test
               }
           }
       }
       stage ('Set Gradle version') {
           steps {
               withEnv(['GRADLE_USER_HOME=C:\\\\Program Files\\\\gradle-3.4.1']) {
                   //test
               }
           }
       }
       stage ('Checkout') {
           steps { //Checkout the repo
               checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '80fab7d4-b24b-4ab4-b39d-7360b6e3d243', url: 'https://github.com/skrish-8/HelloWorld.git']]])
           }
       }
       stage ('Build') {
           steps {
               script {
                  bat label: '', script: 'echo %JAVA_HOME%'
                  bat label: '', script: 'echo %ANDROID_SDK_ROOT%'
                  //bat label: '', script: 'gradle -v'
                  //bat label: '', script: 'gradlew clean build'
                  //bat label: '', script: 'cd "C:\\Users\\722769\\Desktop\\Frogger\\VC_FroggerOOBE"'
                  //bat label: '', script: 'gradlew assembleDebug'
               }
           }
       }
   }
}
