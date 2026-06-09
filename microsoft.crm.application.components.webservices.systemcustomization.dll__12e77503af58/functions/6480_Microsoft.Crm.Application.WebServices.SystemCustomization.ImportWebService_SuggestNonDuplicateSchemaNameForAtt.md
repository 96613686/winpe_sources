# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForAttribute

- ea: `0x6480`
- end: `0x64ce`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForAttribute`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6240`
- `0x6380`

## callees

- `0x6480`
- `0x6a20`

## pseudocode

```c

```

## disassembly

```asm
0x6480  ldc.i4.0
0x6481  stloc.0
0x6482  ldarg.1
0x6483  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6488  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x648d  stloc.1
0x648e  ldarg.0
0x648f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache()
0x6494  ldarg.2
0x6495  ldc.i4.1
0x6496  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x649b  stloc.2
0x649c  br.s     loc_64B5
0x649e  ldarg.1
0x649f  ldloca.s 0
0x64a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64a6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x64ab  call     string [mscorlib]System.String::Concat(string, string)
0x64b0  stloc.1
0x64b1  ldloc.0
0x64b2  ldc.i4.1
0x64b3  add
0x64b4  stloc.0
0x64b5  ldloc.2
0x64b6  ldloc.1
0x64b7  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetSchemaName(string)
0x64bc  ldc.i4.1
0x64bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x64c2  brtrue.s loc_649E
0x64c4  ldloc.1
0x64c5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64ca  brtrue.s loc_649E
0x64cc  ldloc.1
0x64cd  ret
```
