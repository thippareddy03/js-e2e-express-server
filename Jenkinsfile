pipeline {
    agent { label 'Open-JDK-11' }
    triggers{ cron('0 */12 * * *') }
    parameters { choice(name: 'BRANCH_TO_BUILD', choices: ['main'], description: 'We are building the project on main branch') }
    stages {
        stage ('version control') {
            steps {
                git branch: "${params.BRANCH_TO_BUILD}", url : 'https://github.com/thippareddy03/js-e2e-express-server.git'
            }
        }
        stage ('npm installation') {
            steps {
                npm 'install'
            }
        }
        stage ('Building the job') {
            steps {
                npm 'run build'
            }
        }
    }
}