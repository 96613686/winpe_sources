# Microsoft.Crm.Workflow.WorkflowContext::.ctor

- ea: `0x18e0`
- end: `0x18f6`
- name: `Microsoft.Crm.Workflow.WorkflowContext::.ctor`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x20`
- `0x280`

## callees

- `0x1900`
- `0x1d80`

## pseudocode

```c

```

## disassembly

```asm
0x18e0  ldarg.0
0x18e1  ldarg.1
0x18e2  ldarg.2
0x18e3  ldarg.3
0x18e4  ldarg.3
0x18e5  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData::get_Data()
0x18ea  ldarg.3
0x18eb  call     class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData Microsoft.Crm.Workflow.WorkflowContext::DeserializeAsyncData(string serialized, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData workflowInstanceData)
0x18f0  call     instance void Microsoft.Crm.Workflow.WorkflowContext::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IWorkflowContextService workflowContextService, string serviceName, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData workflowInstanceData, class [Microsoft.Crm]Microsoft.Crm.AsyncOperationData operationData)
0x18f5  ret
```
