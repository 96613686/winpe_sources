# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeBindResponse

- ea: `0x73d0`
- end: `0x7494`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeBindResponse`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6f70`
- `0x74c0`

## callees

- `0x73d0`
- `0x8050`
- `0x157e0`
- `0x15820`
- `0x15a20`
- `0x15a30`
- `0x15a70`
- `0x15ba0`
- `0x16270`

## string_xrefs

- `0x7439`: `NumberOfAppointmentsForUpdateGetSuccess`
- `0x747e`: `NumberOfAppointmentsForUpdateGetError`

## pseudocode

```c

```

## disassembly

```asm
0x73d0  ldarg.2
0x73d1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> SyncDataCollection::get_UpdateSyncData()
0x73d6  ldarg.s  7
0x73d8  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::get_Item(!!T0)
0x73dd  stloc.0
0x73de  ldloc.0
0x73df  ldarg.s  6
0x73e1  callvirt instance void SyncData::set_SyncResult(class SyncResult value)
0x73e6  ldarg.3
0x73e7  brfalse.s loc_7447
0x73e9  ldloc.0
0x73ea  callvirt instance class SyncResult SyncData::get_SyncResult()
0x73ef  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x73f4  stloc.1
0x73f5  ldc.i4.0
0x73f6  stloc.2
0x73f7  ldloca.s 1
0x73f9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x73fe  ldloc.2
0x73ff  beq.s    loc_7404
0x7401  ldc.i4.1
0x7402  br.s     loc_740E
0x7404  ldloca.s 1
0x7406  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x740b  ldc.i4.0
0x740c  ceq
0x740e  brfalse.s loc_7447
0x7410  ldarg.3
0x7411  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.GetItemResponse::get_Item()
0x7416  castclass [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment
0x741b  stloc.3
0x741c  ldloc.0
0x741d  ldloc.3
0x741e  callvirt instance void SyncData::InitializeAppointment(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment appointment)
0x7423  ldarg.s  5
0x7425  ldloc.3
0x7426  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment>::Add(var<u1>)
0x742b  ldarg.s  4
0x742d  ldloc.0
0x742e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData>::Add(var<u1>)
0x7433  ldarg.0
0x7434  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7439  ldstr    aNumberofappoin_5// "NumberOfAppointmentsForUpdateGetSuccess"
0x743e  ldc.i4.1
0x743f  ldc.i4.s 0x32
0x7441  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x7446  pop
0x7447  ldloc.0
0x7448  callvirt instance class SyncResult SyncData::get_SyncResult()
0x744d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype OperationResult> SyncResult::get_Result()
0x7452  stloc.1
0x7453  ldc.i4.0
0x7454  stloc.2
0x7455  ldloca.s 1
0x7457  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::GetValueOrDefault()
0x745c  ldloc.2
0x745d  beq.s    loc_7462
0x745f  ldc.i4.0
0x7460  br.s     loc_7469
0x7462  ldloca.s 1
0x7464  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype OperationResult>::get_HasValue()
0x7469  brfalse.s loc_748C
0x746b  ldarg.0
0x746c  ldarg.1
0x746d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x7472  ldloc.0
0x7473  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class SyncData syncData)
0x7478  ldarg.0
0x7479  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x747e  ldstr    aNumberofappoin_6// "NumberOfAppointmentsForUpdateGetError"
0x7483  ldc.i4.1
0x7484  ldc.i4.s 0x32
0x7486  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x748b  pop
0x748c  ldloc.0
0x748d  ldnull
0x748e  callvirt instance void SyncData::set_SyncResult(class SyncResult value)
0x7493  ret
```
