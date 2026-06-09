# Microsoft.Crm.Asynchronous.TransactionLogBackupConfiguration::get_DegreeOfParallelism

- ea: `0xae20`
- end: `0xae31`
- name: `Microsoft.Crm.Asynchronous.TransactionLogBackupConfiguration::get_DegreeOfParallelism`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xaf60`
- `0xaf80`

## pseudocode

```c

```

## disassembly

```asm
0xae20  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xae25  ldstr    aMaintenancejob_4// "MaintenanceJobsBackupDOP"
0xae2a  ldc.i4.1
0xae2b  callvirt T0x2B000019
0xae30  ret
```
