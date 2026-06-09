# Microsoft.Crm.Asynchronous.BulkDeleteParametersCollector::Collect

- ea: `0x52d0`
- end: `0x52e2`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteParametersCollector::Collect`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6660`
- `0x70e0`

## pseudocode

```c

```

## disassembly

```asm
0x52d0  ldarg.0
0x52d1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.BulkDeleteParametersCollector::_configuration
0x52d6  newobj   instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x52db  ldarg.1
0x52dc  callvirt instance void Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForBulkDelete(class [Microsoft.Crm]Microsoft.Crm.ISqmSession session)
0x52e1  ret
```
