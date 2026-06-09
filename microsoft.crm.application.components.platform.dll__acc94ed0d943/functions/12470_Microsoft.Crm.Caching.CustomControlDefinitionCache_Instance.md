# Microsoft.Crm.Caching.CustomControlDefinitionCache::Instance

- ea: `0x12470`
- end: `0x124ba`
- name: `Microsoft.Crm.Caching.CustomControlDefinitionCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4af30`

## callees

- `0x12470`

## string_xrefs

- `0x1248f`: `Microsoft.Crm.Application.Components.Platform`
- `0x124a5`: `Microsoft.Crm.Application.Components.Platform`
- `0x124aa`: `Microsoft.Crm.Caching.CustomControlDefinitionCacheLoader`
- `0x12494`: `Microsoft.Crm.Caching.CustomControlDefinitionCacheLoaderProxy`

## pseudocode

```c

```

## disassembly

```asm
0x12470  ldsfld   class Microsoft.Crm.Caching.CustomControlDefinitionCache Microsoft.Crm.Caching.CustomControlDefinitionCache::_innerCache
0x12475  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition>::get_IsCacheLoaderInitialized()
0x1247a  brtrue.s loc_124B4
0x1247c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x12481  brfalse.s loc_124A0
0x12483  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x12488  brtrue.s loc_124A0
0x1248a  ldsfld   class Microsoft.Crm.Caching.CustomControlDefinitionCache Microsoft.Crm.Caching.CustomControlDefinitionCache::_innerCache
0x1248f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x12494  ldstr    aMicrosoftCrmCa_1// "Microsoft.Crm.Caching.CustomControlDefi"...
0x12499  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition>::SetLoader(string, string)
0x1249e  br.s     loc_124B4
0x124a0  ldsfld   class Microsoft.Crm.Caching.CustomControlDefinitionCache Microsoft.Crm.Caching.CustomControlDefinitionCache::_innerCache
0x124a5  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x124aa  ldstr    aMicrosoftCrmCa// "Microsoft.Crm.Caching.CustomControlDefi"...
0x124af  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition>::SetLoader(string, string)
0x124b4  ldsfld   class Microsoft.Crm.Caching.CustomControlDefinitionCache Microsoft.Crm.Caching.CustomControlDefinitionCache::_innerCache
0x124b9  ret
```
