# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkDeleteInExchangeRequestsAsFailed

- ea: `0x7ac0`
- end: `0x7ad9`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::MarkDeleteInExchangeRequestsAsFailed`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7600`

## callees

- `0x7860`
- `0x7ac0`

## pseudocode

```c

```

## disassembly

```asm
0x7ac0  ldarg.s  4
0x7ac2  stloc.0
0x7ac3  br.s     loc_7AD3
0x7ac5  ldarg.0
0x7ac6  ldarg.1
0x7ac7  ldarg.2
0x7ac8  ldarg.3
0x7ac9  ldloc.0
0x7aca  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::HandleDeleteInExchangeResponse(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class Data deletionData, class SyncResult syncResult, int32 index)
0x7acf  ldloc.0
0x7ad0  ldc.i4.1
0x7ad1  add
0x7ad2  stloc.0
0x7ad3  ldloc.0
0x7ad4  ldarg.s  5
0x7ad6  blt.s    loc_7AC5
0x7ad8  ret
```
