# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write992_DeliverPromoteEmailRequest

- ea: `0x4ee60`
- end: `0x4f00d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write992_DeliverPromoteEmailRequest`
- size: `429`
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
- `0x4ee60`

## string_xrefs

- `0x4eea5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eebf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eed5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eefa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ef15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ef2b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ef41`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ef57`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ef6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ef83`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ef99`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4efb1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4efc7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4efdd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eff3`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x4ee60  ldarg.3
0x4ee61  brtrue.s loc_4EE70
0x4ee63  ldarg.s  4
0x4ee65  brfalse.s loc_4EE6F
0x4ee67  ldarg.0
0x4ee68  ldarg.1
0x4ee69  ldarg.2
0x4ee6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4ee6f  ret
0x4ee70  ldarg.s  5
0x4ee72  brtrue.s loc_4EE90
0x4ee74  ldarg.3
0x4ee75  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4ee7a  stloc.0
0x4ee7b  ldloc.0
0x4ee7c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest
0x4ee81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ee86  beq.s    loc_4EE90
0x4ee88  ldarg.0
0x4ee89  ldarg.3
0x4ee8a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4ee8f  throw
0x4ee90  ldarg.0
0x4ee91  ldarg.1
0x4ee92  ldarg.2
0x4ee93  ldarg.3
0x4ee94  ldc.i4.0
0x4ee95  ldnull
0x4ee96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4ee9b  ldarg.s  5
0x4ee9d  brfalse.s loc_4EEAF
0x4ee9f  ldarg.0
0x4eea0  ldstr    aDeliverpromote// "DeliverPromoteEmailRequest"
0x4eea5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eeaa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4eeaf  ldarg.3
0x4eeb0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4eeb5  stloc.1
0x4eeb6  ldloc.1
0x4eeb7  brfalse.s loc_4EEF4
0x4eeb9  ldarg.0
0x4eeba  ldstr    aOptionalparame_0// "OptionalParameters"
0x4eebf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eec4  ldnull
0x4eec5  ldc.i4.0
0x4eec6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4eecb  ldc.i4.0
0x4eecc  stloc.2
0x4eecd  br.s     loc_4EEE8
0x4eecf  ldarg.0
0x4eed0  ldstr    aOptionalparame// "OptionalParameter"
0x4eed5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eeda  ldloc.1
0x4eedb  ldloc.2
0x4eedc  ldelem.ref
0x4eedd  ldc.i4.1
0x4eede  ldc.i4.0
0x4eedf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4eee4  ldloc.2
0x4eee5  ldc.i4.1
0x4eee6  add
0x4eee7  stloc.2
0x4eee8  ldloc.2
0x4eee9  ldloc.1
0x4eeea  ldlen
0x4eeeb  conv.i4
0x4eeec  blt.s    loc_4EECF
0x4eeee  ldarg.0
0x4eeef  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4eef4  ldarg.0
0x4eef5  ldstr    aEmailid// "EmailId"
0x4eefa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eeff  ldarg.3
0x4ef00  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_EmailId()
0x4ef05  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4ef0a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4ef0f  ldarg.0
0x4ef10  ldstr    aMessageid_0// "MessageId"
0x4ef15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ef1a  ldarg.3
0x4ef1b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_MessageId()
0x4ef20  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4ef25  ldarg.0
0x4ef26  ldstr    aSubject_0// "Subject"
0x4ef2b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ef30  ldarg.3
0x4ef31  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_Subject()
0x4ef36  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4ef3b  ldarg.0
0x4ef3c  ldstr    aFrom// "From"
0x4ef41  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ef46  ldarg.3
0x4ef47  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_From()
0x4ef4c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4ef51  ldarg.0
0x4ef52  ldstr    aTo// "To"
0x4ef57  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ef5c  ldarg.3
0x4ef5d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_To()
0x4ef62  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4ef67  ldarg.0
0x4ef68  ldstr    aCc_0// "Cc"
0x4ef6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ef72  ldarg.3
0x4ef73  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_Cc()
0x4ef78  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4ef7d  ldarg.0
0x4ef7e  ldstr    aBcc_0// "Bcc"
0x4ef83  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ef88  ldarg.3
0x4ef89  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_Bcc()
0x4ef8e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4ef93  ldarg.0
0x4ef94  ldstr    aReceivedon_0// "ReceivedOn"
0x4ef99  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ef9e  ldarg.3
0x4ef9f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_ReceivedOn()
0x4efa4  ldc.i4.0
0x4efa5  ldc.i4.0
0x4efa6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x4efab  ldarg.0
0x4efac  ldstr    aSubmittedby_0// "SubmittedBy"
0x4efb1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4efb6  ldarg.3
0x4efb7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_SubmittedBy()
0x4efbc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4efc1  ldarg.0
0x4efc2  ldstr    aImportance// "Importance"
0x4efc7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4efcc  ldarg.3
0x4efcd  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_Importance()
0x4efd2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4efd7  ldarg.0
0x4efd8  ldstr    aBody_0// "Body"
0x4efdd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4efe2  ldarg.3
0x4efe3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_Body()
0x4efe8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4efed  ldarg.0
0x4efee  ldstr    aAttachments// "Attachments"
0x4eff3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eff8  ldarg.3
0x4eff9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DeliverPromoteEmailRequest::get_Attachments()
0x4effe  ldc.i4.0
0x4efff  ldc.i4.0
0x4f000  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write179_BusinessEntityCollection(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection o, bool isNullable, bool needType)
0x4f005  ldarg.0
0x4f006  ldarg.3
0x4f007  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4f00c  ret
```
