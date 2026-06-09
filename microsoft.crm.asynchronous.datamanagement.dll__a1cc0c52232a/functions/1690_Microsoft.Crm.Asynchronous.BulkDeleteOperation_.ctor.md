# Microsoft.Crm.Asynchronous.BulkDeleteOperation::.ctor

- ea: `0x1690`
- end: `0x16a6`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::.ctor`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xee0`

## pseudocode

```c

```

## disassembly

```asm
0x1690  ldarg.0
0x1691  ldarg.1
0x1692  ldarg.2
0x1693  ldarg.3
0x1694  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationCommand::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x1699  ldarg.0
0x169a  ldarg.3
0x169b  newobj   instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x16a0  stfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x16a5  ret
```
