
node {

    try {

        stage('Checkout') {
            git branch: 'main',
                url: 'https://github.com/sushanth100kj/inbjava.git'
        }

        stage('Build') {
            echo 'Building the project...'

            // Add your actual build command here
        }

        stage('Test') {
            echo 'Testing the project...'

            // Add your actual test command here
        }

    } catch (Exception e) {

        currentBuild.result = 'FAILURE'
        throw e

    } finally {

        emailext(
            to: 'sushanthsujith2006@gmail.com',
            subject: "Jenkins Build ${currentBuild.currentResult}: ${env.JOB_NAME} #${env.BUILD_NUMBER}",

            body: """
                Hello,

                Your Jenkins project build is completed.

                Project: ${env.JOB_NAME}
                Build Number: ${env.BUILD_NUMBER}
                Build Status: ${currentBuild.currentResult}

                Build URL: ${env.BUILD_URL}

                Regards,
                Jenkins Automation
            """,

            mimeType: 'text/plain'
        )
    }
}
