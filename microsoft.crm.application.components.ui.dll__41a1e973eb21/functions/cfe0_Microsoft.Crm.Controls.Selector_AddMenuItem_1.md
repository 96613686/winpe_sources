# Microsoft.Crm.Controls.Selector::AddMenuItem_1

- ea: `0xcfe0`
- end: `0xd064`
- name: `Microsoft.Crm.Controls.Selector::AddMenuItem_1`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xcf10`

## callees

- `0xcfe0`

## string_xrefs

- `0xd043`: `iconPath`

## pseudocode

```c

```

## disassembly

```asm
0xcfe0  ldarg.0
0xcfe1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Controls.Selector::doc
0xcfe6  ldstr    aMenuitem// "MenuItem"
0xcfeb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0xcff0  stloc.0
0xcff1  ldarg.0
0xcff2  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Controls.Selector::declaration
0xcff7  ldloc.0
0xcff8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xcffd  pop
0xcffe  ldloc.0
0xcfff  ldstr    aId// "id"
0xd004  ldarg.2
0xd005  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xd00a  ldloc.0
0xd00b  ldstr    aType// "type"
0xd010  ldarg.3
0xd011  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xd016  ldloc.0
0xd017  ldstr    aDisplay// "display"
0xd01c  ldarg.1
0xd01d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xd022  ldloc.0
0xd023  ldstr    aIsenabled// "isenabled"
0xd028  ldarga.s 5
0xd02a  call     instance string [mscorlib]System.Boolean::ToString()
0xd02f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xd034  ldarg.s  4
0xd036  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd03b  brtrue.s loc_D063
0xd03d  ldarg.0
0xd03e  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Controls.Selector::doc
0xd043  ldstr    aIconpath// "iconPath"
0xd048  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xd04d  stloc.1
0xd04e  ldloc.1
0xd04f  ldarg.s  4
0xd051  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xd056  ldloc.0
0xd057  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xd05c  ldloc.1
0xd05d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xd062  pop
0xd063  ret
```
