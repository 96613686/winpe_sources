# Microsoft.Crm.Workflow.Services.SetStateActivityService::SetStateInternal

- ea: `0x19ee0`
- end: `0x19f4c`
- name: `Microsoft.Crm.Workflow.Services.SetStateActivityService::SetStateInternal`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x19e30`
- `0x19e80`

## callees

- `0x14b50`
- `0x19ee0`
- `0x2e710`
- `0x2f0d0`

## pseudocode

```c

```

## disassembly

```asm
0x19ee0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x19ee5  stloc.0
0x19ee6  ldloc.0
0x19ee7  ldarg.0
0x19ee8  stfld    class Microsoft.Crm.Workflow.Services.SetStateActivityService <>c__DisplayClass4_0::<>4__this
0x19eed  ldloc.0
0x19eee  ldarg.1
0x19eef  stfld    string <>c__DisplayClass4_0::entityName
0x19ef4  ldloc.0
0x19ef5  ldarg.2
0x19ef6  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::entityId
0x19efb  ldloc.0
0x19efc  ldarg.3
0x19efd  stfld    int32 <>c__DisplayClass4_0::state
0x19f02  ldloc.0
0x19f03  ldarg.s  4
0x19f05  stfld    int32 <>c__DisplayClass4_0::status
0x19f0a  ldloc.0
0x19f0b  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::entityId
0x19f10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19f15  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19f1a  brfalse.s loc_19F2C
0x19f1c  ldstr    aCannotFindReco_3// "Cannot find record to change state"
0x19f21  ldc.i4   0x80045031
0x19f26  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19f2b  throw
0x19f2c  ldloc.0
0x19f2d  ldnull
0x19f2e  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x19f33  ldarg.0
0x19f34  ldloc.0
0x19f35  ldftn    instance void <>c__DisplayClass4_0::<SetStateInternal>b__0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x19f3b  newobj   instance void ActivityDelegate::.ctor(object object, native int method)
0x19f40  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext(class ActivityDelegate activityDelegate)
0x19f45  ldloc.0
0x19f46  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x19f4b  ret
```
