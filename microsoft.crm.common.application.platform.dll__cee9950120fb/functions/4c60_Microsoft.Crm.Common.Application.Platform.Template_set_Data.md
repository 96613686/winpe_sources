# Microsoft.Crm.Common.Application.Platform.Template::set_Data

- ea: `0x4c60`
- end: `0x4d5a`
- name: `Microsoft.Crm.Common.Application.Platform.Template::set_Data`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4bf0`
- `0x4c60`
- `0x4d60`

## string_xrefs

- `0x4c84`: `/template/html`
- `0x4cca`: `/template/subjecthtml`
- `0x4d25`: `presentationxml`
- `0x4d41`: `subjectpresentationxml`

## pseudocode

```c

```

## disassembly

```asm
0x4c60  ldnull
0x4c61  stloc.0
0x4c62  ldnull
0x4c63  dup
0x4c64  stloc.s  4
0x4c66  dup
0x4c67  stloc.3
0x4c68  dup
0x4c69  stloc.2
0x4c6a  stloc.1
0x4c6b  ldarg.1
0x4c6c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4c71  stloc.s  5
0x4c73  ldarg.1
0x4c74  ldstr    aHtml// "<html"
0x4c79  ldc.i4.4
0x4c7a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4c7f  ldc.i4.m1
0x4c80  beq.s    loc_4CB6
0x4c82  ldloc.s  5
0x4c84  ldstr    aTemplateHtml// "/template/html"
0x4c89  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4c8e  stloc.s  7
0x4c90  ldloc.s  7
0x4c92  brfalse.s loc_4CB6
0x4c94  ldloc.s  5
0x4c96  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4c9b  ldloc.s  7
0x4c9d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x4ca2  pop
0x4ca3  ldloc.s  7
0x4ca5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4caa  stloc.0
0x4cab  ldarg.0
0x4cac  ldloc.0
0x4cad  ldloca.s 1
0x4caf  ldloca.s 2
0x4cb1  call     instance void Microsoft.Crm.Common.Application.Platform.Template::HtmlToXmlAndXsl(string html, string& xml, string& xsl)
0x4cb6  ldnull
0x4cb7  stloc.s  6
0x4cb9  ldarg.1
0x4cba  ldstr    aSubjecthtml// "<subjecthtml"
0x4cbf  ldc.i4.4
0x4cc0  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4cc5  ldc.i4.m1
0x4cc6  beq.s    loc_4D0C
0x4cc8  ldloc.s  5
0x4cca  ldstr    aTemplateSubjec// "/template/subjecthtml"
0x4ccf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4cd4  stloc.s  8
0x4cd6  ldloc.s  8
0x4cd8  brfalse.s loc_4D0C
0x4cda  ldloc.s  5
0x4cdc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4ce1  ldloc.s  8
0x4ce3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x4ce8  pop
0x4ce9  ldloc.s  8
0x4ceb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4cf0  stloc.s  6
0x4cf2  ldarg.0
0x4cf3  ldloc.s  6
0x4cf5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x4cfa  ldloca.s 3
0x4cfc  ldloca.s 4
0x4cfe  call     instance void Microsoft.Crm.Common.Application.Platform.Template::HtmlToXmlAndXsl(string html, string& xml, string& xsl)
0x4d03  ldarg.0
0x4d04  ldloc.s  6
0x4d06  call     instance string Microsoft.Crm.Common.Application.Platform.Template::ParseHtml(string html)
0x4d0b  stloc.3
0x4d0c  ldloc.s  5
0x4d0e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x4d13  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x4d18  starg.s  1
0x4d1a  ldarg.0
0x4d1b  ldarg.1
0x4d1c  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x4d21  ldloc.0
0x4d22  brfalse.s loc_4D3C
0x4d24  ldarg.0
0x4d25  ldstr    aPresentationxm// "presentationxml"
0x4d2a  ldloc.1
0x4d2b  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4d30  ldarg.0
0x4d31  ldstr    aBody// "body"
0x4d36  ldloc.2
0x4d37  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4d3c  ldloc.s  6
0x4d3e  brfalse.s loc_4D59
0x4d40  ldarg.0
0x4d41  ldstr    aSubjectpresent// "subjectpresentationxml"
0x4d46  ldloc.3
0x4d47  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4d4c  ldarg.0
0x4d4d  ldstr    aSubject// "subject"
0x4d52  ldloc.s  4
0x4d54  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4d59  ret
```
