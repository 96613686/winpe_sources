# Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupFinish

- ea: `0xdc00`
- end: `0xdc11`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupFinish`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb80`

## callees

- `0xdc20`

## pseudocode

```c

```

## disassembly

```asm
0xdc00  ldarg.0
0xdc01  ldarg.1
0xdc02  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xdc07  ldarg.2
0xdc08  ldarg.3
0xdc09  ldarg.s  4
0xdc0b  call     instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupFinish(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.DateTime endTime, int64 duration, valuetype [mscorlib]System.Guid organizationId, string fileName)
0xdc10  ret
```
