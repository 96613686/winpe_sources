# Microsoft.Crm.Workflow.WorkflowContextBase::CreateActionLog

- ea: `0x7e90`
- end: `0x7edd`
- name: `Microsoft.Crm.Workflow.WorkflowContextBase::CreateActionLog`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10420`
- `0x11ec0`

## callees

- `0x7e90`
- `0x7ee0`
- `0x10260`
- `0x109a0`

## pseudocode

```c

```

## disassembly

```asm
0x7e90  ldarg.s  4
0x7e92  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.BusinessProcessFlowContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_BusinessProcessFlowContext()
0x7e97  stloc.0
0x7e98  ldarg.s  4
0x7e9a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_ExecutionContext()
0x7e9f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7ea4  ldc.i4.0
0x7ea5  ldc.i4.0
0x7ea6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x7eab  stloc.1
0x7eac  ldloc.1
0x7ead  ldarg.s  4
0x7eaf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_ExecutionContext()
0x7eb4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x7eb9  ldc.i4.1
0x7eba  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x7ebf  ldarg.0
0x7ec0  ldarg.1
0x7ec1  ldarg.2
0x7ec2  ldarg.3
0x7ec3  ldloc.0
0x7ec4  ldloc.1
0x7ec5  call     void Microsoft.Crm.Workflow.WorkflowContextBase::CreateActionLog(valuetype [mscorlib]System.Guid sessionId, int32 status, int32 errorCode, string errorMessage, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.BusinessProcessFlowContext businessProcessContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7eca  ldloc.1
0x7ecb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x7ed0  leave.s  loc_7EDC
0x7ed2  ldloc.1
0x7ed3  brfalse.s loc_7EDB
0x7ed5  ldloc.1
0x7ed6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7edb  endfinally
0x7edc  ret
```
