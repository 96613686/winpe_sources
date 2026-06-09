# Microsoft.Crm.Caching.SolutionCache::Instance

- ea: `0x98fc0`
- end: `0x9900a`
- name: `Microsoft.Crm.Caching.SolutionCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2e40`
- `0x2f10`
- `0x2f70`
- `0x2fb0`
- `0x3190`
- `0x3210`

## callees

- `0x98fc0`

## string_xrefs

- `0x98fdf`: `Microsoft.Crm.Application.Components.Platform`
- `0x98fe4`: `Microsoft.Crm.Caching.SolutionDataCacheLoaderProxy`
- `0x98ffa`: `Microsoft.Crm.Caching.SolutionDataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x98fc0  ldsfld   class Microsoft.Crm.Caching.SolutionCache Microsoft.Crm.Caching.SolutionCache::_innerCache
0x98fc5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISolution>::get_IsCacheLoaderInitialized()
0x98fca  brtrue.s loc_99004
0x98fcc  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x98fd1  brfalse.s loc_98FF0
0x98fd3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x98fd8  brtrue.s loc_98FF0
0x98fda  ldsfld   class Microsoft.Crm.Caching.SolutionCache Microsoft.Crm.Caching.SolutionCache::_innerCache
0x98fdf  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x98fe4  ldstr    aMicrosoftCrmCa_87// "Microsoft.Crm.Caching.SolutionDataCache"...
0x98fe9  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISolution>::SetLoader(string, string)
0x98fee  br.s     loc_99004
0x98ff0  ldsfld   class Microsoft.Crm.Caching.SolutionCache Microsoft.Crm.Caching.SolutionCache::_innerCache
0x98ff5  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x98ffa  ldstr    aMicrosoftCrmCa_88// "Microsoft.Crm.Caching.SolutionDataCache"...
0x98fff  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISolution>::SetLoader(string, string)
0x99004  ldsfld   class Microsoft.Crm.Caching.SolutionCache Microsoft.Crm.Caching.SolutionCache::_innerCache
0x99009  ret
```
