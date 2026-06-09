# Microsoft.Crm.Workflow.Services.ChildWorkflowActivityService::StartChildWorkflowInternal

- ea: `0x15e50`
- end: `0x15ebc`
- name: `Microsoft.Crm.Workflow.Services.ChildWorkflowActivityService::StartChildWorkflowInternal`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x15dd0`
- `0x15e10`

## callees

- `0x14b50`
- `0x15e50`
- `0x2e710`
- `0x2e8a0`

## pseudocode

```c

```

## disassembly

```asm
0x15e50  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x15e55  stloc.0
0x15e56  ldloc.0
0x15e57  ldarg.0
0x15e58  stfld    class Microsoft.Crm.Workflow.Services.ChildWorkflowActivityService <>c__DisplayClass4_0::<>4__this
0x15e5d  ldloc.0
0x15e5e  ldarg.3
0x15e5f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::workflowId
0x15e64  ldloc.0
0x15e65  ldarg.2
0x15e66  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::entityId
0x15e6b  ldloc.0
0x15e6c  ldarg.s  4
0x15e6e  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <>c__DisplayClass4_0::InputParameters
0x15e73  ldloc.0
0x15e74  ldarg.1
0x15e75  stfld    string <>c__DisplayClass4_0::entityName
0x15e7a  ldloc.0
0x15e7b  ldfld    string <>c__DisplayClass4_0::entityName
0x15e80  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15e85  brtrue.s loc_15E99
0x15e87  ldloc.0
0x15e88  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::entityId
0x15e8d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15e92  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15e97  brfalse.s loc_15EA9
0x15e99  ldstr    aCannotFindReco_0// "Cannot find record to be used for child"...
0x15e9e  ldc.i4   0x80045031
0x15ea3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x15ea8  throw
0x15ea9  ldarg.0
0x15eaa  ldloc.0
0x15eab  ldftn    instance void <>c__DisplayClass4_0::<StartChildWorkflowInternal>b__0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x15eb1  newobj   instance void ActivityDelegate::.ctor(object object, native int method)
0x15eb6  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext(class ActivityDelegate activityDelegate)
0x15ebb  ret
```
