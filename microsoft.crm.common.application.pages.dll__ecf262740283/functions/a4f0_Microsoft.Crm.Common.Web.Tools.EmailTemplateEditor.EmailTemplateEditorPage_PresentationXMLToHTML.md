# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::PresentationXMLToHTML

- ea: `0xa4f0`
- end: `0xa547`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::PresentationXMLToHTML`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa2c0`

## callees

- `0xa330`

## string_xrefs

- `0xa4fe`: `emailTemplateEditor.xsl`

## pseudocode

```c

```

## disassembly

```asm
0xa4f0  ldarg.1
0xa4f1  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xa4f6  stloc.0
0xa4f7  ldarg.0
0xa4f8  ldloc.0
0xa4f9  call     instance void Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ApplyDisplayNames(class [System.Xml]System.Xml.XmlDocument presentationXml)
0xa4fe  ldstr    aEmailtemplatee// "emailTemplateEditor.xsl"
0xa503  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0xa508  stloc.1
0xa509  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0xa50e  dup
0xa50f  ldloc.1
0xa510  ldnull
0xa511  ldnull
0xa512  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltSettings, class [System.Xml]System.Xml.XmlResolver)
0xa517  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa51c  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xa521  stloc.2
0xa522  ldloc.0
0xa523  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xa528  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xa52d  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0xa532  ldnull
0xa533  ldloc.2
0xa534  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [mscorlib]System.IO.TextWriter)
0xa539  ldarg.2
0xa53a  ldloc.2
0xa53b  callvirt instance string [mscorlib]System.Object::ToString()
0xa540  call     string [Microsoft.Crm.SafeHtml]Microsoft.Crm.SafeHtml::GetSafeHtml(string)
0xa545  stind.ref
0xa546  ret
```
