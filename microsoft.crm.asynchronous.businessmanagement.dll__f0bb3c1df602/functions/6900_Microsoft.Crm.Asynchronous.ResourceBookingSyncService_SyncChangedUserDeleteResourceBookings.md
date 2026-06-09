# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncChangedUserDeleteResourceBookings

- ea: `0x6900`
- end: `0x6a0d`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncChangedUserDeleteResourceBookings`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b50`

## callees

- `0x6900`
- `0x74e0`
- `0x8ab0`
- `0x13d00`
- `0x13f60`
- `0x15740`
- `0x157f0`
- `0x15e20`
- `0x15ea0`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x6906`: `MethodSyncChangedUserDeleteResourceBookings`
- `0x6a02`: `MethodSyncChangedUserDeleteResourceBookings`
- `0x6916`: `MethodSyncChangedUserDeleteResourceBookings_QueryNext`
- `0x6932`: `MethodSyncChangedUserDeleteResourceBookings_QueryNext`
- `0x698c`: `isdeletedinexchange`

## pseudocode

```c

```

## disassembly

```asm
0x6900  ldarg.0
0x6901  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6906  ldstr    aMethodsyncchan// "MethodSyncChangedUserDeleteResourceBook"...
0x690b  callvirt instance void Metrics::StartTimer(string name)
0x6910  ldarg.0
0x6911  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6916  ldstr    aMethodsyncchan_0// "MethodSyncChangedUserDeleteResourceBook"...
0x691b  callvirt instance void Metrics::StartTimer(string name)
0x6920  ldarg.1
0x6921  callvirt instance class IEntityQuery SyncConfig::get_Query()
0x6926  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> IEntityQuery::Next()
0x692b  stloc.0
0x692c  ldarg.0
0x692d  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6932  ldstr    aMethodsyncchan_0// "MethodSyncChangedUserDeleteResourceBook"...
0x6937  callvirt instance void Metrics::StopTimer(string name)
0x693c  call     bool RunTimeControl::get_IsExpired()
0x6941  brtrue   loc_69FC
0x6946  newobj   instance void SyncDeleteCollection::.ctor()
0x694b  stloc.1
0x694c  ldloc.0
0x694d  brfalse  loc_69FC
0x6952  ldloc.0
0x6953  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x6958  stloc.2
0x6959  br.s     loc_69A5
0x695b  ldloc.2
0x695c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x6961  dup
0x6962  ldstr    aUserid// "userid"
0x6967  callvirt T0x2B000013
0x696c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x6971  stloc.3
0x6972  dup
0x6973  ldstr    aExchangeentryi// "exchangeentryid"
0x6978  callvirt T0x2B000011
0x697d  stloc.s  4
0x697f  dup
0x6980  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x6985  callvirt T0x2B000010
0x698a  stloc.s  5
0x698c  ldstr    aIsdeletedinexc// "isdeletedinexchange"
0x6991  callvirt T0x2B000014
0x6996  brtrue.s loc_69A5
0x6998  ldloc.1
0x6999  ldloc.3
0x699a  ldloc.s  4
0x699c  ldc.i4.0
0x699d  ldloc.s  5
0x699f  callvirt instance bool SyncDeleteCollection::Add(valuetype [mscorlib]System.Guid userId, string exchangeId, bool keepIdMappingAfterExchangeDelete, valuetype [mscorlib]System.Guid mappingId)
0x69a4  pop
0x69a5  ldloc.2
0x69a6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x69ab  brtrue.s loc_695B
0x69ad  leave.s  loc_69B9
0x69af  ldloc.2
0x69b0  brfalse.s loc_69B8
0x69b2  ldloc.2
0x69b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69b8  endfinally
0x69b9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x69be  ldc.i4.0
0x69bf  ldc.i4.0
0x69c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x69c5  stloc.s  6
0x69c7  ldloc.s  6
0x69c9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x69ce  ldarg.1
0x69cf  ldloc.s  6
0x69d1  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x69d6  ldarg.0
0x69d7  ldarg.1
0x69d8  ldloc.1
0x69d9  ldc.i4.1
0x69da  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteCollectionInExchange(class SyncConfig syncConfig, class SyncDeleteCollection syncDeleteCollection, bool runTimeControlEnabled)
0x69df  leave.s  loc_69FC
0x69e1  ldloc.s  6
0x69e3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x69e8  ldarg.1
0x69e9  ldnull
0x69ea  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x69ef  endfinally
0x69f0  ldloc.s  6
0x69f2  brfalse.s loc_69FB
0x69f4  ldloc.s  6
0x69f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69fb  endfinally
0x69fc  ldarg.0
0x69fd  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6a02  ldstr    aMethodsyncchan// "MethodSyncChangedUserDeleteResourceBook"...
0x6a07  callvirt instance void Metrics::StopTimer(string name)
0x6a0c  ret
```
