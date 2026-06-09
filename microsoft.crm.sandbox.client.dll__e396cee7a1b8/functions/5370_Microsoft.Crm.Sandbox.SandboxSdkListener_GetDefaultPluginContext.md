# Microsoft.Crm.Sandbox.SandboxSdkListener::GetDefaultPluginContext

- ea: `0x5370`
- end: `0x53d2`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetDefaultPluginContext`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5180`

## callees

- `0x5370`

## pseudocode

```c

```

## disassembly

```asm
0x5370  ldnull
0x5371  stloc.0
0x5372  ldarg.0
0x5373  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_OrganizationId()
0x5378  ldc.i4.0
0x5379  ldc.i4.0
0x537a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x537f  stloc.1
0x5380  ldloc.1
0x5381  ldc.i4.0
0x5382  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x5387  ldloc.1
0x5388  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x538d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_CorrelationToken(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken)
0x5392  ldloc.1
0x5393  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x5398  call     valuetype [mscorlib]System.Guid [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::get_CurrentThreadActivityId()
0x539d  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_CorrelationId(valuetype [mscorlib]System.Guid)
0x53a2  ldnull
0x53a3  ldarg.1
0x53a4  ldarg.2
0x53a5  ldc.i4.0
0x53a6  ldc.i4.0
0x53a7  ldc.i4.0
0x53a8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x53ad  ldc.i4.0
0x53ae  ldloc.1
0x53af  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::.ctor(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory, string, string, int32, int32, int32, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x53b4  stloc.0
0x53b5  ldloc.1
0x53b6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x53bb  leave.s  loc_53D0
0x53bd  pop
0x53be  ldloc.1
0x53bf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x53c4  rethrow
0x53c6  ldloc.1
0x53c7  brfalse.s loc_53CF
0x53c9  ldloc.1
0x53ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x53cf  endfinally
0x53d0  ldloc.0
0x53d1  ret
```
