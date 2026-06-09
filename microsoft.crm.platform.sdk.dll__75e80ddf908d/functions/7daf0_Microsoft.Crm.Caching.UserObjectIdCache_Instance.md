# Microsoft.Crm.Caching.UserObjectIdCache::Instance

- ea: `0x7daf0`
- end: `0x7db6c`
- name: `Microsoft.Crm.Caching.UserObjectIdCache::Instance`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7daf0`

## string_xrefs

- `0x7db2b`: `Microsoft.Crm.Application.Components.Platform`
- `0x7db30`: `Microsoft.Crm.Caching.UserObjectIdCacheLoaderProxy`
- `0x7db46`: `Microsoft.Crm.Caching.UserObjectIdCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x7daf0  ldsfld   class Microsoft.Crm.Caching.UserObjectIdCache Microsoft.Crm.Caching.UserObjectIdCache::_cacheInstance
0x7daf5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_IsCacheLoaderInitialized()
0x7dafa  brtrue.s loc_7DB66
0x7dafc  ldsfld   object Microsoft.Crm.Caching.UserObjectIdCache::_lock
0x7db01  stloc.0
0x7db02  ldc.i4.0
0x7db03  stloc.1
0x7db04  ldloc.0
0x7db05  ldloca.s 1
0x7db07  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7db0c  ldsfld   class Microsoft.Crm.Caching.UserObjectIdCache Microsoft.Crm.Caching.UserObjectIdCache::_cacheInstance
0x7db11  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_IsCacheLoaderInitialized()
0x7db16  brtrue.s loc_7DB5A
0x7db18  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x7db1d  brfalse.s loc_7DB3C
0x7db1f  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x7db24  brtrue.s loc_7DB3C
0x7db26  ldsfld   class Microsoft.Crm.Caching.UserObjectIdCache Microsoft.Crm.Caching.UserObjectIdCache::_cacheInstance
0x7db2b  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x7db30  ldstr    aMicrosoftCrmCa_27// "Microsoft.Crm.Caching.UserObjectIdCache"...
0x7db35  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::SetLoader(string, string)
0x7db3a  br.s     loc_7DB50
0x7db3c  ldsfld   class Microsoft.Crm.Caching.UserObjectIdCache Microsoft.Crm.Caching.UserObjectIdCache::_cacheInstance
0x7db41  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x7db46  ldstr    aMicrosoftCrmCa_28// "Microsoft.Crm.Caching.UserObjectIdCache"...
0x7db4b  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::SetLoader(string, string)
0x7db50  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UalRolesConstants::AppServer
0x7db55  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserAccessLoggingHelper::StartSession(valuetype [mscorlib]System.Guid)
0x7db5a  leave.s  loc_7DB66
0x7db5c  ldloc.1
0x7db5d  brfalse.s loc_7DB65
0x7db5f  ldloc.0
0x7db60  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7db65  endfinally
0x7db66  ldsfld   class Microsoft.Crm.Caching.UserObjectIdCache Microsoft.Crm.Caching.UserObjectIdCache::_cacheInstance
0x7db6b  ret
```
