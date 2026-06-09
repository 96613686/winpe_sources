# Microsoft.Crm.Caching.SimilarityRuleCache::Instance

- ea: `0x98e00`
- end: `0x98e4a`
- name: `Microsoft.Crm.Caching.SimilarityRuleCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x98e00`

## string_xrefs

- `0x98e1f`: `Microsoft.Crm.Application.Components.Platform`
- `0x98e24`: `Microsoft.Crm.Caching.SimilarityRuleCacheLoaderProxy`
- `0x98e3a`: `Microsoft.Crm.Caching.SimilarityRuleCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x98e00  ldsfld   class Microsoft.Crm.Caching.SimilarityRuleCache Microsoft.Crm.Caching.SimilarityRuleCache::_innerCache
0x98e05  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISimilarityRulesData>::get_IsCacheLoaderInitialized()
0x98e0a  brtrue.s loc_98E44
0x98e0c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x98e11  brfalse.s loc_98E30
0x98e13  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x98e18  brtrue.s loc_98E30
0x98e1a  ldsfld   class Microsoft.Crm.Caching.SimilarityRuleCache Microsoft.Crm.Caching.SimilarityRuleCache::_innerCache
0x98e1f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x98e24  ldstr    aMicrosoftCrmCa_85// "Microsoft.Crm.Caching.SimilarityRuleCac"...
0x98e29  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISimilarityRulesData>::SetLoader(string, string)
0x98e2e  br.s     loc_98E44
0x98e30  ldsfld   class Microsoft.Crm.Caching.SimilarityRuleCache Microsoft.Crm.Caching.SimilarityRuleCache::_innerCache
0x98e35  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x98e3a  ldstr    aMicrosoftCrmCa_86// "Microsoft.Crm.Caching.SimilarityRuleCac"...
0x98e3f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISimilarityRulesData>::SetLoader(string, string)
0x98e44  ldsfld   class Microsoft.Crm.Caching.SimilarityRuleCache Microsoft.Crm.Caching.SimilarityRuleCache::_innerCache
0x98e49  ret
```
