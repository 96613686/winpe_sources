# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1268_CheckIncomingEmailRequest

- ea: `0x59170`
- end: `0x59290`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1268_CheckIncomingEmailRequest`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x59170`

## string_xrefs

- `0x591b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x591cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x591e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5920a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59220`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59236`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5924c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59262`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59278`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x591b0`: `CheckIncomingEmailRequest`

## pseudocode

```c

```

## disassembly

```asm
0x59170  ldarg.3
0x59171  brtrue.s loc_59180
0x59173  ldarg.s  4
0x59175  brfalse.s loc_5917F
0x59177  ldarg.0
0x59178  ldarg.1
0x59179  ldarg.2
0x5917a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5917f  ret
0x59180  ldarg.s  5
0x59182  brtrue.s loc_591A0
0x59184  ldarg.3
0x59185  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5918a  stloc.0
0x5918b  ldloc.0
0x5918c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckIncomingEmailRequest
0x59191  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x59196  beq.s    loc_591A0
0x59198  ldarg.0
0x59199  ldarg.3
0x5919a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x5919f  throw
0x591a0  ldarg.0
0x591a1  ldarg.1
0x591a2  ldarg.2
0x591a3  ldarg.3
0x591a4  ldc.i4.0
0x591a5  ldnull
0x591a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x591ab  ldarg.s  5
0x591ad  brfalse.s loc_591BF
0x591af  ldarg.0
0x591b0  ldstr    aCheckincominge// "CheckIncomingEmailRequest"
0x591b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x591ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x591bf  ldarg.3
0x591c0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x591c5  stloc.1
0x591c6  ldloc.1
0x591c7  brfalse.s loc_59204
0x591c9  ldarg.0
0x591ca  ldstr    aOptionalparame_0// "OptionalParameters"
0x591cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x591d4  ldnull
0x591d5  ldc.i4.0
0x591d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x591db  ldc.i4.0
0x591dc  stloc.2
0x591dd  br.s     loc_591F8
0x591df  ldarg.0
0x591e0  ldstr    aOptionalparame// "OptionalParameter"
0x591e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x591ea  ldloc.1
0x591eb  ldloc.2
0x591ec  ldelem.ref
0x591ed  ldc.i4.1
0x591ee  ldc.i4.0
0x591ef  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x591f4  ldloc.2
0x591f5  ldc.i4.1
0x591f6  add
0x591f7  stloc.2
0x591f8  ldloc.2
0x591f9  ldloc.1
0x591fa  ldlen
0x591fb  conv.i4
0x591fc  blt.s    loc_591DF
0x591fe  ldarg.0
0x591ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59204  ldarg.0
0x59205  ldstr    aMessageid_0// "MessageId"
0x5920a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5920f  ldarg.3
0x59210  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckIncomingEmailRequest::get_MessageId()
0x59215  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5921a  ldarg.0
0x5921b  ldstr    aSubject_0// "Subject"
0x59220  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59225  ldarg.3
0x59226  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckIncomingEmailRequest::get_Subject()
0x5922b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x59230  ldarg.0
0x59231  ldstr    aFrom// "From"
0x59236  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5923b  ldarg.3
0x5923c  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckIncomingEmailRequest::get_From()
0x59241  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x59246  ldarg.0
0x59247  ldstr    aTo// "To"
0x5924c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59251  ldarg.3
0x59252  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckIncomingEmailRequest::get_To()
0x59257  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5925c  ldarg.0
0x5925d  ldstr    aCc_0// "Cc"
0x59262  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59267  ldarg.3
0x59268  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckIncomingEmailRequest::get_Cc()
0x5926d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x59272  ldarg.0
0x59273  ldstr    aBcc_0// "Bcc"
0x59278  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5927d  ldarg.3
0x5927e  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckIncomingEmailRequest::get_Bcc()
0x59283  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x59288  ldarg.0
0x59289  ldarg.3
0x5928a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x5928f  ret
```
