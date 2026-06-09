# Microsoft.Crm.Workflow.WorkflowExpansionPlugin::Execute

- ea: `0x2500`
- end: `0x2562`
- name: `Microsoft.Crm.Workflow.WorkflowExpansionPlugin::Execute`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2500  ldarg.1
0x2501  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x2506  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x250b  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x2510  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x2515  stloc.0
0x2516  ldloc.0
0x2517  castclass [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext
0x251c  stloc.1
0x251d  ldloc.1
0x251e  ldloc.1
0x251f  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_Depth()
0x2524  ldc.i4.1
0x2525  sub
0x2526  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::set_Depth(int32)
0x252b  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ExpandWorkflowsRequest::.ctor()
0x2530  stloc.2
0x2531  ldloc.2
0x2532  ldloc.1
0x2533  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_AsyncEvent()
0x2538  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RequestId()
0x253d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2542  ldloc.2
0x2543  ldloc.0
0x2544  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x2549  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ExpandWorkflowsRequest::set_ExpansionTaskId(valuetype [mscorlib]System.Guid)
0x254e  ldloc.1
0x254f  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_AsyncEvent()
0x2554  ldc.i4.1
0x2555  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x255a  ldloc.2
0x255b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2560  pop
0x2561  ret
```
