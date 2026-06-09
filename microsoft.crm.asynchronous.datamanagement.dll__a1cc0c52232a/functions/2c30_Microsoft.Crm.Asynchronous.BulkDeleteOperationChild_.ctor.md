# Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::.ctor

- ea: `0x2c30`
- end: `0x2c46`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::.ctor`
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
0x2c30  ldarg.0
0x2c31  ldarg.1
0x2c32  ldarg.2
0x2c33  ldarg.3
0x2c34  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationCommand::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x2c39  ldarg.0
0x2c3a  ldarg.3
0x2c3b  newobj   instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x2c40  stfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_bulkDeleteDataAccess
0x2c45  ret
```
