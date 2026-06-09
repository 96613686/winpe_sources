# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelOldAndExecuteNewWorkFlows

- ea: `0x12350`
- end: `0x12397`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelOldAndExecuteNewWorkFlows`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x12ca0`
- `0x12ef0`

## callees

- `0x12350`
- `0x126d0`
- `0x12750`
- `0x12850`
- `0x12990`

## pseudocode

```c

```

## disassembly

```asm
0x12350  ldnull
0x12351  stloc.0
0x12352  ldarg.s  4
0x12354  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12359  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1235e  brfalse.s loc_1237E
0x12360  ldarg.0
0x12361  ldarg.2
0x12362  ldarg.1
0x12363  ldc.i4.1
0x12364  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ImpersonateUserForSLAWorkflows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, bool toCancelWorkflow)
0x12369  stloc.0
0x1236a  ldarg.3
0x1236b  ldloc.0
0x1236c  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetAllWorkFlowInstances(valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService organizationService)
0x12371  ldloc.0
0x12372  ldarg.1
0x12373  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12378  ldarg.3
0x12379  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelWorkFlows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection entityCollection, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService organizationService, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext, valuetype [mscorlib]System.Guid incidentId)
0x1237e  ldarg.0
0x1237f  ldarg.2
0x12380  ldarg.1
0x12381  ldc.i4.0
0x12382  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ImpersonateUserForSLAWorkflows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, bool toCancelWorkflow)
0x12387  stloc.0
0x12388  ldarg.2
0x12389  ldarg.3
0x1238a  ldloc.0
0x1238b  ldarg.1
0x1238c  ldarg.s  6
0x1238e  ldarg.s  5
0x12390  ldc.i4.1
0x12391  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ExecuteWorkflow(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService organizationService, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext context, int32 onHoldTime, int32 slaKpiStatus, int32 invokeChildWFs)
0x12396  ret
```
