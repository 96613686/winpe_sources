# Microsoft.Crm.Metadata.AttributeService::CreateOptionSet

- ea: `0x1d850`
- end: `0x1da0a`
- name: `Microsoft.Crm.Metadata.AttributeService::CreateOptionSet`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1c170`

## callees

- `0x18470`
- `0x184f0`
- `0x18740`
- `0x18760`
- `0x1d850`
- `0x22840`
- `0x23280`
- `0x40f10`
- `0x4a800`
- `0x4ab20`
- `0x4ab30`
- `0x4ab40`
- `0x4ab50`
- `0x4ab60`
- `0x4abb0`
- `0x4abc0`
- `0x4b080`

## string_xrefs

- `0x1d979`: `OptionSetId should not have been changed inside the OptionSetService.CreateInternal method. Initial OptionSetId = ({0}). New OptionSetId = ({1})`

## pseudocode

```c

```

## disassembly

```asm
0x1d850  ldarg.0
0x1d851  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1d856  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d85b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x1d860  brtrue   loc_1D9C0
0x1d865  ldarg.0
0x1d866  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1d86b  isinst   Microsoft.Crm.Metadata.OptionSetCreateInfo
0x1d870  stloc.0
0x1d871  ldloc.0
0x1d872  brtrue.s loc_1D886
0x1d874  ldarg.0
0x1d875  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1d87a  castclass Microsoft.Crm.Metadata.OptionSetForAttributeInfo
0x1d87f  ldarg.2
0x1d880  newobj   instance void Microsoft.Crm.Metadata.OptionSetCreateInfo::.ctor(class Microsoft.Crm.Metadata.OptionSetForAttributeInfo optionSetForAttributeInfo, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x1d885  stloc.0
0x1d886  ldarg.0
0x1d887  call     valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType Microsoft.Crm.Metadata.AttributeService::GetOptionSetTypeForEnum(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo)
0x1d88c  stloc.1
0x1d88d  ldloc.0
0x1d88e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d893  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x1d898  ldstr    aOptionsetid// "optionsetid"
0x1d89d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1d8a2  brtrue.s loc_1D8BB
0x1d8a4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d8a9  ldloc.0
0x1d8aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d8af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x1d8b4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d8b9  brfalse.s loc_1D8CB
0x1d8bb  ldloc.0
0x1d8bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d8c1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1d8c6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetId(valuetype [mscorlib]System.Guid)
0x1d8cb  ldloc.0
0x1d8cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d8d1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x1d8d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d8db  brfalse.s loc_1D8FA
0x1d8dd  ldloc.0
0x1d8de  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d8e3  ldarg.0
0x1d8e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d8e9  ldarg.1
0x1d8ea  ldarg.2
0x1d8eb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1d8f0  call     string Microsoft.Crm.Metadata.AttributeService::GenerateLocalOptionSetName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription attributeDescription, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x1d8f5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_Name(string)
0x1d8fa  ldloc.0
0x1d8fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.OptionSetInfo::get_DisplayNames()
0x1d900  brtrue.s loc_1D90E
0x1d902  ldloc.0
0x1d903  ldarg.0
0x1d904  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_DisplayNames()
0x1d909  callvirt instance void Microsoft.Crm.Metadata.OptionSetInfo::set_DisplayNames(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection value)
0x1d90e  ldloc.0
0x1d90f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.OptionSetInfo::get_Descriptions()
0x1d914  brtrue.s loc_1D922
0x1d916  ldloc.0
0x1d917  ldarg.0
0x1d918  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_Description()
0x1d91d  callvirt instance void Microsoft.Crm.Metadata.OptionSetInfo::set_Descriptions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection value)
0x1d922  ldloc.0
0x1d923  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d928  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x1d92d  ldstr    aOptionsettype// "optionsettype"
0x1d932  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1d937  brfalse.s loc_1D945
0x1d939  ldloc.0
0x1d93a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d93f  ldloc.1
0x1d940  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetType(int32)
0x1d945  ldnull
0x1d946  ldloc.0
0x1d947  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.OptionSetInfo::get_IntroducedVersion()
0x1d94c  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1d951  brfalse.s loc_1D95F
0x1d953  ldloc.0
0x1d954  ldarg.0
0x1d955  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.AttributeInfo::get_IntroducedVersion()
0x1d95a  callvirt instance void Microsoft.Crm.Metadata.OptionSetInfo::set_IntroducedVersion(class [mscorlib]System.Version value)
0x1d95f  ldloc.0
0x1d960  ldarg.1
0x1d961  ldarg.2
0x1d962  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.OptionSetService::CreateInternal(class Microsoft.Crm.Metadata.OptionSetCreateInfo optionSetInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1d967  stloc.2
0x1d968  ldloc.0
0x1d969  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d96e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x1d973  ldloc.2
0x1d974  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d979  ldstr    aOptionsetidSho// "OptionSetId should not have been change"...
0x1d97e  ldc.i4.2
0x1d97f  newarr   [mscorlib]System.Object
0x1d984  dup
0x1d985  ldc.i4.0
0x1d986  ldloc.0
0x1d987  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d98c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x1d991  box      [mscorlib]System.Guid
0x1d996  stelem.ref
0x1d997  dup
0x1d998  ldc.i4.1
0x1d999  ldloc.2
0x1d99a  box      [mscorlib]System.Guid
0x1d99f  stelem.ref
0x1d9a0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x1d9a5  ldarg.0
0x1d9a6  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1d9ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d9b0  ldloc.0
0x1d9b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d9b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x1d9bb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetId(valuetype [mscorlib]System.Guid)
0x1d9c0  ldarg.0
0x1d9c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d9c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1d9cb  ldstr    aOptionsetid// "optionsetid"
0x1d9d0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1d9d5  brtrue.s loc_1D9EE
0x1d9d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d9dc  ldarg.0
0x1d9dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d9e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x1d9e7  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d9ec  brfalse.s loc_1DA09
0x1d9ee  ldarg.0
0x1d9ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d9f4  ldarg.0
0x1d9f5  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1d9fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1d9ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x1da04  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_OptionSetId(valuetype [mscorlib]System.Guid)
0x1da09  ret
```
