# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointStart

- ea: `0xda30`
- end: `0xda3e`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointStart`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb80`

## callees

- `0xda40`

## pseudocode

```c

```

## disassembly

```asm
0xda30  ldarg.0
0xda31  ldarg.1
0xda32  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xda37  ldarg.2
0xda38  call     instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointStart(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.Guid organizationId)
0xda3d  ret
```
