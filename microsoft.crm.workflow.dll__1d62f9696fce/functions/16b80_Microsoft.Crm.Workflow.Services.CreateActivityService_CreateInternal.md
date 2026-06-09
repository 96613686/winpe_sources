# Microsoft.Crm.Workflow.Services.CreateActivityService::CreateInternal

- ea: `0x16b80`
- end: `0x16bc7`
- name: `Microsoft.Crm.Workflow.Services.CreateActivityService::CreateInternal`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x16ac0`
- `0x16b30`

## callees

- `0x14b50`
- `0x14e40`
- `0x2e710`
- `0x2ea80`

## pseudocode

```c

```

## disassembly

```asm
0x16b80  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x16b85  stloc.0
0x16b86  ldloc.0
0x16b87  ldarg.1
0x16b88  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x16b8d  ldloc.0
0x16b8e  ldarg.0
0x16b8f  stfld    class Microsoft.Crm.Workflow.Services.CreateActivityService <>c__DisplayClass4_0::<>4__this
0x16b94  ldloc.0
0x16b95  ldarg.2
0x16b96  stfld    string <>c__DisplayClass4_0::StepId
0x16b9b  ldloc.0
0x16b9c  ldnull
0x16b9d  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x16ba2  ldarg.0
0x16ba3  ldloc.0
0x16ba4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x16ba9  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetWorkflowCreatedActivityFlag(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x16bae  ldarg.0
0x16baf  ldloc.0
0x16bb0  ldftn    instance void <>c__DisplayClass4_0::<CreateInternal>b__0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x16bb6  newobj   instance void ActivityDelegate::.ctor(object object, native int method)
0x16bbb  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext(class ActivityDelegate activityDelegate)
0x16bc0  ldloc.0
0x16bc1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x16bc6  ret
```
