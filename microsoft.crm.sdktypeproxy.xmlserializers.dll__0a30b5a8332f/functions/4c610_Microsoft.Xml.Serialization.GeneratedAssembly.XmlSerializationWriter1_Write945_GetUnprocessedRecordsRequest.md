# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write945_GetUnprocessedRecordsRequest

- ea: `0x4c610`
- end: `0x4c75b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write945_GetUnprocessedRecordsRequest`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4c610`

## string_xrefs

- `0x4c655`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c68a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c6a0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c6c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c6e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c6fc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c723`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c73e`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x4c610  ldarg.3
0x4c611  brtrue.s loc_4C620
0x4c613  ldarg.s  4
0x4c615  brfalse.s loc_4C61F
0x4c617  ldarg.0
0x4c618  ldarg.1
0x4c619  ldarg.2
0x4c61a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4c61f  ret
0x4c620  ldarg.s  5
0x4c622  brtrue.s loc_4C640
0x4c624  ldarg.3
0x4c625  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4c62a  stloc.0
0x4c62b  ldloc.0
0x4c62c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest
0x4c631  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c636  beq.s    loc_4C640
0x4c638  ldarg.0
0x4c639  ldarg.3
0x4c63a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4c63f  throw
0x4c640  ldarg.0
0x4c641  ldarg.1
0x4c642  ldarg.2
0x4c643  ldarg.3
0x4c644  ldc.i4.0
0x4c645  ldnull
0x4c646  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4c64b  ldarg.s  5
0x4c64d  brfalse.s loc_4C65F
0x4c64f  ldarg.0
0x4c650  ldstr    aGetunprocessed// "GetUnprocessedRecordsRequest"
0x4c655  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c65a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4c65f  ldarg.0
0x4c660  ldstr    aReturndynamice// "ReturnDynamicEntities"
0x4c665  ldstr    asc_1A34A2// ""
0x4c66a  ldarg.3
0x4c66b  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::get_ReturnDynamicEntities()
0x4c670  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4c675  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x4c67a  ldarg.3
0x4c67b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4c680  stloc.1
0x4c681  ldloc.1
0x4c682  brfalse.s loc_4C6BF
0x4c684  ldarg.0
0x4c685  ldstr    aOptionalparame_0// "OptionalParameters"
0x4c68a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c68f  ldnull
0x4c690  ldc.i4.0
0x4c691  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4c696  ldc.i4.0
0x4c697  stloc.2
0x4c698  br.s     loc_4C6B3
0x4c69a  ldarg.0
0x4c69b  ldstr    aOptionalparame// "OptionalParameter"
0x4c6a0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c6a5  ldloc.1
0x4c6a6  ldloc.2
0x4c6a7  ldelem.ref
0x4c6a8  ldc.i4.1
0x4c6a9  ldc.i4.0
0x4c6aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4c6af  ldloc.2
0x4c6b0  ldc.i4.1
0x4c6b1  add
0x4c6b2  stloc.2
0x4c6b3  ldloc.2
0x4c6b4  ldloc.1
0x4c6b5  ldlen
0x4c6b6  conv.i4
0x4c6b7  blt.s    loc_4C69A
0x4c6b9  ldarg.0
0x4c6ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c6bf  ldarg.0
0x4c6c0  ldstr    aEntityname_0// "EntityName"
0x4c6c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c6ca  ldarg.3
0x4c6cb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::get_EntityName()
0x4c6d0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4c6d5  ldarg.3
0x4c6d6  callvirt instance string[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::get_Columns()
0x4c6db  stloc.3
0x4c6dc  ldloc.3
0x4c6dd  brfalse.s loc_4C71D
0x4c6df  ldarg.0
0x4c6e0  ldstr    aColumns// "Columns"
0x4c6e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c6ea  ldnull
0x4c6eb  ldc.i4.0
0x4c6ec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4c6f1  ldc.i4.0
0x4c6f2  stloc.s  4
0x4c6f4  br.s     loc_4C710
0x4c6f6  ldarg.0
0x4c6f7  ldstr    aString// "string"
0x4c6fc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c701  ldloc.3
0x4c702  ldloc.s  4
0x4c704  ldelem.ref
0x4c705  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullableStringLiteral(string, string, string)
0x4c70a  ldloc.s  4
0x4c70c  ldc.i4.1
0x4c70d  add
0x4c70e  stloc.s  4
0x4c710  ldloc.s  4
0x4c712  ldloc.3
0x4c713  ldlen
0x4c714  conv.i4
0x4c715  blt.s    loc_4C6F6
0x4c717  ldarg.0
0x4c718  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c71d  ldarg.0
0x4c71e  ldstr    aRuleid// "RuleId"
0x4c723  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c728  ldarg.3
0x4c729  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::get_RuleId()
0x4c72e  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4c733  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c738  ldarg.0
0x4c739  ldstr    aPagesize// "PageSize"
0x4c73e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c743  ldarg.3
0x4c744  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::get_PageSize()
0x4c749  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4c74e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c753  ldarg.0
0x4c754  ldarg.3
0x4c755  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4c75a  ret
```
