# Word2003XmlFileHandler::ProcessForAttachedTemplate

- ea: `0xa4150`
- end: `0xa4213`
- name: `Word2003XmlFileHandler::ProcessForAttachedTemplate`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x47460`
- `0xa3f40`
- `0xa4150`

## string_xrefs

- `0xa4167`: `http://schemas.microsoft.com/office/word/2003/wordml`
- `0xa416d`: `http://schemas.microsoft.com/office/word/2003/auxHint`
- `0xa4150`: `_static/Tools/MailMerge/CRMTemplate.dot`
- `0xa4198`: `//w:attachedTemplate`
- `0xa41aa`: `w:attachedTemplate`

## pseudocode

```c

```

## disassembly

```asm
0xa4150  ldstr    aStaticToolsMai// "_static/Tools/MailMerge/CRMTemplate.dot"
0xa4155  ldc.i4.0
0xa4156  ldarg.0
0xa4157  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext WordXmlFileHandler::get_Context()
0xa415c  call     class [System]System.Uri Microsoft.Crm.Application.Utility.Util::GetAbsoluteUrl(string relativePath, bool prependOrgName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xa4161  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xa4166  stloc.0
0xa4167  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/office/wor"...
0xa416c  stloc.1
0xa416d  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/office/wor"...
0xa4172  stloc.2
0xa4173  ldarg.1
0xa4174  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa4179  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa417e  stloc.3
0xa417f  ldloc.3
0xa4180  ldstr    aW// "w"
0xa4185  ldloc.1
0xa4186  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa418b  ldloc.3
0xa418c  ldstr    aWx// "wx"
0xa4191  ldloc.2
0xa4192  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4197  ldarg.1
0xa4198  ldstr    aWAttachedtempl// "//w:attachedTemplate"
0xa419d  ldloc.3
0xa419e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa41a3  stloc.s  4
0xa41a5  ldloc.s  4
0xa41a7  brtrue.s loc_A41D6
0xa41a9  ldarg.1
0xa41aa  ldstr    aWAttachedtempl_0// "w:attachedTemplate"
0xa41af  ldloc.1
0xa41b0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa41b5  stloc.s  4
0xa41b7  ldarg.1
0xa41b8  ldstr    aWDocpr// "//w:docPr"
0xa41bd  ldloc.3
0xa41be  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa41c3  stloc.s  6
0xa41c5  ldloc.s  6
0xa41c7  ldloc.s  4
0xa41c9  ldloc.s  6
0xa41cb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa41d0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa41d5  pop
0xa41d6  ldloc.s  4
0xa41d8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa41dd  ldstr    aWVal// "w:val"
0xa41e2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa41e7  stloc.s  5
0xa41e9  ldloc.s  5
0xa41eb  brtrue.s loc_A420A
0xa41ed  ldarg.1
0xa41ee  ldstr    aWVal// "w:val"
0xa41f3  ldloc.1
0xa41f4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string, string)
0xa41f9  stloc.s  5
0xa41fb  ldloc.s  4
0xa41fd  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4202  ldloc.s  5
0xa4204  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4209  pop
0xa420a  ldloc.s  5
0xa420c  ldloc.0
0xa420d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4212  ret
```
