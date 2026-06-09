# Microsoft.Crm.Workflow.Services.AssignActivityService::AssignInternal

- ea: `0x15c90`
- end: `0x15cfc`
- name: `Microsoft.Crm.Workflow.Services.AssignActivityService::AssignInternal`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x15b90`
- `0x15be0`

## callees

- `0x14b50`
- `0x15c90`
- `0x2e710`
- `0x2e7b0`

## pseudocode

```c

```

## disassembly

```asm
0x15c90  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x15c95  stloc.0
0x15c96  ldloc.0
0x15c97  ldarg.0
0x15c98  stfld    class Microsoft.Crm.Workflow.Services.AssignActivityService <>c__DisplayClass4_0::<>4__this
0x15c9d  ldloc.0
0x15c9e  ldarg.2
0x15c9f  stfld    string <>c__DisplayClass4_0::entityName
0x15ca4  ldloc.0
0x15ca5  ldarg.1
0x15ca6  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::entityId
0x15cab  ldloc.0
0x15cac  ldarg.3
0x15cad  stfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.AssignType <>c__DisplayClass4_0::assignType
0x15cb2  ldloc.0
0x15cb3  ldarg.s  4
0x15cb5  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::assignTo
0x15cba  ldloc.0
0x15cbb  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::entityId
0x15cc0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15cc5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15cca  brfalse.s loc_15CDC
0x15ccc  ldstr    aCannotFindReco// "Cannot find record to be assigned"
0x15cd1  ldc.i4   0x80045031
0x15cd6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x15cdb  throw
0x15cdc  ldloc.0
0x15cdd  ldnull
0x15cde  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x15ce3  ldarg.0
0x15ce4  ldloc.0
0x15ce5  ldftn    instance void <>c__DisplayClass4_0::<AssignInternal>b__0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x15ceb  newobj   instance void ActivityDelegate::.ctor(object object, native int method)
0x15cf0  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext(class ActivityDelegate activityDelegate)
0x15cf5  ldloc.0
0x15cf6  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x15cfb  ret
```
