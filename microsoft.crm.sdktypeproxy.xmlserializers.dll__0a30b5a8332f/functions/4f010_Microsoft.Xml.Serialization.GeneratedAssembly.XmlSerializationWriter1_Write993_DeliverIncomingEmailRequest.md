# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write993_DeliverIncomingEmailRequest

- ea: `0x4f010`
- end: `0x4f1a2`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write993_DeliverIncomingEmailRequest`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x5cf0`
- `0x2fdf0`
- `0x346f0`
- `0x4f010`

## string_xrefs

- `0x4f055`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f06f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f085`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f0aa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f0c0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f0d6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f0ec`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f102`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f118`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f12e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f146`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f15c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f172`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f188`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4f050`: `DeliverIncomingEmailRequest`

## pseudocode

```c

```

## disassembly

```asm
0x4f010  ldarg.3
0x4f011  brtrue.s loc_4F020
0x4f013  ldarg.s  4
0x4f015  brfalse.s loc_4F01F
0x4f017  ldarg.0
0x4f018  ldarg.1
0x4f019  ldarg.2
0x4f01a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4f01f  ret
0x4f020  ldarg.s  5
0x4f022  brtrue.s loc_4F040
0x4f024  ldarg.3
0x4f025  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4f02a  stloc.0
0x4f02b  ldloc.0
0x4f02c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest
0x4f031  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f036  beq.s    loc_4F040
0x4f038  ldarg.0
0x4f039  ldarg.3
0x4f03a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4f03f  throw
0x4f040  ldarg.0
0x4f041  ldarg.1
0x4f042  ldarg.2
0x4f043  ldarg.3
0x4f044  ldc.i4.0
0x4f045  ldnull
0x4f046  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4f04b  ldarg.s  5
0x4f04d  brfalse.s loc_4F05F
0x4f04f  ldarg.0
0x4f050  ldstr    aDeliverincomin// "DeliverIncomingEmailRequest"
0x4f055  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f05a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4f05f  ldarg.3
0x4f060  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4f065  stloc.1
0x4f066  ldloc.1
0x4f067  brfalse.s loc_4F0A4
0x4f069  ldarg.0
0x4f06a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4f06f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f074  ldnull
0x4f075  ldc.i4.0
0x4f076  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4f07b  ldc.i4.0
0x4f07c  stloc.2
0x4f07d  br.s     loc_4F098
0x4f07f  ldarg.0
0x4f080  ldstr    aOptionalparame// "OptionalParameter"
0x4f085  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f08a  ldloc.1
0x4f08b  ldloc.2
0x4f08c  ldelem.ref
0x4f08d  ldc.i4.1
0x4f08e  ldc.i4.0
0x4f08f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4f094  ldloc.2
0x4f095  ldc.i4.1
0x4f096  add
0x4f097  stloc.2
0x4f098  ldloc.2
0x4f099  ldloc.1
0x4f09a  ldlen
0x4f09b  conv.i4
0x4f09c  blt.s    loc_4F07F
0x4f09e  ldarg.0
0x4f09f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4f0a4  ldarg.0
0x4f0a5  ldstr    aMessageid_0// "MessageId"
0x4f0aa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f0af  ldarg.3
0x4f0b0  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_MessageId()
0x4f0b5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f0ba  ldarg.0
0x4f0bb  ldstr    aSubject_0// "Subject"
0x4f0c0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f0c5  ldarg.3
0x4f0c6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_Subject()
0x4f0cb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f0d0  ldarg.0
0x4f0d1  ldstr    aFrom// "From"
0x4f0d6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f0db  ldarg.3
0x4f0dc  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_From()
0x4f0e1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f0e6  ldarg.0
0x4f0e7  ldstr    aTo// "To"
0x4f0ec  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f0f1  ldarg.3
0x4f0f2  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_To()
0x4f0f7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f0fc  ldarg.0
0x4f0fd  ldstr    aCc_0// "Cc"
0x4f102  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f107  ldarg.3
0x4f108  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_Cc()
0x4f10d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f112  ldarg.0
0x4f113  ldstr    aBcc_0// "Bcc"
0x4f118  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f11d  ldarg.3
0x4f11e  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_Bcc()
0x4f123  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f128  ldarg.0
0x4f129  ldstr    aReceivedon_0// "ReceivedOn"
0x4f12e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f133  ldarg.3
0x4f134  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_ReceivedOn()
0x4f139  ldc.i4.0
0x4f13a  ldc.i4.0
0x4f13b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x4f140  ldarg.0
0x4f141  ldstr    aSubmittedby_0// "SubmittedBy"
0x4f146  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f14b  ldarg.3
0x4f14c  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_SubmittedBy()
0x4f151  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f156  ldarg.0
0x4f157  ldstr    aImportance// "Importance"
0x4f15c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f161  ldarg.3
0x4f162  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_Importance()
0x4f167  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f16c  ldarg.0
0x4f16d  ldstr    aBody_0// "Body"
0x4f172  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f177  ldarg.3
0x4f178  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_Body()
0x4f17d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4f182  ldarg.0
0x4f183  ldstr    aAttachments// "Attachments"
0x4f188  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4f18d  ldarg.3
0x4f18e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverIncomingEmailRequest::get_Attachments()
0x4f193  ldc.i4.0
0x4f194  ldc.i4.0
0x4f195  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x4f19a  ldarg.0
0x4f19b  ldarg.3
0x4f19c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4f1a1  ret
```
