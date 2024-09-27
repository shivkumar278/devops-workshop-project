## SonarQube Configuration 

1. Create Sonar cloud account on https://sonarcloud.io
2. Generate an Authentication token on SonarQube
    Account --> my account --> Security --> Generate Tokens 

3. On Jenkins create credentials 
   Manage Jenkins --> manage credentials --> system --> Global credentials --> add credentials
 - Credentials type: `Secret text`
 - ID: `sonarqube-key`

4. Install SonarQube plugin
    Manage Jenkins --> Available plugins 
    Search for `sonarqube scanner`

5. Configure sonarqube server 
   Manage Jenkins --> Configure System --> sonarqube server 
   Add Sonarqube server 
   - Name: `sonar-server`
   - Server URL: `https://sonarcloud.io/`
   - Server authentication token: `sonarqube-key`

6. Configure sonarqube scanner 
   Manage Jenkins --> Global Tool configuration --> Sonarqube scanner 
   Add sonarqube scanner 
   - Sonarqube scanner: `sonar-scanner`

   

### Create a configuration file in the root directory of the project:

sonar-project.properties

# Add more detail to both client and server-side analysis logs

sonar.verbose

# Must be unique in a given SonarQube instance
sonar.projectKey=my-project

# This is the name and version displayed in the SonarQube UI.

# Was mandatory prior to SonarQube 6.1.

sonar.projectName=My project
sonar.projectVersion=1.0
 
# Path is relative to the sonar-project.properties file.

# Replace "\" by "/" on Windows.

# This property is optional if sonar.modules is set. 

sonar.sources=src
 
# Encoding of the source code. Default is default system encoding

sonar.sourceEncoding=UTF-8

===========================================================================
sonar.verbose=true
sonar.organization=
sonar.projectKey=my-project
sonar.projectName=My project
sonar.language=java
sonar.projectVersion=1.0
sonar.sourceEncoding=UTF-8
sonar.sources=src
sonar.java.binaries=target/classes
sonar.coverage.jacoco.xmlReportPath=




