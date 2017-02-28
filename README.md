checkDnsProvider is a simple shell script that takes an input file of domains and identifies information about name servers, # of DNS providers, and certain information about the web server used by that domain.  

DESCRIPTION:  checkDnsProvider takes an input file of domains (samples included for Alexa top 50, and RSP sponsors), and identifies information about name servers,
		      DNS providers, and certain information about the web server used by that domain,  Information
		      identified includes:
			- Number of name servers resolving the domain
			- Number of DNS providers used by the domain
			- Type of Web Server used by the domain, which helps identify if a CDN is being used by the domain
			- inspects the HTTP HEADERS 'Server' and 'Via' from the HTTP response

REQUIREMENTS:	You will need the following tools available in your environment (in the future I'll put this in a docker container):

				dig	- used to interrogate DNS name servers
				curl	- used to transfer data from or to a server, including HTTP GET or HEAD requests used here

			Make sure the 'NSDomains' file is in your local directory.  NSDomains maps certain name server domains to specific DNS providers

			Please set the HOMEDIR variable below to your local directory where the script is located

OUTPUT:	The script outputs a CSV file listing domains, number of name servers, number of DNS providers, and HTTP header info.  
		This CSV file can be imported into excel for easy filtering and analysis

		The script also outputs a detailed log file, and an error file identifying name server domains not currently mapped to a DNS provider

QUESTIONS: Feel free to contact me at rharbin@gmail.com
	   http://reynold.harbin.io
