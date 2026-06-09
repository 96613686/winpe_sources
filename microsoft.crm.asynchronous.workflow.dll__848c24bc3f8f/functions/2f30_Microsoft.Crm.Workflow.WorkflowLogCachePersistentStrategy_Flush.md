# Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Flush

- ea: `0x2f30`
- end: `0x2f53`
- name: `Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::Flush`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2ec0`

## callees

- `0x1a90`
- `0x28e0`
- `0x2920`

## pseudocode

```c

```

## disassembly

```asm
0x2f30  ldarg.0
0x2f31  ldfld    class Microsoft.Crm.Workflow.WorkflowContext Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::_context
0x2f36  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.WorkflowContext::get_OrganizationConfiguration()
0x2f3b  newobj   instance void Microsoft.Crm.Workflow.WorkflowLogDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x2f40  ldarg.0
0x2f41  ldfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor> Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::operations
0x2f46  ldarg.0
0x2f47  ldfld    class Microsoft.Crm.Workflow.WorkflowContext Microsoft.Crm.Workflow.WorkflowLogCachePersistentStrategy::_context
0x2f4c  callvirt instance int32 Microsoft.Crm.Workflow.WorkflowLogDataAccess::FlushPendingWorkflowLog(class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Workflow.WorkflowLogDescriptor> logs, class Microsoft.Crm.Workflow.WorkflowContext context)
0x2f51  pop
0x2f52  ret
```
