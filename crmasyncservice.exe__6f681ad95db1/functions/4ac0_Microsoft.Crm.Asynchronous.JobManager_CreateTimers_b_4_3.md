# Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_3

- ea: `0x4ac0`
- end: `0x4acd`
- name: `Microsoft.Crm.Asynchronous.JobManager::<CreateTimers>b__4_3`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x45a0`

## pseudocode

```c

```

## disassembly

```asm
0x4ac0  ldarg.0
0x4ac1  ldarg.1
0x4ac2  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::get_CancellationToken()
0x4ac7  call     instance void Microsoft.Crm.Asynchronous.JobManager::OnOrgDatabaseBackupCleanupTimerEvent(valuetype [mscorlib]System.Threading.CancellationToken token)
0x4acc  ret
```
