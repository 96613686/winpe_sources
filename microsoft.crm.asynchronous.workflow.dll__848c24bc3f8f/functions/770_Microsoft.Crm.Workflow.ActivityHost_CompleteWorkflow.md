# Microsoft.Crm.Workflow.ActivityHost::CompleteWorkflow

- ea: `0x770`
- end: `0x803`
- name: `Microsoft.Crm.Workflow.ActivityHost::CompleteWorkflow`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x770`
- `0xb50`
- `0xb70`

## pseudocode

```c

```

## disassembly

```asm
0x770  ldarg.1
0x771  isinst   [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationSucceededResult
0x776  ldnull
0x777  cgt.un
0x779  stloc.0
0x77a  ldarg.0
0x77b  ldarg.2
0x77c  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::ClearHandlers(class [System.Activities]System.Activities.WorkflowApplication)
0x781  ldarg.3
0x782  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_GoingIdle()
0x787  brtrue.s loc_791
0x789  ldarg.0
0x78a  ldarg.3
0x78b  ldloc.0
0x78c  call     instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::ClearWorkflowInstance(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext, bool)
0x791  ldloc.0
0x792  brfalse.s loc_7DE
0x794  ldarg.3
0x795  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x79a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x79f  ldstr    aWorkflow// "workflow"
0x7a4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a9  brfalse.s loc_7DE
0x7ab  ldarg.3
0x7ac  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsAutoDeleteSet()
0x7b1  brfalse.s loc_7DE
0x7b3  ldarg.0
0x7b4  ldarg.3
0x7b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7ba  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::WorkflowResolveOrganizationConfiguration(valuetype [mscorlib]System.Guid)
0x7bf  stloc.1
0x7c0  ldarg.1
0x7c1  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult::get_ResultCode()
0x7c6  ldarg.3
0x7c7  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_Event()
0x7cc  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent
0x7d1  ldloc.1
0x7d2  newobj   instance void [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.DeleteUsingSdkCommand::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x7d7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueuedDatabaseCommand)
0x7dc  starg.s  1
0x7de  ldarg.0
0x7df  ldarg.1
0x7e0  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::OnPostWorkflowThreadEnded(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult)
0x7e5  ldarg.3
0x7e6  ldarg.1
0x7e7  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::EndProcessing(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult)
0x7ec  leave.s  loc_802
0x7ee  stloc.2
0x7ef  ldarg.0
0x7f0  ldarg.3
0x7f1  ldloc.2
0x7f2  call     instance void Microsoft.Crm.Workflow.ActivityHost::LogException(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [mscorlib]System.Exception ex)
0x7f7  leave.s  loc_802
0x7f9  ldarg.0
0x7fa  ldarg.3
0x7fb  ldarg.1
0x7fc  call     instance void Microsoft.Crm.Workflow.ActivityHost::EndAsyncEvent(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result)
0x801  endfinally
0x802  ret
```
