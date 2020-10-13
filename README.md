# LogicMonitor DataSource to monitor Palo Alto Networks GlobalProtect active Gateway sessions

This DataSource, `GlobalProtect_Gateway_Active_Sessions,` is available in the LogicMonitor Exchange (LM Locator JZ97Z6)

## Description

The custom DataSource will keep a running count of the number of active GlobalProtect sessions for each Gateway presented on the monitored Firewall. Active Discovery will find each Gateway as its own Instance.

## Requirements

This was tested on PAN-OS 8.1

You must have `paloalto.apikey.pass` defined in the Resource (it's recommended to create an API-only user to generate the key, with appropriate access)

## Components

### [Applies To](components/applies_to)

Filter the DataSource to just PaloAlto devices

### [Active Discovery; Groovy Script](components/active_discovery-groovy_script)

This will discover each Gateway as a unique Instance. Inactive Instances are **not** automatically deleted.

### [Collector Attributes; Groovy Script](components/collector_attributes-groovy_script)

The collector will poll each Instance to return the defined values.

### [Datapoint; current_users](components/datapoint-current_users)

This is a NormalDatapoint, metric is gauge, output is interpreted with multi-line key-value pairs.

### [Datapoint; previous_users](components/datapoint-previous_users)

This is a NormalDatapoint, metric is gauge, output is interpreted with multi-line key-value pairs.