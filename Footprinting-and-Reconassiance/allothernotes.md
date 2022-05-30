#### All notes, don't need individual files

Greate tool, also found in Kali to search for employee and network info
```
theHarvester -d eccouncil.com -l 200 -d google
theHarvester -d eccouncil.com -l 200 -d linkedin
```

Darkweb search engine over tor browser
```
https://onionlandsearchengine.com
```

Used Sherlock python module to search for a username across all sites
```
https://github.com/sherlock-project/sherlock.git
```

Used Followermonk to gather information about peoples twitter handles
```
https://followerwonk.com/analyze/satyanadella
```

Used ping to validate response times
```
sudo ping www.certifiedhacker.com -f -l 1300
```

DNS and registration info
```
https://centralops.net/
```

Also in Kali is "cewl" to extract word list
```
cewl -d 2 -m5 www.certifiedhacker.com
``` 

Lookup domain information
```
whois.domaintools.com
```


#### DNS Footprinting

Can be performed using nslookup or nslookup.io

Going into interactive mode
```
nslookup <enter>
set type=a
www.certifiedhacker.com

set type=cname
www.certifiedhacker.com
```

Reverse dnslookup

Can use either parrot or KaliLinux to use "dnsrecon". 
First find the IP of the domain using https://www.yougetsignal.com/
Then with the range, using "dnsrecon" tool to check the DNS PTR Records
```
dnsrecon -r 172.67.203.0-172.67.203.255
```


#### Network Footprinting

Validate using https://www.arin.net/about/welcome/region and enter the public ip of the site to retrieve information from 


#### Footprinting using tools

Using recon-ng 

```
recon-ng <enter>
marketplace install all
modules search
workspaces create CEH
workspaces list
show domains
db insert domains 
> wellhello.com
> 
modules load brute
modules load recon/domains-hosts/brute_hosts
run
back
modules load reverse_resolve
modules load recon/hosts-hosts/reverse_resolve 
show hosts
modules load reporting
modules load reporting/html 
info
options set CREATOR Sam
options set CUSTOMER wellhello.com
options set FILENAME /tmp/results.html
run <produces the report>
```

Using recon-ng for person  (domain contacts) information footprinting
```
workspaces cerate reconnaissance
modules load recon/domains-contacts/whois_pocs
info
options set SOURCE wellhello.com
run <note the names to follow>
modules load recon/profiles-profiles/namechk
options set SOURCE BrandonStout
run
back
moudles load recon/profiles-profiles/profiler
run
back
modules load reporting/html
options set CREATOR Sam
options set CUSTOMER wellhello.com
options set FILENAME /tmp/profiledresult.html
```


Using Maltego

<< Most of the items and options have changed >>


Using Other tools

```
usufy.py -n <Target name> -p twitter facebook instagram // Okay to have name with spaces
```

There are many other similar tools.
```
searchfy.py // Info about users on social networks
mailfy.py // Information about email accounts
phonefy.py // Search for existence of a number
entify.py // Regular expression search
```

Using BillCipher

Another python utility to extracts multiple details about a given site
```
python3 billcipher.py <enter>
## Enter the site or ip address twice
## Select the option
```