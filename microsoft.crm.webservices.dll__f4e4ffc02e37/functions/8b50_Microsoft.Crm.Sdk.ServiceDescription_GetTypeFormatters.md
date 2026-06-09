# Microsoft.Crm.Sdk.ServiceDescription::GetTypeFormatters

- ea: `0x8b50`
- end: `0x8b5c`
- name: `Microsoft.Crm.Sdk.ServiceDescription::GetTypeFormatters`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8ae0`

## callees

- `0x8b60`

## pseudocode

```c

```

## disassembly

```asm
0x8b50  ldarg.0
0x8b51  ldstr    aIfieldformatte// "IFieldFormatter"
0x8b56  call     instance class [mscorlib]System.Collections.IEnumerable Microsoft.Crm.Sdk.ServiceDescription::GetTypes(string interfaceName)
0x8b5b  ret
```
