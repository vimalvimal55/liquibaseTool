# liquibaseTool


This sample uses mysql as db source , liquibase tool from maven tool .
If you want to set up local mysql , 
use this following path http://www.mysqltutorial.org/install-mysql/
else 
https://www.sitepoint.com/how-to-install-mysql/ use this to install it from source. 

after downloading it in a path , 
		D:\liquibaseTool>

open command line mode 
1 . cmd from Runner 

2. give following command 

		-- D:\liquibaseTool>mvn -v
		-- Apache Maven 3.6.1 (d66c9c0b3152b2e69ee9bac180bb8fcc8e6af555; 2019-04-05T00:30:29+05:30)
		-- Maven home: D:\ApacheMaven_3.6.1\bin\..
		-- Java version: 11.0.1, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk-11.0.1
		-- Default locale: en_US, platform encoding: Cp1252
		-- OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"
		
	It must have the maven version installed , else start installing maven first.
	
		-- 1. download maven from internet
		-- 2. create bat file with following command , place folders accodring to your system.
			-- set MAVEN_HOME=D:\ApacheMaven_3.6.1;
			-- set PATH=%PATH%;D:\ApacheMaven_3.6.1\bin;
			-- set PATH=%PATH%;c:\programfiles\java\jdk-8\bin;
			-- cmd 


3. Now you are ready to use the liquise maven tool .

4. start providing command like this 


5. D:\liquibaseTool>mvn clean liquibase:update -Dliquibase  -Dliquibase.url=jdbc:mysql://localhost:3306/bookdb?useSSL=false -Dliquibase.username=root -Dliquibase.password=password

(according to above line the local db should be running at port 3306 with scheme bookdb)
(We suggest you to use heidi sql as work bench)

	
		-- here the liquibase:update can be changed according to  you wish , please visit this page for further commands and features fo it. 
		-- https://www.liquibase.org/documentation/maven/index.html

 6. Now at this point after running a command you may get error like mvn is not able to download the stuff.
 7. if you are in private network it will not create an error it will download smoothly.
 8. if you in infosys netwrok , you need to download everything from infosys artifactory.
 9. insdie liquibaseTool you will find settings.xml place this in #C:\Users\<isntalledUser>\.m2 
 10. inside the settings.xml update username as well .  ( <<username>> )

 
         -- <configuration>
				<httpConfiguration>
					<all>
						<params>
							<param>
								<name>http.authentication.preemptive</name>
								<value>%b,true</value>
							</param>
						</params>
					</all>
				</httpConfiguration>
				<httpHeaders>
					<property>
						<name>username</name>
						<!--update it below -->
						<value><<username>></value>
					</property>
				</httpHeaders>
			</configuration>
 
 

## Running liquibse against oracle db 
here I have seen beautiful video explaining this 
https://blogs.oracle.com/shay/introduction-to-liquibase-and-managing-your-database-source-code
(exactly at 6.41 to 7.21 time frame it gives idea about running commands)


