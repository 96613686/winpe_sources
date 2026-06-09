# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetDefaultDecription

- ea: `0xa2a0`
- end: `0xa2fe`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetDefaultDecription`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa0c0`

## callees

- `0xa2a0`

## pseudocode

```c

```

## disassembly

```asm
0xa2a0  ldsfld   string [mscorlib]System.String::Empty
0xa2a5  stloc.0
0xa2a6  ldarg.0
0xa2a7  ldarg.1
0xa2a8  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_PrimaryEntityName()
0xa2ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0xa2b2  stloc.1
0xa2b3  ldarg.0
0xa2b4  ldarg.1
0xa2b5  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0xa2ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0xa2bf  stloc.2
0xa2c0  ldloc.1
0xa2c1  brfalse.s loc_A2FC
0xa2c3  ldloc.2
0xa2c4  brfalse.s loc_A2FC
0xa2c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa2cb  stloc.3
0xa2cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa2d1  ldloc.3
0xa2d2  ldstr    aSystemcustomiz_4// "SystemCustomization.RelationshipUtil.De"...
0xa2d7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa2dc  ldc.i4.2
0xa2dd  newarr   [mscorlib]System.Object
0xa2e2  dup
0xa2e3  ldc.i4.0
0xa2e4  ldloc.1
0xa2e5  ldc.i4.1
0xa2e6  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xa2eb  stelem.ref
0xa2ec  dup
0xa2ed  ldc.i4.1
0xa2ee  ldloc.2
0xa2ef  ldc.i4.1
0xa2f0  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0xa2f5  stelem.ref
0xa2f6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa2fb  stloc.0
0xa2fc  ldloc.0
0xa2fd  ret
```
