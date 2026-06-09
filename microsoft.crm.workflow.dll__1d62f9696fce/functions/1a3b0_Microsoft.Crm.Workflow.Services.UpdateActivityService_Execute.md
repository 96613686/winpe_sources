# Microsoft.Crm.Workflow.Services.UpdateActivityService::Execute

- ea: `0x1a3b0`
- end: `0x1a40c`
- name: `Microsoft.Crm.Workflow.Services.UpdateActivityService::Execute`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x67a0`
- `0x14770`
- `0x1a3b0`
- `0x1a4a0`

## string_xrefs

- `0x1a3b3`: `Invalid argument: updateActivity`

## pseudocode

```c

```

## disassembly

```asm
0x1a3b0  ldarg.2
0x1a3b1  brtrue.s loc_1A3C3
0x1a3b3  ldstr    aInvalidArgumen_1// "Invalid argument: updateActivity"
0x1a3b8  ldc.i4   0x80040203
0x1a3bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1a3c2  throw
0x1a3c3  ldarg.1
0x1a3c4  brtrue.s loc_1A3D6
0x1a3c6  ldstr    aInvalidArgumen_0// "Invalid argument: executionContext"
0x1a3cb  ldc.i4   0x80040203
0x1a3d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1a3d5  throw
0x1a3d6  ldarg.0
0x1a3d7  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x1a3dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Workflow.IAsyncWorkflowContext::get_LegacyConversionContext()
0x1a3e1  ldarg.2
0x1a3e2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.UpdateActivity::get_Entity()
0x1a3e7  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x1a3ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a3f1  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x1a3f6  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x1a3fb  stloc.0
0x1a3fc  ldarg.0
0x1a3fd  ldloc.0
0x1a3fe  ldarg.2
0x1a3ff  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.UpdateActivity::get_StepId()
0x1a404  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.Services.UpdateActivityService::UpdateInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string stepId)
0x1a409  pop
0x1a40a  ldc.i4.3
0x1a40b  ret
```
