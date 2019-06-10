path=C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
startup directory=C:\aws\scripts
Arguments=StartMonitoring.ps1


https://stephenmann.io/post/continuous-delivery-with-beanstalk-codepipeline-and-terraform/
http://microservices.today/CI-CD-Solution-with-AWS/

https://www.codejava.net/frameworks/spring/spring-boot/spring-boot-crud-example-with-spring-mvc-spring-data-jpa-thymeleaf-hibernate-mysql
https://dzone.com/articles/best-performance-practices-for-hibernate-5-and-spr
https://www.logicbig.com/tutorials/spring-framework/spring-web-mvc/spring-message-body.html#id-res-status
https://www.accenture.com/_acnmedia/PDF-89/Accenture-Unleasing-the-Power-of-AWS-with-AccentureCS.pdf
https://javadeveloperzone.com/spring/spring-jpa-dynamic-query-example/
https://issart.com/blog/how-to-use-criteria-api-with-spring-boot/
https://stackoverflow.com/questions/44278066/how-to-use-criteria-queries-in-spring-boot-data-jpa-application
https://examples.javacodegeeks.com/enterprise-java/jpa/jpa-criteriabuilder-example/
https://www.javacodegeeks.com/2013/04/jpa-2-0-criteria-query-with-hibernate.html


		Protocol protocol = Protocol.http;
		String distributionDomain = "";
		File privateKeyFile = new File("");
		String s3ObjectKey = "1010/32-19-5-2019-753.jpeg";
		String keyPairId = "";
		Date dateLessThan=ServiceUtils.parseIso8601Date("2019-05-29T18:30:00.000Z");
		//Date dateLessThan = DateUtils.formatIso8601Date("2012-11-14T22:20:00.000Z");
		//Date dateGreaterThan = DateUtils.formatIso8601Date("2011-11-14T22:20:00.000Z");

		String url1 = CloudFrontUrlSigner.getSignedURLWithCannedPolicy(protocol, distributionDomain, privateKeyFile,s3ObjectKey, keyPairId, dateLessThan);
		
		System.out.println("URL :: "+url1);


### For ubuntu keys for ppa curl command
https://askubuntu.com/questions/13065/how-do-i-fix-the-gpg-error-no-pubkey

node {
    stage('Repository') {
        git url: ''
        sh 'npm install'
    }
    stage('Code analyse') {
        sh 'echo "Run some lints"'
    }
    stage('Unit test') {
        sh 'echo "Tests will back"'
    }
    stage('Build') {
        sh '/usr/lib/node_modules/@angular/cli/bin/ng build'
    }
    stage('Bundle the artifacts') {
        sh 'tar -czvf pep-tool.tar.gz dist/*'
    }
    stage('SSH transfer') {
		
		script {
		sshPublisher(
		   continueOnError: false, failOnError: true,
		   publishers: [
			sshPublisherDesc(
			 configName: "ConfiguredName",
			 verbose: true,
			 transfers: [
			  sshTransfer(
			   sourceFiles: "*.tar.gz",
			   removePrefix: "",
			   remoteDirectory: "",
			   execCommand: "/home/ubuntu/WEB/angular/uideployment.sh"
			  )
			 ])
		   ])
		}
	}
}
