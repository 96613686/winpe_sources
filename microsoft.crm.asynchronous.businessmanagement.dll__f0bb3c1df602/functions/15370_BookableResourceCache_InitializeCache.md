# BookableResourceCache::InitializeCache

- ea: `0x15370`
- end: `0x154a8`
- name: `BookableResourceCache::InitializeCache`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x152c0`

## callees

- `0x140b0`
- `0x152a0`
- `0x152b0`
- `0x15370`
- `0x178e0`
- `0x17900`
- `0x17920`
- `0x17940`
- `0x17950`
- `0x17960`
- `0x17970`

## pseudocode

```c

```

## disassembly

```asm
0x15370  ldarg.0
0x15371  ldfld    valuetype [mscorlib]System.Guid BookableResourceCache::organizationId
0x15376  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1537b  stloc.0
0x1537c  ldarg.0
0x1537d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::.ctor()
0x15382  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByBookableResourceId
0x15387  ldarg.0
0x15388  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::.ctor()
0x1538d  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByUserId
0x15392  ldarg.0
0x15393  ldfld    class BookableResourceQuery BookableResourceCache::bookableResourceQuery
0x15398  brtrue.s loc_1539D
0x1539a  ldnull
0x1539b  br.s     loc_153A8
0x1539d  ldarg.0
0x1539e  ldfld    class BookableResourceQuery BookableResourceCache::bookableResourceQuery
0x153a3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> PagedEntityQuery::Next()
0x153a8  stloc.1
0x153a9  ldarg.0
0x153aa  ldc.i8   0x7FFFFFFFFFFFFFFF
0x153b3  call     instance void BookableResourceCache::set_MinSyncVersionNumber(int64 value)
0x153b8  br       loc_154A1
0x153bd  ldloc.1
0x153be  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x153c3  stloc.2
0x153c4  br       loc_1547E
0x153c9  ldloc.2
0x153ca  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x153cf  dup
0x153d0  ldstr    aBookableresour_12// "bookableresourceid"
0x153d5  callvirt T0x2B000010
0x153da  stloc.3
0x153db  ldstr    aUserid// "userid"
0x153e0  callvirt T0x2B000013
0x153e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x153ea  stloc.s  4
0x153ec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x153f1  ldloc.s  4
0x153f3  ldloc.0
0x153f4  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x153f9  stloc.s  5
0x153fb  ldloc.s  5
0x153fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultMailbox()
0x15402  pop
0x15403  ldloc.s  5
0x15405  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsResourceBookingExchangeSyncEnabled()
0x1540a  brfalse.s loc_1547E
0x1540c  newobj   instance void CacheData::.ctor()
0x15411  dup
0x15412  ldloc.3
0x15413  callvirt instance void CacheData::set_BookableResourceId(valuetype [mscorlib]System.Guid value)
0x15418  dup
0x15419  ldloc.s  4
0x1541b  callvirt instance void CacheData::set_UserId(valuetype [mscorlib]System.Guid value)
0x15420  dup
0x15421  ldloc.s  5
0x15423  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x15428  callvirt instance void CacheData::set_BusinessUnitId(valuetype [mscorlib]System.Guid value)
0x1542d  dup
0x1542e  ldloc.s  5
0x15430  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultMailbox()
0x15435  callvirt instance void CacheData::set_MailboxId(valuetype [mscorlib]System.Guid value)
0x1543a  dup
0x1543b  ldloc.s  5
0x1543d  callvirt instance int64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_ResourceBookingExchangeSyncVersion()
0x15442  callvirt instance void CacheData::set_LastSyncVersionNumber(int64 value)
0x15447  stloc.s  6
0x15449  ldarg.0
0x1544a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByBookableResourceId
0x1544f  ldloc.3
0x15450  ldloc.s  6
0x15452  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::Add(var<u1>, !!T0)
0x15457  ldarg.0
0x15458  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByUserId
0x1545d  ldloc.s  4
0x1545f  ldloc.s  6
0x15461  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::Add(var<u1>, !!T0)
0x15466  ldarg.0
0x15467  ldarg.0
0x15468  call     instance int64 BookableResourceCache::get_MinSyncVersionNumber()
0x1546d  ldloc.s  6
0x1546f  callvirt instance int64 CacheData::get_LastSyncVersionNumber()
0x15474  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x15479  call     instance void BookableResourceCache::set_MinSyncVersionNumber(int64 value)
0x1547e  ldloc.2
0x1547f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15484  brtrue   loc_153C9
0x15489  leave.s  loc_15495
0x1548b  ldloc.2
0x1548c  brfalse.s loc_15494
0x1548e  ldloc.2
0x1548f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15494  endfinally
0x15495  ldarg.0
0x15496  ldfld    class BookableResourceQuery BookableResourceCache::bookableResourceQuery
0x1549b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> PagedEntityQuery::Next()
0x154a0  stloc.1
0x154a1  ldloc.1
0x154a2  brtrue   loc_153BD
0x154a7  ret
```
