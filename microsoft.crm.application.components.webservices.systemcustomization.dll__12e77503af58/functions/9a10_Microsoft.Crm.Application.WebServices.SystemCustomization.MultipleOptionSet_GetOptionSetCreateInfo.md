# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetCreateInfo

- ea: `0x9a10`
- end: `0x9bca`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetCreateInfo`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x9260`

## callees

- `0x190`
- `0x1a0`
- `0x1c0`
- `0x200`
- `0x220`
- `0x270`
- `0x310`
- `0x9a10`
- `0x9d60`
- `0x9d90`

## pseudocode

```c

```

## disassembly

```asm
0x9a10  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9a15  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x9a1a  stloc.0
0x9a1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9a20  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9a25  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9a2a  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetCreateInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9a2f  stloc.1
0x9a30  ldarg.0
0x9a31  ldstr    aType// "type"
0x9a36  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x9a3b  ldstr    aValues// "values"
0x9a40  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x9a45  stloc.2
0x9a46  ldloc.1
0x9a47  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x9a4c  ldarg.0
0x9a4d  ldstr    aSchemaname// "schemaname"
0x9a52  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9a57  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_Name(string)
0x9a5c  ldloc.1
0x9a5d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x9a62  ldarg.0
0x9a63  ldstr    aExternalname// "externalname"
0x9a68  ldsfld   string [mscorlib]System.String::Empty
0x9a6d  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9a72  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ExternalTypeName(string)
0x9a77  ldloc.1
0x9a78  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_DisplayNames()
0x9a7d  ldarg.0
0x9a7e  ldstr    aDisplayname// "displayname"
0x9a83  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9a88  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetStringLabel(string str)
0x9a8d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x9a92  ldloc.1
0x9a93  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Descriptions()
0x9a98  ldarg.0
0x9a99  ldstr    aDescription// "description"
0x9a9e  ldsfld   string [mscorlib]System.String::Empty
0x9aa3  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9aa8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetStringLabel(string str)
0x9aad  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x9ab2  ldarg.0
0x9ab3  ldstr    aParentoptionse// "parentoptionsetid"
0x9ab8  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x9abd  brfalse.s loc_9ADA
0x9abf  ldloc.1
0x9ac0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x9ac5  ldarg.0
0x9ac6  ldstr    aParentoptionse// "parentoptionsetid"
0x9acb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9ad0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name, valuetype [mscorlib]System.Guid defaultValue)
0x9ad5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ParentOptionSetId(valuetype [mscorlib]System.Guid)
0x9ada  ldarg.0
0x9adb  ldstr    aParentoptionse// "parentoptionsetid"
0x9ae0  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x9ae5  brfalse.s loc_9B02
0x9ae7  ldloc.1
0x9ae8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x9aed  ldarg.0
0x9aee  ldstr    aParentoptionse// "parentoptionsetid"
0x9af3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9af8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name, valuetype [mscorlib]System.Guid defaultValue)
0x9afd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ParentOptionSetId(valuetype [mscorlib]System.Guid)
0x9b02  ldloc.2
0x9b03  ldstr    aValue// "value"
0x9b08  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x9b0d  stloc.3
0x9b0e  ldc.i4.0
0x9b0f  stloc.s  4
0x9b11  br       loc_9BBE
0x9b16  ldloc.3
0x9b17  ldloc.s  4
0x9b19  ldelem.ref
0x9b1a  stloc.s  5
0x9b1c  ldloc.s  5
0x9b1e  ldstr    aLabel// "label"
0x9b23  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9b28  stloc.s  6
0x9b2a  ldloc.s  5
0x9b2c  ldstr    aExternalname// "externalname"
0x9b31  ldsfld   string [mscorlib]System.String::Empty
0x9b36  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9b3b  stloc.s  7
0x9b3d  ldloc.s  5
0x9b3f  ldstr    aValue// "value"
0x9b44  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x9b49  stloc.s  8
0x9b4b  ldloc.s  5
0x9b4d  ldstr    aColor// "color"
0x9b52  ldstr    a0000ff// "#0000ff"
0x9b57  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9b5c  stloc.s  9
0x9b5e  ldnull
0x9b5f  stloc.s  0xA
0x9b61  ldloc.s  5
0x9b63  ldstr    aParentvalues// "parentvalues"
0x9b68  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x9b6d  brfalse.s loc_9B7D
0x9b6f  ldloc.s  5
0x9b71  ldstr    aParentvalues// "parentvalues"
0x9b76  callvirt T0x2B000002
0x9b7b  stloc.s  0xA
0x9b7d  ldloc.s  5
0x9b7f  ldstr    aDescription// "description"
0x9b84  ldsfld   string [mscorlib]System.String::Empty
0x9b89  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9b8e  stloc.s  0xB
0x9b90  ldloc.s  8
0x9b92  ldc.i4   0x80000000
0x9b97  beq.s    loc_9BB8
0x9b99  ldloc.1
0x9b9a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x9b9f  ldloc.s  8
0x9ba1  ldloc.s  8
0x9ba3  ldloc.s  9
0x9ba5  ldloc.s  6
0x9ba7  ldloc.s  0xB
0x9ba9  ldloc.0
0x9baa  ldloc.s  0xA
0x9bac  ldloc.s  7
0x9bae  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetOption(int32 optionValue, string optionColor, string optionLabel, string description, int32 languageCode, class [mscorlib]System.Collections.Generic.IList`1<int32> parentValues, string externalValue)
0x9bb3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0x9bb8  ldloc.s  4
0x9bba  ldc.i4.1
0x9bbb  add
0x9bbc  stloc.s  4
0x9bbe  ldloc.s  4
0x9bc0  ldloc.3
0x9bc1  ldlen
0x9bc2  conv.i4
0x9bc3  blt      loc_9B16
0x9bc8  ldloc.1
0x9bc9  ret
```
