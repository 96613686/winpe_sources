# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write917_LogSuccessBulkOperationRequest

- ea: `0x4af50`
- end: `0x4b089`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write917_LogSuccessBulkOperationRequest`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4af50`

## string_xrefs

- `0x4af95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4afaf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4afc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4afea`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b005`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b020`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b03b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b056`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b071`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4b036`: `CreatedObjectId`
- `0x4b051`: `CreatedObjectTypeCode`

## pseudocode

```c

```

## disassembly

```asm
0x4af50  ldarg.3
0x4af51  brtrue.s loc_4AF60
0x4af53  ldarg.s  4
0x4af55  brfalse.s loc_4AF5F
0x4af57  ldarg.0
0x4af58  ldarg.1
0x4af59  ldarg.2
0x4af5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4af5f  ret
0x4af60  ldarg.s  5
0x4af62  brtrue.s loc_4AF80
0x4af64  ldarg.3
0x4af65  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4af6a  stloc.0
0x4af6b  ldloc.0
0x4af6c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogSuccessBulkOperationRequest
0x4af71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4af76  beq.s    loc_4AF80
0x4af78  ldarg.0
0x4af79  ldarg.3
0x4af7a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4af7f  throw
0x4af80  ldarg.0
0x4af81  ldarg.1
0x4af82  ldarg.2
0x4af83  ldarg.3
0x4af84  ldc.i4.0
0x4af85  ldnull
0x4af86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4af8b  ldarg.s  5
0x4af8d  brfalse.s loc_4AF9F
0x4af8f  ldarg.0
0x4af90  ldstr    aLogsuccessbulk// "LogSuccessBulkOperationRequest"
0x4af95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4af9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4af9f  ldarg.3
0x4afa0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4afa5  stloc.1
0x4afa6  ldloc.1
0x4afa7  brfalse.s loc_4AFE4
0x4afa9  ldarg.0
0x4afaa  ldstr    aOptionalparame_0// "OptionalParameters"
0x4afaf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4afb4  ldnull
0x4afb5  ldc.i4.0
0x4afb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4afbb  ldc.i4.0
0x4afbc  stloc.2
0x4afbd  br.s     loc_4AFD8
0x4afbf  ldarg.0
0x4afc0  ldstr    aOptionalparame// "OptionalParameter"
0x4afc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4afca  ldloc.1
0x4afcb  ldloc.2
0x4afcc  ldelem.ref
0x4afcd  ldc.i4.1
0x4afce  ldc.i4.0
0x4afcf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4afd4  ldloc.2
0x4afd5  ldc.i4.1
0x4afd6  add
0x4afd7  stloc.2
0x4afd8  ldloc.2
0x4afd9  ldloc.1
0x4afda  ldlen
0x4afdb  conv.i4
0x4afdc  blt.s    loc_4AFBF
0x4afde  ldarg.0
0x4afdf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4afe4  ldarg.0
0x4afe5  ldstr    aBulkoperationi// "BulkOperationId"
0x4afea  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4afef  ldarg.3
0x4aff0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogSuccessBulkOperationRequest::get_BulkOperationId()
0x4aff5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4affa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4afff  ldarg.0
0x4b000  ldstr    aRegardingobjec_1// "RegardingObjectId"
0x4b005  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b00a  ldarg.3
0x4b00b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogSuccessBulkOperationRequest::get_RegardingObjectId()
0x4b010  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4b015  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b01a  ldarg.0
0x4b01b  ldstr    aRegardingobjec_2// "RegardingObjectTypeCode"
0x4b020  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b025  ldarg.3
0x4b026  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogSuccessBulkOperationRequest::get_RegardingObjectTypeCode()
0x4b02b  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4b030  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b035  ldarg.0
0x4b036  ldstr    aCreatedobjecti// "CreatedObjectId"
0x4b03b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b040  ldarg.3
0x4b041  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogSuccessBulkOperationRequest::get_CreatedObjectId()
0x4b046  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4b04b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b050  ldarg.0
0x4b051  ldstr    aCreatedobjectt// "CreatedObjectTypeCode"
0x4b056  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b05b  ldarg.3
0x4b05c  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogSuccessBulkOperationRequest::get_CreatedObjectTypeCode()
0x4b061  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4b066  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4b06b  ldarg.0
0x4b06c  ldstr    aAdditionalinfo// "AdditionalInfo"
0x4b071  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4b076  ldarg.3
0x4b077  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.LogSuccessBulkOperationRequest::get_AdditionalInfo()
0x4b07c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4b081  ldarg.0
0x4b082  ldarg.3
0x4b083  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4b088  ret
```
