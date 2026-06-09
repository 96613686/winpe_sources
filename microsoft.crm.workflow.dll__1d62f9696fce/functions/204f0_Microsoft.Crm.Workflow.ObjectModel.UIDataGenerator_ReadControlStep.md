# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadControlStep

- ea: `0x204f0`
- end: `0x2061d`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadControlStep`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x20620`
- `0x22480`

## callees

- `0x204f0`
- `0x2cdf0`
- `0x2ce10`
- `0x2ce30`
- `0x2ce50`
- `0x2ce70`
- `0x2ce90`
- `0x2ceb0`
- `0x2ced0`

## pseudocode

```c

```

## disassembly

```asm
0x204f0  ldarg.0
0x204f1  ldarg.1
0x204f2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x204f7  ldc.i4.0
0x204f8  call     T0x2B00002E
0x204fd  stloc.0
0x204fe  ldloc.0
0x204ff  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_ControlId()
0x20504  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20509  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2050e  stloc.1
0x2050f  ldloc.0
0x20510  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_ClassId()
0x20515  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x2051a  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2051f  stloc.2
0x20520  ldloc.0
0x20521  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_DataFieldName()
0x20526  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x2052b  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x20530  stloc.3
0x20531  ldloc.0
0x20532  callvirt instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_SystemStepType()
0x20537  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<int32>::get_Expression()
0x2053c  castclass class [System.Activities]System.Activities.Expressions.Literal`1<int32>
0x20541  stloc.s  4
0x20543  ldloc.0
0x20544  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_IsSystemControl()
0x20549  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x2054e  castclass class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x20553  stloc.s  5
0x20555  ldloc.0
0x20556  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_Parameters()
0x2055b  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20560  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x20565  stloc.s  6
0x20567  ldloc.0
0x20568  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_ControlDisplayName()
0x2056d  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x20572  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x20577  stloc.s  7
0x20579  ldarg.0
0x2057a  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2057f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20584  stloc.s  8
0x20586  ldloc.s  8
0x20588  ldarg.0
0x20589  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2058e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20593  ldloc.s  8
0x20595  ldloc.1
0x20596  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x2059b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlId(string)
0x205a0  ldloc.s  8
0x205a2  ldloc.2
0x205a3  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x205a8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ClassId(string)
0x205ad  ldloc.s  8
0x205af  ldloc.3
0x205b0  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x205b5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_DataFieldName(string)
0x205ba  ldloc.s  8
0x205bc  ldloc.s  4
0x205be  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<int32>::get_Value()
0x205c3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_SystemStepType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SystemStep)
0x205c8  ldloc.s  8
0x205ca  ldloc.s  5
0x205cc  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x205d1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_IsSystemControl(bool)
0x205d6  ldloc.s  8
0x205d8  ldloc.s  6
0x205da  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x205df  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_Parameters(string)
0x205e4  ldloc.s  8
0x205e6  ldloc.s  7
0x205e8  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x205ed  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_ControlDisplayName(string)
0x205f2  ldloc.0
0x205f3  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_IsUnbound()
0x205f8  brfalse.s loc_2061A
0x205fa  ldloc.0
0x205fb  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.Control::get_IsUnbound()
0x20600  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x20605  castclass class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x2060a  stloc.s  9
0x2060c  ldloc.s  8
0x2060e  ldloc.s  9
0x20610  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x20615  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ControlStep::set_IsUnbound(bool)
0x2061a  ldloc.s  8
0x2061c  ret
```
