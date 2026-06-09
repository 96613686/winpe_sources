# Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsConfiguration::get_JobExpiredThresholdInSeconds

- ea: `0x6f50`
- end: `0x6f65`
- name: `Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsConfiguration::get_JobExpiredThresholdInSeconds`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x66d0`

## pseudocode

```c

```

## disassembly

```asm
0x6f50  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x6f55  ldstr    aMaintenancejob_1// "MaintenanceJobsExpiredThresholdSeconds"
0x6f5a  ldc.i4   0x258
0x6f5f  callvirt T0x2B00000C
0x6f64  ret
```
