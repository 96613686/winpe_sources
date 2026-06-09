# Microsoft.Crm.XmlStringParameterAttribute::CreateXmlDocument

- ea: `0x19e0`
- end: `0x1a46`
- name: `Microsoft.Crm.XmlStringParameterAttribute::CreateXmlDocument`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19a0`

## callees

- `0x19e0`

## pseudocode

```c

```

## disassembly

```asm
0x19e0  ldarg.1
0x19e1  brfalse.s loc_19EB
0x19e3  ldarg.1
0x19e4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x19e9  brtrue.s loc_19F8
0x19eb  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x19f0  dup
0x19f1  ldnull
0x19f2  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x19f7  ret
0x19f8  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x19fd  stloc.0
0x19fe  ldloc.0
0x19ff  ldc.i4.1
0x1a00  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreWhitespace(bool)
0x1a05  ldarg.1
0x1a06  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x1a0b  stloc.1
0x1a0c  ldloc.1
0x1a0d  ldloc.0
0x1a0e  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x1a13  stloc.2
0x1a14  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1a19  dup
0x1a1a  ldnull
0x1a1b  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x1a20  dup
0x1a21  ldloc.2
0x1a22  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x1a27  ldloc.1
0x1a28  callvirt instance void [mscorlib]System.IO.TextReader::Close()
0x1a2d  stloc.3
0x1a2e  leave.s  loc_1A44
0x1a30  ldloc.2
0x1a31  brfalse.s loc_1A39
0x1a33  ldloc.2
0x1a34  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a39  endfinally
0x1a3a  ldloc.1
0x1a3b  brfalse.s loc_1A43
0x1a3d  ldloc.1
0x1a3e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a43  endfinally
0x1a44  ldloc.3
0x1a45  ret
```
