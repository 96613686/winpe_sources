# Microsoft.Crm.Workflow.WorkflowContext::UpdateWorkflowInstanceStage

- ea: `0x1d60`
- end: `0x1d78`
- name: `Microsoft.Crm.Workflow.WorkflowContext::UpdateWorkflowInstanceStage`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1a90`
- `0x2290`

## pseudocode

```c

```

## disassembly

```asm
0x1d60  ldarg.0
0x1d61  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.WorkflowContext::get_OrganizationConfiguration()
0x1d66  newobj   instance void Microsoft.Crm.Workflow.WorkflowDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x1d6b  ldarg.0
0x1d6c  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OperationId()
0x1d71  ldarg.1
0x1d72  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowDataAccess::UpdateWorkflowInstanceStage(valuetype [mscorlib]System.Guid, string)
0x1d77  ret
```
