# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleCreateInExchangeResponse

- ea: `0x6e20`
- end: `0x6f45`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleCreateInExchangeResponse`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ba0`
- `0x6f50`

## callees

- `0x6e20`
- `0x7d00`
- `0x8050`
- `0x157e0`
- `0x15820`
- `0x159a0`
- `0x159c0`
- `0x159d0`
- `0x15a20`
- `0x15a30`
- `0x15b70`
- `0x15b90`
- `0x16270`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x6e26`: `MethodHandleCreateInExchangeResponse`
- `0x6f3a`: `MethodHandleCreateInExchangeResponse`
- `0x6e72`: `NumberOfAppointmentsForCreateSyncSuccess`
- `0x6e88`: `NumberOfAppointmentsForCreateSyncError`

## pseudocode

```c

```

## disassembly

```asm
0x6e20  ldarg.0
0x6e21  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6e26  ldstr    aMethodhandlecr// "MethodHandleCreateInExchangeResponse"
0x6e2b  callvirt instance void Metrics::StartTimer(string name)
0x6e30  ldarg.2
0x6e31  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> SyncDataCollection::get_CreateSyncData()
0x6e36  ldarg.s  4
0x6e38  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::get_Item(!!T0)
0x6e3d  stloc.0
0x6e3e  ldloc.0
0x6e3f  ldarg.3
0x6e40  callvirt instance void SyncData::set_SyncResult(class SyncResult value)
0x6e45  ldloc.0
0x6e46  callvirt instance class SyncResult SyncData::get_SyncResult()
0x6e4b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x6e50  stloc.2
0x6e51  ldc.i4.0
0x6e52  stloc.3
0x6e53  ldloca.s 2
0x6e55  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x6e5a  ldloc.3
0x6e5b  beq.s    loc_6E60
0x6e5d  ldc.i4.1
0x6e5e  br.s     loc_6E6A
0x6e60  ldloca.s 2
0x6e62  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x6e67  ldc.i4.0
0x6e68  ceq
0x6e6a  brfalse.s loc_6E82
0x6e6c  ldarg.0
0x6e6d  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6e72  ldstr    aNumberofappoin_0// "NumberOfAppointmentsForCreateSyncSucces"...
0x6e77  ldc.i4.1
0x6e78  ldc.i4.s 0x32
0x6e7a  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x6e7f  pop
0x6e80  br.s     loc_6E96
0x6e82  ldarg.0
0x6e83  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6e88  ldstr    aNumberofappoin_1// "NumberOfAppointmentsForCreateSyncError"
0x6e8d  ldc.i4.1
0x6e8e  ldc.i4.s 0x32
0x6e90  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x6e95  pop
0x6e96  ldarg.2
0x6e97  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> SyncDataCollection::get_CreateAppointments()
0x6e9c  ldarg.s  4
0x6e9e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::get_Item(!!T0)
0x6ea3  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x6ea8  brtrue.s loc_6EB1
0x6eaa  ldsfld   string [mscorlib]System.String::Empty
0x6eaf  br.s     loc_6EC8
0x6eb1  ldarg.2
0x6eb2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> SyncDataCollection::get_CreateAppointments()
0x6eb7  ldarg.s  4
0x6eb9  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::get_Item(!!T0)
0x6ebe  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x6ec3  callvirt instance string [mscorlib]System.Object::ToString()
0x6ec8  stloc.1
0x6ec9  ldloc.0
0x6eca  callvirt instance valuetype [mscorlib]System.Guid SyncData::get_Id()
0x6ecf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ed4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ed9  brfalse.s loc_6EEC
0x6edb  ldarg.0
0x6edc  ldarg.1
0x6edd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x6ee2  ldarg.2
0x6ee3  ldloc.0
0x6ee4  ldloc.1
0x6ee5  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::InsertSyncIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class SyncDataCollection collection, class SyncData syncData, string exchangeId)
0x6eea  br.s     loc_6F34
0x6eec  ldloc.0
0x6eed  callvirt instance class SyncResult SyncData::get_SyncResult()
0x6ef2  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x6ef7  stloc.2
0x6ef8  ldc.i4.0
0x6ef9  stloc.3
0x6efa  ldloca.s 2
0x6efc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x6f01  ldloc.3
0x6f02  beq.s    loc_6F07
0x6f04  ldc.i4.1
0x6f05  br.s     loc_6F11
0x6f07  ldloca.s 2
0x6f09  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x6f0e  ldc.i4.0
0x6f0f  ceq
0x6f11  brfalse.s loc_6F27
0x6f13  ldloc.0
0x6f14  callvirt instance string SyncData::get_ExchangeId()
0x6f19  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6f1e  brfalse.s loc_6F27
0x6f20  ldloc.0
0x6f21  ldloc.1
0x6f22  callvirt instance void SyncData::set_ExchangeId(string value)
0x6f27  ldarg.0
0x6f28  ldarg.1
0x6f29  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x6f2e  ldloc.0
0x6f2f  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class SyncData syncData)
0x6f34  ldarg.0
0x6f35  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6f3a  ldstr    aMethodhandlecr// "MethodHandleCreateInExchangeResponse"
0x6f3f  callvirt instance void Metrics::StopTimer(string name)
0x6f44  ret
```
