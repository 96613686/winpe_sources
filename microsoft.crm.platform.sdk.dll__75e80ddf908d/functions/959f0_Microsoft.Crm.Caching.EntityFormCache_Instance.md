# Microsoft.Crm.Caching.EntityFormCache::Instance

- ea: `0x959f0`
- end: `0x95a3a`
- name: `Microsoft.Crm.Caching.EntityFormCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x959f0`

## string_xrefs

- `0x95a0f`: `Microsoft.Crm.Application.Components.Platform`
- `0x95a14`: `Microsoft.Crm.Caching.EntityFormCacheLoaderProxy`
- `0x95a2a`: `Microsoft.Crm.Caching.EntityFormCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x959f0  ldsfld   class Microsoft.Crm.Caching.EntityFormCache Microsoft.Crm.Caching.EntityFormCache::_staticInstance
0x959f5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.EntityFormCacheKey, class Microsoft.Crm.Caching.IEntityFormCacheValue>::get_IsCacheLoaderInitialized()
0x959fa  brtrue.s loc_95A34
0x959fc  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x95a01  brfalse.s loc_95A20
0x95a03  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x95a08  brtrue.s loc_95A20
0x95a0a  ldsfld   class Microsoft.Crm.Caching.EntityFormCache Microsoft.Crm.Caching.EntityFormCache::_staticInstance
0x95a0f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x95a14  ldstr    aMicrosoftCrmCa_46// "Microsoft.Crm.Caching.EntityFormCacheLo"...
0x95a19  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.EntityFormCacheKey, class Microsoft.Crm.Caching.IEntityFormCacheValue>::SetLoader(string, string)
0x95a1e  br.s     loc_95A34
0x95a20  ldsfld   class Microsoft.Crm.Caching.EntityFormCache Microsoft.Crm.Caching.EntityFormCache::_staticInstance
0x95a25  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x95a2a  ldstr    aMicrosoftCrmCa_47// "Microsoft.Crm.Caching.EntityFormCacheLo"...
0x95a2f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Caching.EntityFormCacheKey, class Microsoft.Crm.Caching.IEntityFormCacheValue>::SetLoader(string, string)
0x95a34  ldsfld   class Microsoft.Crm.Caching.EntityFormCache Microsoft.Crm.Caching.EntityFormCache::_staticInstance
0x95a39  ret
```
