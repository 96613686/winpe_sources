# Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::.ctor

- ea: `0x27d0`
- end: `0x27e5`
- name: `Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1c70`

## pseudocode

```c

```

## disassembly

```asm
0x27d0  ldarg.0
0x27d1  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::.ctor()
0x27d6  ldarg.0
0x27d7  ldarg.1
0x27d8  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::_context
0x27dd  ldarg.0
0x27de  ldarg.2
0x27df  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::_configuration
0x27e4  ret
```
