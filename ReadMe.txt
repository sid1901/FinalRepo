To generate spring data model from swagger specs :

1. Install wget on windows.
extract wget zip from below link and install 
\\punnfil02\PSD2_sharedspace$\sid\wget-1.11.4-1-setup.exe.zip

2. Get Swagger codegen latest executable jar directly from Maven.org using wget.
Go to directory, wherer wget binary installed (ex : C:\Program Files (x86)\GnuWin32\bin)
Open cmd at above location and run below command.
wget http://central.maven.org/maven2/io/swagger/swagger-codegen-cli/2.3.1/swagger-codegen-cli-2.3.1.jar -O swagger-codegen-cli-2.3.1.jar

3. Generate Spring Domain from Swagger using codegen jar.
Keep above jar and swagger file at same location and run below command on cmd.
java -jar swagger-codegen-cli-2.3.1.jar generate -i CMA2_swagger.json -l spring -o resultPath --model-package com.capgemini.psd2.cma2_0.aisp.domain

or to generate with java8 date's use library as below:
java -jar swagger-codegen-cli-2.3.1.jar generate -i CMA2_swagger.json -l spring -o resultPath --model-package com.capgemini.psd2.cma2_0.aisp.domain -DdateLibrary=java8

Models will be generate under resultPath/

FOR INTERNATION CONSENT USED: 

java -jar swagger-codegen-cli2.3.1.jar generate -i IPConsent.json -l spring -o resultPath --model-package com.capgemini.psd2.pisp.domain --api-package com.capgemini.psd2.pisp.api -DdateLibrary=java8

Weather API
java -jar swagger-codegen-cli2.3.1.jar generate -i EmployeeApi.json -l spring -o result --model-package sid.work.domain --api-package sid.work.api --group-id sid.work --artifact-id EmployeeApi --artifact-version 1.0.0 -DdateLibrary=java8