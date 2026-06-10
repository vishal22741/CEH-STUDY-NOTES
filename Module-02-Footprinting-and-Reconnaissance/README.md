# Module 02 - Footprinting and Reconnaissance

## What is FootPrinting ?
  Footprinting is the process of gathering information about a target organization, network, or system through passive 
  and active methods. It is the first phase of ethical hacking

## What is Reconnaissance ?
Gathering information about a target to understand its infrastructure, identify potential vulnerabilities
and prepare for further security assessment activities

## Footprinting vs Reconnaissance 
Footprinting is the process of collecting information about a target, while reconnaissance is the overall information-gathering phase
that includes footprinting and other intelligence-gathering activities

## Types of Information gathering ?
   -Passive :
      Gathering of information about target without direct interaction 
      Examples: search engines like google , social media platforms etc...
   -Active :
      Gathering of information about target with direct interaction
      Examples: Nmap, Traceroute, ping ,etc.

 ## Why Footprinting is needed ?
  Footprinting is the first phase of ethical hacking. It helps security professionals gather information about a target's infrastructure, technologies,
  employees, and public exposure. This information can be used to identify potential attack surfaces and security weaknesses
  
  ### Practical Demonstrations

  ## Gathering domain and subdomain information 
  ## Tools used : Harvester , Sublistr3r , Recon-ng , Netcraft
  ### Harvester :
  Which is an automated tool used to gather information through search engines and which also gives email-related information
  along with sub-domain information
  Syntax:
  ```bash
  theHarvester -d <domain_name> -b <source>
  ```
 explaination:
     -d:specifies domain name
     -b:specifies source name which is search engine name available in harvester tool like google, bing, yahoo etc.
 ### Sublist3r :
  Which is used to collect sub-domain information of a target
  Syntax:
  ```bash
    python3 sublist3r.py -d <domain_name>
   ```
explaination:
   which is also an automated tool which we have to download it from availabe github repositories
   to clone it from github the syntax is "git clone <link>"
 ### Recon-ng :
  Recon-ng is an OSINT framework used to gather information through various reconnaissance modules.
  explaination:
  By default it comes with no modules installation , to install modules - marketplace refresh, marketplace search, marketplace install <module_name>,
  search availabe modules in recon-ng - modules search or 
  marketplace search , now select required modules - modules load <module_name>, set required options for that module- "options list" ,
  "options set SOURCE <domain>" and run
  ex:modules load recon/domains-hosts/bing_domain_web
 ### Netcraft :
 Netcraft is a web-based reconnaissance service used to gather information about websites, hosting providers, technologies, and infrastructure details.
 
## Gathering domain related information with Whois lookup
 syntax:
 ```bash
    whois tata.com
```
 whois is an protocol command-line utility that provides domain registration information such as registrar details, registration dates,
 name servers, and contact information when publicly available.

 ## collecting profiles with usernames 
 Tool : Sherlock 
  syntax:
  ```bash
   sherlock <username>
  ```
 It searches multiple social media platforms and reports accounts associated with the specified username.

 ## Collecting Emails 
 Tool : Infoga 
 Infoga (Information Gathering) is an OSINT (Open Source Intelligence) tool used to collect and analyze publicly available email addresses associated with a target domain. It searches various public sources and search engines to discover email addresses and provides information related to those emails
  syntax :
  ```bash
    python3 infoga.py -t <domain> -s all
  ```
explaination:
   here -t specifies target and -s all specifies search engines like 
  google,bing,censys,yahoo,etc

 ## Collecting organisation information- Waybackmachine
  Visit: archive.org/web
  Wayback Machine archives historical versions of websites and helps identify previously exposed information, old directories, and historical content

  ## TO find out target ip , open ports , Route-path 
  ## Tools: Ping , Traceroute , Telnet , Nmap ,etc..
   Syntax : 
   ```bash
      ping <domain_name>
   ```
   It sends ICMP Echo Request packets to determine whether a host is reachable and displays the resolved IP address ,
   a successful reply generally indicates that the host is reachable and No reply may indicate that ICMP traffic 
  is blocked by a firewall. The host may  still be online .If ICMP traffic is blocked, TCP- or UDP-based tools such as Nmap can
  be used to verify host availability.
   
  ## Traceroute :
   Syntax:
   ```bash
       traceroute <domain_name>
   ```
   Traceroute shows how we reach a target system and how many devices (routers/hops) are involved between the source and the destination

   ## Telnet :
  Syntax:
     ```bash
     telnet <domain> <port>
     ```
     Which enables TCP connection with host and specifies whether particular port is open and accessible.
     If the response displays "Connected", the host is reachable and the specified TCP port is open

   ##Nmap :
     Syntax:
     
     ```bash
     nmap <ip>
     ```

  Example:nmap 192.168.0.33
      Nmap is network scanning tool used to identify open ports, running services, service versions, and for host discovery and service enumeration
      Commonly used options:
    ```bash
     nmap -sV <target>   # Service version detection
     nmap -O <target>    # Operating system detection
     ```
     
 
 <img width="1920" height="922" alt="nmap" src="https://github.com/user-attachments/assets/f3cb3aca-1901-46df-9bea-b6801561f7c2" />


  ## IP Tracking Technique
  ### Grabify
  Educational example of how tracking links can record connection information when a user accesses a URL
explanation:
1. Visit grabify.link
2. Create tracking link
3. Send link to target
4. When target clicks → IP captured
5. Shows location, browser, OS info
### IP Tracking Awareness
 This helps security professionals
understand privacy risks associated with clicking unknown links.

 ## Google Dorks
Using advanced Google search operators to find sensitive information
ex: site:domain.com
    intitle:"index of"
    filetype:pdf site:domain.com
    inurl:admin
    inurl:login 
  
   These operators help refine search results and can reveal publicly accessible information such as login pages, documents, directory listings, 
   and administrative interfaces for instance if we search inurl:login in search engines like google it displayes all websites 
    that contain login pages 

  ## Countermeasures
- Limit public information exposure
- Use privacy settings on social media
- Enable WHOIS privacy protection
- Use different usernames on platforms
- Keep sensitive files offline
- Restrict unnecessary ICMP responses through firewall rules.
- Monitor for information leakage

  ## My Key Takeaway
Footprinting shows how much information is
publicly available about any organization.
Even simple tools like Sherlock and Google
Dorks can reveal sensitive information about
a target without any direct interaction.

## References
- CEH v13 Module 02
      
