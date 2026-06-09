# Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::InitializeTriggerConditions

- ea: `0x3a570`
- end: `0x3a5fd`
- name: `Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::InitializeTriggerConditions`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3a500`
- `0x3a520`
- `0x3a540`
- `0x3a560`
- `0x3a570`
- `0x3a600`
- `0x3ac10`
- `0x3ad20`
- `0x3af70`

## string_xrefs

- `0x3a583`: `createstage`
- `0x3a59e`: `deletestage`
- `0x3a5bd`: `updatestage`

## pseudocode

```c

```

## disassembly

```asm
0x3a570  ldarg.0
0x3a571  ldarg.1
0x3a572  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::InitializeTriggerConditions(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity workflowEntity)
0x3a577  ldarg.0
0x3a578  ldc.i4.2
0x3a579  call     instance bool Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTriggerCondition(valuetype Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions condition)
0x3a57e  brfalse.s loc_3A592
0x3a580  ldarg.0
0x3a581  ldarg.0
0x3a582  ldarg.1
0x3a583  ldstr    aCreatestage// "createstage"
0x3a588  call     instance int32 Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::ReadStage(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity workflowEntity, string stageColumnName)
0x3a58d  call     instance void Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_CreateStage(int32 value)
0x3a592  ldarg.0
0x3a593  ldc.i4.4
0x3a594  call     instance bool Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::ContainsTriggerCondition(valuetype Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions condition)
0x3a599  brfalse.s loc_3A5AD
0x3a59b  ldarg.0
0x3a59c  ldarg.0
0x3a59d  ldarg.1
0x3a59e  ldstr    aDeletestage// "deletestage"
0x3a5a3  call     instance int32 Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::ReadStage(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity workflowEntity, string stageColumnName)
0x3a5a8  call     instance void Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_DeleteStage(int32 value)
0x3a5ad  ldarg.0
0x3a5ae  call     instance string Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_UpdateAttributeList()
0x3a5b3  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3a5b8  brtrue.s loc_3A5CC
0x3a5ba  ldarg.0
0x3a5bb  ldarg.0
0x3a5bc  ldarg.1
0x3a5bd  ldstr    aUpdatestage// "updatestage"
0x3a5c2  call     instance int32 Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::ReadStage(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity workflowEntity, string stageColumnName)
0x3a5c7  call     instance void Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_UpdateStage(int32 value)
0x3a5cc  ldarg.0
0x3a5cd  ldarg.1
0x3a5ce  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3a5d3  ldstr    aRunas// "runas"
0x3a5d8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3a5dd  brtrue.s loc_3A5E2
0x3a5df  ldc.i4.1
0x3a5e0  br.s     loc_3A5F7
0x3a5e2  ldarg.1
0x3a5e3  ldstr    aRunas// "runas"
0x3a5e8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3a5ed  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x3a5f2  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x3a5f7  call     instance void Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_RunAs(int32 value)
0x3a5fc  ret
```
