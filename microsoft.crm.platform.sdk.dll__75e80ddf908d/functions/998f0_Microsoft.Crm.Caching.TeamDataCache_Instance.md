# Microsoft.Crm.Caching.TeamDataCache::Instance

- ea: `0x998f0`
- end: `0x9993a`
- name: `Microsoft.Crm.Caching.TeamDataCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x998f0`

## string_xrefs

- `0x9990f`: `Microsoft.Crm.Application.Components.Platform`
- `0x99914`: `Microsoft.Crm.Caching.TeamDataCacheLoaderProxy`
- `0x9992a`: `Microsoft.Crm.Caching.TeamDataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x998f0  ldsfld   class Microsoft.Crm.Caching.TeamDataCache Microsoft.Crm.Caching.TeamDataCache::_innerCache
0x998f5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ITeam>::get_IsCacheLoaderInitialized()
0x998fa  brtrue.s loc_99934
0x998fc  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x99901  brfalse.s loc_99920
0x99903  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x99908  brtrue.s loc_99920
0x9990a  ldsfld   class Microsoft.Crm.Caching.TeamDataCache Microsoft.Crm.Caching.TeamDataCache::_innerCache
0x9990f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x99914  ldstr    aMicrosoftCrmCa_93// "Microsoft.Crm.Caching.TeamDataCacheLoad"...
0x99919  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ITeam>::SetLoader(string, string)
0x9991e  br.s     loc_99934
0x99920  ldsfld   class Microsoft.Crm.Caching.TeamDataCache Microsoft.Crm.Caching.TeamDataCache::_innerCache
0x99925  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9992a  ldstr    aMicrosoftCrmCa_94// "Microsoft.Crm.Caching.TeamDataCacheLoad"...
0x9992f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ITeam>::SetLoader(string, string)
0x99934  ldsfld   class Microsoft.Crm.Caching.TeamDataCache Microsoft.Crm.Caching.TeamDataCache::_innerCache
0x99939  ret
```
