<h1>Sonar Scanner Setup Manual Ad-Hoc Scans (Windows)</h1>

<h2>Description</h2>
Here are the steps to setup Sonar Scanner on Windows along with the manual commands to run to produce an code analysis report in SonarQube.
<br />

<h2>Tools Used </h2>

- <b>Windows 10</b> 
- <b>AWS</b>
- <b>Sonar Qube</b>
- <b>Sonar Scanner</b>
- <b>Java</b>

<h2>Step 1: Sonar Scanner Setup</h2>

- First, make sure you have Java Development Kit (JDK) installed on your Windows machine. You can download it from the Oracle website and then install it. [Download the Latest Java LTS Free ](https://www.oracle.com/java/technologies/downloads/#java11)
- Next, download the Sonar Scanner for Windows from the official SonarQube website. Look for the latest version compatible with your operating system.
- Once the download is complete, extract the contents of the downloaded ZIP file to a directory of your choice. Let's call this directory "sonar-scanner".
- Open the extracted "sonar-scanner" directory and locate the file named "sonar-scanner.properties". Open this file in a text editor.
- In the "sonar-scanner.properties" file, find the line that starts with "sonar.host.url" and uncomment it by removing the "#" symbol at the beginning of the line. Replace the URL with the address of your SonarQube server.
- Save the changes to the "sonar-scanner.properties" file and close it.
- Next, add the "sonar-scanner/bin" directory to your system's PATH environment variable. This will allow you to run the Sonar Scanner from any location in the command prompt.
- To do this, right-click on the "This PC" or "My Computer" icon on your desktop or in the Start Menu, and select "Properties".
- In the System Properties window, click on the "Advanced system settings" link on the left-hand side.
- In the System Properties dialog, click on the "Environment Variables" button.
- In the Environment Variables dialog, locate the "Path" variable under the "System variables" section and click on the "Edit" button.
- In the Edit Environment Variable dialog, click on the "New" button and enter the path to the "sonar-scanner/bin" directory. For example, if you extracted the Sonar Scanner to "C:\sonar-scanner", you would add "C:\sonar-scanner\bin" to the PATH variable.
- Click "OK" in all the open windows to save the changes.
- Now, open a new command prompt window and type "sonar-scanner" to verify that the Sonar Scanner is installed correctly. If everything is set up properly, you should see the scanner running and generating analysis reports for your project.

<h2>Step 2: Create SonarQube Project and Clone Repositories</h2>

- Submit DevOps request ticket to have your SonarQube project created and we will provide the project key, project token, and manual commands for your manual scan.
- Clone the Bitbucket repository locally to your machine in the location of your choice.
- Install SonarQube Scanner on your machine if you haven't already done so. You can find the installation instructions on the SonarQube website: SonarScanner 
- Configure SonarQube properties for your project. Create or modify the sonar-project.properties file in the root directory of your project.
- Specify the necessary properties in the sonar-project.properties file, such SonarQube server URL, and authentication credentials.

#sonar.host.url=http://xx.xx.xx.xx:9000
 
- Exclude the non-scannable files from the scanning process. You can do this by configuring the sonar.exclusions property in the sonar-project.properties file. This property allows you to specify file patterns to exclude during the analysis.
- Open a command prompt or terminal and navigate to the root directory of your cloned repository.
- Execute the SonarQube scanner command from the root directory of where you cloned your repos to start the analysis. For Python projects, you can use the command sonar-scanner or sonar-scanner.bat depending on your operating system. Here are the commands below:

a. Replace project_key with the value from the project in SonarQube
b. Replace project_token with the value from the project in SonarQube

sonar-scanner.bat -D"sonar.projectKey=project_key" -D"sonar.sources=." -D"sonar.host.url=<SONARQUBE_URL>" -D"sonar.login=#project_token"<br><br>
sonar-scanner.bat -D"sonar.projectKey=project_key" -D"sonar.sources=." -D"sonar.host.url=<SONARQUBE_URL>" -D"sonar.login=#project_token"<br><br>
sonar-scanner.bat -D"sonar.projectKey=project_key" -D"sonar.sources=." -D"sonar.host.url=<SONARQUBE_URL>" -D"sonar.login=#project_token"<br><br>

- Wait for the analysis to complete from your terminal. The scanner will analyze the Python files and send the results to your SonarQube server.
- Access your SonarQube server and review the analysis results for the scanned files.
