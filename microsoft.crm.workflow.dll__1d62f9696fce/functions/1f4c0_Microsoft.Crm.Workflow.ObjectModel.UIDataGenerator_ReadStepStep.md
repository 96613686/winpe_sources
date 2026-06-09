# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStepStep

- ea: `0x1f4c0`
- end: `0x1f512`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStepStep`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1f4c0`
- `0x1f540`
- `0x1f610`
- `0x2d2a0`
- `0x2d2c0`

## pseudocode

```c

```

## disassembly

```asm
0x1f4c0  ldarg.0
0x1f4c1  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f4c6  ldarg.1
0x1f4c7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x1f4cc  stloc.0
0x1f4cd  ldloc.0
0x1f4ce  ldarg.0
0x1f4cf  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f4d4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1f4d9  ldarg.2
0x1f4da  isinst   Microsoft.Crm.Workflow.Activities.StepComposite
0x1f4df  stloc.1
0x1f4e0  ldloc.1
0x1f4e1  brfalse.s loc_1F500
0x1f4e3  ldloc.0
0x1f4e4  ldloc.1
0x1f4e5  callvirt instance string Microsoft.Crm.Workflow.Activities.StepComposite::get_ProcessStepId()
0x1f4ea  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.Utils.StringUtility::ReduceToCanonicalForm(string)
0x1f4ef  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::set_StepStepId(string)
0x1f4f4  ldloc.0
0x1f4f5  ldloc.1
0x1f4f6  callvirt instance bool Microsoft.Crm.Workflow.Activities.StepComposite::get_IsProcessRequired()
0x1f4fb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepStep::set_IsProcessRequired(bool)
0x1f500  ldarg.0
0x1f501  ldloc.0
0x1f502  ldarg.2
0x1f503  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddLabels(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x1f508  ldarg.0
0x1f509  ldloc.0
0x1f50a  ldarg.2
0x1f50b  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddChildSteps(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase compositeStep, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x1f510  ldloc.0
0x1f511  ret
```
