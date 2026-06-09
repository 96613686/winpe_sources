# Microsoft.Crm.Caching.EmailServerProfileCache::Instance

- ea: `0x95870`
- end: `0x958de`
- name: `Microsoft.Crm.Caching.EmailServerProfileCache::Instance`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x95870`

## string_xrefs

- `0x958b3`: `Microsoft.Crm.Application.Components.Platform`
- `0x95897`: `IsInSyncServiceContext`
- `0x958b8`: `Microsoft.Crm.Caching.EmailServerProfileCacheLoaderProxy`
- `0x958ce`: `Microsoft.Crm.Caching.EmailServerProfileCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x95870  ldsfld   class Microsoft.Crm.Caching.EmailServerProfileCache Microsoft.Crm.Caching.EmailServerProfileCache::_innerCache
0x95875  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IEmailServerProfile>::get_IsCacheLoaderInitialized()
0x9587a  brtrue.s loc_958D8
0x9587c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x95881  brfalse.s loc_95897
0x95883  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x95888  brtrue.s loc_95897
0x9588a  ldc.i4.0
0x9588b  ldstr    aNotValidInOffl// "Not valid in offline context"
0x95890  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x95895  br.s     loc_958D8
0x95897  ldstr    aIsinsyncservic// "IsInSyncServiceContext"
0x9589c  ldc.i4.0
0x9589d  box      [mscorlib]System.Boolean
0x958a2  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x958a7  unbox.any [mscorlib]System.Boolean
0x958ac  brfalse.s loc_958C4
0x958ae  ldsfld   class Microsoft.Crm.Caching.EmailServerProfileCache Microsoft.Crm.Caching.EmailServerProfileCache::_innerCache
0x958b3  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x958b8  ldstr    aMicrosoftCrmCa_44// "Microsoft.Crm.Caching.EmailServerProfil"...
0x958bd  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IEmailServerProfile>::SetLoader(string, string)
0x958c2  br.s     loc_958D8
0x958c4  ldsfld   class Microsoft.Crm.Caching.EmailServerProfileCache Microsoft.Crm.Caching.EmailServerProfileCache::_innerCache
0x958c9  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x958ce  ldstr    aMicrosoftCrmCa_45// "Microsoft.Crm.Caching.EmailServerProfil"...
0x958d3  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IEmailServerProfile>::SetLoader(string, string)
0x958d8  ldsfld   class Microsoft.Crm.Caching.EmailServerProfileCache Microsoft.Crm.Caching.EmailServerProfileCache::_innerCache
0x958dd  ret
```
