# <>c__DisplayClass4_0::<UpdateInternal>b__0

- ea: `0x2f190`
- end: `0x2f24e`
- name: `<>c__DisplayClass4_0::<UpdateInternal>b__0`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x14770`
- `0x14790`
- `0x14ba0`
- `0x14ca0`
- `0x14e90`
- `0x2f190`

## pseudocode

```c

```

## disassembly

```asm
0x2f190  ldarg.0
0x2f191  ldfld    class Microsoft.Crm.Workflow.Services.UpdateActivityService <>c__DisplayClass4_0::<>4__this
0x2f196  ldarg.0
0x2f197  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2f19c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2f1a1  ldarg.0
0x2f1a2  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2f1a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x2f1ac  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.LockHandle Microsoft.Crm.Workflow.Services.ActivityServiceBase::TryAcquireLockWithRetry(string entityLogicalName, valuetype [mscorlib]System.Guid entityId)
0x2f1b1  stloc.0
0x2f1b2  ldarg.1
0x2f1b3  ldarg.0
0x2f1b4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2f1b9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x2f1be  ldarg.0
0x2f1bf  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2f1c4  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2f1c9  ldstr    aEmail// "email"
0x2f1ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f1d3  brfalse.s loc_2F202
0x2f1d5  ldarg.0
0x2f1d6  ldfld    class Microsoft.Crm.Workflow.Services.UpdateActivityService <>c__DisplayClass4_0::<>4__this
0x2f1db  ldarg.0
0x2f1dc  ldfld    class Microsoft.Crm.Workflow.Services.UpdateActivityService <>c__DisplayClass4_0::<>4__this
0x2f1e1  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x2f1e6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x2f1eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2f1f0  ldarg.0
0x2f1f1  ldfld    string <>c__DisplayClass4_0::stepId
0x2f1f6  ldarg.0
0x2f1f7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::primaryId
0x2f1fc  ldarg.1
0x2f1fd  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::AttachMimeEmailAttachment(valuetype [mscorlib]System.Guid workflowActivationId, string stepId, valuetype [mscorlib]System.Guid emailId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x2f202  ldarg.0
0x2f203  ldfld    class Microsoft.Crm.Workflow.Services.UpdateActivityService <>c__DisplayClass4_0::<>4__this
0x2f208  ldarg.0
0x2f209  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2f20e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2f213  ldarg.0
0x2f214  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::primaryId
0x2f219  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord(string entityName, valuetype [mscorlib]System.Guid entityId)
0x2f21e  ldarg.0
0x2f21f  ldarg.0
0x2f220  ldfld    class Microsoft.Crm.Workflow.Services.UpdateActivityService <>c__DisplayClass4_0::<>4__this
0x2f225  ldarg.0
0x2f226  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::entity
0x2f22b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x2f230  ldarg.0
0x2f231  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::primaryId
0x2f236  ldarg.1
0x2f237  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.Services.ActivityServiceBase::RetrieveEntityInternal(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x2f23c  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x2f241  leave.s  loc_2F24D
0x2f243  ldloc.0
0x2f244  brfalse.s loc_2F24C
0x2f246  ldloc.0
0x2f247  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f24c  endfinally
0x2f24d  ret
```
