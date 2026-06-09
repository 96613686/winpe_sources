# Microsoft.Crm.Reporting.SRSReport::CreateChildNode

- ea: `0x1460`
- end: `0x1487`
- name: `Microsoft.Crm.Reporting.SRSReport::CreateChildNode`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1000`
- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x1460  ldarg.0
0x1461  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x1466  ldarg.2
0x1467  ldarg.0
0x1468  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Reporting.SRSReport::_rdlDoc
0x146d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1472  callvirt instance string [System.Xml]System.Xml.XmlNode::get_NamespaceURI()
0x1477  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x147c  stloc.0
0x147d  ldarg.1
0x147e  ldloc.0
0x147f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1484  pop
0x1485  ldloc.0
0x1486  ret
```
