# Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ConvertStringToPicklist

- ea: `0x1d720`
- end: `0x1d7e0`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ConvertStringToPicklist`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1d920`

## callees

- `0x1d720`
- `0x1dfc0`
- `0x1dfd0`

## string_xrefs

- `0x1d742`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x1d720  ldarg.0
0x1d721  ldstr    aValue// "value"
0x1d726  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d72b  ldarg.1
0x1d72c  ldstr    aEntityname// "entityName"
0x1d731  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d736  ldarg.2
0x1d737  ldstr    aAttributename// "attributeName"
0x1d73c  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d741  ldarg.3
0x1d742  ldstr    aCache// "cache"
0x1d747  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d74c  ldarg.s  4
0x1d74e  ldstr    aOrganizationid// "organizationId"
0x1d753  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x1d758  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::.ctor()
0x1d75d  stloc.0
0x1d75e  ldloc.0
0x1d75f  ldarg.0
0x1d760  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d765  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1d76a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::set_Value(int32)
0x1d76f  ldarg.3
0x1d770  ldarg.1
0x1d771  ldc.i4.1
0x1d772  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1d777  ldarg.2
0x1d778  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1d77d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x1d782  stloc.1
0x1d783  ldstr    aLanguageid// "LanguageId"
0x1d788  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x1d78d  castclass [mscorlib]System.String
0x1d792  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d797  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1d79c  stloc.2
0x1d79d  ldloc.1
0x1d79e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x1d7a3  ldloc.0
0x1d7a4  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::get_Value()
0x1d7a9  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::ContainsKey(var<u1>)
0x1d7ae  brfalse.s loc_1D7DE
0x1d7b0  ldloc.0
0x1d7b1  ldloc.1
0x1d7b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x1d7b7  ldloc.0
0x1d7b8  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::get_Value()
0x1d7bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x1d7c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x1d7c7  ldloc.2
0x1d7c8  ldarg.s  4
0x1d7ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1d7cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d7d4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x1d7d9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist::set_name(string)
0x1d7de  ldloc.0
0x1d7df  ret
```
