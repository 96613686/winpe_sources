# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPicklistInfo

- ea: `0xbe0`
- end: `0xf2a`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPicklistInfo`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x190`
- `0x1a0`
- `0x1c0`
- `0x200`
- `0x220`
- `0x270`
- `0x310`
- `0xbe0`
- `0xf30`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0xbe0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbe5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xbea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xbef  stloc.0
0xbf0  ldarg.1
0xbf1  ldloc.0
0xbf2  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.PicklistAttributeInfo::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbf7  stloc.1
0xbf8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xbfd  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xc02  stloc.2
0xc03  ldarg.0
0xc04  ldstr    aOptionsetid// "optionsetid"
0xc09  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xc0e  brfalse.s loc_C55
0xc10  ldarg.0
0xc11  ldstr    aOptionsetid// "optionsetid"
0xc16  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xc1b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc20  brtrue.s loc_C55
0xc22  ldloc.1
0xc23  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xc28  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xc2d  ldc.i4.1
0xc2e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_IsGlobal(bool)
0xc33  ldloc.1
0xc34  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xc39  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xc3e  ldarg.0
0xc3f  ldstr    aOptionsetid// "optionsetid"
0xc44  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xc49  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc4e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetId(valuetype [mscorlib]System.Guid)
0xc53  br.s     loc_C66
0xc55  ldloc.1
0xc56  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xc5b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xc60  ldc.i4.0
0xc61  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_IsGlobal(bool)
0xc66  ldarg.2
0xc67  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata
0xc6c  stloc.3
0xc6d  ldloc.3
0xc6e  brfalse.s loc_CA6
0xc70  ldloc.1
0xc71  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xc76  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xc7b  ldloc.3
0xc7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSet()
0xc81  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_IsGlobal()
0xc86  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_IsGlobal(bool)
0xc8b  ldloc.1
0xc8c  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xc91  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xc96  ldloc.3
0xc97  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSet()
0xc9c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Id()
0xca1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetId(valuetype [mscorlib]System.Guid)
0xca6  ldloc.3
0xca7  brfalse  loc_D6C
0xcac  ldloc.3
0xcad  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Locked()
0xcb2  brtrue.s loc_CC4
0xcb4  ldarg.0
0xcb5  ldstr    aValues// "values"
0xcba  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xcbf  brtrue   loc_D6C
0xcc4  ldloc.1
0xcc5  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xcca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xccf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0xcd4  brtrue   loc_D5B
0xcd9  ldloc.3
0xcda  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPicklistOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata::get_PicklistOptions()
0xcdf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistOption>::GetEnumerator()
0xce4  stloc.s  4
0xce6  br.s     loc_D44
0xce8  ldloc.s  4
0xcea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistOption>::get_Current()
0xcef  dup
0xcf0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0xcf5  ldloc.2
0xcf6  ldloc.0
0xcf7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcfc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xd01  stloc.s  5
0xd03  dup
0xd04  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0xd09  stloc.s  6
0xd0b  dup
0xd0c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Color()
0xd11  stloc.s  7
0xd13  dup
0xd14  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_ExternalValue()
0xd19  stloc.s  8
0xd1b  dup
0xd1c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Descriptions()
0xd21  ldloc.2
0xd22  ldloc.0
0xd23  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd28  stloc.s  9
0xd2a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_ParentValues()
0xd2f  stloc.s  0xA
0xd31  ldloc.1
0xd32  ldloc.s  6
0xd34  ldloc.s  7
0xd36  ldloc.s  0xA
0xd38  ldloc.s  5
0xd3a  ldloc.s  9
0xd3c  ldloc.2
0xd3d  ldloc.s  8
0xd3f  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddPicklistOption(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.PicklistAttributeInfo picklistInfo, int32 optionValue, string optionColor, class [mscorlib]System.Collections.Generic.IList`1<int32> parentValues, string optionLabel, string optionDescription, int32 languageCode, string externalValue)
0xd44  ldloc.s  4
0xd46  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd4b  brtrue.s loc_CE8
0xd4d  leave.s  loc_D5B
0xd4f  ldloc.s  4
0xd51  brfalse.s loc_D5A
0xd53  ldloc.s  4
0xd55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd5a  endfinally
0xd5b  ldloc.1
0xd5c  ldloc.3
0xd5d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata::get_DefaultValue()
0xd62  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.PicklistAttributeInfo::set_DefaultValue(int32)
0xd67  br       loc_E9D
0xd6c  ldc.i4   0x80000000
0xd71  stloc.s  0xC
0xd73  ldloc.1
0xd74  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xd79  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xd7e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0xd83  brtrue   loc_E6F
0xd88  ldarg.0
0xd89  ldstr    aValues// "values"
0xd8e  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xd93  stloc.s  0xB
0xd95  ldloc.s  0xB
0xd97  ldstr    aValue// "value"
0xd9c  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0xda1  stloc.s  0xD
0xda3  ldc.i4.0
0xda4  stloc.s  0xE
0xda6  br       loc_E48
0xdab  ldloc.s  0xD
0xdad  ldloc.s  0xE
0xdaf  ldelem.ref
0xdb0  stloc.s  0xF
0xdb2  ldloc.s  0xF
0xdb4  ldstr    aLabel// "label"
0xdb9  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xdbe  stloc.s  0x10
0xdc0  ldloc.s  0xF
0xdc2  ldstr    aValue// "value"
0xdc7  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xdcc  stloc.s  0x11
0xdce  ldloc.s  0xF
0xdd0  ldstr    aColor// "color"
0xdd5  ldstr    a0000ff// "#0000ff"
0xdda  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xddf  stloc.s  0x12
0xde1  ldloc.s  0xF
0xde3  ldstr    aExternalname// "externalname"
0xde8  ldsfld   string [mscorlib]System.String::Empty
0xded  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xdf2  stloc.s  0x13
0xdf4  ldloc.s  0xF
0xdf6  ldstr    aDescription// "description"
0xdfb  ldsfld   string [mscorlib]System.String::Empty
0xe00  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xe05  stloc.s  0x14
0xe07  ldnull
0xe08  stloc.s  0x15
0xe0a  ldloc.s  0xF
0xe0c  ldstr    aParentvalues// "parentvalues"
0xe11  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xe16  brfalse.s loc_E26
0xe18  ldloc.s  0xF
0xe1a  ldstr    aParentvalues// "parentvalues"
0xe1f  callvirt T0x2B000002
0xe24  stloc.s  0x15
0xe26  ldloc.s  0x11
0xe28  ldc.i4   0x80000000
0xe2d  beq.s    loc_E42
0xe2f  ldloc.1
0xe30  ldloc.s  0x11
0xe32  ldloc.s  0x12
0xe34  ldloc.s  0x15
0xe36  ldloc.s  0x10
0xe38  ldloc.s  0x14
0xe3a  ldloc.2
0xe3b  ldloc.s  0x13
0xe3d  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::AddPicklistOption(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.PicklistAttributeInfo picklistInfo, int32 optionValue, string optionColor, class [mscorlib]System.Collections.Generic.IList`1<int32> parentValues, string optionLabel, string optionDescription, int32 languageCode, string externalValue)
0xe42  ldloc.s  0xE
0xe44  ldc.i4.1
0xe45  add
0xe46  stloc.s  0xE
0xe48  ldloc.s  0xE
0xe4a  ldloc.s  0xD
0xe4c  ldlen
0xe4d  conv.i4
0xe4e  blt      loc_DAB
0xe53  ldloc.s  0xB
0xe55  ldstr    aDefault// "default"
0xe5a  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xe5f  brfalse.s loc_E6F
0xe61  ldloc.s  0xB
0xe63  ldstr    aDefault// "default"
0xe68  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xe6d  stloc.s  0xC
0xe6f  ldarg.0
0xe70  ldstr    aDefaultvalue// "defaultvalue"
0xe75  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xe7a  brfalse.s loc_E89
0xe7c  ldarg.0
0xe7d  ldstr    aDefaultvalue// "defaultvalue"
0xe82  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xe87  stloc.s  0xC
0xe89  ldloc.1
0xe8a  ldc.i4   0x80000000
0xe8f  ldloc.s  0xC
0xe91  beq.s    loc_E97
0xe93  ldloc.s  0xC
0xe95  br.s     loc_E98
0xe97  ldc.i4.m1
0xe98  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.PicklistAttributeInfo::set_DefaultValue(int32)
0xe9d  ldarg.0
0xe9e  ldstr    aParentenumattr// "parentenumattributeid"
0xea3  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xea8  brfalse.s loc_EC9
0xeaa  ldarg.0
0xeab  ldstr    aParentenumattr// "parentenumattributeid"
0xeb0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xeb5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name, valuetype [mscorlib]System.Guid defaultValue)
0xeba  stloc.s  0x16
0xebc  ldloc.1
0xebd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0xec2  ldloc.s  0x16
0xec4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ParentEnumAttributeId(valuetype [mscorlib]System.Guid)
0xec9  ldarg.0
0xeca  ldstr    aSourcetype// "sourcetype"
0xecf  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xed4  brfalse.s loc_EE2
0xed6  ldloc.1
0xed7  ldarg.0
0xed8  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDataSourceType Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
0xedd  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_SourceType(int32)
0xee2  ldarg.0
0xee3  ldstr    aFormuladefinit// "formuladefinition"
0xee8  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xeed  brfalse.s loc_F00
0xeef  ldloc.1
0xef0  ldarg.0
0xef1  ldstr    aFormuladefinit// "formuladefinition"
0xef6  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xefb  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_FormulaDefinition(string)
0xf00  ldarg.0
0xf01  ldstr    aOptionsetexter// "optionsetexternalname"
0xf06  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xf0b  brfalse.s loc_F28
0xf0d  ldloc.1
0xf0e  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0xf13  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0xf18  ldarg.0
0xf19  ldstr    aOptionsetexter// "optionsetexternalname"
0xf1e  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xf23  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ExternalTypeName(string)
0xf28  ldloc.1
0xf29  ret
```
