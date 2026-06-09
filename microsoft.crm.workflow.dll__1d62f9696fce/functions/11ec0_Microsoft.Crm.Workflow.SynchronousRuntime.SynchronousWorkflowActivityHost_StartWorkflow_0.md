# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::StartWorkflow_0

- ea: `0x11ec0`
- end: `0x12041`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::StartWorkflow_0`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x11df0`

## callees

- `0x5800`
- `0x5c30`
- `0x67d0`
- `0x67e0`
- `0x6a80`
- `0x7e90`
- `0x106f0`
- `0x11ec0`
- `0x120a0`
- `0x12670`

## string_xrefs

- `0x11f31`: `Sync workflow '{0}' completed successfully`

## pseudocode

```c

```

## disassembly

```asm
0x11ec0  ldarg.2
0x11ec1  isinst   Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x11ec6  stloc.0
0x11ec7  ldarg.1
0x11ec8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_Name()
0x11ecd  stloc.1
0x11ece  ldarg.2
0x11ecf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x11ed4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x11ed9  stloc.2
0x11eda  ldarg.0
0x11edb  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11ee0  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfXamlActivityReadTime
0x11ee5  ldloc.0
0x11ee6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_PluginTrace()
0x11eeb  ldc.i4.4
0x11eec  newarr   [mscorlib]System.Object
0x11ef1  dup
0x11ef2  ldc.i4.0
0x11ef3  ldstr    aStartingSyncWo// "Starting sync workflow '"
0x11ef8  stelem.ref
0x11ef9  dup
0x11efa  ldc.i4.1
0x11efb  ldloc.1
0x11efc  stelem.ref
0x11efd  dup
0x11efe  ldc.i4.2
0x11eff  ldstr    aId_0// "', Id: "
0x11f04  stelem.ref
0x11f05  dup
0x11f06  ldc.i4.3
0x11f07  ldloc.2
0x11f08  box      [mscorlib]System.Guid
0x11f0d  stelem.ref
0x11f0e  call     string [mscorlib]System.String::Concat(object[])
0x11f13  ldc.i4.0
0x11f14  newarr   [mscorlib]System.Object
0x11f19  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0x11f1e  ldarg.0
0x11f1f  ldarg.1
0x11f20  callvirt instance class [System.Activities]System.Activities.Activity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::get_Activity()
0x11f25  ldarg.2
0x11f26  call     instance void Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::ExecuteWorkflowUsingInvoker(class [System.Activities]System.Activities.Activity workflow, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x11f2b  ldloc.0
0x11f2c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_PluginTrace()
0x11f31  ldstr    aSyncWorkflow0C// "Sync workflow '{0}' completed successfu"...
0x11f36  ldc.i4.1
0x11f37  newarr   [mscorlib]System.Object
0x11f3c  dup
0x11f3d  ldc.i4.0
0x11f3e  ldloc.1
0x11f3f  stelem.ref
0x11f40  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0x11f45  ldarg.0
0x11f46  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11f4b  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfRuntimeTime
0x11f50  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11f55  ldc.i4.2
0x11f56  ldc.i4.0
0x11f57  ldnull
0x11f58  ldloc.0
0x11f59  call     void Microsoft.Crm.Workflow.WorkflowContextBase::CreateActionLog(valuetype [mscorlib]System.Guid sessionId, int32 status, int32 errorCode, string errorMessage, class Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext synchronousWorkflowContext)
0x11f5e  leave    loc_12040
0x11f63  stloc.3
0x11f64  ldloc.3
0x11f65  isinst   Microsoft.Crm.Workflow.SynchronousRuntime.CrmSynchronousWorkflowRuntimeException
0x11f6a  brfalse.s loc_11F73
0x11f6c  ldloc.3
0x11f6d  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x11f72  stloc.3
0x11f73  ldnull
0x11f74  stloc.s  4
0x11f76  ldloc.3
0x11f77  isinst   [System.Activities]System.Activities.Statements.WorkflowTerminatedException
0x11f7c  brfalse.s loc_11F8D
0x11f7e  ldloc.3
0x11f7f  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x11f84  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException
0x11f89  stloc.s  4
0x11f8b  br.s     loc_11F95
0x11f8d  ldloc.3
0x11f8e  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException
0x11f93  stloc.s  4
0x11f95  ldloc.s  4
0x11f97  brfalse.s loc_11FA8
0x11f99  ldloc.s  4
0x11f9b  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OperationStatus [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::get_Status()
0x11fa0  ldc.i4.4
0x11fa1  bne.un.s loc_11FA8
0x11fa3  leave    loc_12040
0x11fa8  ldarg.0
0x11fa9  ldloc.3
0x11faa  ldarg.2
0x11fab  call     instance void Microsoft.Crm.Workflow.ActivityHostBase::HandleFault(class [mscorlib]System.Exception exception, class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x11fb0  ldarg.2
0x11fb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x11fb6  ldc.i4.s 0x1E
0x11fb8  ldstr    aStartworkflowE// "StartWorkflow: Error from synchronous w"...
0x11fbd  ldc.i4.2
0x11fbe  newarr   [mscorlib]System.Object
0x11fc3  dup
0x11fc4  ldc.i4.0
0x11fc5  ldarg.2
0x11fc6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x11fcb  box      [mscorlib]System.Guid
0x11fd0  stelem.ref
0x11fd1  dup
0x11fd2  ldc.i4.1
0x11fd3  ldloc.3
0x11fd4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x11fd9  stelem.ref
0x11fda  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11fdf  ldloc.0
0x11fe0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_PluginTrace()
0x11fe5  ldstr    aSyncWorkflow0T// "Sync workflow '{0}' terminated with err"...
0x11fea  ldloc.1
0x11feb  ldloc.3
0x11fec  callvirt instance string [mscorlib]System.Exception::get_Message()
0x11ff1  call     string [mscorlib]System.String::Format(string, object, object)
0x11ff6  ldc.i4.0
0x11ff7  newarr   [mscorlib]System.Object
0x11ffc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService::Trace(string, object[])
0x12001  ldarg.2
0x12002  ldarg.0
0x12003  ldarg.2
0x12004  ldloc.3
0x12005  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.ActivityHostBase::CreateWorkflowOperationResult(class Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [mscorlib]System.Exception exception)
0x1200a  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_OperationStatus(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult value)
0x1200f  ldarg.2
0x12010  ldarg.2
0x12011  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Workflow.ICommonWorkflowContext::get_OperationStatus()
0x12016  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::EndProcessing(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result)
0x1201b  ldloc.3
0x1201c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12021  ldloc.3
0x12022  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::.ctor(string, class [mscorlib]System.Exception)
0x12027  throw
0x12028  ldarg.0
0x12029  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1202e  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfEndTime
0x12033  ldarg.0
0x12034  ldarg.2
0x12035  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1203a  call     instance void Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::LogPerfMesurementCounters(valuetype [mscorlib]System.Guid organizationId)
0x1203f  endfinally
0x12040  ret
```
