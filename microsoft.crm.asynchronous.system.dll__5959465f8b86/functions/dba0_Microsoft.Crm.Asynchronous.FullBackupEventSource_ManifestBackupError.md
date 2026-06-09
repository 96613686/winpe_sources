# Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupError

- ea: `0xdba0`
- end: `0xdbb6`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupError`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb80`

## callees

- `0xdbc0`

## pseudocode

```c

```

## disassembly

```asm
0xdba0  ldarg.0
0xdba1  ldarg.1
0xdba2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xdba7  ldarg.2
0xdba8  ldarg.3
0xdba9  ldarg.s  4
0xdbab  callvirt instance string [mscorlib]System.Object::ToString()
0xdbb0  call     instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupError(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.DateTime errorTime, int64 duration, valuetype [mscorlib]System.Guid organizationId, string exceptionDetails)
0xdbb5  ret
```
