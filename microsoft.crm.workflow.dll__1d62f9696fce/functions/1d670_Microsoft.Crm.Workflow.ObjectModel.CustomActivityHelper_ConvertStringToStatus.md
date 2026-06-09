# Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ConvertStringToStatus

- ea: `0x1d670`
- end: `0x1d71d`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ConvertStringToStatus`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1d920`

## callees

- `0x1dfc0`
- `0x1dfd0`

## string_xrefs

- `0x1d692`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x1d670  ldarg.0
0x1d671  ldstr    aValue// "value"
0x1d676  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d67b  ldarg.1
0x1d67c  ldstr    aEntityname// "entityName"
0x1d681  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d686  ldarg.2
0x1d687  ldstr    aAttributename// "attributeName"
0x1d68c  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d691  ldarg.3
0x1d692  ldstr    aCache// "cache"
0x1d697  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1d69c  ldarg.s  4
0x1d69e  ldstr    aOrganizationid// "organizationId"
0x1d6a3  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x1d6a8  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::.ctor()
0x1d6ad  stloc.0
0x1d6ae  ldloc.0
0x1d6af  ldarg.0
0x1d6b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d6b5  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1d6ba  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::set_Value(int32)
0x1d6bf  ldarg.3
0x1d6c0  ldarg.1
0x1d6c1  ldc.i4.1
0x1d6c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1d6c7  ldarg.2
0x1d6c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1d6cd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x1d6d2  stloc.1
0x1d6d3  ldstr    aLanguageid// "LanguageId"
0x1d6d8  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x1d6dd  castclass [mscorlib]System.String
0x1d6e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d6e7  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1d6ec  stloc.2
0x1d6ed  ldloc.0
0x1d6ee  ldloc.1
0x1d6ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x1d6f4  ldloc.0
0x1d6f5  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::get_Value()
0x1d6fa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x1d6ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x1d704  ldloc.2
0x1d705  ldarg.s  4
0x1d707  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1d70c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d711  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x1d716  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status::set_name(string)
0x1d71b  ldloc.0
0x1d71c  ret
```
