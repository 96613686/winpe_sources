# Microsoft.Crm.Application.WebServices.WorkflowWebService::WritePrimitiveSlugNode

- ea: `0x25c0`
- end: `0x25ee`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::WritePrimitiveSlugNode`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x25f0`
- `0x2700`

## pseudocode

```c

```

## disassembly

```asm
0x25c0  ldarg.1
0x25c1  ldstr    aSlugelement// "slugelement"
0x25c6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x25cb  ldarg.1
0x25cc  ldstr    aType// "type"
0x25d1  ldstr    aPrimitive// "primitive"
0x25d6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25db  ldarg.1
0x25dc  ldstr    aValue// "value"
0x25e1  ldarg.2
0x25e2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x25e7  ldarg.1
0x25e8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x25ed  ret
```
