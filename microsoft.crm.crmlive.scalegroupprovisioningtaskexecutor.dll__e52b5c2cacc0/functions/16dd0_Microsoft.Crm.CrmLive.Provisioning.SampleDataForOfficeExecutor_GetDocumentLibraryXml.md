# Microsoft.Crm.CrmLive.Provisioning.SampleDataForOfficeExecutor::GetDocumentLibraryXml

- ea: `0x16dd0`
- end: `0x16e60`
- name: `Microsoft.Crm.CrmLive.Provisioning.SampleDataForOfficeExecutor::GetDocumentLibraryXml`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x169c0`

## callees

- `0x16dd0`

## string_xrefs

- `0x16ddb`: `<SelectedEntitiesXml/>`
- `0x16de8`: `/SelectedEntitiesXml`

## pseudocode

```c

```

## disassembly

```asm
0x16dd0  ldarg.1
0x16dd1  ldstr    aSelectedentiti// "selectedEntities"
0x16dd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x16ddb  ldstr    aSelectedentiti_0// "<SelectedEntitiesXml/>"
0x16de0  ldc.i4.0
0x16de1  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string, bool)
0x16de6  stloc.0
0x16de7  ldloc.0
0x16de8  ldstr    aSelectedentiti_1// "/SelectedEntitiesXml"
0x16ded  ldnull
0x16dee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x16df3  stloc.1
0x16df4  ldarg.1
0x16df5  stloc.3
0x16df6  ldc.i4.0
0x16df7  stloc.s  4
0x16df9  br.s     loc_16E51
0x16dfb  ldloc.3
0x16dfc  ldloc.s  4
0x16dfe  ldelem.ref
0x16dff  stloc.s  5
0x16e01  ldloc.0
0x16e02  ldstr    aEntity// "entity"
0x16e07  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x16e0c  stloc.2
0x16e0d  ldloc.0
0x16e0e  ldstr    aName_0// "name"
0x16e13  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x16e18  stloc.s  6
0x16e1a  ldloc.s  6
0x16e1c  ldloc.s  5
0x16e1e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x16e23  ldloc.2
0x16e24  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x16e29  ldloc.s  6
0x16e2b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::SetNamedItem(class [System.Xml]System.Xml.XmlNode)
0x16e30  pop
0x16e31  ldloc.2
0x16e32  ldloc.0
0x16e33  ldstr    a1// "1"
0x16e38  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x16e3d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x16e42  pop
0x16e43  ldloc.1
0x16e44  ldloc.2
0x16e45  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x16e4a  pop
0x16e4b  ldloc.s  4
0x16e4d  ldc.i4.1
0x16e4e  add
0x16e4f  stloc.s  4
0x16e51  ldloc.s  4
0x16e53  ldloc.3
0x16e54  ldlen
0x16e55  conv.i4
0x16e56  blt.s    loc_16DFB
0x16e58  ldloc.0
0x16e59  ldc.i4.0
0x16e5a  call     T0x2B000084
0x16e5f  ret
```
