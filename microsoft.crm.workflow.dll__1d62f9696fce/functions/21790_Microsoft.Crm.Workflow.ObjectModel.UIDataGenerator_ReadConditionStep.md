# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadConditionStep

- ea: `0x21790`
- end: `0x2182c`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadConditionStep`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x21790`
- `0x21830`
- `0x2d5f0`
- `0x2d670`

## pseudocode

```c

```

## disassembly

```asm
0x21790  ldc.i4.0
0x21791  stloc.0
0x21792  ldarg.1
0x21793  brfalse.s loc_217A3
0x21795  ldarg.0
0x21796  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2179b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x217a0  stloc.1
0x217a1  br.s     loc_217AF
0x217a3  ldarg.0
0x217a4  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x217a9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x217ae  stloc.1
0x217af  ldloc.1
0x217b0  ldarg.0
0x217b1  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x217b6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x217bb  br.s     loc_217EB
0x217bd  ldarg.2
0x217be  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x217c3  ldloc.0
0x217c4  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x217c9  isinst   [System.Activities]System.Activities.Statements.Persist
0x217ce  brtrue.s loc_217E7
0x217d0  ldarg.0
0x217d1  ldloc.1
0x217d2  ldarg.2
0x217d3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x217d8  ldloca.s 0
0x217da  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadBranchStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase parentStep, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> sequenceActivities, int32& activityIndex)
0x217df  stloc.2
0x217e0  ldloc.1
0x217e1  ldloc.2
0x217e2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x217e7  ldloc.0
0x217e8  ldc.i4.1
0x217e9  add
0x217ea  stloc.0
0x217eb  ldloc.0
0x217ec  ldarg.2
0x217ed  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x217f2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x217f7  blt.s    loc_217BD
0x217f9  ldarg.2
0x217fa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_ContainsElseBranch()
0x217ff  stloc.3
0x21800  ldloca.s 3
0x21802  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x21807  brfalse.s loc_2182A
0x21809  ldloc.1
0x2180a  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep
0x2180f  brfalse.s loc_2182A
0x21811  ldloc.1
0x21812  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep
0x21817  ldarg.2
0x21818  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_ContainsElseBranch()
0x2181d  stloc.3
0x2181e  ldloca.s 3
0x21820  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x21825  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep::set_ContainsElseBranch(bool)
0x2182a  ldloc.1
0x2182b  ret
```
