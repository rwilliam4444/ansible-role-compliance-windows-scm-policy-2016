# Role Name:
- ansible-role-compliance-windows-scm-policy-2016

# Description:
This SCM Policy Role was based off the CIS specs for 2016 servers.   This role
covers the "SCM" CIS section only. The checks and remediation commands are for
local settings only. Group Policy settings may override these settings. When the
"remediate" variable is set to "YES", the role will try to remediate the
server's setting(s) accoridng to the CIS standards.  The defaults/main.yml file
can be used to disable specific CIS items (i.e. "execute_<cis task #>") from
executing. The default value in the defaults/main.yml for these CIS item
variables (i.e. "execute_<cis task #>") is set to "YES". The value "YES" means
that the CIS item will execute at run time. Set the value to "NO" if you want to
skip this CIS item in question from executing.

# Requirements:
Windows Ansible related pre-requisites

# Role Variables:
# Defaults file for ansible-role-compliance-windows-scm-policy-2016

Parameter | Choices/Defaults|Comments
----------|-----------------|--------
__remediate__ |"NO"| variable used to determine whether or not to remediate.
__LocalAccountTokenFilterPolicy_cis__ |"1"| CIS value.
__UseLogonCredential_cis__ |"0"| CIS value.


# Example Playbook:
---
 - hosts: [win]
   roles:
   - ansible-role-compliance-windows-scm-policy-2016


# Author Information:
Richard M. Williams (williamsitv@yahoo.com)
