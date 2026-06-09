# Microsoft.Crm.Asynchronous.ResourceBookingSyncServiceOperation::InternalExecute

- ea: `0x8b90`
- end: `0x8c01`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncServiceOperation::InternalExecute`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x5d50`
- `0x5da0`
- `0x8b90`

## pseudocode

```c

```

## disassembly

```asm
0x8b90  ldarg.1
0x8b91  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x8b96  ldc.i4.s 0x44
0x8b98  ceq
0x8b9a  ldstr    aOperationTypeM_4// "Operation type must be 'Resource Bookin"...
0x8b9f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8ba4  ldarg.0
0x8ba5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x8baa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x8baf  ldc.i4.0
0x8bb0  ldc.i4.0
0x8bb1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x8bb6  stloc.0
0x8bb7  ldloc.0
0x8bb8  ldc.i4.0
0x8bb9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x8bbe  ldloc.0
0x8bbf  ldarg.1
0x8bc0  ldc.i4.1
0x8bc1  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x8bc6  newobj   instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService systemService)
0x8bcb  stloc.1
0x8bcc  ldloc.1
0x8bcd  callvirt instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Run()
0x8bd2  leave.s  loc_8BDE
0x8bd4  ldloc.1
0x8bd5  brfalse.s loc_8BDD
0x8bd7  ldloc.1
0x8bd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8bdd  endfinally
0x8bde  leave.s  loc_8BE9
0x8be0  pop
0x8be1  ldloc.0
0x8be2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x8be7  rethrow
0x8be9  ldloc.0
0x8bea  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x8bef  leave.s  loc_8BFB
0x8bf1  ldloc.0
0x8bf2  brfalse.s loc_8BFA
0x8bf4  ldloc.0
0x8bf5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8bfa  endfinally
0x8bfb  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x8c00  ret
```
