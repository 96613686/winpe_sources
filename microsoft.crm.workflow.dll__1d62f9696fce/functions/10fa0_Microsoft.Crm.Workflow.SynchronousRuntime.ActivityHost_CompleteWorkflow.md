# Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::CompleteWorkflow

- ea: `0x10fa0`
- end: `0x11091`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::CompleteWorkflow`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x5bf0`
- `0x67e0`
- `0x6a80`
- `0x9380`
- `0x93b0`
- `0xd9d0`
- `0xd9f0`
- `0xdfe0`
- `0xe930`
- `0x10fa0`
- `0x110a0`
- `0x11490`

## string_xrefs

- `0x1103c`: `Jumping to a Linled child interactive workflow session. Originating Session '{0}', Parent Session '{1}', Linked child workflow session '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x10fa0  ldarg.0
0x10fa1  ldarg.1
0x10fa2  ldarg.2
0x10fa3  ldarg.3
0x10fa4  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::CompleteWorkflow(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result, class [System.Activities]System.Activities.WorkflowApplication activityInstance, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x10fa9  ldarg.3
0x10faa  ldarg.1
0x10fab  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_OperationStatus(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult value)
0x10fb0  ldarg.3
0x10fb1  isinst   Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext
0x10fb6  stloc.0
0x10fb7  ldarg.1
0x10fb8  isinst   Microsoft.Crm.Workflow.WorkflowOperationPausedResult
0x10fbd  brfalse.s loc_1100A
0x10fbf  ldloc.0
0x10fc0  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowOutputContext()
0x10fc5  callvirt instance class Microsoft.Crm.Workflow.PageUIDetail Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext::get_PageUIDetail()
0x10fca  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityDetail> Microsoft.Crm.Workflow.PageUIDetail::get_InteractionActivitiesDetails()
0x10fcf  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityDetail>::get_Count()
0x10fd4  ldc.i4.0
0x10fd5  ble.s    loc_1100A
0x10fd7  ldarg.3
0x10fd8  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationPausedResult::.ctor()
0x10fdd  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_OperationStatus(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult value)
0x10fe2  ldarg.3
0x10fe3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x10fe8  ldc.i4.s 0x1E
0x10fea  ldstr    aInteractiveWor// "Interactive workflow runtime found an  "...
0x10fef  ldc.i4.1
0x10ff0  newarr   [mscorlib]System.Object
0x10ff5  dup
0x10ff6  ldc.i4.0
0x10ff7  ldarg.3
0x10ff8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10ffd  box      [mscorlib]System.Guid
0x11002  stelem.ref
0x11003  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11008  br.s     loc_11080
0x1100a  ldarg.1
0x1100b  isinst   Microsoft.Crm.Workflow.WorkflowOperationSucceededResult
0x11010  brfalse.s loc_11080
0x11012  ldloc.0
0x11013  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowOutputContext()
0x11018  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0x1101d  pop
0x1101e  ldarg.3
0x1101f  ldloc.0
0x11020  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowOutputContext()
0x11025  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0x1102a  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationSucceededResult::.ctor(valuetype [mscorlib]System.Guid nextLinkedChildWorkflowInstanceId)
0x1102f  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_OperationStatus(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult value)
0x11034  ldarg.3
0x11035  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1103a  ldc.i4.s 0x1E
0x1103c  ldstr    aJumpingToALinl// "Jumping to a Linled child interactive w"...
0x11041  ldc.i4.3
0x11042  newarr   [mscorlib]System.Object
0x11047  dup
0x11048  ldc.i4.0
0x11049  ldloc.0
0x1104a  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowOutputContext()
0x1104f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OriginatingWorkflowInstanceId()
0x11054  box      [mscorlib]System.Guid
0x11059  stelem.ref
0x1105a  dup
0x1105b  ldc.i4.1
0x1105c  ldarg.3
0x1105d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x11062  box      [mscorlib]System.Guid
0x11067  stelem.ref
0x11068  dup
0x11069  ldc.i4.2
0x1106a  ldloc.0
0x1106b  callvirt instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.SynchronousRuntime.IInteractiveWorkflowContext::get_InteractiveWorkflowOutputContext()
0x11070  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0x11075  box      [mscorlib]System.Guid
0x1107a  stelem.ref
0x1107b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11080  ldarg.3
0x11081  ldarg.1
0x11082  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::EndProcessing(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result)
0x11087  leave.s  loc_11090
0x11089  ldarg.0
0x1108a  call     instance void Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::SignalSyncThreadContext()
0x1108f  endfinally
0x11090  ret
```
