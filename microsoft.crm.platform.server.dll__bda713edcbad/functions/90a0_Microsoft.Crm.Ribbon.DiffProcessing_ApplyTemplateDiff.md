# Microsoft.Crm.Ribbon.DiffProcessing::ApplyTemplateDiff

- ea: `0x90a0`
- end: `0x9133`
- name: `Microsoft.Crm.Ribbon.DiffProcessing::ApplyTemplateDiff`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8ec0`

## callees

- `0x90a0`

## string_xrefs

- `0x90a1`: `//Templates/RibbonTemplates`
- `0x90c4`: `GroupTemplate`
- `0x90fd`: `GroupTemplate[@Id="`

## pseudocode

```c

```

## disassembly

```asm
0x90a0  ldarg.0
0x90a1  ldstr    aTemplatesRibbo// "//Templates/RibbonTemplates"
0x90a6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x90ab  stloc.0
0x90ac  ldloc.0
0x90ad  brfalse  loc_9132
0x90b2  ldarg.0
0x90b3  ldstr    aWrapper// "Wrapper"
0x90b8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x90bd  dup
0x90be  ldarg.1
0x90bf  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x90c4  ldstr    aGrouptemplate// "GroupTemplate"
0x90c9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x90ce  stloc.1
0x90cf  ldloc.1
0x90d0  brtrue.s loc_90D5
0x90d2  ldnull
0x90d3  br.s     loc_90F8
0x90d5  ldloc.1
0x90d6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x90db  dup
0x90dc  brtrue.s loc_90E2
0x90de  pop
0x90df  ldnull
0x90e0  br.s     loc_90F8
0x90e2  ldstr    aId_0// "Id"
0x90e7  call     instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x90ec  dup
0x90ed  brtrue.s loc_90F3
0x90ef  pop
0x90f0  ldnull
0x90f1  br.s     loc_90F8
0x90f3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x90f8  stloc.2
0x90f9  ldloc.1
0x90fa  brfalse.s loc_9132
0x90fc  ldloc.0
0x90fd  ldstr    aGrouptemplateI// "GroupTemplate[@Id=\""
0x9102  ldloc.2
0x9103  ldstr    asc_C56F8// "\"]"
0x9108  call     string [mscorlib]System.String::Concat(string, string, string)
0x910d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x9112  stloc.3
0x9113  ldloc.3
0x9114  brtrue.s loc_9124
0x9116  ldloc.0
0x9117  ldloc.1
0x9118  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::Clone()
0x911d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x9122  pop
0x9123  ret
0x9124  ldloc.0
0x9125  ldloc.1
0x9126  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::Clone()
0x912b  ldloc.3
0x912c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::ReplaceChild(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x9131  pop
0x9132  ret
```
