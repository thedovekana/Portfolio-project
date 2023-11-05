pipeline {
    agent any

    stages {
        stage('SCM Checkout') {
            steps {
                git 'https://github.com/thedovekana/Portfolio-ansible-project.git'
            }
        }
        stage('Deploy app ') {
            steps {
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible', sshCredentials: [encryptedPassphrase: '{AQAAABAAAAAQSi4dsW+NG2gyfclfPAPZM730nShTf6+qLoQTI6NGu+g=}', key: '', keyPath: '', username: 'ansible'], transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''git clone https://github.com/thedovekana/Portfolio-ansible-project.git 
cd Portfolio-ansible-project/ 
ansible-playbook app-deploy.yml -i inventory''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/ansible/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
