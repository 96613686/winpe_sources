# Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::InitializeFromWorkflowDefinition

- ea: `0x3add0`
- end: `0x3af65`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::InitializeFromWorkflowDefinition`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x3aae0`
- `0x3ab20`
- `0x3ab60`
- `0x3ab70`
- `0x3ab80`
- `0x3abc0`
- `0x3abe0`
- `0x3ac00`
- `0x3acc0`
- `0x3add0`
- `0x3af70`

## string_xrefs

- `0x3ae7c`: `asyncautodelete`
- `0x3ae89`: `asyncautodelete`

## pseudocode

```c

```

## disassembly

```asm
0x3add0  ldarg.1
0x3add1  ldstr    aType_0// "type"
0x3add6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3addb  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x3ade0  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x3ade5  stloc.0
0x3ade6  ldarg.0
0x3ade7  ldloc.0
0x3ade8  ldc.i4.3
0x3ade9  ceq
0x3adeb  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_IsTemplate(bool value)
0x3adf0  ldarg.1
0x3adf1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3adf6  ldstr    aScope// "scope"
0x3adfb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3ae00  brfalse.s loc_3AE1F
0x3ae02  ldarg.1
0x3ae03  ldstr    aScope// "scope"
0x3ae08  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3ae0d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x3ae12  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x3ae17  stloc.1
0x3ae18  ldarg.0
0x3ae19  ldloc.1
0x3ae1a  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_Scope(int32 value)
0x3ae1f  ldarg.1
0x3ae20  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3ae25  ldstr    aRendererobject// "rendererobjecttypecode"
0x3ae2a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3ae2f  brfalse.s loc_3AE47
0x3ae31  ldarg.0
0x3ae32  ldarg.1
0x3ae33  ldstr    aRendererobject// "rendererobjecttypecode"
0x3ae38  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3ae3d  castclass [mscorlib]System.String
0x3ae42  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowRendererObjectTypeCode(string value)
0x3ae47  ldarg.1
0x3ae48  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3ae4d  ldstr    aCategory// "category"
0x3ae52  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3ae57  brfalse.s loc_3AE76
0x3ae59  ldarg.1
0x3ae5a  ldstr    aCategory// "category"
0x3ae5f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3ae64  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x3ae69  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x3ae6e  stloc.2
0x3ae6f  ldarg.0
0x3ae70  ldloc.2
0x3ae71  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowCategory(int32 value)
0x3ae76  ldarg.1
0x3ae77  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3ae7c  ldstr    aAsyncautodelet// "asyncautodelete"
0x3ae81  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3ae86  brfalse.s loc_3AEA1
0x3ae88  ldarg.1
0x3ae89  ldstr    aAsyncautodelet// "asyncautodelete"
0x3ae8e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3ae93  unbox.any [mscorlib]System.Boolean
0x3ae98  brfalse.s loc_3AEA1
0x3ae9a  ldarg.0
0x3ae9b  ldc.i4.1
0x3ae9c  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_AsyncAutoDelete(bool value)
0x3aea1  ldarg.1
0x3aea2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3aea7  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x3aeac  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3aeb1  brfalse.s loc_3AECC
0x3aeb3  ldarg.1
0x3aeb4  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x3aeb9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3aebe  unbox.any [mscorlib]System.Boolean
0x3aec3  brfalse.s loc_3AECC
0x3aec5  ldarg.0
0x3aec6  ldc.i4.1
0x3aec7  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_SyncWorkflowLogOnFailure(bool value)
0x3aecc  ldarg.1
0x3aecd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3aed2  ldstr    aOndemand// "ondemand"
0x3aed7  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3aedc  brfalse.s loc_3AEF7
0x3aede  ldarg.1
0x3aedf  ldstr    aOndemand// "ondemand"
0x3aee4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3aee9  unbox.any [mscorlib]System.Boolean
0x3aeee  brfalse.s loc_3AEF7
0x3aef0  ldarg.0
0x3aef1  ldc.i4.4
0x3aef2  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes trigger)
0x3aef7  ldarg.0
0x3aef8  ldc.i4.1
0x3aef9  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_IsCrmUIWorkflow(bool value)
0x3aefe  ldarg.1
0x3aeff  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3af04  ldstr    aSubprocess// "subprocess"
0x3af09  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3af0e  brfalse.s loc_3AF29
0x3af10  ldarg.1
0x3af11  ldstr    aSubprocess// "subprocess"
0x3af16  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3af1b  unbox.any [mscorlib]System.Boolean
0x3af20  brfalse.s loc_3AF29
0x3af22  ldarg.0
0x3af23  ldc.i4.8
0x3af24  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes trigger)
0x3af29  ldarg.0
0x3af2a  call     instance int32 Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowCategory()
0x3af2f  ldc.i4.1
0x3af30  bne.un.s loc_3AF5D
0x3af32  ldarg.1
0x3af33  ldstr    aOndemand// "ondemand"
0x3af38  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3af3d  unbox.any [mscorlib]System.Boolean
0x3af42  brtrue.s loc_3AF5D
0x3af44  ldarg.1
0x3af45  ldstr    aSubprocess// "subprocess"
0x3af4a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3af4f  unbox.any [mscorlib]System.Boolean
0x3af54  brtrue.s loc_3AF5D
0x3af56  ldarg.0
0x3af57  ldc.i4.4
0x3af58  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTrigger(valuetype Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerTypes trigger)
0x3af5d  ldarg.0
0x3af5e  ldarg.1
0x3af5f  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::InitializeTriggerConditions(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity workflowEntity)
0x3af64  ret
```
