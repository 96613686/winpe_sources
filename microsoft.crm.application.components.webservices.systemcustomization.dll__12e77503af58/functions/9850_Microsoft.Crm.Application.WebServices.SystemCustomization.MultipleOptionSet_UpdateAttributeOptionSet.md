# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::UpdateAttributeOptionSet

- ea: `0x9850`
- end: `0x9a07`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::UpdateAttributeOptionSet`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x190`
- `0x1a0`
- `0x1c0`
- `0x200`
- `0x220`
- `0x270`
- `0x330`
- `0x9850`
- `0x9d90`

## pseudocode

```c

```

## disassembly

```asm
0x9850  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteOptionSet()
0x9855  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x985a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x985f  brtrue.s loc_9872
0x9861  ldc.i4   0x80040277
0x9866  ldc.i4.0
0x9867  newarr   [mscorlib]System.Object
0x986c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9871  throw
0x9872  ldarg.1
0x9873  ldstr    aType// "type"
0x9878  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x987d  stloc.0
0x987e  ldloc.0
0x987f  ldstr    aOptionsetid// "optionsetid"
0x9884  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x9889  brfalse.s loc_989D
0x988b  ldloc.0
0x988c  ldstr    aOptionsetid// "optionsetid"
0x9891  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9896  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x989b  brfalse.s loc_989E
0x989d  ret
0x989e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x98a3  ldc.i4.1
0x98a4  ldc.i4.1
0x98a5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetByIdDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSets(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetGlobalFilters, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetTypeFilters)
0x98aa  ldloc.0
0x98ab  ldstr    aOptionsetid// "optionsetid"
0x98b0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x98b5  ldloca.s 1
0x98b7  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>::TryGetValue(var<u1>, !!T0)
0x98bc  brtrue.s loc_98CF
0x98be  ldc.i4   0x80040363
0x98c3  ldc.i4.0
0x98c4  newarr   [mscorlib]System.Object
0x98c9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x98ce  throw
0x98cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x98d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x98d9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x98de  stloc.2
0x98df  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x98e4  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x98e9  stloc.3
0x98ea  ldloc.1
0x98eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Id()
0x98f0  ldloc.2
0x98f1  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetUpdateInfo::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x98f6  stloc.s  4
0x98f8  ldloc.0
0x98f9  ldstr    aValues// "values"
0x98fe  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x9903  ldloc.s  4
0x9905  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x990a  ldloc.1
0x990b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_ExternalTypeName()
0x9910  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ExternalTypeName(string)
0x9915  ldloc.s  4
0x9917  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_DisplayNames()
0x991c  ldloc.1
0x991d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_DisplayNames()
0x9922  ldloc.3
0x9923  ldloc.2
0x9924  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9929  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x992e  ldloc.s  4
0x9930  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Descriptions()
0x9935  ldloc.1
0x9936  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Descriptions()
0x993b  ldloc.3
0x993c  ldloc.2
0x993d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9942  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x9947  ldstr    aValue// "value"
0x994c  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x9951  stloc.s  5
0x9953  ldc.i4.0
0x9954  stloc.s  6
0x9956  br       loc_99DD
0x995b  ldloc.s  5
0x995d  ldloc.s  6
0x995f  ldelem.ref
0x9960  dup
0x9961  ldstr    aLabel// "label"
0x9966  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x996b  stloc.s  7
0x996d  dup
0x996e  ldstr    aExternalname// "externalname"
0x9973  ldsfld   string [mscorlib]System.String::Empty
0x9978  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x997d  stloc.s  8
0x997f  dup
0x9980  ldstr    aValue// "value"
0x9985  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x998a  stloc.s  9
0x998c  dup
0x998d  ldstr    aColor// "color"
0x9992  ldstr    a0000ff// "#0000ff"
0x9997  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x999c  stloc.s  0xA
0x999e  ldstr    aDescription// "description"
0x99a3  ldsfld   string [mscorlib]System.String::Empty
0x99a8  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x99ad  stloc.s  0xB
0x99af  ldloc.s  9
0x99b1  ldc.i4   0x80000000
0x99b6  beq.s    loc_99D7
0x99b8  ldloc.s  4
0x99ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x99bf  ldloc.s  9
0x99c1  ldloc.s  9
0x99c3  ldloc.s  0xA
0x99c5  ldloc.s  7
0x99c7  ldloc.s  0xB
0x99c9  ldloc.3
0x99ca  ldnull
0x99cb  ldloc.s  8
0x99cd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetOption(int32 optionValue, string optionColor, string optionLabel, string description, int32 languageCode, class [mscorlib]System.Collections.Generic.IList`1<int32> parentValues, string externalValue)
0x99d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0x99d7  ldloc.s  6
0x99d9  ldc.i4.1
0x99da  add
0x99db  stloc.s  6
0x99dd  ldloc.s  6
0x99df  ldloc.s  5
0x99e1  ldlen
0x99e2  conv.i4
0x99e3  blt      loc_995B
0x99e8  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetService::.ctor()
0x99ed  ldloc.1
0x99ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Id()
0x99f3  ldloc.s  4
0x99f5  ldc.i4.1
0x99f6  ldarg.0
0x99f7  call     instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0x99fc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9a01  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9a06  ret
```
