# Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport

- ea: `0x8b80`
- end: `0x8b93`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadTypeExport`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x88e0`

## callees

- `0x8810`

## pseudocode

```c

```

## disassembly

```asm
0x8b80  ldarg.0
0x8b81  ldfld    class [mscorlib]System.Collections.IList Microsoft.Crm.Sdk.ServiceDescription::_typesToExport
0x8b86  ldarg.1
0x8b87  call     class [mscorlib]System.Type Microsoft.Crm.Sdk.ServiceDescription::LoadType(string partialTypeName)
0x8b8c  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8b91  pop
0x8b92  ret
```
