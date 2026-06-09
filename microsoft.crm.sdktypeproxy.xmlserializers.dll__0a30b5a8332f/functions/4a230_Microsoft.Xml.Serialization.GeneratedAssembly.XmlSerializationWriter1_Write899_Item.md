# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write899_Item

- ea: `0x4a230`
- end: `0x4a334`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write899_Item`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x173e0`
- `0x2fdf0`
- `0x4a230`

## string_xrefs

- `0x4a275`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a28f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a2a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a2ca`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a2e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a2fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a317`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x4a230  ldarg.3
0x4a231  brtrue.s loc_4A240
0x4a233  ldarg.s  4
0x4a235  brfalse.s loc_4A23F
0x4a237  ldarg.0
0x4a238  ldarg.1
0x4a239  ldarg.2
0x4a23a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4a23f  ret
0x4a240  ldarg.s  5
0x4a242  brtrue.s loc_4A260
0x4a244  ldarg.3
0x4a245  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4a24a  stloc.0
0x4a24b  ldloc.0
0x4a24c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostOutlookSyncSubscriptionClientsRequest
0x4a251  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a256  beq.s    loc_4A260
0x4a258  ldarg.0
0x4a259  ldarg.3
0x4a25a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4a25f  throw
0x4a260  ldarg.0
0x4a261  ldarg.1
0x4a262  ldarg.2
0x4a263  ldarg.3
0x4a264  ldc.i4.0
0x4a265  ldnull
0x4a266  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4a26b  ldarg.s  5
0x4a26d  brfalse.s loc_4A27F
0x4a26f  ldarg.0
0x4a270  ldstr    aPostoutlooksyn// "PostOutlookSyncSubscriptionClientsReque"...
0x4a275  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a27a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4a27f  ldarg.3
0x4a280  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4a285  stloc.1
0x4a286  ldloc.1
0x4a287  brfalse.s loc_4A2C4
0x4a289  ldarg.0
0x4a28a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4a28f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a294  ldnull
0x4a295  ldc.i4.0
0x4a296  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4a29b  ldc.i4.0
0x4a29c  stloc.2
0x4a29d  br.s     loc_4A2B8
0x4a29f  ldarg.0
0x4a2a0  ldstr    aOptionalparame// "OptionalParameter"
0x4a2a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a2aa  ldloc.1
0x4a2ab  ldloc.2
0x4a2ac  ldelem.ref
0x4a2ad  ldc.i4.1
0x4a2ae  ldc.i4.0
0x4a2af  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4a2b4  ldloc.2
0x4a2b5  ldc.i4.1
0x4a2b6  add
0x4a2b7  stloc.2
0x4a2b8  ldloc.2
0x4a2b9  ldloc.1
0x4a2ba  ldlen
0x4a2bb  conv.i4
0x4a2bc  blt.s    loc_4A29F
0x4a2be  ldarg.0
0x4a2bf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4a2c4  ldarg.0
0x4a2c5  ldstr    aClientid// "ClientId"
0x4a2ca  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a2cf  ldarg.3
0x4a2d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostOutlookSyncSubscriptionClientsRequest::get_ClientId()
0x4a2d5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4a2da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a2df  ldarg.0
0x4a2e0  ldstr    aEntityname_0// "EntityName"
0x4a2e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a2ea  ldarg.3
0x4a2eb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostOutlookSyncSubscriptionClientsRequest::get_EntityName()
0x4a2f0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a2f5  ldarg.0
0x4a2f6  ldstr    aSyncaction// "SyncAction"
0x4a2fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a300  ldarg.0
0x4a301  ldarg.3
0x4a302  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostOutlookSyncSubscriptionClientsRequest::get_SyncAction()
0x4a307  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write897_SyncAction(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction v)
0x4a30c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a311  ldarg.0
0x4a312  ldstr    aBatchsize// "BatchSize"
0x4a317  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a31c  ldarg.3
0x4a31d  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostOutlookSyncSubscriptionClientsRequest::get_BatchSize()
0x4a322  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4a327  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a32c  ldarg.0
0x4a32d  ldarg.3
0x4a32e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4a333  ret
```
