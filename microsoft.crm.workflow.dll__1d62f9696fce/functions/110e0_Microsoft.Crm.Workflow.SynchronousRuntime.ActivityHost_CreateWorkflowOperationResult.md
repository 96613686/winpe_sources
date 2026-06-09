# Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::CreateWorkflowOperationResult

- ea: `0x110e0`
- end: `0x111d6`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::CreateWorkflowOperationResult`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x330`
- `0x340`
- `0x5db0`
- `0x92f0`
- `0x9300`
- `0x9360`
- `0x110e0`

## pseudocode

```c

```

## disassembly

```asm
0x110e0  ldarg.0
0x110e1  ldarg.2
0x110e2  call     instance class Microsoft.Crm.Asynchronous.ErrorAction Microsoft.Crm.Workflow.ActivityHostBase::GetErrorAction(class [mscorlib]System.Exception exception)
0x110e7  stloc.0
0x110e8  ldarg.2
0x110e9  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x110ee  stloc.1
0x110ef  ldloc.0
0x110f0  callvirt instance valuetype Microsoft.Crm.Asynchronous.ErrorActionType Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x110f5  stloc.2
0x110f6  ldloc.2
0x110f7  switch   loc_11121, loc_11121, loc_11121, loc_11121, loc_11116, loc_11121
0x11114  br.s     loc_11121
0x11116  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationSucceededResult::.ctor()
0x1111b  stloc.1
0x1111c  br       loc_111D4
0x11121  ldarg.2
0x11122  isinst   [mscorlib]System.Collections.Generic.KeyNotFoundException
0x11127  brfalse.s loc_11152
0x11129  ldloc.0
0x1112a  callvirt instance valuetype Microsoft.Crm.Asynchronous.ErrorActionType Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x1112f  brtrue.s loc_11152
0x11131  ldc.i4   0x80045050
0x11136  ldc.i4.1
0x11137  newarr   [mscorlib]System.Object
0x1113c  dup
0x1113d  ldc.i4.0
0x1113e  ldarg.2
0x1113f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x11144  stelem.ref
0x11145  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1114a  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x1114f  stloc.1
0x11150  br.s     loc_111A4
0x11152  ldarg.2
0x11153  isinst   [mscorlib]System.NullReferenceException
0x11158  brfalse.s loc_11183
0x1115a  ldloc.0
0x1115b  callvirt instance valuetype Microsoft.Crm.Asynchronous.ErrorActionType Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x11160  brtrue.s loc_11183
0x11162  ldc.i4   0x80045050
0x11167  ldc.i4.1
0x11168  newarr   [mscorlib]System.Object
0x1116d  dup
0x1116e  ldc.i4.0
0x1116f  ldarg.2
0x11170  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x11175  stelem.ref
0x11176  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1117b  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x11180  stloc.1
0x11181  br.s     loc_111A4
0x11183  ldarg.2
0x11184  ldloc.0
0x11185  callvirt instance int32 Microsoft.Crm.Asynchronous.ErrorAction::get_ErrorCode()
0x1118a  ldstr    aWorkflowFailed// "Workflow failed due to error: {0}"
0x1118f  ldc.i4.1
0x11190  newarr   [mscorlib]System.Object
0x11195  dup
0x11196  ldc.i4.0
0x11197  ldarg.2
0x11198  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1119d  stelem.ref
0x1119e  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex, int32 errorCode, string errorFormat, object[] args)
0x111a3  stloc.1
0x111a4  ldnull
0x111a5  ldarg.1
0x111a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x111ab  ldc.i4.s 0x1E
0x111ad  ldstr    aWorkflow0Faile// "Workflow '{0}' failed due to error: {1}"...
0x111b2  ldc.i4.2
0x111b3  newarr   [mscorlib]System.Object
0x111b8  dup
0x111b9  ldc.i4.0
0x111ba  ldarg.1
0x111bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x111c0  box      [mscorlib]System.Guid
0x111c5  stelem.ref
0x111c6  dup
0x111c7  ldc.i4.1
0x111c8  ldarg.2
0x111c9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x111ce  stelem.ref
0x111cf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x111d4  ldloc.1
0x111d5  ret
```
