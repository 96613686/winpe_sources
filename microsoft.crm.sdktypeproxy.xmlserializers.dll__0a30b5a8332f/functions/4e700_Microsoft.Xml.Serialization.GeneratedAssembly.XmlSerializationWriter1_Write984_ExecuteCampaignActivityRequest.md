# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write984_ExecuteCampaignActivityRequest

- ea: `0x4e700`
- end: `0x4e821`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write984_ExecuteCampaignActivityRequest`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x17440`
- `0x19ce0`
- `0x2fdf0`
- `0x4e700`

## string_xrefs

- `0x4e745`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e75f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e775`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e79a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e7b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e7d0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e7e8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e803`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4e7e3`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x4e700  ldarg.3
0x4e701  brtrue.s loc_4E710
0x4e703  ldarg.s  4
0x4e705  brfalse.s loc_4E70F
0x4e707  ldarg.0
0x4e708  ldarg.1
0x4e709  ldarg.2
0x4e70a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4e70f  ret
0x4e710  ldarg.s  5
0x4e712  brtrue.s loc_4E730
0x4e714  ldarg.3
0x4e715  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4e71a  stloc.0
0x4e71b  ldloc.0
0x4e71c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExecuteCampaignActivityRequest
0x4e721  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e726  beq.s    loc_4E730
0x4e728  ldarg.0
0x4e729  ldarg.3
0x4e72a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4e72f  throw
0x4e730  ldarg.0
0x4e731  ldarg.1
0x4e732  ldarg.2
0x4e733  ldarg.3
0x4e734  ldc.i4.0
0x4e735  ldnull
0x4e736  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4e73b  ldarg.s  5
0x4e73d  brfalse.s loc_4E74F
0x4e73f  ldarg.0
0x4e740  ldstr    aExecutecampaig// "ExecuteCampaignActivityRequest"
0x4e745  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e74a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4e74f  ldarg.3
0x4e750  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4e755  stloc.1
0x4e756  ldloc.1
0x4e757  brfalse.s loc_4E794
0x4e759  ldarg.0
0x4e75a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4e75f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e764  ldnull
0x4e765  ldc.i4.0
0x4e766  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4e76b  ldc.i4.0
0x4e76c  stloc.2
0x4e76d  br.s     loc_4E788
0x4e76f  ldarg.0
0x4e770  ldstr    aOptionalparame// "OptionalParameter"
0x4e775  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e77a  ldloc.1
0x4e77b  ldloc.2
0x4e77c  ldelem.ref
0x4e77d  ldc.i4.1
0x4e77e  ldc.i4.0
0x4e77f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4e784  ldloc.2
0x4e785  ldc.i4.1
0x4e786  add
0x4e787  stloc.2
0x4e788  ldloc.2
0x4e789  ldloc.1
0x4e78a  ldlen
0x4e78b  conv.i4
0x4e78c  blt.s    loc_4E76F
0x4e78e  ldarg.0
0x4e78f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4e794  ldarg.0
0x4e795  ldstr    aCampaignactivi_5// "CampaignActivityId"
0x4e79a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e79f  ldarg.3
0x4e7a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExecuteCampaignActivityRequest::get_CampaignActivityId()
0x4e7a5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4e7aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4e7af  ldarg.0
0x4e7b0  ldstr    aPropagate// "Propagate"
0x4e7b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e7ba  ldarg.3
0x4e7bb  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExecuteCampaignActivityRequest::get_Propagate()
0x4e7c0  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4e7c5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4e7ca  ldarg.0
0x4e7cb  ldstr    aActivity// "Activity"
0x4e7d0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e7d5  ldarg.3
0x4e7d6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExecuteCampaignActivityRequest::get_Activity()
0x4e7db  ldc.i4.0
0x4e7dc  ldc.i4.0
0x4e7dd  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x4e7e2  ldarg.0
0x4e7e3  ldstr    aTemplateid_0// "TemplateId"
0x4e7e8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e7ed  ldarg.3
0x4e7ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExecuteCampaignActivityRequest::get_TemplateId()
0x4e7f3  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4e7f8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4e7fd  ldarg.0
0x4e7fe  ldstr    aOwnershipoptio// "OwnershipOptions"
0x4e803  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4e808  ldarg.0
0x4e809  ldarg.3
0x4e80a  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ExecuteCampaignActivityRequest::get_OwnershipOptions()
0x4e80f  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write890_PropagationOwnershipOptions(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions v)
0x4e814  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4e819  ldarg.0
0x4e81a  ldarg.3
0x4e81b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4e820  ret
```
