# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointFinish

- ea: `0xdad0`
- end: `0xdae3`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointFinish`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb80`

## callees

- `0xdaf0`

## pseudocode

```c

```

## disassembly

```asm
0xdad0  ldarg.0
0xdad1  ldarg.1
0xdad2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xdad7  ldarg.2
0xdad8  ldarg.3
0xdad9  ldarg.s  4
0xdadb  ldarg.s  5
0xdadd  call     instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointFinish(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.DateTime endTime, int64 duration, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid restorePointId, string buildVersion)
0xdae2  ret
```
