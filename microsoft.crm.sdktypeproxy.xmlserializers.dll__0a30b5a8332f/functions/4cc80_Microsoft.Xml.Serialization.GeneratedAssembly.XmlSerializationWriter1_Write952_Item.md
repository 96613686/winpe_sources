# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write952_Item

- ea: `0x4cc80`
- end: `0x4cd9a`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write952_Item`
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
- `0x4cc80`

## string_xrefs

- `0x4ccc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ccdf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4ccf5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4cd1a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4cd35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4cd4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4cd67`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4cd82`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4cd7d`: `ColumnSetXml`

## pseudocode

```c

```

## disassembly

```asm
0x4cc80  ldarg.3
0x4cc81  brtrue.s loc_4CC90
0x4cc83  ldarg.s  4
0x4cc85  brfalse.s loc_4CC8F
0x4cc87  ldarg.0
0x4cc88  ldarg.1
0x4cc89  ldarg.2
0x4cc8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4cc8f  ret
0x4cc90  ldarg.s  5
0x4cc92  brtrue.s loc_4CCB0
0x4cc94  ldarg.3
0x4cc95  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4cc9a  stloc.0
0x4cc9b  ldloc.0
0x4cc9c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetOutlookSyncDataSubscriptionClientsRequest
0x4cca1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4cca6  beq.s    loc_4CCB0
0x4cca8  ldarg.0
0x4cca9  ldarg.3
0x4ccaa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4ccaf  throw
0x4ccb0  ldarg.0
0x4ccb1  ldarg.1
0x4ccb2  ldarg.2
0x4ccb3  ldarg.3
0x4ccb4  ldc.i4.0
0x4ccb5  ldnull
0x4ccb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4ccbb  ldarg.s  5
0x4ccbd  brfalse.s loc_4CCCF
0x4ccbf  ldarg.0
0x4ccc0  ldstr    aGetoutlooksync// "GetOutlookSyncDataSubscriptionClientsRe"...
0x4ccc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ccca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4cccf  ldarg.3
0x4ccd0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4ccd5  stloc.1
0x4ccd6  ldloc.1
0x4ccd7  brfalse.s loc_4CD14
0x4ccd9  ldarg.0
0x4ccda  ldstr    aOptionalparame_0// "OptionalParameters"
0x4ccdf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4cce4  ldnull
0x4cce5  ldc.i4.0
0x4cce6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4cceb  ldc.i4.0
0x4ccec  stloc.2
0x4cced  br.s     loc_4CD08
0x4ccef  ldarg.0
0x4ccf0  ldstr    aOptionalparame// "OptionalParameter"
0x4ccf5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ccfa  ldloc.1
0x4ccfb  ldloc.2
0x4ccfc  ldelem.ref
0x4ccfd  ldc.i4.1
0x4ccfe  ldc.i4.0
0x4ccff  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4cd04  ldloc.2
0x4cd05  ldc.i4.1
0x4cd06  add
0x4cd07  stloc.2
0x4cd08  ldloc.2
0x4cd09  ldloc.1
0x4cd0a  ldlen
0x4cd0b  conv.i4
0x4cd0c  blt.s    loc_4CCEF
0x4cd0e  ldarg.0
0x4cd0f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4cd14  ldarg.0
0x4cd15  ldstr    aClientid// "ClientId"
0x4cd1a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4cd1f  ldarg.3
0x4cd20  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetOutlookSyncDataSubscriptionClientsRequest::get_ClientId()
0x4cd25  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4cd2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4cd2f  ldarg.0
0x4cd30  ldstr    aEntityname_0// "EntityName"
0x4cd35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4cd3a  ldarg.3
0x4cd3b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetOutlookSyncDataSubscriptionClientsRequest::get_EntityName()
0x4cd40  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4cd45  ldarg.0
0x4cd46  ldstr    aSyncaction// "SyncAction"
0x4cd4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4cd50  ldarg.0
0x4cd51  ldarg.3
0x4cd52  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetOutlookSyncDataSubscriptionClientsRequest::get_SyncAction()
0x4cd57  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write897_SyncAction(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SyncAction v)
0x4cd5c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4cd61  ldarg.0
0x4cd62  ldstr    aBatchsize// "BatchSize"
0x4cd67  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4cd6c  ldarg.3
0x4cd6d  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetOutlookSyncDataSubscriptionClientsRequest::get_BatchSize()
0x4cd72  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4cd77  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4cd7c  ldarg.0
0x4cd7d  ldstr    aColumnsetxml_0// "ColumnSetXml"
0x4cd82  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4cd87  ldarg.3
0x4cd88  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetOutlookSyncDataSubscriptionClientsRequest::get_ColumnSetXml()
0x4cd8d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4cd92  ldarg.0
0x4cd93  ldarg.3
0x4cd94  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4cd99  ret
```
