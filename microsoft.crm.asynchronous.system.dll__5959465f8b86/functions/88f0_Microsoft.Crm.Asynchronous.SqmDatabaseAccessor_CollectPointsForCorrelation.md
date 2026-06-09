# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCorrelation

- ea: `0x88f0`
- end: `0x88ff`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCorrelation`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8220`

## callees

- `0x8900`
- `0x8960`

## pseudocode

```c

```

## disassembly

```asm
0x88f0  ldarg.0
0x88f1  ldarg.1
0x88f2  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectOrganizationCorrelationSettings(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x88f7  ldarg.0
0x88f8  ldarg.1
0x88f9  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForCorrelatedEmails(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x88fe  ret
```
