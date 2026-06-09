# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkAsPendingInSyncIdMapping

- ea: `0x7c10`
- end: `0x7cf5`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkAsPendingInSyncIdMapping`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x6b10`

## callees

- `0x7c10`
- `0x7d00`
- `0x8050`
- `0x157e0`
- `0x15950`
- `0x159a0`
- `0x15a30`
- `0x15b50`
- `0x15bb0`
- `0x16260`
- `0x16390`
- `0x163e0`

## pseudocode

```c

```

## disassembly

```asm
0x7c10  ldarg.0
0x7c11  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7c16  ldstr    aMethodmarkaspe// "MethodMarkAsPendingInSyncIdMapping"
0x7c1b  callvirt instance void Metrics::StartTimer(string name)
0x7c20  ldarg.2
0x7c21  brfalse  loc_7CE4
0x7c26  ldarg.2
0x7c27  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> SyncDataCollection::get_PendingSyncData()
0x7c2c  brfalse  loc_7CE4
0x7c31  ldarg.2
0x7c32  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> SyncDataCollection::get_PendingSyncData()
0x7c37  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::get_Count()
0x7c3c  ldc.i4.0
0x7c3d  ble      loc_7CE4
0x7c42  ldarg.2
0x7c43  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService SyncDataCollection::get_ExchangeService()
0x7c48  brfalse  loc_7CE4
0x7c4d  ldarg.0
0x7c4e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7c53  ldstr    aNumberofusersf_2// "NumberOfUsersForPendingSync"
0x7c58  ldc.i4.1
0x7c59  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x7c5e  pop
0x7c5f  ldarg.0
0x7c60  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7c65  ldstr    aNumberofappoin_10// "NumberOfAppointmentsForPendingSync"
0x7c6a  ldarg.2
0x7c6b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> SyncDataCollection::get_PendingSyncData()
0x7c70  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::get_Count()
0x7c75  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x7c7a  pop
0x7c7b  ldarg.2
0x7c7c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> SyncDataCollection::get_PendingSyncData()
0x7c81  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::GetEnumerator()
0x7c86  stloc.0
0x7c87  br.s     loc_7CD0
0x7c89  ldloc.0
0x7c8a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class SyncData>::get_Current()
0x7c8f  stloc.1
0x7c90  ldloc.1
0x7c91  ldc.i4.3
0x7c92  newobj   instance void SyncResult::.ctor(valuetype OperationResult result)
0x7c97  callvirt instance void SyncData::set_SyncResult(class SyncResult value)
0x7c9c  ldloc.1
0x7c9d  callvirt instance valuetype [mscorlib]System.Guid SyncData::get_Id()
0x7ca2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7ca7  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7cac  brfalse.s loc_7CC3
0x7cae  ldarg.0
0x7caf  ldarg.1
0x7cb0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x7cb5  ldarg.2
0x7cb6  ldloc.1
0x7cb7  ldsfld   string [mscorlib]System.String::Empty
0x7cbc  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::InsertSyncIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class SyncDataCollection collection, class SyncData syncData, string exchangeId)
0x7cc1  br.s     loc_7CD0
0x7cc3  ldarg.0
0x7cc4  ldarg.1
0x7cc5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x7cca  ldloc.1
0x7ccb  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class SyncData syncData)
0x7cd0  ldloc.0
0x7cd1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7cd6  brtrue.s loc_7C89
0x7cd8  leave.s  loc_7CE4
0x7cda  ldloc.0
0x7cdb  brfalse.s loc_7CE3
0x7cdd  ldloc.0
0x7cde  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ce3  endfinally
0x7ce4  ldarg.0
0x7ce5  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7cea  ldstr    aMethodmarkaspe// "MethodMarkAsPendingInSyncIdMapping"
0x7cef  callvirt instance void Metrics::StopTimer(string name)
0x7cf4  ret
```
