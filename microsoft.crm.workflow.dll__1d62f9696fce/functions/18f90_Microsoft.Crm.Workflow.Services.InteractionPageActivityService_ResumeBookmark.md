# Microsoft.Crm.Workflow.Services.InteractionPageActivityService::ResumeBookmark

- ea: `0x18f90`
- end: `0x18ffe`
- name: `Microsoft.Crm.Workflow.Services.InteractionPageActivityService::ResumeBookmark`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0xdee0`
- `0xdf50`
- `0xe0b0`
- `0x14770`
- `0x14a40`
- `0x18cc0`
- `0x18d00`

## pseudocode

```c

```

## disassembly

```asm
0x18f90  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18f95  ldc.i4.s 0x1E
0x18f97  ldstr    aResumebookmark// "ResumeBookmark: Resumed interactive wor"...
0x18f9c  ldc.i4.2
0x18f9d  newarr   [mscorlib]System.Object
0x18fa2  dup
0x18fa3  ldc.i4.0
0x18fa4  ldarg.0
0x18fa5  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18faa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x18faf  box      [mscorlib]System.Guid
0x18fb4  stelem.ref
0x18fb5  dup
0x18fb6  ldc.i4.1
0x18fb7  ldarg.0
0x18fb8  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowInputContext()
0x18fbd  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x18fc2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityResult> Microsoft.Crm.Workflow.PageResult::get_InteractionActivitiesResults()
0x18fc7  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::get_Count()
0x18fcc  box      [mscorlib]System.Int32
0x18fd1  stelem.ref
0x18fd2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18fd7  ldarg.0
0x18fd8  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowInputContext()
0x18fdd  ldc.i4.1
0x18fde  callvirt instance void Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::set_UnderResumeBookmarkProcessing(bool value)
0x18fe3  ldarg.0
0x18fe4  ldarg.1
0x18fe5  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::RestoreExecutionProperties(class [System.Activities]System.Activities.NativeActivityContext context)
0x18fea  ldc.i4.0
0x18feb  stloc.0
0x18fec  ldarg.3
0x18fed  ldarg.1
0x18fee  ldloc.0
0x18fef  callvirt instance void class [System.Activities]System.Activities.Variable`1<int32>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x18ff4  ldarg.0
0x18ff5  ldarg.1
0x18ff6  ldarg.2
0x18ff7  ldarg.3
0x18ff8  call     instance void Microsoft.Crm.Workflow.Services.InteractionPageActivityService::Execute(class [System.Activities]System.Activities.NativeActivityContext executionContext, class Microsoft.Crm.Workflow.Activities.InteractionPage interactionPage, class [System.Activities]System.Activities.Variable`1<int32> executionPointer)
0x18ffd  ret
```
