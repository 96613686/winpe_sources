# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForEmailServerProfileConfiguration

- ea: `0x83e0`
- end: `0x8404`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectPointsForEmailServerProfileConfiguration`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8220`

## callees

- `0x8410`
- `0x8490`
- `0x8510`
- `0x85b0`
- `0x8600`

## pseudocode

```c

```

## disassembly

```asm
0x83e0  ldarg.0
0x83e1  ldarg.1
0x83e2  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectEmailServerTypeAndActiveProfile(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x83e7  ldarg.0
0x83e8  ldarg.1
0x83e9  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectIncomingConnectionType(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x83ee  ldarg.0
0x83ef  ldarg.1
0x83f0  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectOutgoingConnectionType(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x83f5  ldarg.0
0x83f6  ldarg.1
0x83f7  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectUseAsWindowsCredentials(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x83fc  ldarg.0
0x83fd  ldarg.1
0x83fe  call     instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectIncomingAndOutgoingAccessType(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x8403  ret
```
