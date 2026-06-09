# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ParseStageComposite

- ea: `0x1f420`
- end: `0x1f475`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ParseStageComposite`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1f400`
- `0x1f480`

## callees

- `0x1f420`
- `0x1f540`
- `0x1f610`
- `0x2d210`
- `0x2d230`
- `0x2d250`

## pseudocode

```c

```

## disassembly

```asm
0x1f420  ldarg.1
0x1f421  ldarg.0
0x1f422  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f427  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1f42c  ldarg.2
0x1f42d  isinst   Microsoft.Crm.Workflow.Activities.StageComposite
0x1f432  stloc.0
0x1f433  ldloc.0
0x1f434  brfalse.s loc_1F464
0x1f436  ldarg.1
0x1f437  ldloc.0
0x1f438  callvirt instance string Microsoft.Crm.Workflow.Activities.StageComposite::get_StageId()
0x1f43d  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.Utils.StringUtility::ReduceToCanonicalForm(string)
0x1f442  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::set_StageId(string)
0x1f447  ldarg.1
0x1f448  ldloc.0
0x1f449  callvirt instance string Microsoft.Crm.Workflow.Activities.StageComposite::get_NextStageId()
0x1f44e  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.Utils.StringUtility::ReduceToCanonicalForm(string)
0x1f453  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::set_NextStageId(string)
0x1f458  ldarg.1
0x1f459  ldloc.0
0x1f45a  callvirt instance string Microsoft.Crm.Workflow.Activities.StageComposite::get_StageCategory()
0x1f45f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::set_StageCategory(string)
0x1f464  ldarg.0
0x1f465  ldarg.1
0x1f466  ldarg.2
0x1f467  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddLabels(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x1f46c  ldarg.0
0x1f46d  ldarg.1
0x1f46e  ldarg.2
0x1f46f  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddChildSteps(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase compositeStep, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x1f474  ret
```
