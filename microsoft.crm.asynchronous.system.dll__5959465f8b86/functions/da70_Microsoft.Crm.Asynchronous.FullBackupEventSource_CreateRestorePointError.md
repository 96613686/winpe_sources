# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointError

- ea: `0xda70`
- end: `0xda86`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointError`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb80`

## callees

- `0xda90`

## pseudocode

```c

```

## disassembly

```asm
0xda70  ldarg.0
0xda71  ldarg.1
0xda72  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xda77  ldarg.2
0xda78  ldarg.3
0xda79  ldarg.s  4
0xda7b  callvirt instance string [mscorlib]System.Object::ToString()
0xda80  call     instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointError(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.DateTime errorTime, int64 duration, valuetype [mscorlib]System.Guid organizationId, string exceptionDetails)
0xda85  ret
```
