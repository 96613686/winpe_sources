# Microsoft.Crm.Asynchronous.BulkDeleteOperation::<InternalExecute>b__15_1

- ea: `0x2b10`
- end: `0x2b22`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::<InternalExecute>b__15_1`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1080`

## pseudocode

```c

```

## disassembly

```asm
0x2b10  ldarg.0
0x2b11  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x2b16  ldarg.0
0x2b17  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempDependentTableName
0x2b1c  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DropTableIfDeletionHadNotStarted(string tableName)
0x2b21  ret
```
