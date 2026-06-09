# Microsoft.Crm.Application.Components.UI.ListEdit::get_MessageXml

- ea: `0x1aa80`
- end: `0x1aaf8`
- name: `Microsoft.Crm.Application.Components.UI.ListEdit::get_MessageXml`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1ad90`

## callees

- `0x1aa80`
- `0x1acf0`
- `0x1ad10`
- `0x1ad30`

## string_xrefs

- `0x1aaa7`: `deletevalue`

## pseudocode

```c

```

## disassembly

```asm
0x1aa80  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1aa85  stloc.0
0x1aa86  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1aa8b  stloc.1
0x1aa8c  ldloc.1
0x1aa8d  ldc.i4.1
0x1aa8e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x1aa93  ldloc.0
0x1aa94  ldloc.1
0x1aa95  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x1aa9a  stloc.2
0x1aa9b  ldloc.2
0x1aa9c  ldstr    aMessages// "messages"
0x1aaa1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1aaa6  ldloc.2
0x1aaa7  ldstr    aDeletevalue// "deletevalue"
0x1aaac  ldarg.0
0x1aaad  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_DeleteValueMessage()
0x1aab2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1aab7  ldloc.2
0x1aab8  ldstr    aSavechangedval// "savechangedvalue"
0x1aabd  ldarg.0
0x1aabe  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_SaveChangedValueMessage()
0x1aac3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1aac8  ldloc.2
0x1aac9  ldstr    aValuechangedwi// "valuechangedwithoutprefix"
0x1aace  ldarg.0
0x1aacf  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_ValueChangedWithoutPrefix()
0x1aad4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1aad9  ldloc.2
0x1aada  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1aadf  ldloc.2
0x1aae0  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1aae5  leave.s  loc_1AAF1
0x1aae7  ldloc.2
0x1aae8  brfalse.s loc_1AAF0
0x1aaea  ldloc.2
0x1aaeb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1aaf0  endfinally
0x1aaf1  ldloc.0
0x1aaf2  callvirt instance string [mscorlib]System.Object::ToString()
0x1aaf7  ret
```
