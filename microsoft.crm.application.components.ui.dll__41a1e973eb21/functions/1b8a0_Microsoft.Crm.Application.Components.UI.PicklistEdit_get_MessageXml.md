# Microsoft.Crm.Application.Components.UI.PicklistEdit::get_MessageXml

- ea: `0x1b8a0`
- end: `0x1b918`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::get_MessageXml`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bd00`

## callees

- `0x1b8a0`
- `0x1bc60`
- `0x1bc80`
- `0x1bca0`

## string_xrefs

- `0x1b8c7`: `deletevalue`

## pseudocode

```c

```

## disassembly

```asm
0x1b8a0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1b8a5  stloc.0
0x1b8a6  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1b8ab  stloc.1
0x1b8ac  ldloc.1
0x1b8ad  ldc.i4.1
0x1b8ae  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x1b8b3  ldloc.0
0x1b8b4  ldloc.1
0x1b8b5  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x1b8ba  stloc.2
0x1b8bb  ldloc.2
0x1b8bc  ldstr    aMessages// "messages"
0x1b8c1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1b8c6  ldloc.2
0x1b8c7  ldstr    aDeletevalue// "deletevalue"
0x1b8cc  ldarg.0
0x1b8cd  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_DeleteValueMessage()
0x1b8d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1b8d7  ldloc.2
0x1b8d8  ldstr    aSavechangedval// "savechangedvalue"
0x1b8dd  ldarg.0
0x1b8de  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_SaveChangedValueMessage()
0x1b8e3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1b8e8  ldloc.2
0x1b8e9  ldstr    aValuechangedwi// "valuechangedwithoutprefix"
0x1b8ee  ldarg.0
0x1b8ef  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_ValueChangedWithoutPrefix()
0x1b8f4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1b8f9  ldloc.2
0x1b8fa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1b8ff  ldloc.2
0x1b900  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1b905  leave.s  loc_1B911
0x1b907  ldloc.2
0x1b908  brfalse.s loc_1B910
0x1b90a  ldloc.2
0x1b90b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b910  endfinally
0x1b911  ldloc.0
0x1b912  callvirt instance string [mscorlib]System.Object::ToString()
0x1b917  ret
```
