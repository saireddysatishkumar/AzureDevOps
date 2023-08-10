### Step1:  Create a .NET webapp
<sub>
	dotnet new sln -o HelloWorldApp
	cd HelloWorldApp
	dotnet new mvc -n HelloWorldApp.Web
	dotnet  sln  HelloWorldApp.sln add HelloWorldApp.Web/HelloWorldApp.Web.csproj
	dotnet build
	dotnet ./bin/Debug/net7.0/HelloWorldApp.Web.dll
	</sub>
# Note: By default webservice should bind to address http://127.0.0.1:5000. But it may fail in mac if address already in use. Aleternatly use below command

dotnet ./bin/Debug/net7.0/HelloWorldApp.Web.dll --urls http://127.0.0.1:8089
# Open Browser and open url http://127.0.0.1:8089

### Step: Create Azure DevOps Project
# Go to ADO > Repos > add ssh-key
### Step: Push HelloWorldApp webapp code to ADO Repos.
# From project location
cd HelloWorldApp
git init
git add .
git commit -m "initial commit" 
git log

git remote add origin git@ssh.dev.azure.com:v3/saireddydevops11/helloworld/helloworld
git push -u origin --all


