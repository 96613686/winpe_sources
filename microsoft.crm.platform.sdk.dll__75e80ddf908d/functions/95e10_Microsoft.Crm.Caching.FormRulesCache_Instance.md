# Microsoft.Crm.Caching.FormRulesCache::Instance

- ea: `0x95e10`
- end: `0x95e5a`
- name: `Microsoft.Crm.Caching.FormRulesCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x95e10`

## string_xrefs

- `0x95e2f`: `Microsoft.Crm.Application.Components.Platform`
- `0x95e34`: `Microsoft.Crm.Caching.FormRulesCacheProxy`
- `0x95e4a`: `Microsoft.Crm.Caching.FormRulesCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x95e10  ldsfld   class Microsoft.Crm.Caching.FormRulesCache Microsoft.Crm.Caching.FormRulesCache::_staticInstance
0x95e15  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IFormRulesCacheValue>::get_IsCacheLoaderInitialized()
0x95e1a  brtrue.s loc_95E54
0x95e1c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x95e21  brfalse.s loc_95E40
0x95e23  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x95e28  brtrue.s loc_95E40
0x95e2a  ldsfld   class Microsoft.Crm.Caching.FormRulesCache Microsoft.Crm.Caching.FormRulesCache::_staticInstance
0x95e2f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x95e34  ldstr    aMicrosoftCrmCa_50// "Microsoft.Crm.Caching.FormRulesCachePro"...
0x95e39  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IFormRulesCacheValue>::SetLoader(string, string)
0x95e3e  br.s     loc_95E54
0x95e40  ldsfld   class Microsoft.Crm.Caching.FormRulesCache Microsoft.Crm.Caching.FormRulesCache::_staticInstance
0x95e45  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x95e4a  ldstr    aMicrosoftCrmCa_51// "Microsoft.Crm.Caching.FormRulesCacheLoa"...
0x95e4f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IFormRulesCacheValue>::SetLoader(string, string)
0x95e54  ldsfld   class Microsoft.Crm.Caching.FormRulesCache Microsoft.Crm.Caching.FormRulesCache::_staticInstance
0x95e59  ret
```
