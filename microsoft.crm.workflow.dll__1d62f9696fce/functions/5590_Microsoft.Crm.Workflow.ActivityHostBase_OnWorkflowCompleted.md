# Microsoft.Crm.Workflow.ActivityHostBase::OnWorkflowCompleted

- ea: `0x5590`
- end: `0x5628`
- name: `Microsoft.Crm.Workflow.ActivityHostBase::OnWorkflowCompleted`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x2e540`

## callees

- `0x5590`
- `0x5700`
- `0x5810`
- `0x5bf0`
- `0x5c30`
- `0x9360`

## string_xrefs

- `0x5598`: `Workflow completed: {0}, {1}: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x5590  ldarg.3
0x5591  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x5596  ldc.i4.s 0x1E
0x5598  ldstr    aWorkflowComple// "Workflow completed: {0}, {1}: {2}"
0x559d  ldc.i4.3
0x559e  newarr   [mscorlib]System.Object
0x55a3  dup
0x55a4  ldc.i4.0
0x55a5  ldarg.1
0x55a6  callvirt instance valuetype [mscorlib]System.Guid [System.Activities]System.Activities.WorkflowApplicationEventArgs::get_InstanceId()
0x55ab  box      [mscorlib]System.Guid
0x55b0  stelem.ref
0x55b1  dup
0x55b2  ldc.i4.1
0x55b3  ldarg.0
0x55b4  ldfld    string Microsoft.Crm.Workflow.ActivityHostBase::_workflowSessionPrimaryKeyName
0x55b9  stelem.ref
0x55ba  dup
0x55bb  ldc.i4.2
0x55bc  ldarg.3
0x55bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x55c2  box      [mscorlib]System.Guid
0x55c7  stelem.ref
0x55c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x55cd  ldarg.0
0x55ce  ldarg.3
0x55cf  callvirt instance void Microsoft.Crm.Workflow.ActivityHostBase::UnsusbscribeAll(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x55d4  ldnull
0x55d5  stloc.0
0x55d6  ldarg.1
0x55d7  callvirt instance class [mscorlib]System.Exception [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs::get_TerminationException()
0x55dc  brfalse.s loc_5618
0x55de  ldarg.1
0x55df  callvirt instance class [mscorlib]System.Exception [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs::get_TerminationException()
0x55e4  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x55e9  brfalse.s loc_55F8
0x55eb  ldarg.1
0x55ec  callvirt instance class [mscorlib]System.Exception [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs::get_TerminationException()
0x55f1  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x55f6  br.s     loc_55FE
0x55f8  ldarg.1
0x55f9  callvirt instance class [mscorlib]System.Exception [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs::get_TerminationException()
0x55fe  stloc.1
0x55ff  ldarg.0
0x5600  ldarg.3
0x5601  ldarg.1
0x5602  callvirt instance class [mscorlib]System.Exception [System.Activities]System.Activities.WorkflowApplicationCompletedEventArgs::get_TerminationException()
0x5607  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.ActivityHostBase::CreateWorkflowOperationResult(class Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [mscorlib]System.Exception exception)
0x560c  stloc.0
0x560d  ldarg.0
0x560e  ldloc.1
0x560f  ldarg.3
0x5610  ldc.i4.1
0x5611  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::HandleFault(class [mscorlib]System.Exception exception, class Microsoft.Crm.Workflow.ICommonWorkflowContext context, bool isStopWorkflow)
0x5616  br.s     loc_561E
0x5618  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationSucceededResult::.ctor()
0x561d  stloc.0
0x561e  ldarg.0
0x561f  ldloc.0
0x5620  ldarg.2
0x5621  ldarg.3
0x5622  callvirt instance void Microsoft.Crm.Workflow.ActivityHostBase::CompleteWorkflow(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result, class [System.Activities]System.Activities.WorkflowApplication activityInstance, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x5627  ret
```
