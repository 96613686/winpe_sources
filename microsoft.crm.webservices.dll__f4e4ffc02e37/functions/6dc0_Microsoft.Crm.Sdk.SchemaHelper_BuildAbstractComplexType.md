# Microsoft.Crm.Sdk.SchemaHelper::BuildAbstractComplexType

- ea: `0x6dc0`
- end: `0x6dd4`
- name: `Microsoft.Crm.Sdk.SchemaHelper::BuildAbstractComplexType`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1a90`
- `0x72c0`
- `0x75b0`

## pseudocode

```c

```

## disassembly

```asm
0x6dc0  newobj   instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x6dc5  dup
0x6dc6  ldarg.0
0x6dc7  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaType::set_Name(string)
0x6dcc  dup
0x6dcd  ldc.i4.1
0x6dce  callvirt instance void [System.Xml]System.Xml.Schema.XmlSchemaComplexType::set_IsAbstract(bool)
0x6dd3  ret
```
