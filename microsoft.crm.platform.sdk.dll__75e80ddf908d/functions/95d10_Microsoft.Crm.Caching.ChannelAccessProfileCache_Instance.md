# Microsoft.Crm.Caching.ChannelAccessProfileCache::Instance

- ea: `0x95d10`
- end: `0x95d5a`
- name: `Microsoft.Crm.Caching.ChannelAccessProfileCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x95d10`

## string_xrefs

- `0x95d2f`: `Microsoft.Crm.Application.Components.Platform`
- `0x95d34`: `Microsoft.Crm.CachingChannelAccessProfileDataCacheLoaderProxy`
- `0x95d4a`: `Microsoft.Crm.Caching.ChannelAccessProfileDataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x95d10  ldsfld   class Microsoft.Crm.Caching.ChannelAccessProfileCache Microsoft.Crm.Caching.ChannelAccessProfileCache::_cacheInstance
0x95d15  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IChannelAccessProfileCacheData>::get_IsCacheLoaderInitialized()
0x95d1a  brtrue.s loc_95D54
0x95d1c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x95d21  brfalse.s loc_95D40
0x95d23  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x95d28  brtrue.s loc_95D40
0x95d2a  ldsfld   class Microsoft.Crm.Caching.ChannelAccessProfileCache Microsoft.Crm.Caching.ChannelAccessProfileCache::_cacheInstance
0x95d2f  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x95d34  ldstr    aMicrosoftCrmCa_48// "Microsoft.Crm.CachingChannelAccessProfi"...
0x95d39  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IChannelAccessProfileCacheData>::SetLoader(string, string)
0x95d3e  br.s     loc_95D54
0x95d40  ldsfld   class Microsoft.Crm.Caching.ChannelAccessProfileCache Microsoft.Crm.Caching.ChannelAccessProfileCache::_cacheInstance
0x95d45  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x95d4a  ldstr    aMicrosoftCrmCa_49// "Microsoft.Crm.Caching.ChannelAccessProf"...
0x95d4f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IChannelAccessProfileCacheData>::SetLoader(string, string)
0x95d54  ldsfld   class Microsoft.Crm.Caching.ChannelAccessProfileCache Microsoft.Crm.Caching.ChannelAccessProfileCache::_cacheInstance
0x95d59  ret
```
