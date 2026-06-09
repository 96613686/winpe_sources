# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntityStep

- ea: `0x1f3a0`
- end: `0x1f3f1`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntityStep`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1f3a0`
- `0x1f610`
- `0x2d310`
- `0x2d350`
- `0x2d370`

## pseudocode

```c

```

## disassembly

```asm
0x1f3a0  ldarg.0
0x1f3a1  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f3a6  ldarg.1
0x1f3a7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x1f3ac  stloc.0
0x1f3ad  ldloc.0
0x1f3ae  ldarg.0
0x1f3af  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f3b4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1f3b9  ldarg.2
0x1f3ba  isinst   Microsoft.Crm.Workflow.Activities.EntityComposite
0x1f3bf  stloc.1
0x1f3c0  ldloc.1
0x1f3c1  brfalse.s loc_1F3E7
0x1f3c3  ldloc.0
0x1f3c4  ldloc.1
0x1f3c5  callvirt instance string Microsoft.Crm.Workflow.Activities.EntityComposite::get_RelationshipName()
0x1f3ca  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::set_RelationshipName(string)
0x1f3cf  ldloc.0
0x1f3d0  ldloc.1
0x1f3d1  callvirt instance string Microsoft.Crm.Workflow.Activities.EntityComposite::get_AttributeName()
0x1f3d6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::set_AttributeName(string)
0x1f3db  ldloc.0
0x1f3dc  ldloc.1
0x1f3dd  callvirt instance bool Microsoft.Crm.Workflow.Activities.EntityComposite::get_IsClosedLoop()
0x1f3e2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::set_IsClosedLoop(bool)
0x1f3e7  ldarg.0
0x1f3e8  ldloc.0
0x1f3e9  ldarg.2
0x1f3ea  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::AddChildSteps(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase compositeStep, class Microsoft.Crm.Workflow.Activities.Composite sequence)
0x1f3ef  ldloc.0
0x1f3f0  ret
```
