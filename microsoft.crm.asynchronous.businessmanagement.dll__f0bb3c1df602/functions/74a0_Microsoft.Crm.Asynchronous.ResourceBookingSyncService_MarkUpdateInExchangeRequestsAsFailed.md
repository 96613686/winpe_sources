# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkUpdateInExchangeRequestsAsFailed

- ea: `0x74a0`
- end: `0x74b9`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkUpdateInExchangeRequestsAsFailed`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6f70`

## callees

- `0x7340`
- `0x74a0`

## pseudocode

```c

```

## disassembly

```asm
0x74a0  ldarg.s  4
0x74a2  stloc.0
0x74a3  br.s     loc_74B3
0x74a5  ldarg.0
0x74a6  ldarg.1
0x74a7  ldarg.2
0x74a8  ldarg.3
0x74a9  ldloc.0
0x74aa  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleUpdateInExchangeResponse(class SyncConfig syncConfig, class [mscorlib]System.Collections.ObjectModel.Collection`1<class SyncData> updateSyncData, class SyncResult syncResult, int32 index)
0x74af  ldloc.0
0x74b0  ldc.i4.1
0x74b1  add
0x74b2  stloc.0
0x74b3  ldloc.0
0x74b4  ldarg.s  5
0x74b6  blt.s    loc_74A5
0x74b8  ret
```
