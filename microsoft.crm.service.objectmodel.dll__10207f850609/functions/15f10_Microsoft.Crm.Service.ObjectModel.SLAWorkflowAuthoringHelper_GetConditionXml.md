# Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::GetConditionXml

- ea: `0x15f10`
- end: `0x15f9f`
- name: `Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::GetConditionXml`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15700`

## callees

- `0x15f10`

## string_xrefs

- `0x15f1a`: `applicablewhenxml`
- `0x15f27`: `applicablewhenxml`

## pseudocode

```c

```

## disassembly

```asm
0x15f10  ldnull
0x15f11  stloc.0
0x15f12  ldnull
0x15f13  stloc.1
0x15f14  ldarg.1
0x15f15  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x15f1a  ldstr    aApplicablewhen// "applicablewhenxml"
0x15f1f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x15f24  brfalse.s loc_15F3C
0x15f26  ldarg.1
0x15f27  ldstr    aApplicablewhen// "applicablewhenxml"
0x15f2c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15f31  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15f36  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x15f3b  stloc.1
0x15f3c  ldarg.2
0x15f3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15f42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x15f47  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x15f4c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15f51  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x15f56  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x15f5b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x15f60  stloc.0
0x15f61  ldarg.0
0x15f62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15f67  ldstr    aAndConditionCo_0// "<and><condition><column id=\"colEntity"...
0x15f6c  ldc.i4.2
0x15f6d  newarr   [mscorlib]System.Object
0x15f72  dup
0x15f73  ldc.i4.0
0x15f74  ldarg.2
0x15f75  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x15f7a  stelem.ref
0x15f7b  dup
0x15f7c  ldc.i4.1
0x15f7d  ldloc.0
0x15f7e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x15f83  stelem.ref
0x15f84  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15f89  stfld    string Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::defaultApplicableWhenCondition
0x15f8e  ldloc.1
0x15f8f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15f94  brtrue.s loc_15F98
0x15f96  ldloc.1
0x15f97  ret
0x15f98  ldarg.0
0x15f99  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAWorkflowAuthoringHelper::defaultApplicableWhenCondition
0x15f9e  ret
```
