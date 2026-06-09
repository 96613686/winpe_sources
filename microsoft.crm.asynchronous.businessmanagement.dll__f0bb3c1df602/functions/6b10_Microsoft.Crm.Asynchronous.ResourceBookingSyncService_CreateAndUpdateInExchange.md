# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CreateAndUpdateInExchange

- ea: `0x6b10`
- end: `0x6b6e`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CreateAndUpdateInExchange`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x62c0`

## callees

- `0x6b10`
- `0x6ba0`
- `0x6f70`
- `0x7c10`
- `0x82b0`
- `0x15760`
- `0x157e0`
- `0x15b10`
- `0x15be0`
- `0x16260`
- `0x16390`

## string_xrefs

- `0x6b16`: `MethodCreateAndUpdateInExchange`
- `0x6b26`: `MethodCreateAndUpdateInExchangeCallCount`

## pseudocode

```c

```

## disassembly

```asm
0x6b10  ldarg.0
0x6b11  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6b16  ldstr    aMethodcreatean// "MethodCreateAndUpdateInExchange"
0x6b1b  callvirt instance void Metrics::StartTimer(string name)
0x6b20  ldarg.0
0x6b21  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6b26  ldstr    aMethodcreatean_0// "MethodCreateAndUpdateInExchangeCallCoun"...
0x6b2b  ldc.i4.1
0x6b2c  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x6b31  pop
0x6b32  ldarg.2
0x6b33  brfalse.s loc_6B6D
0x6b35  ldarg.0
0x6b36  ldarg.1
0x6b37  ldarg.2
0x6b38  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::CreateInExchange(class SyncConfig syncConfig, class SyncDataCollection collection)
0x6b3d  ldarg.0
0x6b3e  ldarg.1
0x6b3f  ldarg.2
0x6b40  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateInExchange(class SyncConfig syncConfig, class SyncDataCollection collection)
0x6b45  ldarg.0
0x6b46  ldarg.1
0x6b47  ldarg.2
0x6b48  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkAsPendingInSyncIdMapping(class SyncConfig syncConfig, class SyncDataCollection collection)
0x6b4d  ldarg.1
0x6b4e  callvirt instance bool SyncConfig::get_UpdateUserStatus()
0x6b53  brfalse.s loc_6B6D
0x6b55  ldarg.0
0x6b56  ldarg.1
0x6b57  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection SyncConfig::get_DbConnection()
0x6b5c  ldarg.2
0x6b5d  callvirt instance valuetype [mscorlib]System.Guid SyncDataCollection::get_UserId()
0x6b62  ldarg.2
0x6b63  callvirt instance int64 SyncDataCollection::get_MaxVersionNumber()
0x6b68  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateUserSyncVersion(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, valuetype [mscorlib]System.Guid userId, int64 lastSyncedVersionNumber)
0x6b6d  ret
```
