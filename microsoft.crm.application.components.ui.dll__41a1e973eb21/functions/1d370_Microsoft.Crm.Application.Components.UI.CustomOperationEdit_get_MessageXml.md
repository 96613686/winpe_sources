# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_MessageXml

- ea: `0x1d370`
- end: `0x1d3ee`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_MessageXml`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d7b0`

## callees

- `0x1d370`
- `0x1d710`
- `0x1d730`
- `0x1d750`

## string_xrefs

- `0x1d38f`: `deletevalue`

## pseudocode

```c

```

## disassembly

```asm
0x1d370  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d375  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x1d37a  stloc.0
0x1d37b  ldloc.0
0x1d37c  ldc.i4.1
0x1d37d  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x1d382  stloc.1
0x1d383  ldloc.1
0x1d384  ldstr    aMessages// "messages"
0x1d389  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1d38e  ldloc.1
0x1d38f  ldstr    aDeletevalue// "deletevalue"
0x1d394  ldarg.0
0x1d395  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_DeleteValueMessage()
0x1d39a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1d39f  ldloc.1
0x1d3a0  ldstr    aSavechangedval// "savechangedvalue"
0x1d3a5  ldarg.0
0x1d3a6  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_SaveChangedValueMessage()
0x1d3ab  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1d3b0  ldloc.1
0x1d3b1  ldstr    aValuechangedwi// "valuechangedwithoutprefix"
0x1d3b6  ldarg.0
0x1d3b7  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_ValueChangedWithoutPrefix()
0x1d3bc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1d3c1  ldloc.1
0x1d3c2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1d3c7  ldloc.1
0x1d3c8  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1d3cd  leave.s  loc_1D3D9
0x1d3cf  ldloc.1
0x1d3d0  brfalse.s loc_1D3D8
0x1d3d2  ldloc.1
0x1d3d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d3d8  endfinally
0x1d3d9  ldloc.0
0x1d3da  callvirt instance string [mscorlib]System.Object::ToString()
0x1d3df  stloc.2
0x1d3e0  leave.s  loc_1D3EC
0x1d3e2  ldloc.0
0x1d3e3  brfalse.s loc_1D3EB
0x1d3e5  ldloc.0
0x1d3e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d3eb  endfinally
0x1d3ec  ldloc.2
0x1d3ed  ret
```
