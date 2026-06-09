# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write898_PostSyncSubscriptionRequest

- ea: `0x4a120`
- end: `0x4a224`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write898_PostSyncSubscriptionRequest`
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
- `0x4a120`

## string_xrefs

- `0x4a165`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a17f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a195`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a1ba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a1d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a1eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a207`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x4a120  ldarg.3
0x4a121  brtrue.s loc_4A130
0x4a123  ldarg.s  4
0x4a125  brfalse.s loc_4A12F
0x4a127  ldarg.0
0x4a128  ldarg.1
0x4a129  ldarg.2
0x4a12a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4a12f  ret
0x4a130  ldarg.s  5
0x4a132  brtrue.s loc_4A150
0x4a134  ldarg.3
0x4a135  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4a13a  stloc.0
0x4a13b  ldloc.0
0x4a13c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostSyncSubscriptionRequest
0x4a141  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a146  beq.s    loc_4A150
0x4a148  ldarg.0
0x4a149  ldarg.3
0x4a14a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4a14f  throw
0x4a150  ldarg.0
0x4a151  ldarg.1
0x4a152  ldarg.2
0x4a153  ldarg.3
0x4a154  ldc.i4.0
0x4a155  ldnull
0x4a156  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4a15b  ldarg.s  5
0x4a15d  brfalse.s loc_4A16F
0x4a15f  ldarg.0
0x4a160  ldstr    aPostsyncsubscr// "PostSyncSubscriptionRequest"
0x4a165  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a16a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4a16f  ldarg.3
0x4a170  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4a175  stloc.1
0x4a176  ldloc.1
0x4a177  brfalse.s loc_4A1B4
0x4a179  ldarg.0
0x4a17a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4a17f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a184  ldnull
0x4a185  ldc.i4.0
0x4a186  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4a18b  ldc.i4.0
0x4a18c  stloc.2
0x4a18d  br.s     loc_4A1A8
0x4a18f  ldarg.0
0x4a190  ldstr    aOptionalparame// "OptionalParameter"
0x4a195  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a19a  ldloc.1
0x4a19b  ldloc.2
0x4a19c  ldelem.ref
0x4a19d  ldc.i4.1
0x4a19e  ldc.i4.0
0x4a19f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4a1a4  ldloc.2
0x4a1a5  ldc.i4.1
0x4a1a6  add
0x4a1a7  stloc.2
0x4a1a8  ldloc.2
0x4a1a9  ldloc.1
0x4a1aa  ldlen
0x4a1ab  conv.i4
0x4a1ac  blt.s    loc_4A18F
0x4a1ae  ldarg.0
0x4a1af  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4a1b4  ldarg.0
0x4a1b5  ldstr    aSubscriptionid_0// "SubscriptionId"
0x4a1ba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a1bf  ldarg.3
0x4a1c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostSyncSubscriptionRequest::get_SubscriptionId()
0x4a1c5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4a1ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a1cf  ldarg.0
0x4a1d0  ldstr    aEntityname_0// "EntityName"
0x4a1d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a1da  ldarg.3
0x4a1db  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostSyncSubscriptionRequest::get_EntityName()
0x4a1e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a1e5  ldarg.0
0x4a1e6  ldstr    aSyncaction// "SyncAction"
0x4a1eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a1f0  ldarg.0
0x4a1f1  ldarg.3
0x4a1f2  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostSyncSubscriptionRequest::get_SyncAction()
0x4a1f7  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write897_SyncAction(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction v)
0x4a1fc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a201  ldarg.0
0x4a202  ldstr    aBatchsize// "BatchSize"
0x4a207  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a20c  ldarg.3
0x4a20d  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PostSyncSubscriptionRequest::get_BatchSize()
0x4a212  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4a217  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a21c  ldarg.0
0x4a21d  ldarg.3
0x4a21e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4a223  ret
```
