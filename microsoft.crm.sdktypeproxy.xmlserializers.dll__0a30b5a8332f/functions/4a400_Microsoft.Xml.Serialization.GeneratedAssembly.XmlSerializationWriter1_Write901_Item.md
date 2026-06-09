# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write901_Item

- ea: `0x4a400`
- end: `0x4a56d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write901_Item`
- size: `365`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x17440`
- `0x2fdf0`
- `0x3a7a0`
- `0x4a400`

## string_xrefs

- `0x4a445`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a45f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a475`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a49a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a4b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a4d0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a4e6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a501`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a51d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a538`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a550`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a4e1`: `TemplateId`
- `0x4a4cb`: `ActivityXml`

## pseudocode

```c

```

## disassembly

```asm
0x4a400  ldarg.3
0x4a401  brtrue.s loc_4A410
0x4a403  ldarg.s  4
0x4a405  brfalse.s loc_4A40F
0x4a407  ldarg.0
0x4a408  ldarg.1
0x4a409  ldarg.2
0x4a40a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4a40f  ret
0x4a410  ldarg.s  5
0x4a412  brtrue.s loc_4A430
0x4a414  ldarg.3
0x4a415  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4a41a  stloc.0
0x4a41b  ldloc.0
0x4a41c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest
0x4a421  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a426  beq.s    loc_4A430
0x4a428  ldarg.0
0x4a429  ldarg.3
0x4a42a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4a42f  throw
0x4a430  ldarg.0
0x4a431  ldarg.1
0x4a432  ldarg.2
0x4a433  ldarg.3
0x4a434  ldc.i4.0
0x4a435  ldnull
0x4a436  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4a43b  ldarg.s  5
0x4a43d  brfalse.s loc_4A44F
0x4a43f  ldarg.0
0x4a440  ldstr    aMyexecutecampa// "MyExecuteCampaignActivityRequest"
0x4a445  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a44a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4a44f  ldarg.3
0x4a450  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4a455  stloc.1
0x4a456  ldloc.1
0x4a457  brfalse.s loc_4A494
0x4a459  ldarg.0
0x4a45a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4a45f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a464  ldnull
0x4a465  ldc.i4.0
0x4a466  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4a46b  ldc.i4.0
0x4a46c  stloc.2
0x4a46d  br.s     loc_4A488
0x4a46f  ldarg.0
0x4a470  ldstr    aOptionalparame// "OptionalParameter"
0x4a475  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a47a  ldloc.1
0x4a47b  ldloc.2
0x4a47c  ldelem.ref
0x4a47d  ldc.i4.1
0x4a47e  ldc.i4.0
0x4a47f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4a484  ldloc.2
0x4a485  ldc.i4.1
0x4a486  add
0x4a487  stloc.2
0x4a488  ldloc.2
0x4a489  ldloc.1
0x4a48a  ldlen
0x4a48b  conv.i4
0x4a48c  blt.s    loc_4A46F
0x4a48e  ldarg.0
0x4a48f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4a494  ldarg.0
0x4a495  ldstr    aCampaignactivi_5// "CampaignActivityId"
0x4a49a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a49f  ldarg.3
0x4a4a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_CampaignActivityId()
0x4a4a5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4a4aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a4af  ldarg.0
0x4a4b0  ldstr    aPropagate// "Propagate"
0x4a4b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a4ba  ldarg.3
0x4a4bb  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_Propagate()
0x4a4c0  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4a4c5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a4ca  ldarg.0
0x4a4cb  ldstr    aActivityxml// "ActivityXml"
0x4a4d0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a4d5  ldarg.3
0x4a4d6  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_ActivityXml()
0x4a4db  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a4e0  ldarg.0
0x4a4e1  ldstr    aTemplateid_0// "TemplateId"
0x4a4e6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a4eb  ldarg.3
0x4a4ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_TemplateId()
0x4a4f1  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4a4f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a4fb  ldarg.0
0x4a4fc  ldstr    aOwnershipoptio// "OwnershipOptions"
0x4a501  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a506  ldarg.0
0x4a507  ldarg.3
0x4a508  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_OwnershipOptions()
0x4a50d  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write890_PropagationOwnershipOptions(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions v)
0x4a512  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a517  ldarg.0
0x4a518  ldstr    aPostworkflowev// "PostWorkflowEvent"
0x4a51d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a522  ldarg.3
0x4a523  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_PostWorkflowEvent()
0x4a528  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4a52d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a532  ldarg.0
0x4a533  ldstr    aOwner// "Owner"
0x4a538  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a53d  ldarg.3
0x4a53e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_Owner()
0x4a543  ldc.i4.0
0x4a544  ldc.i4.0
0x4a545  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write515_Moniker(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker o, bool isNullable, bool needType)
0x4a54a  ldarg.0
0x4a54b  ldstr    aSendemail// "SendEmail"
0x4a550  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a555  ldarg.3
0x4a556  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyExecuteCampaignActivityRequest::get_SendEmail()
0x4a55b  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4a560  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a565  ldarg.0
0x4a566  ldarg.3
0x4a567  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4a56c  ret
```
