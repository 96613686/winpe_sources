# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetDisplayModeStep

- ea: `0x201a0`
- end: `0x2025f`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetDisplayModeStep`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1a9b0`
- `0x1a9d0`
- `0x1a9f0`
- `0x1aa10`
- `0x1aa30`
- `0x201a0`
- `0x22a40`

## pseudocode

```c

```

## disassembly

```asm
0x201a0  ldarg.0
0x201a1  ldarg.1
0x201a2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x201a7  ldc.i4.0
0x201a8  call     T0x2B000028
0x201ad  stloc.0
0x201ae  ldloc.0
0x201af  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetDisplayMode::get_ControlId()
0x201b4  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x201b9  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x201be  stloc.1
0x201bf  ldloc.0
0x201c0  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetDisplayMode::get_ControlType()
0x201c5  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x201ca  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x201cf  stloc.2
0x201d0  ldloc.0
0x201d1  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.ClientActivities.SetDisplayMode::get_IsReadOnly()
0x201d6  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x201db  castclass class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x201e0  stloc.3
0x201e1  ldarg.0
0x201e2  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x201e7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x201ec  stloc.s  4
0x201ee  ldloc.s  4
0x201f0  ldloc.1
0x201f1  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x201f6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::set_ControlId(string)
0x201fb  ldloc.s  4
0x201fd  ldloc.2
0x201fe  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x20203  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::set_ControlType(string)
0x20208  ldloc.s  4
0x2020a  ldloc.3
0x2020b  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x20210  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::set_IsReadOnly(bool)
0x20215  ldloc.0
0x20216  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetDisplayMode::get_Entity()
0x2021b  brfalse.s loc_2025C
0x2021d  ldloc.0
0x2021e  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.ClientActivities.SetDisplayMode::get_EntityName()
0x20223  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20228  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2022d  stloc.s  5
0x2022f  ldloc.0
0x20230  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ClientActivities.SetDisplayMode::get_Entity()
0x20235  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Expression()
0x2023a  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x2023f  stloc.s  6
0x20241  ldloc.s  4
0x20243  ldarg.0
0x20244  ldloc.s  6
0x20246  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_ExpressionText()
0x2024b  ldloc.s  5
0x2024d  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x20252  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x20257  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetDisplayModeStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x2025c  ldloc.s  4
0x2025e  ret
```
