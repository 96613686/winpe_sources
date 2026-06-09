# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadActionStep

- ea: `0x20620`
- end: `0x206eb`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadActionStep`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1f540`
- `0x1f610`
- `0x204f0`
- `0x20620`
- `0x2d410`
- `0x2d430`
- `0x2d450`
- `0x2d470`
- `0x2d490`
- `0x2d4b0`

## pseudocode

```c

```

## disassembly

```asm
0x20620  ldarg.0
0x20621  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x20626  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2062b  stloc.0
0x2062c  ldloc.0
0x2062d  ldarg.0
0x2062e  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x20633  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20638  ldarg.1
0x20639  isinst   Microsoft.Crm.Workflow.Activities.ActionComposite
0x2063e  stloc.1
0x2063f  ldloc.1
0x20640  brfalse  loc_206C8
0x20645  ldloc.0
0x20646  ldloc.1
0x20647  callvirt instance string Microsoft.Crm.Workflow.Activities.ActionComposite::get_ActionId()
0x2064c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::set_ActionId(string)
0x20651  ldloc.0
0x20652  ldloc.1
0x20653  callvirt instance int32 Microsoft.Crm.Workflow.Activities.ActionComposite::get_ActionType()
0x20658  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::set_ActionType(int32)
0x2065d  ldloc.0
0x2065e  ldloc.1
0x2065f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Activities.ActionComposite::get_ProcessId()
0x20664  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::set_ProcessId(valuetype [mscorlib]System.Guid)
0x20669  ldloc.0
0x2066a  ldloc.1
0x2066b  callvirt instance string Microsoft.Crm.Workflow.Activities.ActionComposite::get_UniqueName()
0x20670  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::set_UniqueName(string)
0x20675  ldloc.0
0x20676  ldloc.1
0x20677  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[] Microsoft.Crm.Workflow.Activities.ActionComposite::get_TriggerEvents()
0x2067c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::set_TriggerEvents(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ProcessTriggerData[])
0x20681  ldloc.1
0x20682  callvirt instance class [System.Activities]System.Activities.Statements.Sequence Microsoft.Crm.Workflow.Activities.ActionComposite::get_ActionControl()
0x20687  brfalse.s loc_206C8
0x20689  ldloc.0
0x2068a  ldarg.0
0x2068b  ldloc.1
0x2068c  callvirt instance class [System.Activities]System.Activities.Statements.Sequence Microsoft.Crm.Workflow.Activities.ActionComposite::get_ActionControl()
0x20691  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadControlStep(class [System.Activities]System.Activities.Statements.Sequence sequence)
0x20696  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::set_ActionControl(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep)
0x2069b  ldloc.0
0x2069c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::get_ActionControl()
0x206a1  ldloc.0
0x206a2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Parent(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x206a7  ldloc.0
0x206a8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x206ad  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepDictionary [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_StepDictionary()
0x206b2  ldloc.0
0x206b3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::get_ActionControl()
0x206b8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x206bd  ldloc.0
0x206be  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::get_ActionControl()
0x206c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::set_Item(var<u1>, !!T0)
0x206c8  ldloc.0
0x206c9  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::get_ActionType()
0x206ce  ldc.i4.4
0x206cf  beq.s    loc_206D9
0x206d1  ldloc.0
0x206d2  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActionStep::get_ActionType()
0x206d7  brtrue.s loc_206E1
0x206d9  ldarg.0
0x206da  ldloc.0
0x206db  ldarg.1
0x206dc  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddLabels(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x206e1  ldarg.0
0x206e2  ldloc.0
0x206e3  ldarg.1
0x206e4  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddChildSteps(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase compositeStep, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x206e9  ldloc.0
0x206ea  ret
```
