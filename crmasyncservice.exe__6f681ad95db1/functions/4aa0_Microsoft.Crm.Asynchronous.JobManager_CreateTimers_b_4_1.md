# Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_1

- ea: `0x4aa0`
- end: `0x4aad`
- name: `Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_1`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x45d0`

## pseudocode

```c

```

## disassembly

```asm
0x4aa0  ldarg.0
0x4aa1  ldarg.1
0x4aa2  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::get_CancellationToken()
0x4aa7  call     instance void Microsoft.Crm.Asynchronous.JobManager::OrgDatabaseJobTimeoutTimerEvent(valuetype [mscorlib]System.Threading.CancellationToken token)
0x4aac  ret
```
