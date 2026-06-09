# Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsConfiguration::get_PollIntervalInSeconds

- ea: `0x6f30`
- end: `0x6f42`
- name: `Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsConfiguration::get_PollIntervalInSeconds`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6310`

## pseudocode

```c

```

## disassembly

```asm
0x6f30  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x6f35  ldstr    aMaintenancejob_0// "MaintenanceJobsPollIntervalInSeconds"
0x6f3a  ldc.i4.s 0x3C
0x6f3c  callvirt T0x2B00000C
0x6f41  ret
```
