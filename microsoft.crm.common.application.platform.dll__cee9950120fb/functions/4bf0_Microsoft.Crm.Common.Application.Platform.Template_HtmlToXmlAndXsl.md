# Microsoft.Crm.Common.Application.Platform.Template::HtmlToXmlAndXsl

- ea: `0x4bf0`
- end: `0x4c41`
- name: `Microsoft.Crm.Common.Application.Platform.Template::HtmlToXmlAndXsl`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4c60`

## callees

- `0x4d60`

## pseudocode

```c

```

## disassembly

```asm
0x4bf0  ldarg.1
0x4bf1  call     string [Microsoft.Crm.SafeHtml]Microsoft.Crm.SafeHtml::GetSafeHtml(string)
0x4bf6  starg.s  1
0x4bf8  ldarg.2
0x4bf9  ldarg.0
0x4bfa  ldarg.1
0x4bfb  call     instance string Microsoft.Crm.Common.Application.Platform.Template::ParseHtml(string html)
0x4c00  stind.ref
0x4c01  ldstr    aMetamorphicxsl// "metamorphicXslEmailSend.xsl"
0x4c06  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0x4c0b  stloc.0
0x4c0c  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x4c11  dup
0x4c12  ldloc.0
0x4c13  ldnull
0x4c14  ldnull
0x4c15  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltSettings, class [System.Xml]System.Xml.XmlResolver)
0x4c1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c1f  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x4c24  stloc.1
0x4c25  ldarg.2
0x4c26  ldind.ref
0x4c27  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x4c2c  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x4c31  ldnull
0x4c32  ldloc.1
0x4c33  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [mscorlib]System.IO.TextWriter)
0x4c38  ldarg.3
0x4c39  ldloc.1
0x4c3a  callvirt instance string [mscorlib]System.Object::ToString()
0x4c3f  stind.ref
0x4c40  ret
```
