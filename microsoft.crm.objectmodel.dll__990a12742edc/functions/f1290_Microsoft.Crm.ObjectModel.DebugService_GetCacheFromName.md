# Microsoft.Crm.ObjectModel.DebugService::GetCacheFromName

- ea: `0xf1290`
- end: `0xf1429`
- name: `Microsoft.Crm.ObjectModel.DebugService::GetCacheFromName`
- size: `409`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xf0a10`
- `0xf0ab0`
- `0xf0c20`

## callees

- `0x4c7a0`
- `0x54ce0`
- `0xf1290`

## string_xrefs

- `0xf1355`: `Microsoft.Crm.Caching.PluginTypeCacheLoader,Microsoft.Crm.Platform.Sdk`
- `0xf1364`: `_pluginAssemblyCache`
- `0xf137c`: `Microsoft.Crm.Caching.SavedQueryCache,Microsoft.Crm.Application.Components.Platform`
- `0xf138b`: `_innerCache`
- `0xf13b2`: `_innerCache`
- `0xf13a3`: `Microsoft.Crm.Caching.DefaultSavedQueryIdsCache,Microsoft.Crm.Application.Components.Platform`
- `0xf13d6`: `Microsoft.Crm.Sdk.ServiceDescriptionCache,Microsoft.Crm.WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xf1290  ldarg.1
0xf1291  ldc.i4.1
0xf1292  sub
0xf1293  switch   loc_F1319, loc_F131F, loc_F1325, loc_F1427, loc_F132B, loc_F1427, loc_F1331, loc_F1337, loc_F133D, loc_F1343, loc_F1349, loc_F134F, loc_F1355, loc_F137C, loc_F13A3, loc_F13CA, loc_F13D0, loc_F1427, loc_F1427, loc_F1427, loc_F13D6, loc_F1427, loc_F13FD, loc_F1403, loc_F1409, loc_F1427, loc_F140F, loc_F1427, loc_F1415, loc_F141B, loc_F1421
0xf1314  br       loc_F1427
0xf1319  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xf131e  ret
0xf131f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0xf1324  ret
0xf1325  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0xf132a  ret
0xf132b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache::Instance()
0xf1330  ret
0xf1331  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SubscriptionDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SubscriptionDataCache::Instance()
0xf1336  ret
0xf1337  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BusinessDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BusinessDataCache::Instance()
0xf133c  ret
0xf133d  call     class [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.Engine.IItemCache [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.Engine.ScheduleCacheInstance::get_CacheInstance()
0xf1342  ret
0xf1343  call     class [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.Engine.IItemCache [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.Storage.ContainerLevelCacheInstance::get_CacheInstance()
0xf1348  ret
0xf1349  call     class [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.Engine.IItemCache [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.Engine.ExpansionCacheInstance::get_CacheInstance()
0xf134e  ret
0xf134f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache::get_Instance()
0xf1354  ret
0xf1355  ldstr    aMicrosoftCrmCa_1// "Microsoft.Crm.Caching.PluginTypeCacheLo"...
0xf135a  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0xf135f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0xf1364  ldstr    aPluginassembly_4// "_pluginAssemblyCache"
0xf1369  ldc.i4.s 0x28
0xf136b  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xf1370  ldnull
0xf1371  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0xf1376  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheDebug
0xf137b  ret
0xf137c  ldstr    aMicrosoftCrmCa_2// "Microsoft.Crm.Caching.SavedQueryCache,M"...
0xf1381  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0xf1386  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0xf138b  ldstr    aInnercache// "_innerCache"
0xf1390  ldc.i4.s 0x28
0xf1392  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xf1397  ldnull
0xf1398  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0xf139d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheDebug
0xf13a2  ret
0xf13a3  ldstr    aMicrosoftCrmCa_3// "Microsoft.Crm.Caching.DefaultSavedQuery"...
0xf13a8  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0xf13ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0xf13b2  ldstr    aInnercache// "_innerCache"
0xf13b7  ldc.i4.s 0x28
0xf13b9  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xf13be  ldnull
0xf13bf  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0xf13c4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheDebug
0xf13c9  ret
0xf13ca  call     class Microsoft.Crm.Caching.MessageProcessorCache Microsoft.Crm.Caching.MessageProcessorCache::get_Instance()
0xf13cf  ret
0xf13d0  call     class Microsoft.Crm.Caching.StepDescriptionCache Microsoft.Crm.Caching.StepDescriptionCache::get_Instance()
0xf13d5  ret
0xf13d6  ldstr    aMicrosoftCrmSd_28// "Microsoft.Crm.Sdk.ServiceDescriptionCac"...
0xf13db  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0xf13e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0xf13e5  ldstr    aInstance_0// "_instance"
0xf13ea  ldc.i4.s 0x28
0xf13ec  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xf13f1  ldnull
0xf13f2  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0xf13f7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheDebug
0xf13fc  ret
0xf13fd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateDetectionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DuplicateDetectionCache::Instance()
0xf1402  ret
0xf1403  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RecordCountCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RecordCountCache::Instance()
0xf1408  ret
0xf1409  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache::Instance()
0xf140e  ret
0xf140f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SystemUserManagerMapCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SystemUserManagerMapCache::Instance()
0xf1414  ret
0xf1415  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserSearchFacetCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserSearchFacetCache::Instance()
0xf141a  ret
0xf141b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PostServiceCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PostServiceCache::Instance()
0xf1420  ret
0xf1421  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PostServiceFollowSelfCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PostServiceFollowSelfCache::Instance()
0xf1426  ret
0xf1427  ldnull
0xf1428  ret
```
