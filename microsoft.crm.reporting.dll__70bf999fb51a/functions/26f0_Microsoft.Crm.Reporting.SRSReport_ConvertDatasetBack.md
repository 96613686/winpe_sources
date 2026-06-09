# Microsoft.Crm.Reporting.SRSReport::ConvertDatasetBack

- ea: `0x26f0`
- end: `0x27cc`
- name: `Microsoft.Crm.Reporting.SRSReport::ConvertDatasetBack`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2150`

## callees

- `0x1440`
- `0x26f0`

## string_xrefs

- `0x271c`: `CommandText`
- `0x2727`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x26f0  ldarg.2
0x26f1  ldarg.1
0x26f2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x26f7  ldstr    aName// "Name"
0x26fc  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2701  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2706  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x270b  castclass [System.Xml]System.Xml.XmlNode
0x2710  stloc.0
0x2711  ldarg.1
0x2712  ldstr    aQuery// "Query"
0x2717  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x271c  ldstr    aCommandtext// "CommandText"
0x2721  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2726  ldloc.0
0x2727  ldstr    aCommandtext// "CommandText"
0x272c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2731  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2736  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x273b  ldloc.0
0x273c  ldstr    aTimeout// "Timeout"
0x2741  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2746  brfalse  loc_27CB
0x274b  ldloc.0
0x274c  ldstr    aTimeout// "Timeout"
0x2751  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2756  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x275b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2760  brfalse.s loc_27A0
0x2762  ldarg.1
0x2763  ldstr    aQuery// "Query"
0x2768  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x276d  ldstr    aTimeout// "Timeout"
0x2772  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2777  brfalse.s loc_27CB
0x2779  ldarg.1
0x277a  ldstr    aQuery// "Query"
0x277f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2784  ldarg.1
0x2785  ldstr    aQuery// "Query"
0x278a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x278f  ldstr    aTimeout// "Timeout"
0x2794  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x2799  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x279e  pop
0x279f  ret
0x27a0  ldarg.0
0x27a1  ldarg.1
0x27a2  ldstr    aQuery// "Query"
0x27a7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x27ac  ldstr    aTimeout// "Timeout"
0x27b1  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Reporting.SRSReport::EnsureChildNodeExists(class [System.Xml]System.Xml.XmlNode parentNode, string childNodeName)
0x27b6  ldloc.0
0x27b7  ldstr    aTimeout// "Timeout"
0x27bc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x27c1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x27c6  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x27cb  ret
```
