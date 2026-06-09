# Microsoft.Crm.Workflow.ActivityHostBase::CreateWorkflowOperationResult

- ea: `0x5c30`
- end: `0x5da7`
- name: `Microsoft.Crm.Workflow.ActivityHostBase::CreateWorkflowOperationResult`
- size: `375`
- prototype: ``
- caller_count: `8`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4eb0`
- `0x4ee0`
- `0x5590`
- `0x5950`
- `0x59f0`
- `0x10ad0`
- `0x11df0`
- `0x11ec0`

## callees

- `0x330`
- `0x340`
- `0x5c30`
- `0x5db0`
- `0x67d0`
- `0x92f0`
- `0x9300`
- `0x9310`
- `0x9330`
- `0x9360`
- `0x9440`
- `0x9480`
- `0x9700`
- `0x9730`

## string_xrefs

- `0x5c6f`: `Workflow suspended temporarily due to error: {0}`
- `0x5cb2`: `PluginTrace`
- `0x5cce`: `PluginTrace`
- `0x5cd9`: `PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x5c30  ldarg.0
0x5c31  ldarg.2
0x5c32  call     instance class Microsoft.Crm.Asynchronous.ErrorAction Microsoft.Crm.Workflow.ActivityHostBase::GetErrorAction(class [mscorlib]System.Exception exception)
0x5c37  stloc.0
0x5c38  ldarg.2
0x5c39  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex)
0x5c3e  stloc.1
0x5c3f  ldloc.0
0x5c40  callvirt instance valuetype Microsoft.Crm.Asynchronous.ErrorActionType Microsoft.Crm.Asynchronous.ErrorAction::get_Type()
0x5c45  stloc.2
0x5c46  ldloc.2
0x5c47  switch   loc_5D3E, loc_5C69, loc_5C93, loc_5D3E, loc_5D61, loc_5D69
0x5c64  br       loc_5D6F
0x5c69  ldloc.0
0x5c6a  callvirt instance int32 Microsoft.Crm.Asynchronous.ErrorAction::get_ErrorCode()
0x5c6f  ldstr    aWorkflowSuspen// "Workflow suspended temporarily due to e"...
0x5c74  ldc.i4.1
0x5c75  newarr   [mscorlib]System.Object
0x5c7a  dup
0x5c7b  ldc.i4.0
0x5c7c  ldarg.2
0x5c7d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x5c82  stelem.ref
0x5c83  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(int32 errorCode, string errorFormat, object[] args)
0x5c88  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationRetryResult::.ctor(class Microsoft.Crm.Workflow.WorkflowOperationFailedResult failure)
0x5c8d  stloc.1
0x5c8e  br       loc_5D6F
0x5c93  ldloc.0
0x5c94  callvirt instance int32 Microsoft.Crm.Asynchronous.ErrorAction::get_ErrorCode()
0x5c99  ldc.i4   0x80040265
0x5c9e  bne.un.s loc_5CEB
0x5ca0  ldarg.2
0x5ca1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5ca6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::.ctor(string)
0x5cab  stloc.3
0x5cac  ldarg.2
0x5cad  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x5cb2  ldstr    aPlugintrace// "PluginTrace"
0x5cb7  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x5cbc  isinst   [mscorlib]System.String
0x5cc1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5cc6  brtrue.s loc_5CE8
0x5cc8  ldloc.3
0x5cc9  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x5cce  ldstr    aPlugintrace// "PluginTrace"
0x5cd3  ldarg.2
0x5cd4  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x5cd9  ldstr    aPlugintrace// "PluginTrace"
0x5cde  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x5ce3  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x5ce8  ldloc.3
0x5ce9  starg.s  2
0x5ceb  ldarg.2
0x5cec  ldloc.0
0x5ced  callvirt instance int32 Microsoft.Crm.Asynchronous.ErrorAction::get_ErrorCode()
0x5cf2  ldstr    aWorkflowTermin_0// "Workflow terminated due to error: {0}"
0x5cf7  ldc.i4.1
0x5cf8  newarr   [mscorlib]System.Object
0x5cfd  dup
0x5cfe  ldc.i4.0
0x5cff  ldarg.2
0x5d00  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x5d05  stelem.ref
0x5d06  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationFailedResult::.ctor(class [mscorlib]System.Exception ex, int32 errorCode, string errorFormat, object[] args)
0x5d0b  stloc.1
0x5d0c  ldnull
0x5d0d  ldarg.1
0x5d0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x5d13  ldc.i4.s 0x1E
0x5d15  ldstr    aWorkflow0Termi// "Workflow '{0}' terminated due to error:"...
0x5d1a  ldc.i4.2
0x5d1b  newarr   [mscorlib]System.Object
0x5d20  dup
0x5d21  ldc.i4.0
0x5d22  ldarg.1
0x5d23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x5d28  box      [mscorlib]System.Guid
0x5d2d  stelem.ref
0x5d2e  dup
0x5d2f  ldc.i4.1
0x5d30  ldarg.2
0x5d31  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x5d36  stelem.ref
0x5d37  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5d3c  br.s     loc_5D6F
0x5d3e  ldloc.0
0x5d3f  callvirt instance int32 Microsoft.Crm.Asynchronous.ErrorAction::get_ErrorCode()
0x5d44  ldarg.2
0x5d45  ldstr    aWorkflowPaused// "Workflow paused due to error: {0}"
0x5d4a  ldc.i4.1
0x5d4b  newarr   [mscorlib]System.Object
0x5d50  dup
0x5d51  ldc.i4.0
0x5d52  ldarg.2
0x5d53  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x5d58  stelem.ref
0x5d59  newobj   instance void Microsoft.Crm.Workflow.WorkflowSystemPausedResult::.ctor(int32 errorCode, class [mscorlib]System.Exception exception, string errorFormat, object[] args)
0x5d5e  stloc.1
0x5d5f  br.s     loc_5D6F
0x5d61  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationSucceededResult::.ctor()
0x5d66  stloc.1
0x5d67  br.s     loc_5D6F
0x5d69  newobj   instance void Microsoft.Crm.Workflow.WorkflowOperationCanceledResult::.ctor()
0x5d6e  stloc.1
0x5d6f  ldarg.1
0x5d70  brfalse.s loc_5DA5
0x5d72  ldarg.1
0x5d73  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.ICommonWorkflowContext::get_OperationStatus()
0x5d78  brfalse.s loc_5DA5
0x5d7a  ldarg.1
0x5d7b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.ICommonWorkflowContext::get_OperationStatus()
0x5d80  isinst   Microsoft.Crm.Workflow.WorkflowHandlerResult
0x5d85  stloc.s  4
0x5d87  ldloc.1
0x5d88  isinst   Microsoft.Crm.Workflow.WorkflowHandlerResult
0x5d8d  stloc.s  5
0x5d8f  ldloc.s  4
0x5d91  brfalse.s loc_5DA5
0x5d93  ldloc.s  5
0x5d95  brfalse.s loc_5DA5
0x5d97  ldloc.s  5
0x5d99  ldloc.s  4
0x5d9b  callvirt instance bool Microsoft.Crm.Workflow.WorkflowHandlerResult::get_ThreadStarted()
0x5da0  callvirt instance void Microsoft.Crm.Workflow.WorkflowHandlerResult::set_ThreadCompleted(bool value)
0x5da5  ldloc.1
0x5da6  ret
```
