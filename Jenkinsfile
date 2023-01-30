node {
checkout scm: [
    $class: 'GitSCM',
    branches: scm.branches,
    extensions: [
        [$class: 'SubmoduleOption',
        disableSubmodules: false,
        parentCredentials: true,
        recursiveSubmodules: true,
        reference: 'https://github.com/rishav199812/updatedrepo.git',
        shallow: true,
        trackingSubmodules: false]
    ],
    submoduleCfg: [],
    userRemoteConfigs: scm.userRemoteConfigs
]
}
pipeline{
    agent any
    stages{
        stage('Test'){
            steps {
                sh "git submodule add -b testnew https://github.com/rishav199812/updatedrepo.git"
                sh "git submodule update --init --recursive"
                sh "git submodule update --remote"
            }
        }
        stage('Hello'){
            steps{
                echo "Checking World"
            }
        }
        stage('World'){
            steps{
                echo "Second Stage"
            }
        }
        stage('Third'){
            steps{
                echo "New Stage"
            }
        }
    }
}
