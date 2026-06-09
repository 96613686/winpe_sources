# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForEmailConnector

- ea: `0x8220`
- end: `0x823d`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForEmailConnector`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x53d0`

## callees

- `0x8240`
- `0x83e0`
- `0x86c0`
- `0x88f0`

## pseudocode

```c

```

## disassembly

```asm
0x8220  ldarg.0
0x8221  ldarg.1
0x8222  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForSentAndReceivedEmails(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x8227  ldarg.0
0x8228  ldarg.1
0x8229  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForEmailServerProfileConfiguration(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x822e  ldarg.0
0x822f  ldarg.1
0x8230  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForMailboxes(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x8235  ldarg.0
0x8236  ldarg.1
0x8237  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCorrelation(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x823c  ret
```
