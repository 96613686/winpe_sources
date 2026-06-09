# Microsoft.Crm.Caching.DuplicateDetectionCache::Instance

- ea: `0x956a0`
- end: `0x956ea`
- name: `Microsoft.Crm.Caching.DuplicateDetectionCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x956a0`

## string_xrefs

- `0x956bf`: `Microsoft.Crm.Application.Components.Platform`
- `0x956c4`: `Microsoft.Crm.Caching.DuplicateDetectionCacheLoaderProxy`
- `0x956da`: `Microsoft.Crm.Caching.DuplicateDetectionCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x956a0  ldsfld   class Microsoft.Crm.Caching.DuplicateDetectionCache Microsoft.Crm.Caching.DuplicateDetectionCache::_innerCache
0x956a5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IDuplicateRulesData>::get_IsCacheLoaderInitialized()
0x956aa  brtrue.s loc_956E4
0x956ac  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x956b1  brfalse.s loc_956D0
0x956b3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x956b8  brtrue.s loc_956D0
0x956ba  ldsfld   class Microsoft.Crm.Caching.DuplicateDetectionCache Microsoft.Crm.Caching.DuplicateDetectionCache::_innerCache
0x956bf  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x956c4  ldstr    aMicrosoftCrmCa_42// "Microsoft.Crm.Caching.DuplicateDetectio"...
0x956c9  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IDuplicateRulesData>::SetLoader(string, string)
0x956ce  br.s     loc_956E4
0x956d0  ldsfld   class Microsoft.Crm.Caching.DuplicateDetectionCache Microsoft.Crm.Caching.DuplicateDetectionCache::_innerCache
0x956d5  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x956da  ldstr    aMicrosoftCrmCa_43// "Microsoft.Crm.Caching.DuplicateDetectio"...
0x956df  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IDuplicateRulesData>::SetLoader(string, string)
0x956e4  ldsfld   class Microsoft.Crm.Caching.DuplicateDetectionCache Microsoft.Crm.Caching.DuplicateDetectionCache::_innerCache
0x956e9  ret
```
