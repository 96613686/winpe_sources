# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1245_CreateActivitiesListRequest

- ea: `0x57df0`
- end: `0x57f5a`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1245_CreateActivitiesListRequest`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x17440`
- `0x19ce0`
- `0x2fdf0`
- `0x3a7a0`
- `0x57df0`

## string_xrefs

- `0x57e35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57e4f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57e65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57e8a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57ea5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57ebb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57ed3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57eee`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57f09`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57f25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57f3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x57ece`: `TemplateId`
- `0x57e30`: `CreateActivitiesListRequest`

## pseudocode

```c

```

## disassembly

```asm
0x57df0  ldarg.3
0x57df1  brtrue.s loc_57E00
0x57df3  ldarg.s  4
0x57df5  brfalse.s loc_57DFF
0x57df7  ldarg.0
0x57df8  ldarg.1
0x57df9  ldarg.2
0x57dfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x57dff  ret
0x57e00  ldarg.s  5
0x57e02  brtrue.s loc_57E20
0x57e04  ldarg.3
0x57e05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x57e0a  stloc.0
0x57e0b  ldloc.0
0x57e0c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest
0x57e11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x57e16  beq.s    loc_57E20
0x57e18  ldarg.0
0x57e19  ldarg.3
0x57e1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x57e1f  throw
0x57e20  ldarg.0
0x57e21  ldarg.1
0x57e22  ldarg.2
0x57e23  ldarg.3
0x57e24  ldc.i4.0
0x57e25  ldnull
0x57e26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x57e2b  ldarg.s  5
0x57e2d  brfalse.s loc_57E3F
0x57e2f  ldarg.0
0x57e30  ldstr    aCreateactiviti// "CreateActivitiesListRequest"
0x57e35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57e3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x57e3f  ldarg.3
0x57e40  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x57e45  stloc.1
0x57e46  ldloc.1
0x57e47  brfalse.s loc_57E84
0x57e49  ldarg.0
0x57e4a  ldstr    aOptionalparame_0// "OptionalParameters"
0x57e4f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57e54  ldnull
0x57e55  ldc.i4.0
0x57e56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x57e5b  ldc.i4.0
0x57e5c  stloc.2
0x57e5d  br.s     loc_57E78
0x57e5f  ldarg.0
0x57e60  ldstr    aOptionalparame// "OptionalParameter"
0x57e65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57e6a  ldloc.1
0x57e6b  ldloc.2
0x57e6c  ldelem.ref
0x57e6d  ldc.i4.1
0x57e6e  ldc.i4.0
0x57e6f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x57e74  ldloc.2
0x57e75  ldc.i4.1
0x57e76  add
0x57e77  stloc.2
0x57e78  ldloc.2
0x57e79  ldloc.1
0x57e7a  ldlen
0x57e7b  conv.i4
0x57e7c  blt.s    loc_57E5F
0x57e7e  ldarg.0
0x57e7f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x57e84  ldarg.0
0x57e85  ldstr    aListid_0// "ListId"
0x57e8a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57e8f  ldarg.3
0x57e90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_ListId()
0x57e95  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x57e9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x57e9f  ldarg.0
0x57ea0  ldstr    aFriendlyname_0// "FriendlyName"
0x57ea5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57eaa  ldarg.3
0x57eab  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_FriendlyName()
0x57eb0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x57eb5  ldarg.0
0x57eb6  ldstr    aActivity// "Activity"
0x57ebb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57ec0  ldarg.3
0x57ec1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_Activity()
0x57ec6  ldc.i4.0
0x57ec7  ldc.i4.0
0x57ec8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x57ecd  ldarg.0
0x57ece  ldstr    aTemplateid_0// "TemplateId"
0x57ed3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57ed8  ldarg.3
0x57ed9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_TemplateId()
0x57ede  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x57ee3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x57ee8  ldarg.0
0x57ee9  ldstr    aPropagate// "Propagate"
0x57eee  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57ef3  ldarg.3
0x57ef4  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_Propagate()
0x57ef9  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x57efe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x57f03  ldarg.0
0x57f04  ldstr    aOwnershipoptio// "OwnershipOptions"
0x57f09  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57f0e  ldarg.0
0x57f0f  ldarg.3
0x57f10  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_OwnershipOptions()
0x57f15  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write890_PropagationOwnershipOptions(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions v)
0x57f1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x57f1f  ldarg.0
0x57f20  ldstr    aOwner// "Owner"
0x57f25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57f2a  ldarg.3
0x57f2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_Owner()
0x57f30  ldc.i4.0
0x57f31  ldc.i4.0
0x57f32  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write515_Moniker(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker o, bool isNullable, bool needType)
0x57f37  ldarg.0
0x57f38  ldstr    aSendemail_0// "sendEmail"
0x57f3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x57f42  ldarg.3
0x57f43  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateActivitiesListRequest::get_sendEmail()
0x57f48  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x57f4d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x57f52  ldarg.0
0x57f53  ldarg.3
0x57f54  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x57f59  ret
```
