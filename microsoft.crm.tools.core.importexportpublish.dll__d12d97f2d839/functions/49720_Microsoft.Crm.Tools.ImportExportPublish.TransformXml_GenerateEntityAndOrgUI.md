# Microsoft.Crm.Tools.ImportExportPublish.TransformXml::GenerateEntityAndOrgUI

- ea: `0x49720`
- end: `0x497d8`
- name: `Microsoft.Crm.Tools.ImportExportPublish.TransformXml::GenerateEntityAndOrgUI`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x496a0`

## callees

- `0x49720`

## string_xrefs

- `0x49768`: `FormXml`
- `0x49777`: `FormXml`
- `0x4979e`: `FieldXml`
- `0x497ad`: `FieldXml`

## pseudocode

```c

```

## disassembly

```asm
0x49720  ldarg.2
0x49721  ldstr    aEntity_0// "Entity"
0x49726  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4972b  stloc.0
0x4972c  ldc.i4.0
0x4972d  stloc.1
0x4972e  ldarg.1
0x4972f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x49734  ldstr    aOtc// "OTC"
0x49739  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4973e  stloc.2
0x4973f  ldloc.2
0x49740  brfalse.s loc_49767
0x49742  ldarg.2
0x49743  ldstr    aObjecttypecode// "ObjectTypeCode"
0x49748  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x4974d  stloc.s  4
0x4974f  ldloc.s  4
0x49751  ldloc.2
0x49752  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x49757  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x4975c  ldloc.0
0x4975d  ldloc.s  4
0x4975f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x49764  pop
0x49765  ldc.i4.1
0x49766  stloc.1
0x49767  ldarg.1
0x49768  ldstr    aFormxml// "FormXml"
0x4976d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x49772  stloc.3
0x49773  ldloc.3
0x49774  brfalse.s loc_4979B
0x49776  ldarg.2
0x49777  ldstr    aFormxml// "FormXml"
0x4977c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x49781  stloc.s  5
0x49783  ldloc.s  5
0x49785  ldloc.3
0x49786  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x4978b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x49790  ldloc.0
0x49791  ldloc.s  5
0x49793  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x49798  pop
0x49799  ldc.i4.1
0x4979a  stloc.1
0x4979b  ldnull
0x4979c  stloc.3
0x4979d  ldarg.1
0x4979e  ldstr    aFieldxml_0// "FieldXml"
0x497a3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x497a8  stloc.3
0x497a9  ldloc.3
0x497aa  brfalse.s loc_497D1
0x497ac  ldarg.2
0x497ad  ldstr    aFieldxml_0// "FieldXml"
0x497b2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x497b7  stloc.s  6
0x497b9  ldloc.s  6
0x497bb  ldloc.3
0x497bc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x497c1  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x497c6  ldloc.0
0x497c7  ldloc.s  6
0x497c9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x497ce  pop
0x497cf  ldc.i4.1
0x497d0  stloc.1
0x497d1  ldloc.1
0x497d2  brfalse.s loc_497D6
0x497d4  ldloc.0
0x497d5  ret
0x497d6  ldnull
0x497d7  ret
```
