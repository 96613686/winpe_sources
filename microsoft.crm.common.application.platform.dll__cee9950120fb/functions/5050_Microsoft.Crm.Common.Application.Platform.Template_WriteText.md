# Microsoft.Crm.Common.Application.Platform.Template::WriteText

- ea: `0x5050`
- end: `0x5069`
- name: `Microsoft.Crm.Common.Application.Platform.Template::WriteText`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4d60`

## pseudocode

```c

```

## disassembly

```asm
0x5050  ldarg.1
0x5051  ldstr    aText// "text"
0x5056  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x505b  ldarg.1
0x505c  ldarg.2
0x505d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteCData(string)
0x5062  ldarg.1
0x5063  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5068  ret
```
