# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInExchangeForDisqualifyingChange

- ea: `0x6b70`
- end: `0x6b9c`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInExchangeForDisqualifyingChange`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x62c0`

## callees

- `0x6b70`
- `0x74e0`
- `0x13d50`
- `0x15de0`
- `0x15ea0`

## pseudocode

```c

```

## disassembly

```asm
0x6b70  ldarg.2
0x6b71  stloc.0
0x6b72  ldarg.2
0x6b73  brfalse.s loc_6B9A
0x6b75  ldarg.3
0x6b76  brfalse.s loc_6B8B
0x6b78  ldarg.2
0x6b79  callvirt instance int32 SyncDeleteCollection::get_Count()
0x6b7e  ldarg.0
0x6b7f  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x6b84  callvirt instance int32 ConfigurationSettings::get_ThresholdDeleteCollectionForDisqualifyingChanges()
0x6b89  blt.s    loc_6B9A
0x6b8b  ldarg.0
0x6b8c  ldarg.1
0x6b8d  ldarg.2
0x6b8e  ldc.i4.0
0x6b8f  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteCollectionInExchange(class SyncConfig syncConfig, class SyncDeleteCollection syncDeleteCollection, bool runTimeControlEnabled)
0x6b94  newobj   instance void SyncDeleteCollection::.ctor()
0x6b99  stloc.0
0x6b9a  ldloc.0
0x6b9b  ret
```
