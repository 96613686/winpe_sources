# Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_CurrentNamespace

- ea: `0x7f00`
- end: `0x7f0c`
- name: `Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_CurrentNamespace`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7fb0`

## callees

- `0x6ba0`

## pseudocode

```c

```

## disassembly

```asm
0x7f00  ldarg.0
0x7f01  ldfld    class Microsoft.Crm.Sdk.SchemaContext Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_context
0x7f06  callvirt instance string Microsoft.Crm.Sdk.SchemaContext::get_CurrentNamespace()
0x7f0b  ret
```
