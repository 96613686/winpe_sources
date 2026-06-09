# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::UpdatePublicationParameters

- ea: `0x29be0`
- end: `0x29d29`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::UpdatePublicationParameters`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x29530`

## callees

- `0x29be0`

## string_xrefs

- `0x29ca8`: `asyncautodelete`
- `0x29c01`: `triggeroncreate`
- `0x29c37`: `triggeroncreate`
- `0x29c1a`: `createstage`
- `0x29c5c`: `triggerondelete`
- `0x29c92`: `triggerondelete`
- `0x29c75`: `deletestage`
- `0x29cde`: `triggeronupdateattributelist`
- `0x29cf5`: `updatestage`

## pseudocode

```c

```

## disassembly

```asm
0x29be0  ldarg.1
0x29be1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x29be6  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters
0x29beb  stloc.0
0x29bec  ldarg.1
0x29bed  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x29bf2  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_TriggerConditions()
0x29bf7  ldc.i4.2
0x29bf8  and
0x29bf9  brfalse.s loc_29C31
0x29bfb  ldarg.0
0x29bfc  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29c01  ldstr    aTriggeroncreat// "triggeroncreate"
0x29c06  ldc.i4.1
0x29c07  box      [mscorlib]System.Boolean
0x29c0c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29c11  ldloc.0
0x29c12  brfalse.s loc_29C47
0x29c14  ldarg.0
0x29c15  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29c1a  ldstr    aCreatestage// "createstage"
0x29c1f  ldloc.0
0x29c20  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::get_CreateStage()
0x29c25  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x29c2a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29c2f  br.s     loc_29C47
0x29c31  ldarg.0
0x29c32  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29c37  ldstr    aTriggeroncreat// "triggeroncreate"
0x29c3c  ldc.i4.0
0x29c3d  box      [mscorlib]System.Boolean
0x29c42  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29c47  ldarg.1
0x29c48  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x29c4d  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_TriggerConditions()
0x29c52  ldc.i4.4
0x29c53  and
0x29c54  brfalse.s loc_29C8C
0x29c56  ldarg.0
0x29c57  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29c5c  ldstr    aTriggerondelet// "triggerondelete"
0x29c61  ldc.i4.1
0x29c62  box      [mscorlib]System.Boolean
0x29c67  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29c6c  ldloc.0
0x29c6d  brfalse.s loc_29CA2
0x29c6f  ldarg.0
0x29c70  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29c75  ldstr    aDeletestage// "deletestage"
0x29c7a  ldloc.0
0x29c7b  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::get_DeleteStage()
0x29c80  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x29c85  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29c8a  br.s     loc_29CA2
0x29c8c  ldarg.0
0x29c8d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29c92  ldstr    aTriggerondelet// "triggerondelete"
0x29c97  ldc.i4.0
0x29c98  box      [mscorlib]System.Boolean
0x29c9d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29ca2  ldarg.0
0x29ca3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29ca8  ldstr    aAsyncautodelet// "asyncautodelete"
0x29cad  ldarg.1
0x29cae  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x29cb3  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_AsyncAutoDelete()
0x29cb8  box      [mscorlib]System.Boolean
0x29cbd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29cc2  ldarg.1
0x29cc3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x29cc8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_UpdateAttributeListForSdk()
0x29ccd  stloc.1
0x29cce  ldloc.1
0x29ccf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29cd4  brfalse.s loc_29CD8
0x29cd6  ldnull
0x29cd7  stloc.1
0x29cd8  ldarg.0
0x29cd9  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29cde  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x29ce3  ldloc.1
0x29ce4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29ce9  ldloc.1
0x29cea  brfalse.s loc_29D0A
0x29cec  ldloc.0
0x29ced  brfalse.s loc_29D0A
0x29cef  ldarg.0
0x29cf0  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29cf5  ldstr    aUpdatestage// "updatestage"
0x29cfa  ldloc.0
0x29cfb  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::get_UpdateStage()
0x29d00  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x29d05  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29d0a  ldloc.0
0x29d0b  brfalse.s loc_29D28
0x29d0d  ldarg.0
0x29d0e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_definition
0x29d13  ldstr    aRunas// "runas"
0x29d18  ldloc.0
0x29d19  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::get_RunAs()
0x29d1e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x29d23  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x29d28  ret
```
