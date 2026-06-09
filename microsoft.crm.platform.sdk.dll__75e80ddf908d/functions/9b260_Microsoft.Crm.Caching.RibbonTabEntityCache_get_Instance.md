# Microsoft.Crm.Caching.RibbonTabEntityCache::get_Instance

- ea: `0x9b260`
- end: `0x9b2a3`
- name: `Microsoft.Crm.Caching.RibbonTabEntityCache::get_Instance`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9ad00`

## callees

- `0x9b260`

## string_xrefs

- `0x9b278`: `Microsoft.Crm.Application.Components.Platform`
- `0x9b27d`: `Microsoft.Crm.Caching.RibbonTabEntityCacheLoaderProxy`
- `0x9b293`: `Microsoft.Crm.Caching.RibbonTabEntityCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x9b260  ldsfld   class Microsoft.Crm.Caching.RibbonTabEntityCache Microsoft.Crm.Caching.RibbonTabEntityCache::_cacheInstance
0x9b265  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, string>::get_IsCacheLoaderInitialized()
0x9b26a  brtrue.s loc_9B29D
0x9b26c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x9b271  brfalse.s loc_9B289
0x9b273  ldsfld   class Microsoft.Crm.Caching.RibbonTabEntityCache Microsoft.Crm.Caching.RibbonTabEntityCache::_cacheInstance
0x9b278  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x9b27d  ldstr    aMicrosoftCrmCa_108// "Microsoft.Crm.Caching.RibbonTabEntityCa"...
0x9b282  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, string>::SetLoader(string, string)
0x9b287  br.s     loc_9B29D
0x9b289  ldsfld   class Microsoft.Crm.Caching.RibbonTabEntityCache Microsoft.Crm.Caching.RibbonTabEntityCache::_cacheInstance
0x9b28e  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9b293  ldstr    aMicrosoftCrmCa_109// "Microsoft.Crm.Caching.RibbonTabEntityCa"...
0x9b298  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, string>::SetLoader(string, string)
0x9b29d  ldsfld   class Microsoft.Crm.Caching.RibbonTabEntityCache Microsoft.Crm.Caching.RibbonTabEntityCache::_cacheInstance
0x9b2a2  ret
```
