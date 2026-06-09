# Microsoft.Crm.Caching.RibbonTabDisplayCache::get_InstanceForBatchLoading

- ea: `0x9b150`
- end: `0x9b193`
- name: `Microsoft.Crm.Caching.RibbonTabDisplayCache::get_InstanceForBatchLoading`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x9b150`

## string_xrefs

- `0x9b168`: `Microsoft.Crm.Application.Components.Platform`
- `0x9b16d`: `Microsoft.Crm.Caching.RibbonTabDisplayCacheLoaderProxy`
- `0x9b183`: `Microsoft.Crm.Caching.RibbonTabDisplayCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x9b150  ldsfld   class Microsoft.Crm.Caching.RibbonTabDisplayCache Microsoft.Crm.Caching.RibbonTabDisplayCache::_cacheInstance
0x9b155  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.RibbonTabDisplayCacheKey, class Microsoft.Crm.Caching.RibbonTabDisplayCacheValue>::get_IsCacheLoaderInitialized()
0x9b15a  brtrue.s loc_9B18D
0x9b15c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x9b161  brfalse.s loc_9B179
0x9b163  ldsfld   class Microsoft.Crm.Caching.RibbonTabDisplayCache Microsoft.Crm.Caching.RibbonTabDisplayCache::_cacheInstance
0x9b168  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x9b16d  ldstr    aMicrosoftCrmCa_106// "Microsoft.Crm.Caching.RibbonTabDisplayC"...
0x9b172  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.RibbonTabDisplayCacheKey, class Microsoft.Crm.Caching.RibbonTabDisplayCacheValue>::SetLoader(string, string)
0x9b177  br.s     loc_9B18D
0x9b179  ldsfld   class Microsoft.Crm.Caching.RibbonTabDisplayCache Microsoft.Crm.Caching.RibbonTabDisplayCache::_cacheInstance
0x9b17e  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9b183  ldstr    aMicrosoftCrmCa_107// "Microsoft.Crm.Caching.RibbonTabDisplayC"...
0x9b188  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.RibbonTabDisplayCacheKey, class Microsoft.Crm.Caching.RibbonTabDisplayCacheValue>::SetLoader(string, string)
0x9b18d  ldsfld   class Microsoft.Crm.Caching.RibbonTabDisplayCache Microsoft.Crm.Caching.RibbonTabDisplayCache::_cacheInstance
0x9b192  ret
```
