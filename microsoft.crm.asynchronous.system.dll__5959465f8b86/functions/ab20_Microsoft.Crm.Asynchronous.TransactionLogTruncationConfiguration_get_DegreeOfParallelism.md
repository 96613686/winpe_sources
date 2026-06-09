# Microsoft.Crm.Asynchronous.TransactionLogTruncationConfiguration::get_DegreeOfParallelism

- ea: `0xab20`
- end: `0xab31`
- name: `Microsoft.Crm.Asynchronous.TransactionLogTruncationConfiguration::get_DegreeOfParallelism`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xabc0`
- `0xabe0`

## pseudocode

```c

```

## disassembly

```asm
0xab20  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xab25  ldstr    aMaintenancejob_3// "MaintenanceJobsTruncateDOP"
0xab2a  ldc.i4.1
0xab2b  callvirt T0x2B000019
0xab30  ret
```
