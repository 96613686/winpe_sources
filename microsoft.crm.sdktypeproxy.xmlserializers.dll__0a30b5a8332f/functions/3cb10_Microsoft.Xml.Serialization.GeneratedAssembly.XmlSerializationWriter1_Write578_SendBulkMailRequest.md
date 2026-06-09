# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write578_SendBulkMailRequest

- ea: `0x3cb10`
- end: `0x3cc28`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write578_SendBulkMailRequest`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x6600`
- `0x2fdf0`
- `0x3a7a0`
- `0x3cb10`

## string_xrefs

- `0x3cb55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cb6f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cb85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cbaa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cbc2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cbdd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cbf3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cc0e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3cbbd`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x3cb10  ldarg.3
0x3cb11  brtrue.s loc_3CB20
0x3cb13  ldarg.s  4
0x3cb15  brfalse.s loc_3CB1F
0x3cb17  ldarg.0
0x3cb18  ldarg.1
0x3cb19  ldarg.2
0x3cb1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3cb1f  ret
0x3cb20  ldarg.s  5
0x3cb22  brtrue.s loc_3CB40
0x3cb24  ldarg.3
0x3cb25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3cb2a  stloc.0
0x3cb2b  ldloc.0
0x3cb2c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendBulkMailRequest
0x3cb31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cb36  beq.s    loc_3CB40
0x3cb38  ldarg.0
0x3cb39  ldarg.3
0x3cb3a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3cb3f  throw
0x3cb40  ldarg.0
0x3cb41  ldarg.1
0x3cb42  ldarg.2
0x3cb43  ldarg.3
0x3cb44  ldc.i4.0
0x3cb45  ldnull
0x3cb46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3cb4b  ldarg.s  5
0x3cb4d  brfalse.s loc_3CB5F
0x3cb4f  ldarg.0
0x3cb50  ldstr    aSendbulkmailre// "SendBulkMailRequest"
0x3cb55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cb5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3cb5f  ldarg.3
0x3cb60  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3cb65  stloc.1
0x3cb66  ldloc.1
0x3cb67  brfalse.s loc_3CBA4
0x3cb69  ldarg.0
0x3cb6a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3cb6f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cb74  ldnull
0x3cb75  ldc.i4.0
0x3cb76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3cb7b  ldc.i4.0
0x3cb7c  stloc.2
0x3cb7d  br.s     loc_3CB98
0x3cb7f  ldarg.0
0x3cb80  ldstr    aOptionalparame// "OptionalParameter"
0x3cb85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cb8a  ldloc.1
0x3cb8b  ldloc.2
0x3cb8c  ldelem.ref
0x3cb8d  ldc.i4.1
0x3cb8e  ldc.i4.0
0x3cb8f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3cb94  ldloc.2
0x3cb95  ldc.i4.1
0x3cb96  add
0x3cb97  stloc.2
0x3cb98  ldloc.2
0x3cb99  ldloc.1
0x3cb9a  ldlen
0x3cb9b  conv.i4
0x3cb9c  blt.s    loc_3CB7F
0x3cb9e  ldarg.0
0x3cb9f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3cba4  ldarg.0
0x3cba5  ldstr    aSender_0// "Sender"
0x3cbaa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cbaf  ldarg.3
0x3cbb0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendBulkMailRequest::get_Sender()
0x3cbb5  ldc.i4.0
0x3cbb6  ldc.i4.0
0x3cbb7  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write515_Moniker(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker o, bool isNullable, bool needType)
0x3cbbc  ldarg.0
0x3cbbd  ldstr    aTemplateid_0// "TemplateId"
0x3cbc2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cbc7  ldarg.3
0x3cbc8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendBulkMailRequest::get_TemplateId()
0x3cbcd  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3cbd2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cbd7  ldarg.0
0x3cbd8  ldstr    aRegardingtype// "RegardingType"
0x3cbdd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cbe2  ldarg.3
0x3cbe3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendBulkMailRequest::get_RegardingType()
0x3cbe8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3cbed  ldarg.0
0x3cbee  ldstr    aRegardingid// "RegardingId"
0x3cbf3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cbf8  ldarg.3
0x3cbf9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendBulkMailRequest::get_RegardingId()
0x3cbfe  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3cc03  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cc08  ldarg.0
0x3cc09  ldstr    aQuery_0// "Query"
0x3cc0e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3cc13  ldarg.3
0x3cc14  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendBulkMailRequest::get_Query()
0x3cc19  ldc.i4.0
0x3cc1a  ldc.i4.0
0x3cc1b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write577_QueryBase(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase o, bool isNullable, bool needType)
0x3cc20  ldarg.0
0x3cc21  ldarg.3
0x3cc22  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3cc27  ret
```
