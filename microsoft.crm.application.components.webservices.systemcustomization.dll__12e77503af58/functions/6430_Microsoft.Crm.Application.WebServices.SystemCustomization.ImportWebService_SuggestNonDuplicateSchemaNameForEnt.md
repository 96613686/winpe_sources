# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForEntity

- ea: `0x6430`
- end: `0x6475`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForEntity`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ed0`

## callees

- `0x6430`
- `0x6a20`

## pseudocode

```c

```

## disassembly

```asm
0x6430  ldc.i4.0
0x6431  stloc.0
0x6432  ldarg.1
0x6433  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6438  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x643d  stloc.1
0x643e  br.s     loc_6457
0x6440  ldarg.1
0x6441  ldloca.s 0
0x6443  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6448  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x644d  call     string [mscorlib]System.String::Concat(string, string)
0x6452  stloc.1
0x6453  ldloc.0
0x6454  ldc.i4.1
0x6455  add
0x6456  stloc.0
0x6457  ldarg.0
0x6458  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache()
0x645d  ldloc.1
0x645e  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetSchemaName(string)
0x6463  ldc.i4.1
0x6464  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x6469  brtrue.s loc_6440
0x646b  ldloc.1
0x646c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6471  brtrue.s loc_6440
0x6473  ldloc.1
0x6474  ret
```
