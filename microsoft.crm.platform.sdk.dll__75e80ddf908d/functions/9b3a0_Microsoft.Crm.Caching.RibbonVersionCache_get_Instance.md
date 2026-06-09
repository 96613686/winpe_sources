# Microsoft.Crm.Caching.RibbonVersionCache::get_Instance

- ea: `0x9b3a0`
- end: `0x9b3e3`
- name: `Microsoft.Crm.Caching.RibbonVersionCache::get_Instance`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9b3f0`

## callees

- `0x9b3a0`

## string_xrefs

- `0x9b3b8`: `Microsoft.Crm.Application.Components.Platform`
- `0x9b3bd`: `Microsoft.Crm.Caching.RibbonVersionCacheLoaderProxy`
- `0x9b3d3`: `Microsoft.Crm.Caching.RibbonVersionCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x9b3a0  ldsfld   class Microsoft.Crm.Caching.RibbonVersionCache Microsoft.Crm.Caching.RibbonVersionCache::_cacheInstance
0x9b3a5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.RibbonVersionData>::get_IsCacheLoaderInitialized()
0x9b3aa  brtrue.s loc_9B3DD
0x9b3ac  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x9b3b1  brfalse.s loc_9B3C9
0x9b3b3  ldsfld   class Microsoft.Crm.Caching.RibbonVersionCache Microsoft.Crm.Caching.RibbonVersionCache::_cacheInstance
0x9b3b8  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x9b3bd  ldstr    aMicrosoftCrmCa_110// "Microsoft.Crm.Caching.RibbonVersionCach"...
0x9b3c2  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.RibbonVersionData>::SetLoader(string, string)
0x9b3c7  br.s     loc_9B3DD
0x9b3c9  ldsfld   class Microsoft.Crm.Caching.RibbonVersionCache Microsoft.Crm.Caching.RibbonVersionCache::_cacheInstance
0x9b3ce  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9b3d3  ldstr    aMicrosoftCrmCa_111// "Microsoft.Crm.Caching.RibbonVersionCach"...
0x9b3d8  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.RibbonVersionData>::SetLoader(string, string)
0x9b3dd  ldsfld   class Microsoft.Crm.Caching.RibbonVersionCache Microsoft.Crm.Caching.RibbonVersionCache::_cacheInstance
0x9b3e2  ret
```
