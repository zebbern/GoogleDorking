# Google Dorking Guide

Google Dorking is an effective method for using advanced search commands to locate specific files, information, or vulnerabilities on websites. It enables precise searches with specific operators. Below is a complete list of commands, organized from basic to advanced, to help you understand how to use Google Dorking.

Dorking Guide Commands From

- Basic Commands
- Advanced Commands
- Then For Pentesters i added a juicy section on the bottom!

## Basic Commands

In Google.com search type these commands and replace examplesite.com with your own or switch out the information to what you are looking for.

| **Command** | **Explanation** |
| --- | --- |
| `site:examplesite.com` | Shows all pages indexed from the website. Useful to view all content on a domain. |
| `site:examplesite.com filetype:pdf` | Displays PDF files from the website. Useful for finding documents. |
| `filetype:pdf OR docx OR xls site:examplesite.com` | Searches multiple document types at once, such as PDF, Word, Excel files. |
| `intext:name site:examplesite.com` | Searches for a name or word across the entire website. Useful for locating specific references. |
| `address intext:name` | Searches for combinations of a name and the word "address." Potentially finds addresses. |
| `phone intext:name` | Searches for name and phone number. Used to find contact information. |
| `site:examplesite.com intitle:contact` | Shows pages with "contact" in the title. Good for finding contact pages. |
| `link:examplesite.com` | Displays pages linking to examplesite.com. Useful to find references from other sites. |
| `related:examplesite.com` | Shows websites Google considers related. Useful for finding similar sites. |
| `site:no "deprecated" | "old"` | Finds pages containing "deprecated" or "old" on a website. |
| `site:examplesite.com filetype:xlsx OR xls` | Searches for Excel files. May contain financial or sensitive data. |
| `site:examplesite.com inurl:admin` | Searches for pages with "admin" in the URL. Useful for finding admin pages. |
| `ip:[IP address]` | Shows all websites hosted on a specific IP address. Used to find all sites on a server. |
| `intitle:"Index of /" site:examplesite.com` | Shows indexed folders that may contain publicly accessible files. |
| `site:no "error" | "error message"` | Searches for error pages or messages on a site. |
| `site:no "financial" | "invoice"` | Finds financial documents, like invoices, on a website. |

## Advanced Dorking Commands

| **Command** | **Explanation** |
| --- | --- |
| `site:examplesite.com inurl:login` | Searches for pages with "login" in the URL. Useful for finding login pages. |
| `cache:examplesite.com` | Shows Google’s cached version of the site. Can be used to see older versions of a page. |
| `allinurl:examplesite.com confidential` | Searches for URLs containing the word "confidential." Useful for finding potentially sensitive pages. |
| `site:examplesite.com inurl:wp-admin` | Searches for WordPress admin pages. May reveal unsecured WordPress sites. |
| `site:examplesite.com intext:"password"` | Searches for occurrences of "password" in the text on the website. May reveal sensitive data if poorly secured. |
| `filetype:sql site:examplesite.com` | Searches for SQL files that may contain database extracts. |
| `filetype:xml site:examplesite.com` | Searches for XML files, which are often used for data exchange and may contain sensitive information. |

| **Command** | **Explanation** |
| --- | --- |
| `intitle:"index of" inurl:ftp` | Searches for open FTP servers that may have publicly accessible files or directories. |
| `site:examplesite.com ext:log` | Searches for log files (.log). Logs may contain sensitive information, such as error descriptions, server messages, or connection data. |
| `site:examplesite.com filetype:bak` | Searches for backup files that may reveal source code or sensitive data. |
| `site:examplesite.com ext:sql "DROP TABLE"` | Searches for SQL files with database commands, including potentially destructive commands that may expose database vulnerabilities. |
| `site:no ext` | Searches for files with various extensions on a website. |
| `site:examplesite.com ext:env` | Searches for ".env" files, which often contain environment variables, including API keys, database passwords, and other sensitive configurations. |
| `site:examplesite.com "phpinfo()"` | Searches for PHP info pages. PHP info pages provide a detailed view of the server configuration, useful for identifying attack surfaces. |
| `site:examplesite.com intext:"powered by WordPress"` | Searches for WordPress installations that may be vulnerable to plugin or theme issues. |
| `site:examplesite.com inurl:wp-content/uploads/` | Searches for uploaded files on WordPress sites. Upload directories may contain insecure or unwanted files. |
| `site:no filetype | filetype` | Searches for specific file types on a site. |
| `site:examplesite.com inurl:"/phpmyadmin/"` | Searches for PHPMyAdmin admin pages, which may be insecure or accessible without proper protection. |
| `site:examplesite.com intext:"username" intext:"password"` | Searches for usernames and passwords exposed in text on the website. Useful for finding hardcoded credentials or poor configurations. |
| `site:examplesite.com intitle:"Login Page"` | Searches for login pages. Useful for identifying public login portals for further testing. |
| `site:examplesite.com filetype:pcap` | Searches for PCAP files (Packet Capture). These may contain network traffic that could reveal sensitive data, such as passwords or session data. |
| `site:examplesite.com "default password"` | Searches for pages containing "default password." This may indicate the use of default passwords, which often pose a significant security risk. |
| `site:no inurl | inurl` | Searches for specific URLs or URL patterns on a site. |
| `site:examplesite.com filetype:swf` | Searches for Flash files (.swf), which can be a source of Cross-Site Scripting (XSS) vulnerabilities. |

## Additional Tips for Pentesting with Google Dorking

1. **Use Dorks for Technology Identification**:
   - **Example**: `site:examplesite.com "powered by Apache"` or `site:examplesite.com "powered by Nginx"`. Helps to identify the server technology, which may reveal specific software vulnerabilities.
   
2. **Searching for Email Addresses**:
   - **Command**: `site:examplesite.com intext:@examplesite.com`. This helps to locate employee email addresses, which may be used for phishing or social engineering.
   
3. **Searching for Sensitive URLs and Parameters**:
   - **Example**: `site:examplesite.com inurl:id= OR inurl:login` to find potentially vulnerable parameters that may be exploited for SQL Injection or other injection attacks.

<aside>
💡 **Additional Google Dorking Examples**:

   - **PHP extension with parameters**: `site:example.com ext:php inurl:?`
   - **API Endpoints**: `site:example.com inurl:api | site:*/rest | site:*/v1 | site:*/v2 | site:*/v3`
   - **Juicy Extensions**: `site:example.com ext:log | ext:txt | ext:conf | ext:cnf | ext:ini | ext:env | ext:sh | ext:bak | ext:backup | ext:swp | ext:old | ext:~ | ext:git | ext:svn | ext:htpasswd | ext:htaccess | ext:json`
   - **High % inurl keywords**: `inurl:conf | inurl:env | inurl:cgi | inurl:bin | inurl:etc | inurl:root | inurl:sql | inurl:backup | inurl:admin | inurl:php site:example.com`
   - **Server Errors**: `inurl:"error" | intitle:"exception" | intitle:"failure" | intitle:"server at" | inurl:exception | "database error" | "SQL syntax" | "undefined index" | "unhandled exception" | "stack trace" site:example.com`
   - **XSS Prone Parameters**: `inurl:q= | inurl:s= | inurl:search= | inurl:query= | inurl:keyword= | inurl:lang= inurl:& site:example.com`
   - **Open Redirect prone parameters**: `inurl:url= | inurl:return= | inurl:next= | inurl:redirect= | inurl:redir= | inurl:ret= | inurl:r2= | inurl:page= inurl:& inurl:http site:example.com`
   - **SQLi Prone Parameters**: `inurl:id= | inurl:pid= | inurl:category= | inurl:cat= | inurl:action= | inurl:sid= | inurl:dir= inurl:& site:example.com`
   - **SSRF Prone Parameters**: `inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:domain= | inurl:page= inurl:& site:example.com`
   - **LFI Prone Parameters**: `inurl:include | inurl:dir | inurl:detail= | inurl:file= | inurl:folder= | inurl:inc= | inurl:locate= | inurl:doc= | inurl:conf= inurl:& site:example.com`
   - **RCE Prone Parameters**: `inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read= | inurl:ping= inurl:& site:example.com`
   - **File upload endpoints**: `site:example.com "choose file"`
   - **API Docs**: `inurl:apidocs | inurl:api-docs | inurl:swagger | inurl:api-explorer site:example.com`
   - **Login Pages**: `inurl:login | inurl:signin | intitle:login | intitle:signin | inurl:secure site:example.com`
   - **Test Environments**: `inurl:test | inurl:env | inurl:dev | inurl:staging | inurl:sandbox | inurl:debug | inurl:temp | inurl:internal | inurl:demo site:example.com`
   - **Sensitive Documents**: `site:example.com ext:txt | ext:pdf | ext:xml | ext:xls | ext:xlsx | ext:ppt | ext:pptx | ext:doc | ext:docx intext:"confidential" | intext:"Not for Public Release" | intext:"internal use only" | intext:"do not distribute"`
   - **Sensitive Parameters**: `inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:example.com`
   - **Adobe Experience Manager (AEM)**: `inurl:/content/usergenerated | inurl:/content/dam | inurl:/jcr:content | inurl:/libs/granite | inurl:/etc/clientlibs | inurl:/content/geometrixx | inurl:/bin/wcm | inurl:/crx/de site:example.com`

</aside>


## Contributions
If you’d like to contribute, feel free to fork this repository and add any tools or resources that enhance the guide. Contributions to specific examples or additional resources will help this collection grow and stay up-to-date with the latest in cybersecurity.

Thank you for exploring the **GoogleDorking**. Together, we’re building a one-stop resource for digital security mastery. 

Lastly Consider to star this if you liked it ;)
Happy hacking! 👾 
