# Microsoft.Crm.Workflow.ActivityHostBase::CompleteWorkflow

- ea: `0x5bf0`
- end: `0x5c26`
- name: `Microsoft.Crm.Workflow.ActivityHostBase::CompleteWorkflow`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x5590`
- `0x5950`
- `0x59f0`
- `0x5a60`
- `0x10ad0`
- `0x10fa0`

## callees

- `0x5190`
- `0x5680`
- `0x5bd0`
- `0x5bf0`
- `0x68e0`
- `0x6a80`
- `0x8be0`

## pseudocode

```c

```

## disassembly

```asm
0x5bf0  ldarg.1
0x5bf1  isinst   Microsoft.Crm.Workflow.WorkflowOperationSucceededResult
0x5bf6  ldnull
0x5bf7  cgt.un
0x5bf9  stloc.0
0x5bfa  ldarg.0
0x5bfb  ldarg.2
0x5bfc  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::ClearHandlers(class [System.Activities]System.Activities.WorkflowApplication activityInstance)
0x5c01  ldarg.0
0x5c02  ldarg.3
0x5c03  ldloc.0
0x5c04  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::ClearWorkflowInstance(class Microsoft.Crm.Workflow.ICommonWorkflowContext context, bool succeeded)
0x5c09  ldloc.0
0x5c0a  brfalse.s loc_5C17
0x5c0c  ldarg.3
0x5c0d  callvirt instance class Microsoft.Crm.Workflow.WorkflowInstanceStateBase Microsoft.Crm.Workflow.ICommonWorkflowContext::get_InstanceState()
0x5c12  callvirt instance void Microsoft.Crm.Workflow.WorkflowInstanceStateBase::Clear()
0x5c17  ldarg.0
0x5c18  ldarg.1
0x5c19  callvirt instance void Microsoft.Crm.Workflow.ActivityHostBase::OnPostWorkflowThreadEnded(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result)
0x5c1e  ldarg.3
0x5c1f  ldarg.1
0x5c20  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::EndProcessing(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result)
0x5c25  ret
```
