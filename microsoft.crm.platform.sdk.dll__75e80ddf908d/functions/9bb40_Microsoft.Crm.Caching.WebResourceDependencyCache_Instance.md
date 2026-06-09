# Microsoft.Crm.Caching.WebResourceDependencyCache::Instance

- ea: `0x9bb40`
- end: `0x9bb8a`
- name: `Microsoft.Crm.Caching.WebResourceDependencyCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x9bb40`

## string_xrefs

- `0x9bb5f`: `Microsoft.Crm.Application.Components.Platform`
- `0x9bb64`: `Microsoft.Crm.Caching.WebResourceDependencyCacheLoaderProxy`
- `0x9bb7a`: `Microsoft.Crm.Caching.WebResourceDependencyCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x9bb40  ldsfld   class Microsoft.Crm.Caching.WebResourceDependencyCache Microsoft.Crm.Caching.WebResourceDependencyCache::_cacheInstance
0x9bb45  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.IWebResourceDependencyCacheKey, class Microsoft.Crm.Caching.IWebResourceDependencyCacheValue>::get_IsCacheLoaderInitialized()
0x9bb4a  brtrue.s loc_9BB84
0x9bb4c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x9bb51  brfalse.s loc_9BB70
0x9bb53  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x9bb58  brtrue.s loc_9BB70
0x9bb5a  ldsfld   class Microsoft.Crm.Caching.WebResourceDependencyCache Microsoft.Crm.Caching.WebResourceDependencyCache::_cacheInstance
0x9bb5f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x9bb64  ldstr    aMicrosoftCrmCa_116// "Microsoft.Crm.Caching.WebResourceDepend"...
0x9bb69  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.IWebResourceDependencyCacheKey, class Microsoft.Crm.Caching.IWebResourceDependencyCacheValue>::SetLoader(string, string)
0x9bb6e  br.s     loc_9BB84
0x9bb70  ldsfld   class Microsoft.Crm.Caching.WebResourceDependencyCache Microsoft.Crm.Caching.WebResourceDependencyCache::_cacheInstance
0x9bb75  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9bb7a  ldstr    aMicrosoftCrmCa_117// "Microsoft.Crm.Caching.WebResourceDepend"...
0x9bb7f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.IWebResourceDependencyCacheKey, class Microsoft.Crm.Caching.IWebResourceDependencyCacheValue>::SetLoader(string, string)
0x9bb84  ldsfld   class Microsoft.Crm.Caching.WebResourceDependencyCache Microsoft.Crm.Caching.WebResourceDependencyCache::_cacheInstance
0x9bb89  ret
```
