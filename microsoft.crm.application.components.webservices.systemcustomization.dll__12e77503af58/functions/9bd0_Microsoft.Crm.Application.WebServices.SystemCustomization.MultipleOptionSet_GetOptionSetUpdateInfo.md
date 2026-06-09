# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetUpdateInfo

- ea: `0x9bd0`
- end: `0x9d57`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetUpdateInfo`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x92a0`

## callees

- `0x190`
- `0x1a0`
- `0x1c0`
- `0x200`
- `0x220`
- `0x270`
- `0x310`
- `0x330`
- `0x9bd0`
- `0x9d60`
- `0x9d90`

## pseudocode

```c

```

## disassembly

```asm
0x9bd0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9bd5  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x9bda  stloc.0
0x9bdb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9be0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9be5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9bea  stloc.1
0x9beb  ldarg.0
0x9bec  ldstr    aOptionsetid// "optionsetid"
0x9bf1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x9bf6  ldloc.1
0x9bf7  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetUpdateInfo::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9bfc  stloc.2
0x9bfd  ldarg.0
0x9bfe  ldstr    aParentoptionse// "parentoptionsetid"
0x9c03  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x9c08  brfalse.s loc_9C25
0x9c0a  ldloc.2
0x9c0b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x9c10  ldarg.0
0x9c11  ldstr    aParentoptionse// "parentoptionsetid"
0x9c16  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9c1b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name, valuetype [mscorlib]System.Guid defaultValue)
0x9c20  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ParentOptionSetId(valuetype [mscorlib]System.Guid)
0x9c25  ldarg.0
0x9c26  ldstr    aType// "type"
0x9c2b  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x9c30  ldstr    aValues// "values"
0x9c35  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x9c3a  ldloc.2
0x9c3b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x9c40  ldarg.0
0x9c41  ldstr    aExternalname// "externalname"
0x9c46  ldsfld   string [mscorlib]System.String::Empty
0x9c4b  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9c50  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ExternalTypeName(string)
0x9c55  ldloc.2
0x9c56  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_DisplayNames()
0x9c5b  ldarg.0
0x9c5c  ldstr    aDisplayname// "displayname"
0x9c61  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9c66  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetStringLabel(string str)
0x9c6b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x9c70  ldloc.2
0x9c71  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Descriptions()
0x9c76  ldarg.0
0x9c77  ldstr    aDescription// "description"
0x9c7c  ldsfld   string [mscorlib]System.String::Empty
0x9c81  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9c86  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetStringLabel(string str)
0x9c8b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x9c90  ldstr    aValue// "value"
0x9c95  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x9c9a  stloc.3
0x9c9b  ldc.i4.0
0x9c9c  stloc.s  4
0x9c9e  br       loc_9D4B
0x9ca3  ldloc.3
0x9ca4  ldloc.s  4
0x9ca6  ldelem.ref
0x9ca7  stloc.s  5
0x9ca9  ldloc.s  5
0x9cab  ldstr    aLabel// "label"
0x9cb0  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9cb5  stloc.s  6
0x9cb7  ldloc.s  5
0x9cb9  ldstr    aExternalname// "externalname"
0x9cbe  ldsfld   string [mscorlib]System.String::Empty
0x9cc3  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9cc8  stloc.s  7
0x9cca  ldloc.s  5
0x9ccc  ldstr    aColor// "color"
0x9cd1  ldstr    a0000ff// "#0000ff"
0x9cd6  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9cdb  stloc.s  8
0x9cdd  ldloc.s  5
0x9cdf  ldstr    aValue// "value"
0x9ce4  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x9ce9  stloc.s  9
0x9ceb  ldnull
0x9cec  stloc.s  0xA
0x9cee  ldloc.s  5
0x9cf0  ldstr    aParentvalues// "parentvalues"
0x9cf5  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x9cfa  brfalse.s loc_9D0A
0x9cfc  ldloc.s  5
0x9cfe  ldstr    aParentvalues// "parentvalues"
0x9d03  callvirt T0x2B000002
0x9d08  stloc.s  0xA
0x9d0a  ldloc.s  5
0x9d0c  ldstr    aDescription// "description"
0x9d11  ldsfld   string [mscorlib]System.String::Empty
0x9d16  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x9d1b  stloc.s  0xB
0x9d1d  ldloc.s  9
0x9d1f  ldc.i4   0x80000000
0x9d24  beq.s    loc_9D45
0x9d26  ldloc.2
0x9d27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x9d2c  ldloc.s  9
0x9d2e  ldloc.s  9
0x9d30  ldloc.s  8
0x9d32  ldloc.s  6
0x9d34  ldloc.s  0xB
0x9d36  ldloc.0
0x9d37  ldloc.s  0xA
0x9d39  ldloc.s  7
0x9d3b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetOptionSetOption(int32 optionValue, string optionColor, string optionLabel, string description, int32 languageCode, class [mscorlib]System.Collections.Generic.IList`1<int32> parentValues, string externalValue)
0x9d40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0x9d45  ldloc.s  4
0x9d47  ldc.i4.1
0x9d48  add
0x9d49  stloc.s  4
0x9d4b  ldloc.s  4
0x9d4d  ldloc.3
0x9d4e  ldlen
0x9d4f  conv.i4
0x9d50  blt      loc_9CA3
0x9d55  ldloc.2
0x9d56  ret
```
