# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeResponse

- ea: `0x7340`
- end: `0x73cf`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeResponse`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6f70`
- `0x74a0`

## callees

- `0x7340`
- `0x8050`
- `0x157e0`
- `0x15820`
- `0x15a20`
- `0x15a30`
- `0x16270`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x7346`: `MethodUpdateInExchange_HandleUpdateAppointmentsResponse`
- `0x73c4`: `MethodUpdateInExchange_HandleUpdateAppointmentsResponse`
- `0x739a`: `NumberOfAppointmentsForUpdateSyncSuccess`
- `0x73b0`: `NumberOfAppointmentsForUpdateSyncError`

## pseudocode

```c

```

## disassembly

```asm
0x7340  ldarg.0
0x7341  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7346  ldstr    aMethodupdatein_4// "MethodUpdateInExchange_HandleUpdateAppo"...
0x734b  callvirt instance void Metrics::StartTimer(string name)
0x7350  ldarg.2
0x7351  ldarg.s  4
0x7353  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::get_Item(!!T0)
0x7358  stloc.0
0x7359  ldloc.0
0x735a  ldarg.3
0x735b  callvirt instance void SyncData::set_SyncResult(class SyncResult value)
0x7360  ldarg.0
0x7361  ldarg.1
0x7362  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x7367  ldloc.0
0x7368  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class SyncData syncData)
0x736d  ldloc.0
0x736e  callvirt instance class SyncResult SyncData::get_SyncResult()
0x7373  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x7378  stloc.1
0x7379  ldc.i4.0
0x737a  stloc.2
0x737b  ldloca.s 1
0x737d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x7382  ldloc.2
0x7383  beq.s    loc_7388
0x7385  ldc.i4.1
0x7386  br.s     loc_7392
0x7388  ldloca.s 1
0x738a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x738f  ldc.i4.0
0x7390  ceq
0x7392  brfalse.s loc_73AA
0x7394  ldarg.0
0x7395  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x739a  ldstr    aNumberofappoin_3// "NumberOfAppointmentsForUpdateSyncSucces"...
0x739f  ldc.i4.1
0x73a0  ldc.i4.s 0x32
0x73a2  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x73a7  pop
0x73a8  br.s     loc_73BE
0x73aa  ldarg.0
0x73ab  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x73b0  ldstr    aNumberofappoin_4// "NumberOfAppointmentsForUpdateSyncError"
0x73b5  ldc.i4.1
0x73b6  ldc.i4.s 0x32
0x73b8  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x73bd  pop
0x73be  ldarg.0
0x73bf  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x73c4  ldstr    aMethodupdatein_4// "MethodUpdateInExchange_HandleUpdateAppo"...
0x73c9  callvirt instance void Metrics::StopTimer(string name)
0x73ce  ret
```
