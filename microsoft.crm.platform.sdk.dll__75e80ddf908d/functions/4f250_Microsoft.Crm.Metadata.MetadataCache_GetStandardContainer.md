# Microsoft.Crm.Metadata.MetadataCache::GetStandardContainer

- ea: `0x4f250`
- end: `0x4f291`
- name: `Microsoft.Crm.Metadata.MetadataCache::GetStandardContainer`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x189d0`
- `0x4e840`

## callees

- `0x19820`
- `0x4ab60`
- `0x4e2e0`
- `0x4f250`

## string_xrefs

- `0x4f268`: `Standard cache must be a ServerDynamicMetadataCache`
- `0x4f285`: `Standard cache missing container`

## pseudocode

```c

```

## disassembly

```asm
0x4f250  ldnull
0x4f251  stloc.0
0x4f252  ldarg.0
0x4f253  ldloca.s 0
0x4f255  call     void Microsoft.Crm.Metadata.MetadataCache::GetStandardInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry& organizationCacheEntry)
0x4f25a  ldloc.0
0x4f25b  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry::cache
0x4f260  isinst   Microsoft.Crm.Metadata.ServerDynamicMetadataCache
0x4f265  dup
0x4f266  brtrue.s loc_4F273
0x4f268  ldstr    aStandardCacheM_0// "Standard cache must be a ServerDynamicM"...
0x4f26d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x4f272  throw
0x4f273  callvirt instance class Microsoft.Crm.Metadata.IMetadataCacheDataProvider Microsoft.Crm.Metadata.ServerDynamicMetadataCache::get_Provider()
0x4f278  callvirt instance class Microsoft.Crm.Metadata.IMetadataContainer Microsoft.Crm.Metadata.IServerMetadataCacheDataProvider::get_MetadataContainer()
0x4f27d  castclass Microsoft.Crm.Metadata.DynamicMetadataContainer
0x4f282  dup
0x4f283  brtrue.s loc_4F290
0x4f285  ldstr    aStandardCacheM_1// "Standard cache missing container"
0x4f28a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmMissingMemberException::.ctor(string)
0x4f28f  throw
0x4f290  ret
```
