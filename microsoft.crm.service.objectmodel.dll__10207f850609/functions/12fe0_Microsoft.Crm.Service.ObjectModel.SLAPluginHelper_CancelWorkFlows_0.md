# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelWorkFlows_0

- ea: `0x12fe0`
- end: `0x13027`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelWorkFlows_0`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x12ca0`

## callees

- `0x12520`
- `0x126d0`
- `0x12750`
- `0x12850`
- `0x12fe0`

## pseudocode

```c

```

## disassembly

```asm
0x12fe0  ldarg.0
0x12fe1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12fe6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12feb  brfalse.s loc_12FEE
0x12fed  ret
0x12fee  ldarg.0
0x12fef  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x12ff4  ldarg.3
0x12ff5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x12ffa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::RetriveSLA(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> SLAId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x12fff  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x13004  stloc.0
0x13005  ldloc.0
0x13006  brfalse.s loc_13026
0x13008  ldarg.2
0x13009  ldloc.0
0x1300a  ldarg.3
0x1300b  ldc.i4.1
0x1300c  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ImpersonateUserForSLAWorkflows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA sla, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext, bool toCancelWorkflow)
0x13011  stloc.1
0x13012  ldarg.1
0x13013  ldloc.1
0x13014  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetAllWorkFlowInstances(valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService organizationService)
0x13019  ldloc.1
0x1301a  ldarg.3
0x1301b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x13020  ldarg.1
0x13021  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelWorkFlows(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection entityCollection, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService organizationService, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext, valuetype [mscorlib]System.Guid incidentId)
0x13026  ret
```
