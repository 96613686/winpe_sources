# Microsoft.Crm.Sdk.FieldFormatterBase::WriteElement

- ea: `0xe50`
- end: `0xe63`
- name: `Microsoft.Crm.Sdk.FieldFormatterBase::WriteElement`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xd10`

## string_xrefs

- `0xe57`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xe50  ldarg.1
0xe51  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0xe56  ldarg.2
0xe57  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0xe5c  ldarg.3
0xe5d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string, string)
0xe62  ret
```
