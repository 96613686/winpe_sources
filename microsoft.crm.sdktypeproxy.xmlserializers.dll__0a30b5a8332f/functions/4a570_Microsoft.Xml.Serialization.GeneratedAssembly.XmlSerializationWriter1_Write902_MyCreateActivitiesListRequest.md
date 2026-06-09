# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write902_MyCreateActivitiesListRequest

- ea: `0x4a570`
- end: `0x4a6c2`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write902_MyCreateActivitiesListRequest`
- size: `338`
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
- `0x4a570`

## string_xrefs

- `0x4a5b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a5cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a5e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a60a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a625`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a63b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a653`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a66e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a689`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a6a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a64e`: `TemplateId`
- `0x4a5b0`: `MyCreateActivitiesListRequest`

## pseudocode

```c

```

## disassembly

```asm
0x4a570  ldarg.3
0x4a571  brtrue.s loc_4A580
0x4a573  ldarg.s  4
0x4a575  brfalse.s loc_4A57F
0x4a577  ldarg.0
0x4a578  ldarg.1
0x4a579  ldarg.2
0x4a57a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4a57f  ret
0x4a580  ldarg.s  5
0x4a582  brtrue.s loc_4A5A0
0x4a584  ldarg.3
0x4a585  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4a58a  stloc.0
0x4a58b  ldloc.0
0x4a58c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest
0x4a591  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a596  beq.s    loc_4A5A0
0x4a598  ldarg.0
0x4a599  ldarg.3
0x4a59a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4a59f  throw
0x4a5a0  ldarg.0
0x4a5a1  ldarg.1
0x4a5a2  ldarg.2
0x4a5a3  ldarg.3
0x4a5a4  ldc.i4.0
0x4a5a5  ldnull
0x4a5a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4a5ab  ldarg.s  5
0x4a5ad  brfalse.s loc_4A5BF
0x4a5af  ldarg.0
0x4a5b0  ldstr    aMycreateactivi// "MyCreateActivitiesListRequest"
0x4a5b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a5ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4a5bf  ldarg.3
0x4a5c0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4a5c5  stloc.1
0x4a5c6  ldloc.1
0x4a5c7  brfalse.s loc_4A604
0x4a5c9  ldarg.0
0x4a5ca  ldstr    aOptionalparame_0// "OptionalParameters"
0x4a5cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a5d4  ldnull
0x4a5d5  ldc.i4.0
0x4a5d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4a5db  ldc.i4.0
0x4a5dc  stloc.2
0x4a5dd  br.s     loc_4A5F8
0x4a5df  ldarg.0
0x4a5e0  ldstr    aOptionalparame// "OptionalParameter"
0x4a5e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a5ea  ldloc.1
0x4a5eb  ldloc.2
0x4a5ec  ldelem.ref
0x4a5ed  ldc.i4.1
0x4a5ee  ldc.i4.0
0x4a5ef  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4a5f4  ldloc.2
0x4a5f5  ldc.i4.1
0x4a5f6  add
0x4a5f7  stloc.2
0x4a5f8  ldloc.2
0x4a5f9  ldloc.1
0x4a5fa  ldlen
0x4a5fb  conv.i4
0x4a5fc  blt.s    loc_4A5DF
0x4a5fe  ldarg.0
0x4a5ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4a604  ldarg.0
0x4a605  ldstr    aListid_0// "ListId"
0x4a60a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a60f  ldarg.3
0x4a610  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest::get_ListId()
0x4a615  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4a61a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a61f  ldarg.0
0x4a620  ldstr    aFriendlyname_0// "FriendlyName"
0x4a625  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a62a  ldarg.3
0x4a62b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest::get_FriendlyName()
0x4a630  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a635  ldarg.0
0x4a636  ldstr    aActivity// "Activity"
0x4a63b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a640  ldarg.3
0x4a641  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest::get_Activity()
0x4a646  ldc.i4.0
0x4a647  ldc.i4.0
0x4a648  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x4a64d  ldarg.0
0x4a64e  ldstr    aTemplateid_0// "TemplateId"
0x4a653  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a658  ldarg.3
0x4a659  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest::get_TemplateId()
0x4a65e  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4a663  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a668  ldarg.0
0x4a669  ldstr    aPropagate// "Propagate"
0x4a66e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a673  ldarg.3
0x4a674  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest::get_Propagate()
0x4a679  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4a67e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a683  ldarg.0
0x4a684  ldstr    aOwnershipoptio// "OwnershipOptions"
0x4a689  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a68e  ldarg.0
0x4a68f  ldarg.3
0x4a690  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest::get_OwnershipOptions()
0x4a695  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write890_PropagationOwnershipOptions(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions v)
0x4a69a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4a69f  ldarg.0
0x4a6a0  ldstr    aPostworkflowev// "PostWorkflowEvent"
0x4a6a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a6aa  ldarg.3
0x4a6ab  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MyCreateActivitiesListRequest::get_PostWorkflowEvent()
0x4a6b0  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4a6b5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a6ba  ldarg.0
0x4a6bb  ldarg.3
0x4a6bc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4a6c1  ret
```
