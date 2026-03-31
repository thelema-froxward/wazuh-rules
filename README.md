# (c) 2024-2026 thelema-froxward

Licensed under the MIT License
Wazuh Custom Detection Rules
===

A comprehensive collection of Wazuh XML detection rules organized into two categories:

## &#x20;Structure


├── web-attacks/          # Web application attack detection rules
│   ├── sql-injection.xml
│   ├── xss.xml
│   ├── rfi-lfi.xml
│   ├── command-injection.xml
│   ├── path-traversal.xml
│   ├── xxe.xml
│   ├── ssrf.xml
│   ├── csrf.xml
│   ├── http-smuggling.xml
│   ├── brute-force-web.xml
│   ├── web-shell.xml
│   ├── api-abuse.xml
│   ├── http-response-splitting.xml
│   ├── open-redirect.xml
│   ├── crlf-injection.xml
│   ├── deserialization.xml
│   ├── ssti.xml
│   ├── idor.xml
│   ├── jwt-attacks.xml
│   ├── graphql-attacks.xml
│   ├── upload-attacks.xml
│   └── wordpress-attacks.xml
│
└── mitre-attck/          # MITRE ATT\&CK mapped detection rules
    ├── initial-access.xml
    ├── execution.xml
    ├── persistence.xml
    ├── privilege-escalation.xml
    ├── defense-evasion.xml
    ├── credential-access.xml
    ├── discovery.xml
    ├── lateral-movement.xml
    ├── collection.xml
    ├── command-and-control.xml
    ├── exfiltration.xml
    ├── impact.xml
    ├── reconnaissance.xml
    └── resource-development.xml


## &#x20;Installation

1. Copy rule files to `/var/ossec/etc/rules/`
2. Add `<include>filename.xml</include>` to `/var/ossec/etc/ossec.conf` inside `<ruleset>`
3. Restart Wazuh: `systemctl restart wazuh-manager`

## &#x20;Rule ID Ranges

|Category|Rule ID Range|
|-|-|
|Web Attacks|100100 – 100999|
|MITRE ATT\&CK|101000 – 101999|

## &#x20;Notes

* Test rules in a staging environment before deploying to production.
* Tune `frequency` and `timeframe` thresholds to match your traffic patterns.
* Rules reference standard Wazuh decoders (web-accesslog, syslog, json, etc.)

