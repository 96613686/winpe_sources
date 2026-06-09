# Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::RemoveInvalidTriggerConditionsForSyncWorkflows

- ea: `0x78270`
- end: `0x78312`
- name: `Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::RemoveInvalidTriggerConditionsForSyncWorkflows`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x79520`
- `0x79720`
- `0x79df0`

## callees

- `0x474c0`
- `0x78270`

## string_xrefs

- `0x782b5`: `Delete`
- `0x782a1`: `Create`
- `0x782c9`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x78270  ldarg.1
0x78271  call     bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::IsGlobalCustomOperation(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x78276  brfalse.s loc_78279
0x78278  ret
0x78279  ldarg.1
0x7827a  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowCategory()
0x7827f  brtrue.s loc_7828A
0x78281  ldarg.1
0x78282  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowMode()
0x78287  ldc.i4.1
0x78288  beq.s    loc_78293
0x7828a  ldarg.1
0x7828b  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowCategory()
0x78290  ldc.i4.3
0x78291  bne.un.s loc_78311
0x78293  ldarg.1
0x78294  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x78299  stloc.0
0x7829a  ldarg.1
0x7829b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x782a0  stloc.1
0x782a1  ldstr    aCreate// "Create"
0x782a6  ldloc.1
0x782a7  call     bool Microsoft.Crm.Application.Utility.Util::MessageAllowsCustomProcessingStep(string messageName, string entityLogicalName)
0x782ac  brtrue.s loc_782B5
0x782ae  ldloc.0
0x782af  ldc.i4.2
0x782b0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::RemoveTriggerCondition(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions)
0x782b5  ldstr    aDelete// "Delete"
0x782ba  ldloc.1
0x782bb  call     bool Microsoft.Crm.Application.Utility.Util::MessageAllowsCustomProcessingStep(string messageName, string entityLogicalName)
0x782c0  brtrue.s loc_782C9
0x782c2  ldloc.0
0x782c3  ldc.i4.4
0x782c4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::RemoveTriggerCondition(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions)
0x782c9  ldstr    aUpdate// "Update"
0x782ce  ldloc.1
0x782cf  call     bool Microsoft.Crm.Application.Utility.Util::MessageAllowsCustomProcessingStep(string messageName, string entityLogicalName)
0x782d4  brtrue.s loc_782E1
0x782d6  ldloc.0
0x782d7  ldsfld   string [mscorlib]System.String::Empty
0x782dc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_UpdateAttributeList(string)
0x782e1  ldstr    aAssign// "Assign"
0x782e6  ldloc.1
0x782e7  call     bool Microsoft.Crm.Application.Utility.Util::MessageAllowsCustomProcessingStep(string messageName, string entityLogicalName)
0x782ec  brtrue.s loc_782F9
0x782ee  ldloc.0
0x782ef  ldstr    aOwnerid// "ownerid"
0x782f4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::RemoveTriggerAttribute(string)
0x782f9  ldstr    aSetstate// "SetState"
0x782fe  ldloc.1
0x782ff  call     bool Microsoft.Crm.Application.Utility.Util::MessageAllowsCustomProcessingStep(string messageName, string entityLogicalName)
0x78304  brtrue.s loc_78311
0x78306  ldloc.0
0x78307  ldstr    aStatecode// "statecode"
0x7830c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::RemoveTriggerAttribute(string)
0x78311  ret
```
