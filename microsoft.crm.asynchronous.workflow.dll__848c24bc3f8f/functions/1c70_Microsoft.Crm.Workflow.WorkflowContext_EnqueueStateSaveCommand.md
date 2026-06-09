# Microsoft.Crm.Workflow.WorkflowContext::EnqueueStateSaveCommand

- ea: `0x1c70`
- end: `0x1d08`
- name: `Microsoft.Crm.Workflow.WorkflowContext::EnqueueStateSaveCommand`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1a90`
- `0x1c70`
- `0x27d0`

## string_xrefs

- `0x1c96`: `SaveWorkflowInstanceState: Queued state save command for workflow {0}; state is {1} bytes, postpone until: {2}, blocked: {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x1c70  ldarg.0
0x1c71  ldarg.0
0x1c72  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.WorkflowContext::get_OrganizationConfiguration()
0x1c77  newobj   instance void Microsoft.Crm.Workflow.AsyncWorkflowSaveInstanceStateCommand::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x1c7c  stloc.0
0x1c7d  ldarg.0
0x1c7e  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x1c83  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent
0x1c88  ldloc.0
0x1c89  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::EnqueueDatabaseCommand(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueuedDatabaseCommand)
0x1c8e  ldarg.0
0x1c8f  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x1c94  ldc.i4.s 0x1E
0x1c96  ldstr    aSaveworkflowin// "SaveWorkflowInstanceState: Queued state"...
0x1c9b  ldc.i4.4
0x1c9c  newarr   [mscorlib]System.Object
0x1ca1  dup
0x1ca2  ldc.i4.0
0x1ca3  ldarg.0
0x1ca4  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_workflowInstanceData
0x1ca9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData::get_EventId()
0x1cae  box      [mscorlib]System.Guid
0x1cb3  stelem.ref
0x1cb4  dup
0x1cb5  ldc.i4.1
0x1cb6  ldarg.0
0x1cb7  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1cbc  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsEmpty()
0x1cc1  brtrue.s loc_1CD5
0x1cc3  ldarg.0
0x1cc4  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1cc9  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_WorkflowState()
0x1cce  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cd3  br.s     loc_1CD6
0x1cd5  ldc.i4.0
0x1cd6  box      [mscorlib]System.Int32
0x1cdb  stelem.ref
0x1cdc  dup
0x1cdd  ldc.i4.2
0x1cde  ldarg.0
0x1cdf  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1ce4  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_PostponeUntil()
0x1ce9  box      [mscorlib]System.DateTime
0x1cee  stelem.ref
0x1cef  dup
0x1cf0  ldc.i4.3
0x1cf1  ldarg.0
0x1cf2  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1cf7  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsBlocked()
0x1cfc  box      [mscorlib]System.Boolean
0x1d01  stelem.ref
0x1d02  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d07  ret
```
