# windos-docker- ASP.NET WebForms
App uses WebForms, the replacement for classic ASP introduced in 2002 

The Dockerfile uses Microsoft's Windows Server Core image with IIS and ASP.NET installed. That provides all the prerequisites for the app, so the rest of the Dockerfile just copies in the ZIP file, expands it and sets up the site.

Build the Docker image:

docker image build `
 -t webforms `
 -f .\docker\webforms\Dockerfile .
Now run the app in a container using server:

docker container run `
 --detach --publish 8082:80 `
 webforms
Browse to port 8082 on the server, and you'll see the ASP.NET WebForms app. 
