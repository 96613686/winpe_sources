# Microsoft.Crm.Common.Application.Platform.Template::ParseHtml

- ea: `0x4d60`
- end: `0x4e90`
- name: `Microsoft.Crm.Common.Application.Platform.Template::ParseHtml`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4bf0`
- `0x4c60`

## callees

- `0x4d60`
- `0x4e90`
- `0x4fb0`
- `0x5050`

## string_xrefs

- `0x4d74`: `template`

## pseudocode

```c

```

## disassembly

```asm
0x4d60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d65  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x4d6a  stloc.0
0x4d6b  ldloc.0
0x4d6c  ldc.i4.0
0x4d6d  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x4d72  stloc.1
0x4d73  ldloc.1
0x4d74  ldstr    aTemplate// "template"
0x4d79  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4d7e  ldc.i4.0
0x4d7f  stloc.2
0x4d80  ldstr    asc_A29E// "{!"
0x4d85  call     instance int32 [mscorlib]System.String::get_Length()
0x4d8a  stloc.s  6
0x4d8c  br       loc_4E5B
0x4d91  ldc.i4.m1
0x4d92  stloc.3
0x4d93  ldc.i4.m1
0x4d94  stloc.s  4
0x4d96  ldarg.1
0x4d97  ldstr    asc_A29E// "{!"
0x4d9c  ldloc.2
0x4d9d  ldc.i4.4
0x4d9e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0x4da3  stloc.3
0x4da4  ldloc.3
0x4da5  ldc.i4.m1
0x4da6  ble      loc_4E4B
0x4dab  ldarg.0
0x4dac  ldloc.1
0x4dad  ldarg.1
0x4dae  ldloc.2
0x4daf  ldloc.3
0x4db0  ldloc.2
0x4db1  sub
0x4db2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4db7  call     instance void Microsoft.Crm.Common.Application.Platform.Template::WriteText(class [System.Xml]System.Xml.XmlWriter writer, string text)
0x4dbc  ldarg.1
0x4dbd  ldstr    asc_882A// "}"
0x4dc2  ldloc.3
0x4dc3  ldc.i4.4
0x4dc4  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0x4dc9  stloc.s  4
0x4dcb  ldarg.1
0x4dcc  ldstr    asc_A29E// "{!"
0x4dd1  ldloc.3
0x4dd2  ldc.i4.1
0x4dd3  add
0x4dd4  ldc.i4.4
0x4dd5  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0x4dda  stloc.s  5
0x4ddc  ldloc.s  5
0x4dde  ldc.i4.m1
0x4ddf  beq.s    loc_4DE7
0x4de1  ldloc.s  5
0x4de3  ldloc.s  4
0x4de5  blt.s    loc_4DEC
0x4de7  ldloc.s  4
0x4de9  ldc.i4.m1
0x4dea  bne.un.s loc_4E03
0x4dec  ldarg.0
0x4ded  ldloc.1
0x4dee  ldarg.1
0x4def  ldloc.3
0x4df0  ldloc.s  6
0x4df2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4df7  call     instance void Microsoft.Crm.Common.Application.Platform.Template::WriteText(class [System.Xml]System.Xml.XmlWriter writer, string text)
0x4dfc  ldloc.3
0x4dfd  ldloc.s  6
0x4dff  add
0x4e00  stloc.2
0x4e01  br.s     loc_4E5B
0x4e03  ldarg.1
0x4e04  ldloc.3
0x4e05  ldloc.s  6
0x4e07  add
0x4e08  ldloc.s  4
0x4e0a  ldloc.3
0x4e0b  sub
0x4e0c  ldloc.s  6
0x4e0e  sub
0x4e0f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4e14  stloc.s  7
0x4e16  ldnull
0x4e17  stloc.s  8
0x4e19  ldarg.0
0x4e1a  ldloc.s  7
0x4e1c  ldloca.s 8
0x4e1e  call     instance bool Microsoft.Crm.Common.Application.Platform.Template::ParseSlug(string slug, [out] class [mscorlib]System.Collections.Generic.List`1<string>& slugParts)
0x4e23  brfalse.s loc_4E30
0x4e25  ldarg.0
0x4e26  ldloc.1
0x4e27  ldloc.s  8
0x4e29  call     instance void Microsoft.Crm.Common.Application.Platform.Template::AppendSlug(class [System.Xml]System.Xml.XmlWriter writer, class [mscorlib]System.Collections.Generic.List`1<string> slugParts)
0x4e2e  br.s     loc_4E44
0x4e30  ldarg.0
0x4e31  ldloc.1
0x4e32  ldarg.1
0x4e33  ldloc.3
0x4e34  ldloc.s  4
0x4e36  ldloc.3
0x4e37  sub
0x4e38  ldc.i4.1
0x4e39  add
0x4e3a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4e3f  call     instance void Microsoft.Crm.Common.Application.Platform.Template::WriteText(class [System.Xml]System.Xml.XmlWriter writer, string text)
0x4e44  ldloc.s  4
0x4e46  ldc.i4.1
0x4e47  add
0x4e48  stloc.2
0x4e49  br.s     loc_4E5B
0x4e4b  ldarg.0
0x4e4c  ldloc.1
0x4e4d  ldarg.1
0x4e4e  ldloc.2
0x4e4f  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4e54  call     instance void Microsoft.Crm.Common.Application.Platform.Template::WriteText(class [System.Xml]System.Xml.XmlWriter writer, string text)
0x4e59  br.s     loc_4E67
0x4e5b  ldloc.2
0x4e5c  ldarg.1
0x4e5d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4e62  blt      loc_4D91
0x4e67  ldloc.1
0x4e68  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4e6d  leave.s  loc_4E79
0x4e6f  ldloc.1
0x4e70  brfalse.s loc_4E78
0x4e72  ldloc.1
0x4e73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e78  endfinally
0x4e79  ldloc.0
0x4e7a  callvirt instance string [mscorlib]System.Object::ToString()
0x4e7f  stloc.s  9
0x4e81  leave.s  loc_4E8D
0x4e83  ldloc.0
0x4e84  brfalse.s loc_4E8C
0x4e86  ldloc.0
0x4e87  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e8c  endfinally
0x4e8d  ldloc.s  9
0x4e8f  ret
```
