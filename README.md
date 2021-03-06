# manageiq\_workers
Ansible role for configuring the workers on ManageIQ / CloudForms Management Engine (CFME) appliances.

## Role Variables
Information about the expected role parameters.

See [Summary of Roles, Workers and Messages](https://access.redhat.com/documentation/en-us/reference_architectures/2017/html/deploying_cloudforms_at_scale/architecture#summary_of_roles_workers_and_messages) for details on the different workers and what they are for.

The _Workers Tab_ colume describes which box on the Workers tab of the Advanced appliance configuration page the value is settable from. If not `Advanced` then the value is only settable via Advanced settings.

| parameter                                                    | required | default       | choices         | appliance workers tab  | comments 
| ------------------------------------------------------------ |:--------:|:-------------:| --------------- | ---------------------- |:-------- 
| manageiq\_generic\_worker\_memory\_threshold                 | No       | 600.megabytes |                 | Generic Workers        |
| manageiq\_generic\_worker\_thread\_count                     | No       | 4             |                 | Generic Workers        |
| manageiq\_priority\_worker\_memory\_threshold                | No       | 600.megabytes |                 | Priorty Workers        |
| manageiq\_priority\_worker\_thread\_count                    | No       | 4             |                 | Priorty Workers        |
| manageiq\_c\_and\_u\_data\_collector\_memory\_threshold      | No       | 400.megabytes |                 | C & U Data Collectors  |
| manageiq\_c\_and\_u\_data\_collector\_thread\_count          | No       | 2             |                 | C & U Data Collectors  |
| manageiq\_c\_and\_u\_data\_processor\_memory\_threshold      | No       | 500.megabytes |                 | C & U Data Processors  |
| manageiq\_c\_and\_u\_data\_processor\_thread\_count          | No       | 2             |                 | C & U Data Processors  |
| manageiq\_event\_monitor\_memory\_threshold                  | No       | 2.gigabytes   |                 | Event Monitor          |
| manageiq\_refresh\_worker\_memory\_threshold                 | No       | 2.gigabytes   |                 | Refresh                |
| manageiq\_connection\_broker\_memory\_threshold              | No       | 2.gigabytes   |                 | Connection Broker      |
| manageiq\_vm\_analysis\_collector\_memory\_threshold         | No       | 600.megabytes |                 | VM Analysis Collectors |
| manageiq\_vm\_analysis\_collector\_thread\_count             | No       | 2             |                 | VM Analysis Collectors |
| manageiq\_ui\_worker\_thread\_count                          | No       | 4             |                 | UI Worker              |
| manageiq\_websocket\_worker\_thread\_count                   | No       | 1             |                 | Websocket Workers      |
| manageiq\_reporting\_worker\_memory\_threshold               | No       | 500.megabytes |                 | Reporting Workers      |
| manageiq\_reporting\_worker\_thread\_count                   | No       | 2             |                 | Reproting Workers      |
| manageiq\_web\_service\_worker\_memory\_threshold            | No       | 1.gigabytes   |                 | Web Service Workers    |
| manageiq\_web\_service\_worker\_thread\_count                | No       | 1             |                 | Web Service Workers    |
| manageiq\_default\_memory\_threshold                         | No       | 400.megabytes |                 | Advanced               |
| manageiq\_default\_thread\_count                             | No       | 1             |                 | Advanced               |
| manageiq\_ansible\_memory\_threshold                         | No       | 0.megabytes   |                 | Advanced               |
| manageiq\_ui\_worker\_memory\_threshold                      | No       | 1.gigabytes   |                 | Advanced               |
| manageiq\_websocket\_worker\_memory\_threshold               | No       | 1.gigabytes   |                 | Advanced               |
| manageiq\_vmdb\_storage\_bridge\_worker\_memory\_threshold   | No       | 2.gigabytes   |                 | Advanced               |
| manageiq\_schedule\_worker\_memory\_threshold                | No       | 500.megabytes |                 | Advanced               |
| manageiq\_netapp\_refresh\_worker\_memory\_threshold         | No       | 2.gigabytes   |                 | Advanced               |
| manageiq\_sims\_refresh\_worker\_memory\_threshold           | No       | 1.gigabytes   |                 | Advanced               |
| manageiq\_storage\_metrics\_collector\_worker\_thread\_count | No       | 2             |                 | Advanced               |
| manageiq\_workers\_validate\_parameters                      | No       | True          | True, False     | N/A                    | True to enable role parameter validation based on what the ManageIQ / CFME UI allows to be configured. False to disable validation and allow the setting of values that the ManageIQ / CFME does not allow users to configure.
| manageiq\_workers\_combined\_edits                           | No       | True          | True, False     | N/A                    | True to do all of the configuraton edits as a single operation. This is more efficent but gives less details about what has changed when diff is enabled due to the nature of diff and the nesting of some attributes. False to do each worker edit as a seperate task. This is less efficent but gives more detail when diff is enabled about what is changing.
