[comment]: # "Auto-generated SOAR connector documentation"
# SonicWALL

Publisher: SonicWALL  
Connector Version: 1\.3\.2  
Product Vendor: SonicWALL  
Product Name: SonicWALL Firewall  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 3\.0\.251  

Manipulate SonicWALL firewall via ECLI

# sonicwall_firewall
A phantom app for sonicwall product


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a SonicWALL Firewall asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**firewall\_mgmt** |  required  | string | Management IP/Hostname of Sonicwall Firewall
**admin\_account** |  required  | string | Administrator's username
**admin\_password** |  required  | password | Administrator's password

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity\.  
[block ip](#action-block-ip) - Block an IP  
[unblock ip](#action-unblock-ip) - Unblock an ip  
[block url](#action-block-url) - Block an URL  
[unblock url](#action-unblock-url) - Unblock an URL  
[block service](#action-block-service) - Block a network service  
[unblock service](#action-unblock-service) - Unblock a network service  

## action: 'test connectivity'
Validate the asset configuration for connectivity\.

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'block ip'
Block an IP

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**target** |  required  | IP address to block | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.operate\_address\.\*\. | string |  `ip` 
action\_result\.summary\.firewall | string | 
action\_result\.summary\.operation | string |   

## action: 'unblock ip'
Unblock an ip

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**target** |  required  | IP address to unblock | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.operate\_address\.\*\. | string |  `ip` 
action\_result\.summary\.firewall | string | 
action\_result\.summary\.operation | string |   

## action: 'block url'
Block an URL

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**target** |  required  | URL to be blocked | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.operate\_address\.\*\. | string |  `url` 
action\_result\.summary\.firewall | string | 
action\_result\.summary\.operation | string |   

## action: 'unblock url'
Unblock an URL

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**target** |  required  | URL to be unblocked | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.operate\_address\.\*\. | string |  `url` 
action\_result\.summary\.firewall | string | 
action\_result\.summary\.operation | string |   

## action: 'block service'
Block a network service

Type: **contain**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**protocol** |  required  | TCP or UDP | string | 
**port** |  required  | Service start port | numeric |  `port` 
**port\_end** |  optional  | Service end port\. Leave blank if to block a single port number | numeric |  `port` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.protocol\.\*\. | string | 
action\_result\.data\.\*\.port\_start\.\*\. | numeric |  `port` 
action\_result\.data\.\*\.port\_end\.\*\. | string |  `port` 
action\_result\.summary\.firewall | string | 
action\_result\.summary\.operation | string |   

## action: 'unblock service'
Unblock a network service

Type: **correct**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**protocol** |  required  | TCP or UDP | string | 
**port** |  required  | Service start port | numeric |  `port` 
**port\_end** |  optional  | Service end port\. Leave blank if to block a single port number | numeric |  `port` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.protocol\.\*\. | string | 
action\_result\.data\.\*\.port\_start\.\*\. | numeric |  `port` 
action\_result\.data\.\*\.port\_end\.\*\. | string |  `port` 
action\_result\.summary\.firewall | string | 
action\_result\.summary\.operation | string | 