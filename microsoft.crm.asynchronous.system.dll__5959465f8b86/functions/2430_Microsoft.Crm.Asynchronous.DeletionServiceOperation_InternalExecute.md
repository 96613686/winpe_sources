# Microsoft.Crm.Asynchronous.DeletionServiceOperation::InternalExecute

- ea: `0x2430`
- end: `0x2473`
- name: `Microsoft.Crm.Asynchronous.DeletionServiceOperation::InternalExecute`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2430`
- `0x2490`

## string_xrefs

- `0x243a`: `Operation type must be 'Deletion Service'`

## pseudocode

```c

```

## disassembly

```asm
0x2430  ldarg.1
0x2431  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x2436  ldc.i4.s 0xE
0x2438  ceq
0x243a  ldstr    aOperationTypeM_6// "Operation type must be 'Deletion Servic"...
0x243f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2444  ldarg.0
0x2445  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x244a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x244f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.DeletionService::.ctor(valuetype [mscorlib]System.Guid)
0x2454  stloc.0
0x2455  ldloc.0
0x2456  ldarg.1
0x2457  newobj   instance void Microsoft.Crm.Asynchronous.DeletionServiceProvider::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x245c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.DeletionService::Run(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.IDeletionServiceProvider)
0x2461  leave.s  loc_246D
0x2463  ldloc.0
0x2464  brfalse.s loc_246C
0x2466  ldloc.0
0x2467  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x246c  endfinally
0x246d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x2472  ret
```
