# Microsoft.Crm.Caching.BusinessDataCache::Instance

- ea: `0x94cf0`
- end: `0x94d3a`
- name: `Microsoft.Crm.Caching.BusinessDataCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x94cf0`

## string_xrefs

- `0x94d0f`: `Microsoft.Crm.Application.Components.Platform`
- `0x94d14`: `Microsoft.Crm.Caching.BusinessDataCacheLoaderProxy`
- `0x94d2a`: `Microsoft.Crm.Caching.BusinessDataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x94cf0  ldsfld   class Microsoft.Crm.Caching.BusinessDataCache Microsoft.Crm.Caching.BusinessDataCache::_innerCache
0x94cf5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IBusiness>::get_IsCacheLoaderInitialized()
0x94cfa  brtrue.s loc_94D34
0x94cfc  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x94d01  brfalse.s loc_94D20
0x94d03  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x94d08  brtrue.s loc_94D20
0x94d0a  ldsfld   class Microsoft.Crm.Caching.BusinessDataCache Microsoft.Crm.Caching.BusinessDataCache::_innerCache
0x94d0f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x94d14  ldstr    aMicrosoftCrmCa_36// "Microsoft.Crm.Caching.BusinessDataCache"...
0x94d19  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IBusiness>::SetLoader(string, string)
0x94d1e  br.s     loc_94D34
0x94d20  ldsfld   class Microsoft.Crm.Caching.BusinessDataCache Microsoft.Crm.Caching.BusinessDataCache::_innerCache
0x94d25  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x94d2a  ldstr    aMicrosoftCrmCa_37// "Microsoft.Crm.Caching.BusinessDataCache"...
0x94d2f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IBusiness>::SetLoader(string, string)
0x94d34  ldsfld   class Microsoft.Crm.Caching.BusinessDataCache Microsoft.Crm.Caching.BusinessDataCache::_innerCache
0x94d39  ret
```
