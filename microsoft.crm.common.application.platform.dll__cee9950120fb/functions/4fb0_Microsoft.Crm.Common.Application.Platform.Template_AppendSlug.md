# Microsoft.Crm.Common.Application.Platform.Template::AppendSlug

- ea: `0x4fb0`
- end: `0x5044`
- name: `Microsoft.Crm.Common.Application.Platform.Template::AppendSlug`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d60`

## callees

- `0x4fb0`

## pseudocode

```c

```

## disassembly

```asm
0x4fb0  ldarg.1
0x4fb1  ldstr    aSlugs// "slugs"
0x4fb6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fbb  ldc.i4.0
0x4fbc  stloc.0
0x4fbd  br.s     loc_5014
0x4fbf  ldarg.1
0x4fc0  ldstr    aSlug// "slug"
0x4fc5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fca  ldarg.1
0x4fcb  ldstr    aEntity// "entity"
0x4fd0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fd5  ldarg.1
0x4fd6  ldarg.2
0x4fd7  ldloc.0
0x4fd8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x4fdd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x4fe2  ldarg.1
0x4fe3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fe8  ldloc.0
0x4fe9  ldc.i4.1
0x4fea  add
0x4feb  stloc.0
0x4fec  ldarg.1
0x4fed  ldstr    aAttribute// "attribute"
0x4ff2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4ff7  ldarg.1
0x4ff8  ldarg.2
0x4ff9  ldloc.0
0x4ffa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x4fff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x5004  ldarg.1
0x5005  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x500a  ldarg.1
0x500b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5010  ldloc.0
0x5011  ldc.i4.1
0x5012  add
0x5013  stloc.0
0x5014  ldloc.0
0x5015  ldarg.2
0x5016  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x501b  ldc.i4.1
0x501c  sub
0x501d  blt.s    loc_4FBF
0x501f  ldarg.1
0x5020  ldstr    aDefault// "default"
0x5025  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x502a  ldarg.1
0x502b  ldarg.2
0x502c  ldloc.0
0x502d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x5032  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x5037  ldarg.1
0x5038  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x503d  ldarg.1
0x503e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5043  ret
```
