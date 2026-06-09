# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write948_GetSyncDataSubscriptionRequest

- ea: `0x4c8f0`
- end: `0x4ca0a`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write948_GetSyncDataSubscriptionRequest`
- size: `282`
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
- `0x4c8f0`

## string_xrefs

- `0x4c935`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c94f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c965`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c98a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c9a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c9bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c9d7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c9f2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c9ed`: `ColumnSetXml`

## pseudocode

```c

```

## disassembly

```asm
0x4c8f0  ldarg.3
0x4c8f1  brtrue.s loc_4C900
0x4c8f3  ldarg.s  4
0x4c8f5  brfalse.s loc_4C8FF
0x4c8f7  ldarg.0
0x4c8f8  ldarg.1
0x4c8f9  ldarg.2
0x4c8fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4c8ff  ret
0x4c900  ldarg.s  5
0x4c902  brtrue.s loc_4C920
0x4c904  ldarg.3
0x4c905  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4c90a  stloc.0
0x4c90b  ldloc.0
0x4c90c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetSyncDataSubscriptionRequest
0x4c911  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c916  beq.s    loc_4C920
0x4c918  ldarg.0
0x4c919  ldarg.3
0x4c91a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4c91f  throw
0x4c920  ldarg.0
0x4c921  ldarg.1
0x4c922  ldarg.2
0x4c923  ldarg.3
0x4c924  ldc.i4.0
0x4c925  ldnull
0x4c926  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4c92b  ldarg.s  5
0x4c92d  brfalse.s loc_4C93F
0x4c92f  ldarg.0
0x4c930  ldstr    aGetsyncdatasub// "GetSyncDataSubscriptionRequest"
0x4c935  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c93a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4c93f  ldarg.3
0x4c940  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4c945  stloc.1
0x4c946  ldloc.1
0x4c947  brfalse.s loc_4C984
0x4c949  ldarg.0
0x4c94a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4c94f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c954  ldnull
0x4c955  ldc.i4.0
0x4c956  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4c95b  ldc.i4.0
0x4c95c  stloc.2
0x4c95d  br.s     loc_4C978
0x4c95f  ldarg.0
0x4c960  ldstr    aOptionalparame// "OptionalParameter"
0x4c965  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c96a  ldloc.1
0x4c96b  ldloc.2
0x4c96c  ldelem.ref
0x4c96d  ldc.i4.1
0x4c96e  ldc.i4.0
0x4c96f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4c974  ldloc.2
0x4c975  ldc.i4.1
0x4c976  add
0x4c977  stloc.2
0x4c978  ldloc.2
0x4c979  ldloc.1
0x4c97a  ldlen
0x4c97b  conv.i4
0x4c97c  blt.s    loc_4C95F
0x4c97e  ldarg.0
0x4c97f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c984  ldarg.0
0x4c985  ldstr    aSubscriptionid_0// "SubscriptionId"
0x4c98a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c98f  ldarg.3
0x4c990  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetSyncDataSubscriptionRequest::get_SubscriptionId()
0x4c995  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4c99a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c99f  ldarg.0
0x4c9a0  ldstr    aEntityname_0// "EntityName"
0x4c9a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c9aa  ldarg.3
0x4c9ab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetSyncDataSubscriptionRequest::get_EntityName()
0x4c9b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4c9b5  ldarg.0
0x4c9b6  ldstr    aSyncaction// "SyncAction"
0x4c9bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c9c0  ldarg.0
0x4c9c1  ldarg.3
0x4c9c2  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetSyncDataSubscriptionRequest::get_SyncAction()
0x4c9c7  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write897_SyncAction(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction v)
0x4c9cc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4c9d1  ldarg.0
0x4c9d2  ldstr    aBatchsize// "BatchSize"
0x4c9d7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c9dc  ldarg.3
0x4c9dd  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetSyncDataSubscriptionRequest::get_BatchSize()
0x4c9e2  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4c9e7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4c9ec  ldarg.0
0x4c9ed  ldstr    aColumnsetxml_0// "ColumnSetXml"
0x4c9f2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c9f7  ldarg.3
0x4c9f8  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetSyncDataSubscriptionRequest::get_ColumnSetXml()
0x4c9fd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4ca02  ldarg.0
0x4ca03  ldarg.3
0x4ca04  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4ca09  ret
```
