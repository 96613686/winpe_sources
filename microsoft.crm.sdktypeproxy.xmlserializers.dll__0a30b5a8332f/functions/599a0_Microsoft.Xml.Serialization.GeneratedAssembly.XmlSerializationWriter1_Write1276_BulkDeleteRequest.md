# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1276_BulkDeleteRequest

- ea: `0x599a0`
- end: `0x59b99`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1276_BulkDeleteRequest`
- size: `505`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x5cf0`
- `0x6600`
- `0x2fdf0`
- `0x599a0`

## string_xrefs

- `0x599e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x599ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59a15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59a44`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59a5b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59a84`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59a9a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59ac1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59ad8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59b1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59b32`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59b69`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59b7f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x599e0`: `BulkDeleteRequest`

## pseudocode

```c

```

## disassembly

```asm
0x599a0  ldarg.3
0x599a1  brtrue.s loc_599B0
0x599a3  ldarg.s  4
0x599a5  brfalse.s loc_599AF
0x599a7  ldarg.0
0x599a8  ldarg.1
0x599a9  ldarg.2
0x599aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x599af  ret
0x599b0  ldarg.s  5
0x599b2  brtrue.s loc_599D0
0x599b4  ldarg.3
0x599b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x599ba  stloc.0
0x599bb  ldloc.0
0x599bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest
0x599c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x599c6  beq.s    loc_599D0
0x599c8  ldarg.0
0x599c9  ldarg.3
0x599ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x599cf  throw
0x599d0  ldarg.0
0x599d1  ldarg.1
0x599d2  ldarg.2
0x599d3  ldarg.3
0x599d4  ldc.i4.0
0x599d5  ldnull
0x599d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x599db  ldarg.s  5
0x599dd  brfalse.s loc_599EF
0x599df  ldarg.0
0x599e0  ldstr    aBulkdeleterequ// "BulkDeleteRequest"
0x599e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x599ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x599ef  ldarg.3
0x599f0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x599f5  stloc.1
0x599f6  ldloc.1
0x599f7  brfalse.s loc_59A34
0x599f9  ldarg.0
0x599fa  ldstr    aOptionalparame_0// "OptionalParameters"
0x599ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59a04  ldnull
0x59a05  ldc.i4.0
0x59a06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x59a0b  ldc.i4.0
0x59a0c  stloc.2
0x59a0d  br.s     loc_59A28
0x59a0f  ldarg.0
0x59a10  ldstr    aOptionalparame// "OptionalParameter"
0x59a15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59a1a  ldloc.1
0x59a1b  ldloc.2
0x59a1c  ldelem.ref
0x59a1d  ldc.i4.1
0x59a1e  ldc.i4.0
0x59a1f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x59a24  ldloc.2
0x59a25  ldc.i4.1
0x59a26  add
0x59a27  stloc.2
0x59a28  ldloc.2
0x59a29  ldloc.1
0x59a2a  ldlen
0x59a2b  conv.i4
0x59a2c  blt.s    loc_59A0F
0x59a2e  ldarg.0
0x59a2f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59a34  ldarg.3
0x59a35  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::get_QuerySet()
0x59a3a  stloc.3
0x59a3b  ldloc.3
0x59a3c  brfalse.s loc_59A7E
0x59a3e  ldarg.0
0x59a3f  ldstr    aQueryset// "QuerySet"
0x59a44  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59a49  ldnull
0x59a4a  ldc.i4.0
0x59a4b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x59a50  ldc.i4.0
0x59a51  stloc.s  4
0x59a53  br.s     loc_59A71
0x59a55  ldarg.0
0x59a56  ldstr    aQuerybase// "QueryBase"
0x59a5b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59a60  ldloc.3
0x59a61  ldloc.s  4
0x59a63  ldelem.ref
0x59a64  ldc.i4.1
0x59a65  ldc.i4.0
0x59a66  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write577_QueryBase(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase o, bool isNullable, bool needType)
0x59a6b  ldloc.s  4
0x59a6d  ldc.i4.1
0x59a6e  add
0x59a6f  stloc.s  4
0x59a71  ldloc.s  4
0x59a73  ldloc.3
0x59a74  ldlen
0x59a75  conv.i4
0x59a76  blt.s    loc_59A55
0x59a78  ldarg.0
0x59a79  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59a7e  ldarg.0
0x59a7f  ldstr    aJobname// "JobName"
0x59a84  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59a89  ldarg.3
0x59a8a  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::get_JobName()
0x59a8f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x59a94  ldarg.0
0x59a95  ldstr    aSendemailnotif// "SendEmailNotification"
0x59a9a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59a9f  ldarg.3
0x59aa0  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::get_SendEmailNotification()
0x59aa5  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x59aaa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x59aaf  ldarg.3
0x59ab0  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::get_ToRecipients()
0x59ab5  stloc.s  5
0x59ab7  ldloc.s  5
0x59ab9  brfalse.s loc_59B09
0x59abb  ldarg.0
0x59abc  ldstr    aTorecipients_0// "ToRecipients"
0x59ac1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59ac6  ldnull
0x59ac7  ldc.i4.0
0x59ac8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x59acd  ldc.i4.0
0x59ace  stloc.s  6
0x59ad0  br.s     loc_59AFB
0x59ad2  ldarg.0
0x59ad3  ldstr    aGuid// "guid"
0x59ad8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59add  ldloc.s  5
0x59adf  ldloc.s  6
0x59ae1  ldelema  [mscorlib]System.Guid
0x59ae6  ldobj    [mscorlib]System.Guid
0x59aeb  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x59af0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x59af5  ldloc.s  6
0x59af7  ldc.i4.1
0x59af8  add
0x59af9  stloc.s  6
0x59afb  ldloc.s  6
0x59afd  ldloc.s  5
0x59aff  ldlen
0x59b00  conv.i4
0x59b01  blt.s    loc_59AD2
0x59b03  ldarg.0
0x59b04  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59b09  ldarg.3
0x59b0a  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::get_CCRecipients()
0x59b0f  stloc.s  7
0x59b11  ldloc.s  7
0x59b13  brfalse.s loc_59B63
0x59b15  ldarg.0
0x59b16  ldstr    aCcrecipients// "CCRecipients"
0x59b1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59b20  ldnull
0x59b21  ldc.i4.0
0x59b22  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x59b27  ldc.i4.0
0x59b28  stloc.s  8
0x59b2a  br.s     loc_59B55
0x59b2c  ldarg.0
0x59b2d  ldstr    aGuid// "guid"
0x59b32  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59b37  ldloc.s  7
0x59b39  ldloc.s  8
0x59b3b  ldelema  [mscorlib]System.Guid
0x59b40  ldobj    [mscorlib]System.Guid
0x59b45  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x59b4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x59b4f  ldloc.s  8
0x59b51  ldc.i4.1
0x59b52  add
0x59b53  stloc.s  8
0x59b55  ldloc.s  8
0x59b57  ldloc.s  7
0x59b59  ldlen
0x59b5a  conv.i4
0x59b5b  blt.s    loc_59B2C
0x59b5d  ldarg.0
0x59b5e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59b63  ldarg.0
0x59b64  ldstr    aRecurrencepatt_0// "RecurrencePattern"
0x59b69  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59b6e  ldarg.3
0x59b6f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::get_RecurrencePattern()
0x59b74  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x59b79  ldarg.0
0x59b7a  ldstr    aStartdatetime// "StartDateTime"
0x59b7f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59b84  ldarg.3
0x59b85  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDeleteRequest::get_StartDateTime()
0x59b8a  ldc.i4.0
0x59b8b  ldc.i4.0
0x59b8c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x59b91  ldarg.0
0x59b92  ldarg.3
0x59b93  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x59b98  ret
```
