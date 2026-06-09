# Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaintenanceIntervalTimerFrequencyMultiplier

- ea: `0x3f60`
- end: `0x3f71`
- name: `Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_MaintenanceIntervalTimerFrequencyMultiplier`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4110`

## pseudocode

```c

```

## disassembly

```asm
0x3f60  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x3f65  ldstr    aAsyncjobstimer// "AsyncJobsTimerFrequencyMultiplier"
0x3f6a  ldc.i4.2
0x3f6b  callvirt T0x2B00000C
0x3f70  ret
```
