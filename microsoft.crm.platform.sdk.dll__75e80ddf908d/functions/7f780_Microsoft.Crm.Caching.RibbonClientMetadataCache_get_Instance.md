# Microsoft.Crm.Caching.RibbonClientMetadataCache::get_Instance

- ea: `0x7f780`
- end: `0x7f7ca`
- name: `Microsoft.Crm.Caching.RibbonClientMetadataCache::get_Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7f780`

## string_xrefs

- `0x7f79f`: `Microsoft.Crm.Application.Components.Platform`
- `0x7f7a4`: `Microsoft.Crm.Caching.RibbonClientMetadataDataCacheLoaderProxy`
- `0x7f7ba`: `Microsoft.Crm.Caching.RibbonClientMetadataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x7f780  ldsfld   class Microsoft.Crm.Caching.RibbonClientMetadataCache Microsoft.Crm.Caching.RibbonClientMetadataCache::_innerCache
0x7f785  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.RibbonClientMetadataCacheValue>::get_IsCacheLoaderInitialized()
0x7f78a  brtrue.s loc_7F7C4
0x7f78c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x7f791  brfalse.s loc_7F7B0
0x7f793  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x7f798  brtrue.s loc_7F7B0
0x7f79a  ldsfld   class Microsoft.Crm.Caching.RibbonClientMetadataCache Microsoft.Crm.Caching.RibbonClientMetadataCache::_innerCache
0x7f79f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x7f7a4  ldstr    aMicrosoftCrmCa_29// "Microsoft.Crm.Caching.RibbonClientMetad"...
0x7f7a9  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.RibbonClientMetadataCacheValue>::SetLoader(string, string)
0x7f7ae  br.s     loc_7F7C4
0x7f7b0  ldsfld   class Microsoft.Crm.Caching.RibbonClientMetadataCache Microsoft.Crm.Caching.RibbonClientMetadataCache::_innerCache
0x7f7b5  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x7f7ba  ldstr    aMicrosoftCrmCa_30// "Microsoft.Crm.Caching.RibbonClientMetad"...
0x7f7bf  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.RibbonClientMetadataCacheValue>::SetLoader(string, string)
0x7f7c4  ldsfld   class Microsoft.Crm.Caching.RibbonClientMetadataCache Microsoft.Crm.Caching.RibbonClientMetadataCache::_innerCache
0x7f7c9  ret
```
