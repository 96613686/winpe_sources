# Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache::Instance

- ea: `0x99a90`
- end: `0x99ace`
- name: `Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache::Instance`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x99a90`

## string_xrefs

- `0x99aa3`: `Microsoft.Crm.Application.Components.Platform`
- `0x99aa8`: `Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCacheLoaderProxy`
- `0x99abe`: `Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x99a90  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x99a95  brfalse.s loc_99AB4
0x99a97  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x99a9c  brtrue.s loc_99AB4
0x99a9e  ldsfld   class Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache::_cacheInstance
0x99aa3  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x99aa8  ldstr    aMicrosoftCrmCa_95// "Microsoft.Crm.Caching.TimeZoneAllDispla"...
0x99aad  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class Microsoft.Crm.Caching.TimeZoneNameCacheData>>::SetLoader(string, string)
0x99ab2  br.s     loc_99AC8
0x99ab4  ldsfld   class Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache::_cacheInstance
0x99ab9  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x99abe  ldstr    aMicrosoftCrmCa_96// "Microsoft.Crm.Caching.TimeZoneAllDispla"...
0x99ac3  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class Microsoft.Crm.Caching.TimeZoneNameCacheData>>::SetLoader(string, string)
0x99ac8  ldsfld   class Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache Microsoft.Crm.Caching.TimeZoneAllDisplayNameCultureIdCache::_cacheInstance
0x99acd  ret
```
