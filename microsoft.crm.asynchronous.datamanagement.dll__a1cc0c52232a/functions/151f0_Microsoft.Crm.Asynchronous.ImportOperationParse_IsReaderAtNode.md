# Microsoft.Crm.Asynchronous.ImportOperationParse::IsReaderAtNode

- ea: `0x151f0`
- end: `0x15212`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::IsReaderAtNode`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x15060`

## callees

- `0x151f0`

## pseudocode

```c

```

## disassembly

```asm
0x151f0  ldarg.0
0x151f1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x151f6  ldarg.1
0x151f7  ldc.i4.4
0x151f8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x151fd  brtrue.s loc_15210
0x151ff  ldarg.0
0x15200  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15205  ldarg.2
0x15206  ldc.i4.4
0x15207  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1520c  ldc.i4.0
0x1520d  ceq
0x1520f  ret
0x15210  ldc.i4.0
0x15211  ret
```
