# Microsoft.Crm.Caching.UserDataCache::Instance

- ea: `0x7b8d0`
- end: `0x7b94c`
- name: `Microsoft.Crm.Caching.UserDataCache::Instance`
- size: `124`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4780`
- `0x9070`
- `0x7b990`
- `0x9f240`
- `0xa02f0`
- `0xa0310`
- `0xa7890`
- `0xa8ed0`
- `0xa8f30`

## callees

- `0x7b8d0`

## string_xrefs

- `0x7b90b`: `Microsoft.Crm.Application.Components.Platform`
- `0x7b910`: `Microsoft.Crm.Caching.UserDataCacheLoaderProxy`
- `0x7b926`: `Microsoft.Crm.Caching.UserDataCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x7b8d0  ldsfld   class Microsoft.Crm.Caching.UserDataCache Microsoft.Crm.Caching.UserDataCache::_cacheInstance
0x7b8d5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IUser>::get_IsCacheLoaderInitialized()
0x7b8da  brtrue.s loc_7B946
0x7b8dc  ldsfld   object Microsoft.Crm.Caching.UserDataCache::_lock
0x7b8e1  stloc.0
0x7b8e2  ldc.i4.0
0x7b8e3  stloc.1
0x7b8e4  ldloc.0
0x7b8e5  ldloca.s 1
0x7b8e7  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7b8ec  ldsfld   class Microsoft.Crm.Caching.UserDataCache Microsoft.Crm.Caching.UserDataCache::_cacheInstance
0x7b8f1  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IUser>::get_IsCacheLoaderInitialized()
0x7b8f6  brtrue.s loc_7B93A
0x7b8f8  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x7b8fd  brfalse.s loc_7B91C
0x7b8ff  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x7b904  brtrue.s loc_7B91C
0x7b906  ldsfld   class Microsoft.Crm.Caching.UserDataCache Microsoft.Crm.Caching.UserDataCache::_cacheInstance
0x7b90b  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x7b910  ldstr    aMicrosoftCrmCa_3// "Microsoft.Crm.Caching.UserDataCacheLoad"...
0x7b915  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IUser>::SetLoader(string, string)
0x7b91a  br.s     loc_7B930
0x7b91c  ldsfld   class Microsoft.Crm.Caching.UserDataCache Microsoft.Crm.Caching.UserDataCache::_cacheInstance
0x7b921  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x7b926  ldstr    aMicrosoftCrmCa_4// "Microsoft.Crm.Caching.UserDataCacheLoad"...
0x7b92b  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IUser>::SetLoader(string, string)
0x7b930  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UalRolesConstants::AppServer
0x7b935  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserAccessLoggingHelper::StartSession(valuetype [mscorlib]System.Guid)
0x7b93a  leave.s  loc_7B946
0x7b93c  ldloc.1
0x7b93d  brfalse.s loc_7B945
0x7b93f  ldloc.0
0x7b940  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7b945  endfinally
0x7b946  ldsfld   class Microsoft.Crm.Caching.UserDataCache Microsoft.Crm.Caching.UserDataCache::_cacheInstance
0x7b94b  ret
```
