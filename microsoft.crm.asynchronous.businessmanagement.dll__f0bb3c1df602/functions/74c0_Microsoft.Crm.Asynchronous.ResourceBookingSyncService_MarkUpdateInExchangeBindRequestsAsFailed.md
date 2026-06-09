# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkUpdateInExchangeBindRequestsAsFailed

- ea: `0x74c0`
- end: `0x74dc`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkUpdateInExchangeBindRequestsAsFailed`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6f70`

## callees

- `0x73d0`
- `0x74c0`

## pseudocode

```c

```

## disassembly

```asm
0x74c0  ldarg.s  4
0x74c2  stloc.0
0x74c3  br.s     loc_74D6
0x74c5  ldarg.0
0x74c6  ldarg.1
0x74c7  ldarg.2
0x74c8  ldnull
0x74c9  ldnull
0x74ca  ldnull
0x74cb  ldarg.3
0x74cc  ldloc.0
0x74cd  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeBindResponse(class SyncConfig syncConfig, class SyncDataCollection collection, class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.GetItemResponse itemResponse, class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> updateSyncData, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment> updateAppointments, class SyncResult syncResult, int32 index)
0x74d2  ldloc.0
0x74d3  ldc.i4.1
0x74d4  add
0x74d5  stloc.0
0x74d6  ldloc.0
0x74d7  ldarg.s  5
0x74d9  blt.s    loc_74C5
0x74db  ret
```
