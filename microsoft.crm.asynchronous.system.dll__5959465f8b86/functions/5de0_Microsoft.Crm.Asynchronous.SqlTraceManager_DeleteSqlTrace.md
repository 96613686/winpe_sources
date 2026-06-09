# Microsoft.Crm.Asynchronous.SqlTraceManager::DeleteSqlTrace

- ea: `0x5de0`
- end: `0x5df2`
- name: `Microsoft.Crm.Asynchronous.SqlTraceManager::DeleteSqlTrace`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5db0`

## callees

- `0x2290`

## pseudocode

```c

```

## disassembly

```asm
0x5de0  ldarg.0
0x5de1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.SqlTraceManager::_connection
0x5de6  ldarg.0
0x5de7  ldfld    string Microsoft.Crm.Asynchronous.SqlTraceManager::_fullTracePath
0x5dec  call     void Microsoft.Crm.Asynchronous.DatabaseTuningUtility::DeleteRemoteFile(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string fileName)
0x5df1  ret
```
