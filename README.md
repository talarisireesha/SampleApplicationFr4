# SampleApplicationFr4


stage('build')
    //{
        
        
        bat("cd C:/Program Files (x86)/dotnet")
        bat('msbuild.exe C:/Users/Sirisha/source/repos/AspDotnetcorewebapp /p:Configurattion=Release')
		}
		/
		
		
		stage('auto build')
    {
        
    bat("cd C:/Program Files (x86)/dotnet") 
    
    //bat ("dotnet D:/sonar-scanner-msbuild-4.7.1.2311-netcoreapp2.0/SonarScanner.MSBuild.dll begin /k:aspwebappcore /d:sonar.host.url=http://localhost:9000 /d:sonar.verbose=true  /d:sonar.login=cced88c05af97816591c4a27c749d94446fb9200" )
    bat("dotnet sonarscanner begin /k:aspwebappcore /d:sonar.host.url=http://localhost:9000  /d:sonar.login=cced88c05af97816591c4a27c749d94446fb9200")
    
    bat('msbuild.exe C:/Users/Sirisha/source/repos/AspDotnetcorewebapp /p:Configurattion=Release')
    bat ("dotnet sonarscanner end /d:sonar.login=cced88c05af97816591c4a27c749d94446fb9200 ")
	}
