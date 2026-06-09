# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForMailboxes

- ea: `0x86c0`
- end: `0x86d6`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForMailboxes`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8220`

## callees

- `0x86e0`
- `0x8800`
- `0x88a0`

## pseudocode

```c

```

## disassembly

```asm
0x86c0  ldarg.0
0x86c1  ldarg.1
0x86c2  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectMailboxPerProfile(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x86c7  ldarg.0
0x86c8  ldarg.1
0x86c9  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectMailboxEmailDeliveryOptions(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x86ce  ldarg.0
0x86cf  ldarg.1
0x86d0  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectForwardMailboxCount(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x86d5  ret
```
