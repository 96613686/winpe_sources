# Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance

- ea: `0x9a0a0`
- end: `0x9a0ea`
- name: `Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9a0a0`

## string_xrefs

- `0x9a0bf`: `Microsoft.Crm.Application.Components.Platform`
- `0x9a0c4`: `Microsoft.Crm.Caching.UserEntityUISettingsCacheLoaderProxy`
- `0x9a0da`: `Microsoft.Crm.Caching.UserEntityUISettingsCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x9a0a0  ldsfld   class Microsoft.Crm.Caching.UserEntityUISettingsCache Microsoft.Crm.Caching.UserEntityUISettingsCache::_innerCache
0x9a0a5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.IUserEntityUISettings>::get_IsCacheLoaderInitialized()
0x9a0aa  brtrue.s loc_9A0E4
0x9a0ac  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x9a0b1  brfalse.s loc_9A0D0
0x9a0b3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x9a0b8  brtrue.s loc_9A0D0
0x9a0ba  ldsfld   class Microsoft.Crm.Caching.UserEntityUISettingsCache Microsoft.Crm.Caching.UserEntityUISettingsCache::_innerCache
0x9a0bf  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x9a0c4  ldstr    aMicrosoftCrmCa_102// "Microsoft.Crm.Caching.UserEntityUISetti"...
0x9a0c9  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.IUserEntityUISettings>::SetLoader(string, string)
0x9a0ce  br.s     loc_9A0E4
0x9a0d0  ldsfld   class Microsoft.Crm.Caching.UserEntityUISettingsCache Microsoft.Crm.Caching.UserEntityUISettingsCache::_innerCache
0x9a0d5  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9a0da  ldstr    aMicrosoftCrmCa_103// "Microsoft.Crm.Caching.UserEntityUISetti"...
0x9a0df  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class Microsoft.Crm.Caching.IUserEntityUISettings>::SetLoader(string, string)
0x9a0e4  ldsfld   class Microsoft.Crm.Caching.UserEntityUISettingsCache Microsoft.Crm.Caching.UserEntityUISettingsCache::_innerCache
0x9a0e9  ret
```
