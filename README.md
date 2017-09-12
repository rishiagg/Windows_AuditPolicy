# Windows AuditPolicy Monitoring
App that can monitor a current Audit Policy on Windows boxes..


Batch File
-------------

**audit_policy_read.bat ** file holds a script that will execute after every 24 Hours.

> **Note:**

		**CMD > AuditPol /get /category:* ** is used to pull the existing Audit policy.
		Time interval can be changed as per the requirement. 
		To make the necessary changes navigate to App > Local > inputs.conf file.
		set the  parameter e.g. "interval = 86400" in seconds.

Input Configuration File
-------------

[script://$SPLUNK_HOME/etc/apps/AuditPolicyUF_Windows/bin/audit_policy_read.bat]

disabled = false

index = XXXXXXXXXXX

interval = 86400

source = audit_policy_read

sourcetype = WinEventLog:AuditPolicy


		Updated ServerClass to WhiteList all windows machines

			whitelist.0 = *
		
			machineTypesFilter=windows-*
