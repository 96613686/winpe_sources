# Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::PresentationXMLToHTML

- ea: `0x9750`
- end: `0x979d`
- name: `Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::PresentationXMLToHTML`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x96c0`
- `0x9710`

## string_xrefs

- `0x9757`: `emailTemplateEditor.xsl`

## pseudocode

```c

```

## disassembly

```asm
0x9750  ldarg.1
0x9751  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x9756  stloc.0
0x9757  ldstr    aEmailtemplatee// "emailTemplateEditor.xsl"
0x975c  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0x9761  stloc.1
0x9762  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x9767  dup
0x9768  ldloc.1
0x9769  ldnull
0x976a  ldnull
0x976b  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltSettings, class [System.Xml]System.Xml.XmlResolver)
0x9770  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9775  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x977a  stloc.2
0x977b  ldloc.0
0x977c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x9781  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x9786  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x978b  ldnull
0x978c  ldloc.2
0x978d  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [mscorlib]System.IO.TextWriter)
0x9792  ldarg.2
0x9793  ldloc.2
0x9794  callvirt instance string [mscorlib]System.Object::ToString()
0x9799  stind.ref
0x979a  ldarg.2
0x979b  ldind.ref
0x979c  ret
```
