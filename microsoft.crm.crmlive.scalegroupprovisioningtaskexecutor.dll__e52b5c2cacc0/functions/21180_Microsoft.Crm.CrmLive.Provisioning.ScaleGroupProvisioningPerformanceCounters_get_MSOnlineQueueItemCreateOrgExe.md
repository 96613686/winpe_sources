# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::get_MSOnlineQueueItemCreateOrgExecutionTime

- ea: `0x21180`
- end: `0x211a2`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::get_MSOnlineQueueItemCreateOrgExecutionTime`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x212e0`
- `0x21320`

## callees

- `0x21180`

## string_xrefs

- `0x21187`: `CRM Scale Group Provisioning Service`
- `0x2118c`: `Microsoft Online Queue Item Create Organization Execution Time`

## pseudocode

```c

```

## disassembly

```asm
0x21180  ldsfld   class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::_queueItemCreateOrgExecutionTime
0x21185  brtrue.s loc_2119C
0x21187  ldstr    aCrmScaleGroupP// "CRM Scale Group Provisioning Service"
0x2118c  ldstr    aMicrosoftOnlin_3// "Microsoft Online Queue Item Create Orga"...
0x21191  ldc.i4.0
0x21192  newobj   instance void [System]System.Diagnostics.PerformanceCounter::.ctor(string, string, bool)
0x21197  stsfld   class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::_queueItemCreateOrgExecutionTime
0x2119c  ldsfld   class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.CrmLive.Provisioning.ScaleGroupProvisioningPerformanceCounters::_queueItemCreateOrgExecutionTime
0x211a1  ret
```
