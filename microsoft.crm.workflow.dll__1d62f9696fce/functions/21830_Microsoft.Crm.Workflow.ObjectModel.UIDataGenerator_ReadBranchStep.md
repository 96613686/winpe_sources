# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadBranchStep

- ea: `0x21830`
- end: `0x219b9`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadBranchStep`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x21790`

## callees

- `0x1f130`
- `0x1f2a0`
- `0x21830`
- `0x22ce0`
- `0x22f90`
- `0x2d170`
- `0x2d4e0`
- `0x2d500`
- `0x2d520`
- `0x2d540`

## pseudocode

```c

```

## disassembly

```asm
0x21830  ldnull
0x21831  stloc.0
0x21832  ldarg.0
0x21833  ldarg.2
0x21834  ldtoken  Microsoft.Crm.Workflow.Activities.ConditionBranch
0x21839  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2183e  ldc.i4.0
0x2183f  ldarg.3
0x21840  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x21845  stloc.1
0x21846  ldarg.0
0x21847  ldarg.2
0x21848  ldarg.3
0x21849  ldind.i4
0x2184a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x2184f  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x21854  castclass Microsoft.Crm.Workflow.Activities.ConditionBranch
0x21859  stloc.2
0x2185a  ldloc.2
0x2185b  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x21860  stloc.3
0x21861  ldarg.0
0x21862  ldloc.3
0x21863  call     instance int32 Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::FindStepNumber(string stepId)
0x21868  stloc.s  4
0x2186a  ldloc.s  4
0x2186c  ldarg.0
0x2186d  ldfld    int32 Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_lastStepId
0x21872  ble.s    loc_2187C
0x21874  ldarg.0
0x21875  ldloc.s  4
0x21877  stfld    int32 Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_lastStepId
0x2187c  ldarg.1
0x2187d  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep
0x21882  stloc.s  5
0x21884  ldarg.1
0x21885  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep
0x2188a  stloc.s  6
0x2188c  ldnull
0x2188d  stloc.s  7
0x2188f  ldloc.2
0x21890  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Condition()
0x21895  brfalse.s loc_218A9
0x21897  ldloc.2
0x21898  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Condition()
0x2189d  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x218a2  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x218a7  stloc.s  7
0x218a9  ldloc.1
0x218aa  brtrue.s loc_218F2
0x218ac  ldloc.s  5
0x218ae  brfalse.s loc_218C5
0x218b0  ldloc.s  5
0x218b2  ldarg.0
0x218b3  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x218b8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x218bd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x218c2  stloc.0
0x218c3  br.s     loc_2191D
0x218c5  ldloc.s  7
0x218c7  brfalse.s loc_218DD
0x218c9  ldloc.s  7
0x218cb  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x218d0  brfalse.s loc_218DD
0x218d2  ldloc.s  6
0x218d4  ldnull
0x218d5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x218da  stloc.0
0x218db  br.s     loc_2191D
0x218dd  ldloc.s  6
0x218df  ldarg.0
0x218e0  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x218e5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x218ea  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x218ef  stloc.0
0x218f0  br.s     loc_2191D
0x218f2  ldloc.2
0x218f3  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Else()
0x218f8  brfalse.s loc_21905
0x218fa  ldloc.s  5
0x218fc  ldloc.1
0x218fd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitTimeoutStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x21902  stloc.0
0x21903  br.s     loc_2191D
0x21905  ldloc.s  5
0x21907  brfalse.s loc_21914
0x21909  ldloc.s  5
0x2190b  ldloc.1
0x2190c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x21911  stloc.0
0x21912  br.s     loc_2191D
0x21914  ldloc.s  6
0x21916  ldloc.1
0x21917  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x2191c  stloc.0
0x2191d  ldarg.0
0x2191e  ldloc.2
0x2191f  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Then()
0x21924  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x21929  castclass Microsoft.Crm.Workflow.Activities.Composite
0x2192e  stloc.s  8
0x21930  ldloc.s  8
0x21932  brfalse.s loc_21986
0x21934  ldloc.0
0x21935  ldarg.1
0x21936  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Parent(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2193b  ldloc.s  8
0x2193d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x21942  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::GetEnumerator()
0x21947  stloc.s  9
0x21949  br.s     loc_2196F
0x2194b  ldloc.s  9
0x2194d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Activity>::get_Current()
0x21952  stloc.s  0xA
0x21954  ldloc.s  0xA
0x21956  isinst   [System.Activities]System.Activities.Statements.Persist
0x2195b  brtrue.s loc_2196F
0x2195d  ldarg.0
0x2195e  ldloc.s  0xA
0x21960  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSingleStep(class [System.Activities]System.Activities.Activity activity)
0x21965  stloc.s  0xB
0x21967  ldloc.0
0x21968  ldloc.s  0xB
0x2196a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2196f  ldloc.s  9
0x21971  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21976  brtrue.s loc_2194B
0x21978  leave.s  loc_21986
0x2197a  ldloc.s  9
0x2197c  brfalse.s loc_21985
0x2197e  ldloc.s  9
0x21980  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21985  endfinally
0x21986  ldloc.0
0x21987  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2198c  ldstr    a0// "{0}"
0x21991  ldc.i4.1
0x21992  newarr   [mscorlib]System.Object
0x21997  dup
0x21998  ldc.i4.0
0x21999  ldloc.s  4
0x2199b  box      [mscorlib]System.Int32
0x219a0  stelem.ref
0x219a1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x219a6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::SetNameAndId(string)
0x219ab  ldloc.0
0x219ac  ldloc.2
0x219ad  callvirt instance string Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Description()
0x219b2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x219b7  ldloc.0
0x219b8  ret
```
