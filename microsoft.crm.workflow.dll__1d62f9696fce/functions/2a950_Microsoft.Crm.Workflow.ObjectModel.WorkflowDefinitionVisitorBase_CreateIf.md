# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateIf

- ea: `0x2a950`
- end: `0x2aa70`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateIf`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x26060`
- `0x291d0`

## callees

- `0x29e50`
- `0x2a950`
- `0x2b7f0`
- `0x2ba20`
- `0x2ba40`
- `0x2d0b0`
- `0x2d170`
- `0x2d190`
- `0x2d4f0`
- `0x2d530`
- `0x2d550`
- `0x2d560`

## pseudocode

```c

```

## disassembly

```asm
0x2a950  ldarg.2
0x2a951  brfalse.s loc_2A971
0x2a953  ldarg.0
0x2a954  ldc.i4.0
0x2a955  ldarg.0
0x2a956  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentStep
0x2a95b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2a960  ldstr    aCondition_0// "_condition"
0x2a965  call     string [mscorlib]System.String::Concat(string, string)
0x2a96a  ldarg.2
0x2a96b  call     T0x2B00004E
0x2a970  pop
0x2a971  newobj   instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::.ctor()
0x2a976  dup
0x2a977  ldarg.1
0x2a978  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2a97d  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2a982  dup
0x2a983  ldarg.1
0x2a984  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2a989  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Description(string value)
0x2a98e  stloc.0
0x2a98f  ldarg.2
0x2a990  brtrue.s loc_2A9A0
0x2a992  ldloc.0
0x2a993  ldc.i4.1
0x2a994  newobj   instance void class [System.Activities]System.Activities.InArgument`1<bool>::.ctor(var<u1>)
0x2a999  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Condition(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x2a99e  br.s     loc_2A9ED
0x2a9a0  ldarg.2
0x2a9a1  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression
0x2a9a6  brtrue.s loc_2A9ED
0x2a9a8  ldarg.2
0x2a9a9  ldarg.0
0x2a9aa  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x2a9af  ldarg.2
0x2a9b0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::get_Workflow()
0x2a9b5  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowCategory()
0x2a9ba  ldc.i4.2
0x2a9bb  bne.un.s loc_2A9D6
0x2a9bd  ldloc.0
0x2a9be  ldarg.0
0x2a9bf  ldarg.2
0x2a9c0  call     instance string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetVariableBooleanCheck(object key)
0x2a9c5  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>::.ctor(string)
0x2a9ca  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::op_Implicit(!!T0)
0x2a9cf  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Condition(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x2a9d4  br.s     loc_2A9ED
0x2a9d6  ldloc.0
0x2a9d7  ldarg.0
0x2a9d8  ldarg.2
0x2a9d9  call     instance string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetVariable(object key)
0x2a9de  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>::.ctor(string)
0x2a9e3  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::op_Implicit(!!T0)
0x2a9e8  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Condition(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x2a9ed  ldarg.1
0x2a9ee  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x2a9f3  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x2a9f8  ldc.i4.0
0x2a9f9  ble.s    loc_2AA5B
0x2a9fb  newobj   instance void Microsoft.Crm.Workflow.Activities.Composite::.ctor()
0x2aa00  stloc.2
0x2aa01  ldloc.2
0x2aa02  ldarg.1
0x2aa03  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2aa08  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2aa0d  ldarg.0
0x2aa0e  ldloc.2
0x2aa0f  call     instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x2aa14  stloc.3
0x2aa15  ldloc.0
0x2aa16  ldloc.3
0x2aa17  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Then(class [System.Activities]System.Activities.Activity value)
0x2aa1c  ldarg.0
0x2aa1d  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2aa22  stloc.s  4
0x2aa24  ldarg.0
0x2aa25  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2aa2a  stloc.s  5
0x2aa2c  ldarg.0
0x2aa2d  ldloc.2
0x2aa2e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x2aa33  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2aa38  ldarg.0
0x2aa39  ldloc.2
0x2aa3a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.Composite::get_Variables()
0x2aa3f  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2aa44  ldarg.0
0x2aa45  ldarg.1
0x2aa46  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitChildren(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase step)
0x2aa4b  ldarg.0
0x2aa4c  ldloc.s  4
0x2aa4e  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2aa53  ldarg.0
0x2aa54  ldloc.s  5
0x2aa56  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2aa5b  ldarg.0
0x2aa5c  ldloc.0
0x2aa5d  call     instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x2aa62  stloc.1
0x2aa63  ldarg.0
0x2aa64  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2aa69  ldloc.1
0x2aa6a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2aa6f  ret
```
