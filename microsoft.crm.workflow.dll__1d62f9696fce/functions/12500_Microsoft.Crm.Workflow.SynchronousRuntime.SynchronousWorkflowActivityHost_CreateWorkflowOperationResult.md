# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::CreateWorkflowOperationResult

- ea: `0x12500`
- end: `0x12624`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::CreateWorkflowOperationResult`
- size: `292`
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
- `0x12500`

## pseudocode

```c

```

## disassembly

```asm
0x12500  ldarg.0
0x12501  ldarg.2
0x12502  call     instance class Microsoft.Crm.Asynchronous.ErrorAction Microsoft.Crm.Workflow.ActivityHostBase::GetErrorAction(class [mscorlib]System.Exception exception)
0x12507  stloc.0
0x12508  ldarg.2
0x12509  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x1250e  stloc.1
0x1250f  ldloc.0
0x12510  callvirt instance valuetype Microsoft.Crm.Asynchronous.ErrorActionType Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x12515  stloc.2
0x12516  ldloc.2
0x12517  switch   loc_12541, loc_12541, loc_12541, loc_12541, loc_12536, loc_12541
0x12534  br.s     loc_12541
0x12536  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationSucceededResult::.ctor()
0x1253b  stloc.1
0x1253c  br       loc_12622
0x12541  ldarg.2
0x12542  isinst   [mscorlib]System.Collections.Generic.KeyNotFoundException
0x12547  brfalse.s loc_12572
0x12549  ldloc.0
0x1254a  callvirt instance valuetype Microsoft.Crm.Asynchronous.ErrorActionType Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x1254f  brtrue.s loc_12572
0x12551  ldc.i4   0x80045050
0x12556  ldc.i4.1
0x12557  newarr   [mscorlib]System.Object
0x1255c  dup
0x1255d  ldc.i4.0
0x1255e  ldarg.2
0x1255f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x12564  stelem.ref
0x12565  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1256a  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x1256f  stloc.1
0x12570  br.s     loc_125C4
0x12572  ldarg.2
0x12573  isinst   [mscorlib]System.NullReferenceException
0x12578  brfalse.s loc_125A3
0x1257a  ldloc.0
0x1257b  callvirt instance valuetype Microsoft.Crm.Asynchronous.ErrorActionType Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x12580  brtrue.s loc_125A3
0x12582  ldc.i4   0x80045050
0x12587  ldc.i4.1
0x12588  newarr   [mscorlib]System.Object
0x1258d  dup
0x1258e  ldc.i4.0
0x1258f  ldarg.2
0x12590  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x12595  stelem.ref
0x12596  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1259b  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x125a0  stloc.1
0x125a1  br.s     loc_125C4
0x125a3  ldarg.2
0x125a4  ldloc.0
0x125a5  callvirt instance int32 Microsoft.Crm.Asynchronous.ErrorAction::get_ErrorCode()
0x125aa  ldstr    aWorkflowFailed// "Workflow failed due to error: {0}"
0x125af  ldc.i4.1
0x125b0  newarr   [mscorlib]System.Object
0x125b5  dup
0x125b6  ldc.i4.0
0x125b7  ldarg.2
0x125b8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x125bd  stelem.ref
0x125be  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex, int32 errorCode, string errorFormat, object[] args)
0x125c3  stloc.1
0x125c4  ldarg.1
0x125c5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x125ca  brtrue.s loc_125D3
0x125cc  ldsfld   string [mscorlib]System.String::Empty
0x125d1  br.s     loc_125ED
0x125d3  ldarg.1
0x125d4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x125d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x125de  stloc.s  4
0x125e0  ldloca.s 4
0x125e2  constrained. [mscorlib]System.Guid
0x125e8  callvirt instance string [mscorlib]System.Object::ToString()
0x125ed  stloc.3
0x125ee  ldnull
0x125ef  ldarg.1
0x125f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x125f5  ldc.i4.s 0x1E
0x125f7  ldstr    aWorkflow0Havin// "Workflow '{0}', having workflowId '{1}'"...
0x125fc  ldc.i4.3
0x125fd  newarr   [mscorlib]System.Object
0x12602  dup
0x12603  ldc.i4.0
0x12604  ldarg.1
0x12605  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x1260a  box      [mscorlib]System.Guid
0x1260f  stelem.ref
0x12610  dup
0x12611  ldc.i4.1
0x12612  ldloc.3
0x12613  stelem.ref
0x12614  dup
0x12615  ldc.i4.2
0x12616  ldarg.2
0x12617  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1261c  stelem.ref
0x1261d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12622  ldloc.1
0x12623  ret
```
