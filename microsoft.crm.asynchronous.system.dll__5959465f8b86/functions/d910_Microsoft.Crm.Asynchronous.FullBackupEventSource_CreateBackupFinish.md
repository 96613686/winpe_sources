# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupFinish

- ea: `0xd910`
- end: `0xd928`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupFinish`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb80`

## callees

- `0xd930`
- `0xe020`

## pseudocode

```c

```

## disassembly

```asm
0xd910  ldarg.0
0xd911  ldarg.1
0xd912  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xd917  ldarg.2
0xd918  ldarg.3
0xd919  ldarg.s  4
0xd91b  ldarg.s  4
0xd91d  call     int64 Microsoft.Crm.Asynchronous.BackupMaintenanceJobsTelemetryUtility::GetFileSizeInMB(string filePath)
0xd922  call     instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupFinish(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.DateTime endTime, int64 duration, valuetype [mscorlib]System.Guid organizationId, string fullBackupPath, int64 sizeInMB)
0xd927  ret
```
