# Microsoft.Crm.Asynchronous.TransactionLogShrinkConfiguration::get_DegreeOfParallelism

- ea: `0xa970`
- end: `0xa981`
- name: `Microsoft.Crm.Asynchronous.TransactionLogShrinkConfiguration::get_DegreeOfParallelism`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa880`
- `0xa8a0`

## pseudocode

```c

```

## disassembly

```asm
0xa970  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xa975  ldstr    aMaintenancejob_1// "MaintenanceJobsShrinkDOP"
0xa97a  ldc.i4.1
0xa97b  callvirt T0x2B000019
0xa980  ret
```
