# Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_0

- ea: `0x4a90`
- end: `0x4a9d`
- name: `Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4470`

## pseudocode

```c

```

## disassembly

```asm
0x4a90  ldarg.0
0x4a91  ldarg.1
0x4a92  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::get_CancellationToken()
0x4a97  call     instance void Microsoft.Crm.Asynchronous.JobManager::OnOrgDatabaseMaintenanceTimerEvent(valuetype [mscorlib]System.Threading.CancellationToken token)
0x4a9c  ret
```
