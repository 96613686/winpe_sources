# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateConditionSequence

- ea: `0x2bb10`
- end: `0x2bbc4`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateConditionSequence`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x26070`
- `0x29200`

## callees

- `0x29e50`
- `0x2b7f0`
- `0x2bb10`
- `0x2d5f0`
- `0x2d610`
- `0x2d640`
- `0x2d680`
- `0x2d690`

## pseudocode

```c

```

## disassembly

```asm
0x2bb10  newobj   instance void Microsoft.Crm.Workflow.Activities.ConditionSequence::.ctor()
0x2bb15  dup
0x2bb16  ldarg.1
0x2bb17  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2bb1c  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2bb21  dup
0x2bb22  ldarg.2
0x2bb23  newobj   instance void class [System.Activities]System.Activities.InArgument`1<bool>::.ctor(var<u1>)
0x2bb28  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionSequence::set_Wait(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x2bb2d  stloc.0
0x2bb2e  ldarg.1
0x2bb2f  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep
0x2bb34  stloc.1
0x2bb35  ldloc.1
0x2bb36  brfalse.s loc_2BB49
0x2bb38  ldloc.0
0x2bb39  ldloc.1
0x2bb3a  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep::get_ContainsElseBranch()
0x2bb3f  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2bb44  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionSequence::set_ContainsElseBranch(valuetype [mscorlib]System.Nullable`1<bool> value)
0x2bb49  ldarg.1
0x2bb4a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2bb4f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2bb54  brtrue.s loc_2BB72
0x2bb56  ldloc.0
0x2bb57  dup
0x2bb58  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x2bb5d  ldstr    asc_3C24E// ": "
0x2bb62  ldarg.1
0x2bb63  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2bb68  call     string [mscorlib]System.String::Concat(string, string, string)
0x2bb6d  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2bb72  ldarg.0
0x2bb73  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bb78  stloc.2
0x2bb79  ldarg.0
0x2bb7a  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2bb7f  stloc.3
0x2bb80  ldarg.0
0x2bb81  ldloc.0
0x2bb82  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x2bb87  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bb8c  ldarg.0
0x2bb8d  ldloc.0
0x2bb8e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Variables()
0x2bb93  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2bb98  ldarg.0
0x2bb99  ldarg.1
0x2bb9a  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitChildren(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase step)
0x2bb9f  ldarg.0
0x2bba0  ldloc.2
0x2bba1  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bba6  ldarg.0
0x2bba7  ldloc.3
0x2bba8  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2bbad  ldarg.0
0x2bbae  ldloc.0
0x2bbaf  call     instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x2bbb4  stloc.s  4
0x2bbb6  ldarg.0
0x2bbb7  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bbbc  ldloc.s  4
0x2bbbe  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2bbc3  ret
```
