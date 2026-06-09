# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForSentAndReceivedEmails

- ea: `0x8240`
- end: `0x825d`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForSentAndReceivedEmails`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x8220`

## callees

- `0x8260`
- `0x82b0`
- `0x8320`
- `0x8390`

## pseudocode

```c

```

## disassembly

```asm
0x8240  ldarg.0
0x8241  ldarg.1
0x8242  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForReceivedEmails(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x8247  ldarg.0
0x8248  ldarg.1
0x8249  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCreatedEmails(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x824e  ldarg.0
0x824f  ldarg.1
0x8250  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForSentEmails(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x8255  ldarg.0
0x8256  ldarg.1
0x8257  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForAverageSendingTime(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x825c  ret
```
