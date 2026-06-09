# Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_2

- ea: `0x4ab0`
- end: `0x4abd`
- name: `Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_2`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x46f0`

## pseudocode

```c

```

## disassembly

```asm
0x4ab0  ldarg.0
0x4ab1  ldarg.1
0x4ab2  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::get_CancellationToken()
0x4ab7  call     instance void Microsoft.Crm.Asynchronous.JobManager::OrgMaintenanceJobSyncTimerEvent(valuetype [mscorlib]System.Threading.CancellationToken token)
0x4abc  ret
```
