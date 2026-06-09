# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncResourceBookings

- ea: `0x62c0`
- end: `0x6510`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::SyncResourceBookings`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x6510`
- `0x8b10`
- `0x8b20`

## callees

- `0x62c0`
- `0x6b10`
- `0x6b70`
- `0x83a0`
- `0x8780`
- `0x8ab0`
- `0x13d00`
- `0x13f60`
- `0x15720`
- `0x15740`
- `0x157a0`
- `0x157f0`
- `0x15bf0`
- `0x15c00`
- `0x15ea0`
- `0x16000`
- `0x16260`
- `0x16390`
- `0x163e0`
- `0x16480`
- `0x16550`

## pseudocode

```c

```

## disassembly

```asm
0x62c0  ldarg.0
0x62c1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x62c6  ldstr    aMethodsyncreso// "MethodSyncResourceBookings"
0x62cb  callvirt instance void Metrics::StartTimer(string name)
0x62d0  ldarg.0
0x62d1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x62d6  ldstr    aMethodsyncreso_0// "MethodSyncResourceBookingsCallCount"
0x62db  ldc.i4.1
0x62dc  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x62e1  pop
0x62e2  ldarg.0
0x62e3  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x62e8  ldstr    aMethodsyncreso_1// "MethodSyncResourceBookings_QueryNext"
0x62ed  callvirt instance void Metrics::StartTimer(string name)
0x62f2  ldarg.1
0x62f3  callvirt instance class IEntityQuery SyncConfig::get_Query()
0x62f8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> IEntityQuery::Next()
0x62fd  stloc.0
0x62fe  ldarg.0
0x62ff  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6304  ldstr    aMethodsyncreso_1// "MethodSyncResourceBookings_QueryNext"
0x6309  callvirt instance void Metrics::StopTimer(string name)
0x630e  ldc.i4.0
0x630f  stloc.1
0x6310  newobj   instance void SyncDeleteCollection::.ctor()
0x6315  stloc.2
0x6316  ldc.i4.0
0x6317  stloc.3
0x6318  br       loc_64F6
0x631d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x6322  ldc.i4.0
0x6323  ldc.i4.0
0x6324  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x6329  stloc.s  4
0x632b  ldloc.s  4
0x632d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6332  ldarg.1
0x6333  ldloc.s  4
0x6335  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x633a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x633f  stloc.s  5
0x6341  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6346  stloc.s  6
0x6348  ldnull
0x6349  stloc.s  7
0x634b  ldnull
0x634c  stloc.s  8
0x634e  ldloc.0
0x634f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x6354  stloc.s  9
0x6356  br       loc_647D
0x635b  ldloc.s  9
0x635d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x6362  stloc.s  0xA
0x6364  ldloc.s  0xA
0x6366  call     bool ResourceBookingUtil::Validate(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity resourceBooking)
0x636b  brfalse  loc_647D
0x6370  ldloc.s  0xA
0x6372  ldstr    aSystemuserSyst// "systemuser.systemuserid"
0x6377  callvirt T0x2B00000F
0x637c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x6381  unbox.any [mscorlib]System.Guid
0x6386  stloc.s  6
0x6388  ldloc.s  5
0x638a  ldloc.s  6
0x638c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6391  brfalse  loc_6467
0x6396  ldarg.0
0x6397  ldarg.1
0x6398  ldloc.s  8
0x639a  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CreateAndUpdateInExchange(class SyncConfig syncConfig, class SyncDataCollection collection)
0x639f  ldarg.0
0x63a0  ldarg.1
0x63a1  ldloc.2
0x63a2  ldc.i4.1
0x63a3  call     instance class SyncDeleteCollection Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInExchangeForDisqualifyingChange(class SyncConfig syncConfig, class SyncDeleteCollection syncDeleteCollection, bool thresholdEnabled)
0x63a8  stloc.2
0x63a9  ldloc.1
0x63aa  ldloc.s  5
0x63ac  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x63b1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x63b6  brtrue.s loc_63BB
0x63b8  ldc.i4.0
0x63b9  br.s     loc_63BC
0x63bb  ldc.i4.1
0x63bc  add
0x63bd  stloc.1
0x63be  call     bool RunTimeControl::get_IsExpired()
0x63c3  stloc.3
0x63c4  ldloc.3
0x63c5  brfalse.s loc_63F0
0x63c7  ldnull
0x63c8  stloc.s  8
0x63ca  ldarg.0
0x63cb  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x63d0  ldstr    aStopped0AfterP// "Stopped {0} after processing {1} users."
0x63d5  ldarg.1
0x63d6  callvirt instance string SyncConfig::get_Name()
0x63db  ldloc.1
0x63dc  box      [mscorlib]System.Int32
0x63e1  call     string [mscorlib]System.String::Format(string, object, object)
0x63e6  callvirt instance void Metrics::RunTimeExpired(string message)
0x63eb  leave    loc_6497
0x63f0  ldloc.s  6
0x63f2  stloc.s  5
0x63f4  ldarg.0
0x63f5  ldarg.1
0x63f6  callvirt instance class BookableResourceCache SyncConfig::get_BookableResourceCache()
0x63fb  ldloc.s  5
0x63fd  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetExchangeService(class BookableResourceCache bookableResourceCache, valuetype [mscorlib]System.Guid userId)
0x6402  stloc.s  7
0x6404  ldloc.s  0xA
0x6406  ldstr    aSystemuserBusi// "systemuser.businessunitid"
0x640b  callvirt T0x2B00000F
0x6410  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x6415  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x641a  stloc.s  0xB
0x641c  ldloc.s  0xA
0x641e  ldstr    aUsersettingsRe// "usersettings.resourcebookingexchangesyn"...
0x6423  callvirt T0x2B00000F
0x6428  stloc.s  0xC
0x642a  ldloc.s  7
0x642c  ldloc.s  5
0x642e  ldloc.s  0xB
0x6430  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x6435  ldloc.s  0xC
0x6437  brtrue.s loc_643D
0x6439  ldc.i4.0
0x643a  conv.i8
0x643b  br.s     loc_6449
0x643d  ldloc.s  0xC
0x643f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x6444  unbox.any [mscorlib]System.Int64
0x6449  call     class SyncDataCollection SyncDataCollection::Create(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService exchangeService, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid businessUnitId, int64 lastSyncVersionNumber)
0x644e  stloc.s  8
0x6450  ldarg.0
0x6451  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6456  ldstr    aUsers// "Users"
0x645b  ldloc.s  6
0x645d  box      [mscorlib]System.Guid
0x6462  callvirt instance void Metrics::AddToSet(string name, object value)
0x6467  ldloc.s  8
0x6469  ldarg.0
0x646a  ldarg.1
0x646b  ldloc.s  5
0x646d  ldloc.s  7
0x646f  ldloc.s  0xA
0x6471  ldloc.2
0x6472  call     instance class SyncData Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetSyncData(class SyncConfig syncConfig, valuetype [mscorlib]System.Guid userId, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService exchangeService, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity resourceBooking, class SyncDeleteCollection deleteCollection)
0x6477  callvirt instance bool SyncDataCollection::Add(class SyncData syncData)
0x647c  pop
0x647d  ldloc.s  9
0x647f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6484  brtrue   loc_635B
0x6489  leave.s  loc_6497
0x648b  ldloc.s  9
0x648d  brfalse.s loc_6496
0x648f  ldloc.s  9
0x6491  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6496  endfinally
0x6497  ldarg.0
0x6498  ldarg.1
0x6499  ldloc.s  8
0x649b  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CreateAndUpdateInExchange(class SyncConfig syncConfig, class SyncDataCollection collection)
0x64a0  ldarg.0
0x64a1  ldarg.1
0x64a2  ldloc.2
0x64a3  ldc.i4.0
0x64a4  call     instance class SyncDeleteCollection Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInExchangeForDisqualifyingChange(class SyncConfig syncConfig, class SyncDeleteCollection syncDeleteCollection, bool thresholdEnabled)
0x64a9  pop
0x64aa  ldloc.3
0x64ab  brtrue.s loc_64D9
0x64ad  ldarg.0
0x64ae  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x64b3  ldstr    aMethodsyncreso_1// "MethodSyncResourceBookings_QueryNext"
0x64b8  callvirt instance void Metrics::StartTimer(string name)
0x64bd  ldarg.1
0x64be  callvirt instance class IEntityQuery SyncConfig::get_Query()
0x64c3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> IEntityQuery::Next()
0x64c8  stloc.0
0x64c9  ldarg.0
0x64ca  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x64cf  ldstr    aMethodsyncreso_1// "MethodSyncResourceBookings_QueryNext"
0x64d4  callvirt instance void Metrics::StopTimer(string name)
0x64d9  leave.s  loc_64F6
0x64db  ldloc.s  4
0x64dd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x64e2  ldarg.1
0x64e3  ldnull
0x64e4  callvirt instance void SyncConfig::set_DbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection value)
0x64e9  endfinally
0x64ea  ldloc.s  4
0x64ec  brfalse.s loc_64F5
0x64ee  ldloc.s  4
0x64f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64f5  endfinally
0x64f6  ldloc.0
0x64f7  brfalse.s loc_64FF
0x64f9  ldloc.3
0x64fa  brfalse  loc_631D
0x64ff  ldarg.0
0x6500  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6505  ldstr    aMethodsyncreso// "MethodSyncResourceBookings"
0x650a  callvirt instance void Metrics::StopTimer(string name)
0x650f  ret
```
