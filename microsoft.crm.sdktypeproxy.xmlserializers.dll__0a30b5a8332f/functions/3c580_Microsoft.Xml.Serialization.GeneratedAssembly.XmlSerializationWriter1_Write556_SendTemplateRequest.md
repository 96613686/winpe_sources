# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write556_SendTemplateRequest

- ea: `0x3c580`
- end: `0x3c6ec`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write556_SendTemplateRequest`
- size: `364`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x3a7a0`
- `0x3c580`

## string_xrefs

- `0x3c5c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c5df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c5f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c61a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c635`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c64d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c66d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c684`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c6b9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c6cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c5c0`: `SendTemplateRequest`
- `0x3c615`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x3c580  ldarg.3
0x3c581  brtrue.s loc_3C590
0x3c583  ldarg.s  4
0x3c585  brfalse.s loc_3C58F
0x3c587  ldarg.0
0x3c588  ldarg.1
0x3c589  ldarg.2
0x3c58a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3c58f  ret
0x3c590  ldarg.s  5
0x3c592  brtrue.s loc_3C5B0
0x3c594  ldarg.3
0x3c595  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c59a  stloc.0
0x3c59b  ldloc.0
0x3c59c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest
0x3c5a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c5a6  beq.s    loc_3C5B0
0x3c5a8  ldarg.0
0x3c5a9  ldarg.3
0x3c5aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3c5af  throw
0x3c5b0  ldarg.0
0x3c5b1  ldarg.1
0x3c5b2  ldarg.2
0x3c5b3  ldarg.3
0x3c5b4  ldc.i4.0
0x3c5b5  ldnull
0x3c5b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3c5bb  ldarg.s  5
0x3c5bd  brfalse.s loc_3C5CF
0x3c5bf  ldarg.0
0x3c5c0  ldstr    aSendtemplatere// "SendTemplateRequest"
0x3c5c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c5ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3c5cf  ldarg.3
0x3c5d0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3c5d5  stloc.1
0x3c5d6  ldloc.1
0x3c5d7  brfalse.s loc_3C614
0x3c5d9  ldarg.0
0x3c5da  ldstr    aOptionalparame_0// "OptionalParameters"
0x3c5df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c5e4  ldnull
0x3c5e5  ldc.i4.0
0x3c5e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3c5eb  ldc.i4.0
0x3c5ec  stloc.2
0x3c5ed  br.s     loc_3C608
0x3c5ef  ldarg.0
0x3c5f0  ldstr    aOptionalparame// "OptionalParameter"
0x3c5f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c5fa  ldloc.1
0x3c5fb  ldloc.2
0x3c5fc  ldelem.ref
0x3c5fd  ldc.i4.1
0x3c5fe  ldc.i4.0
0x3c5ff  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3c604  ldloc.2
0x3c605  ldc.i4.1
0x3c606  add
0x3c607  stloc.2
0x3c608  ldloc.2
0x3c609  ldloc.1
0x3c60a  ldlen
0x3c60b  conv.i4
0x3c60c  blt.s    loc_3C5EF
0x3c60e  ldarg.0
0x3c60f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3c614  ldarg.0
0x3c615  ldstr    aTemplateid_0// "TemplateId"
0x3c61a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c61f  ldarg.3
0x3c620  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::get_TemplateId()
0x3c625  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c62a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c62f  ldarg.0
0x3c630  ldstr    aSender_0// "Sender"
0x3c635  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c63a  ldarg.3
0x3c63b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::get_Sender()
0x3c640  ldc.i4.0
0x3c641  ldc.i4.0
0x3c642  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write515_Moniker(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker o, bool isNullable, bool needType)
0x3c647  ldarg.0
0x3c648  ldstr    aRecipienttype// "RecipientType"
0x3c64d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c652  ldarg.3
0x3c653  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::get_RecipientType()
0x3c658  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3c65d  ldarg.3
0x3c65e  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::get_RecipientIds()
0x3c663  stloc.3
0x3c664  ldloc.3
0x3c665  brfalse.s loc_3C6B3
0x3c667  ldarg.0
0x3c668  ldstr    aRecipientids// "RecipientIds"
0x3c66d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c672  ldnull
0x3c673  ldc.i4.0
0x3c674  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3c679  ldc.i4.0
0x3c67a  stloc.s  4
0x3c67c  br.s     loc_3C6A6
0x3c67e  ldarg.0
0x3c67f  ldstr    aGuid// "guid"
0x3c684  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c689  ldloc.3
0x3c68a  ldloc.s  4
0x3c68c  ldelema  [mscorlib]System.Guid
0x3c691  ldobj    [mscorlib]System.Guid
0x3c696  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c69b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c6a0  ldloc.s  4
0x3c6a2  ldc.i4.1
0x3c6a3  add
0x3c6a4  stloc.s  4
0x3c6a6  ldloc.s  4
0x3c6a8  ldloc.3
0x3c6a9  ldlen
0x3c6aa  conv.i4
0x3c6ab  blt.s    loc_3C67E
0x3c6ad  ldarg.0
0x3c6ae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3c6b3  ldarg.0
0x3c6b4  ldstr    aRegardingtype// "RegardingType"
0x3c6b9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c6be  ldarg.3
0x3c6bf  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::get_RegardingType()
0x3c6c4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3c6c9  ldarg.0
0x3c6ca  ldstr    aRegardingid// "RegardingId"
0x3c6cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c6d4  ldarg.3
0x3c6d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::get_RegardingId()
0x3c6da  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c6df  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c6e4  ldarg.0
0x3c6e5  ldarg.3
0x3c6e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3c6eb  ret
```
