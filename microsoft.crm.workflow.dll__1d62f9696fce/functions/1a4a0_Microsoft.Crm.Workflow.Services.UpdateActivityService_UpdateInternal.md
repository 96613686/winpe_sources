# Microsoft.Crm.Workflow.Services.UpdateActivityService::UpdateInternal

- ea: `0x1a4a0`
- end: `0x1a50e`
- name: `Microsoft.Crm.Workflow.Services.UpdateActivityService::UpdateInternal`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a3b0`
- `0x1a460`

## callees

- `0x14b50`
- `0x1a4a0`
- `0x2e710`
- `0x2f180`

## string_xrefs

- `0x1a4e5`: `Cannot find record to be updated`

## pseudocode

```c

```

## disassembly

```asm
0x1a4a0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x1a4a5  stloc.0
0x1a4a6  ldloc.0
0x1a4a7  ldarg.0
0x1a4a8  stfld    class Microsoft.Crm.Workflow.Services.UpdateActivityService <>c__DisplayClass4_0::<>4__this
0x1a4ad  ldloc.0
0x1a4ae  ldarg.1
0x1a4af  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x1a4b4  ldloc.0
0x1a4b5  ldarg.2
0x1a4b6  stfld    string <>c__DisplayClass4_0::stepId
0x1a4bb  ldloc.0
0x1a4bc  ldnull
0x1a4bd  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x1a4c2  ldloc.0
0x1a4c3  ldloc.0
0x1a4c4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x1a4c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1a4ce  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::primaryId
0x1a4d3  ldloc.0
0x1a4d4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::primaryId
0x1a4d9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a4de  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a4e3  brfalse.s loc_1A4F5
0x1a4e5  ldstr    aCannotFindReco_2// "Cannot find record to be updated"
0x1a4ea  ldc.i4   0x80045031
0x1a4ef  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1a4f4  throw
0x1a4f5  ldarg.0
0x1a4f6  ldloc.0
0x1a4f7  ldftn    instance void <>c__DisplayClass4_0::<UpdateInternal>b__0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x1a4fd  newobj   instance void ActivityDelegate::.ctor(object object, native int method)
0x1a502  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext(class ActivityDelegate activityDelegate)
0x1a507  ldloc.0
0x1a508  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x1a50d  ret
```
