# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write988_Item

- ea: `0x4ea70`
- end: `0x4ebc4`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write988_Item`
- size: `340`
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
- `0x4ea70`

## string_xrefs

- `0x4eab5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eacf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eae5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eb0a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eb25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eb40`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eb58`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eb73`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eb8f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eba7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4eb53`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x4ea70  ldarg.3
0x4ea71  brtrue.s loc_4EA80
0x4ea73  ldarg.s  4
0x4ea75  brfalse.s loc_4EA7F
0x4ea77  ldarg.0
0x4ea78  ldarg.1
0x4ea79  ldarg.2
0x4ea7a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4ea7f  ret
0x4ea80  ldarg.s  5
0x4ea82  brtrue.s loc_4EAA0
0x4ea84  ldarg.3
0x4ea85  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4ea8a  stloc.0
0x4ea8b  ldloc.0
0x4ea8c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest
0x4ea91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ea96  beq.s    loc_4EAA0
0x4ea98  ldarg.0
0x4ea99  ldarg.3
0x4ea9a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4ea9f  throw
0x4eaa0  ldarg.0
0x4eaa1  ldarg.1
0x4eaa2  ldarg.2
0x4eaa3  ldarg.3
0x4eaa4  ldc.i4.0
0x4eaa5  ldnull
0x4eaa6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4eaab  ldarg.s  5
0x4eaad  brfalse.s loc_4EABF
0x4eaaf  ldarg.0
0x4eab0  ldstr    aDistributecamp// "DistributeCampaignActivityRequest"
0x4eab5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eaba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4eabf  ldarg.3
0x4eac0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4eac5  stloc.1
0x4eac6  ldloc.1
0x4eac7  brfalse.s loc_4EB04
0x4eac9  ldarg.0
0x4eaca  ldstr    aOptionalparame_0// "OptionalParameters"
0x4eacf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ead4  ldnull
0x4ead5  ldc.i4.0
0x4ead6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4eadb  ldc.i4.0
0x4eadc  stloc.2
0x4eadd  br.s     loc_4EAF8
0x4eadf  ldarg.0
0x4eae0  ldstr    aOptionalparame// "OptionalParameter"
0x4eae5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eaea  ldloc.1
0x4eaeb  ldloc.2
0x4eaec  ldelem.ref
0x4eaed  ldc.i4.1
0x4eaee  ldc.i4.0
0x4eaef  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4eaf4  ldloc.2
0x4eaf5  ldc.i4.1
0x4eaf6  add
0x4eaf7  stloc.2
0x4eaf8  ldloc.2
0x4eaf9  ldloc.1
0x4eafa  ldlen
0x4eafb  conv.i4
0x4eafc  blt.s    loc_4EADF
0x4eafe  ldarg.0
0x4eaff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4eb04  ldarg.0
0x4eb05  ldstr    aCampaignactivi_5// "CampaignActivityId"
0x4eb0a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eb0f  ldarg.3
0x4eb10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest::get_CampaignActivityId()
0x4eb15  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4eb1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4eb1f  ldarg.0
0x4eb20  ldstr    aPropagate// "Propagate"
0x4eb25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eb2a  ldarg.3
0x4eb2b  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest::get_Propagate()
0x4eb30  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4eb35  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4eb3a  ldarg.0
0x4eb3b  ldstr    aActivity// "Activity"
0x4eb40  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eb45  ldarg.3
0x4eb46  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest::get_Activity()
0x4eb4b  ldc.i4.0
0x4eb4c  ldc.i4.0
0x4eb4d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x4eb52  ldarg.0
0x4eb53  ldstr    aTemplateid_0// "TemplateId"
0x4eb58  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eb5d  ldarg.3
0x4eb5e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest::get_TemplateId()
0x4eb63  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4eb68  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4eb6d  ldarg.0
0x4eb6e  ldstr    aOwnershipoptio// "OwnershipOptions"
0x4eb73  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eb78  ldarg.0
0x4eb79  ldarg.3
0x4eb7a  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest::get_OwnershipOptions()
0x4eb7f  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write890_PropagationOwnershipOptions(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions v)
0x4eb84  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4eb89  ldarg.0
0x4eb8a  ldstr    aOwner// "Owner"
0x4eb8f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4eb94  ldarg.3
0x4eb95  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest::get_Owner()
0x4eb9a  ldc.i4.0
0x4eb9b  ldc.i4.0
0x4eb9c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write515_Moniker(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker o, bool isNullable, bool needType)
0x4eba1  ldarg.0
0x4eba2  ldstr    aSendemail// "SendEmail"
0x4eba7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4ebac  ldarg.3
0x4ebad  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DistributeCampaignActivityRequest::get_SendEmail()
0x4ebb2  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4ebb7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4ebbc  ldarg.0
0x4ebbd  ldarg.3
0x4ebbe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4ebc3  ret
```
