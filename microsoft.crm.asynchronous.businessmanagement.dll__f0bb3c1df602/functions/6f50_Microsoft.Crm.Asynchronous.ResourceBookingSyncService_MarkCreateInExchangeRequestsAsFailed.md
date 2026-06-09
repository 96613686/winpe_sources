# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkCreateInExchangeRequestsAsFailed

- ea: `0x6f50`
- end: `0x6f69`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkCreateInExchangeRequestsAsFailed`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ba0`

## callees

- `0x6e20`
- `0x6f50`

## pseudocode

```c

```

## disassembly

```asm
0x6f50  ldarg.s  4
0x6f52  stloc.0
0x6f53  br.s     loc_6F63
0x6f55  ldarg.0
0x6f56  ldarg.1
0x6f57  ldarg.2
0x6f58  ldarg.3
0x6f59  ldloc.0
0x6f5a  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleCreateInExchangeResponse(class SyncConfig syncConfig, class SyncDataCollection collection, class SyncResult syncResult, int32 index)
0x6f5f  ldloc.0
0x6f60  ldc.i4.1
0x6f61  add
0x6f62  stloc.0
0x6f63  ldloc.0
0x6f64  ldarg.s  5
0x6f66  blt.s    loc_6F55
0x6f68  ret
```
