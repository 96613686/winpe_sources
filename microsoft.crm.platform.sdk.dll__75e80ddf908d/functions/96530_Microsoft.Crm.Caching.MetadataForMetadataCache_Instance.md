# Microsoft.Crm.Caching.MetadataForMetadataCache::Instance

- ea: `0x96530`
- end: `0x965a0`
- name: `Microsoft.Crm.Caching.MetadataForMetadataCache::Instance`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x708f0`

## callees

- `0x96530`

## string_xrefs

- `0x96559`: `IsInSyncServiceContext`
- `0x96548`: `Microsoft.Crm.Application.Outlook.Components.Platform`
- `0x9654d`: `Microsoft.Crm.Caching.ClientMetadataForMetadataCacheLoader`
- `0x9657a`: `Microsoft.Crm.Caching.SyncServiceMetadataForMetadataCacheLoaderProxy`
- `0x96590`: `Microsoft.Crm.Caching.MetadataForMetadataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x96530  ldsfld   class Microsoft.Crm.Caching.MetadataForMetadataCache Microsoft.Crm.Caching.MetadataForMetadataCache::_staticInstance
0x96535  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [mscorlib]System.Version, class Microsoft.Crm.Caching.MetadataForMetadataSharedOrganizationData>::get_IsCacheLoaderInitialized()
0x9653a  brtrue.s loc_9659A
0x9653c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x96541  brfalse.s loc_96559
0x96543  ldsfld   class Microsoft.Crm.Caching.MetadataForMetadataCache Microsoft.Crm.Caching.MetadataForMetadataCache::_staticInstance
0x96548  ldstr    aMicrosoftCrmAp_3// "Microsoft.Crm.Application.Outlook.Compo"...
0x9654d  ldstr    aMicrosoftCrmCa_57// "Microsoft.Crm.Caching.ClientMetadataFor"...
0x96552  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [mscorlib]System.Version, class Microsoft.Crm.Caching.MetadataForMetadataSharedOrganizationData>::SetLoader(string, string)
0x96557  br.s     loc_9659A
0x96559  ldstr    aIsinsyncservic// "IsInSyncServiceContext"
0x9655e  ldc.i4.0
0x9655f  box      [mscorlib]System.Boolean
0x96564  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x96569  unbox.any [mscorlib]System.Boolean
0x9656e  brfalse.s loc_96586
0x96570  ldsfld   class Microsoft.Crm.Caching.MetadataForMetadataCache Microsoft.Crm.Caching.MetadataForMetadataCache::_staticInstance
0x96575  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9657a  ldstr    aMicrosoftCrmCa_58// "Microsoft.Crm.Caching.SyncServiceMetada"...
0x9657f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [mscorlib]System.Version, class Microsoft.Crm.Caching.MetadataForMetadataSharedOrganizationData>::SetLoader(string, string)
0x96584  br.s     loc_9659A
0x96586  ldsfld   class Microsoft.Crm.Caching.MetadataForMetadataCache Microsoft.Crm.Caching.MetadataForMetadataCache::_staticInstance
0x9658b  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x96590  ldstr    aMicrosoftCrmCa_59// "Microsoft.Crm.Caching.MetadataForMetada"...
0x96595  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class [mscorlib]System.Version, class Microsoft.Crm.Caching.MetadataForMetadataSharedOrganizationData>::SetLoader(string, string)
0x9659a  ldsfld   class Microsoft.Crm.Caching.MetadataForMetadataCache Microsoft.Crm.Caching.MetadataForMetadataCache::_staticInstance
0x9659f  ret
```
