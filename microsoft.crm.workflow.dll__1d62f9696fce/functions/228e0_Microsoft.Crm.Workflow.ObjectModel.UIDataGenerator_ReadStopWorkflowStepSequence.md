# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStopWorkflowStepSequence

- ea: `0x228e0`
- end: `0x22a37`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStopWorkflowStepSequence`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1fcc0`
- `0x228e0`
- `0x22ce0`

## pseudocode

```c

```

## disassembly

```asm
0x228e0  ldarg.0
0x228e1  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x228e6  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x228eb  stloc.0
0x228ec  ldarg.0
0x228ed  ldarg.1
0x228ee  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x228f3  ldc.i4.0
0x228f4  call     T0x2B00003E
0x228f9  stloc.1
0x228fa  ldloc.1
0x228fb  brfalse  loc_22A35
0x22900  ldloc.0
0x22901  ldloc.1
0x22902  call     valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStatusValue(class [System.Activities]System.Activities.Statements.TerminateWorkflow terminateActivity)
0x22907  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::set_Status(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus)
0x2290c  ldc.i4.0
0x2290d  stloc.2
0x2290e  ldloc.0
0x2290f  ldarg.0
0x22910  ldarg.1
0x22911  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x22916  ldtoken  [System.Activities]System.Activities.Statements.TerminateWorkflow
0x2291b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22920  ldc.i4.0
0x22921  ldloca.s 2
0x22923  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x22928  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::set_StatusMessage(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x2292d  ldarg.1
0x2292e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x22933  brfalse  loc_22A35
0x22938  ldarg.1
0x22939  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2293e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::get_Count()
0x22943  ldc.i4.0
0x22944  ble      loc_22A35
0x22949  ldc.i4.0
0x2294a  stloc.3
0x2294b  ldc.i4.0
0x2294c  stloc.s  4
0x2294e  ldc.i4.0
0x2294f  stloc.s  5
0x22951  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::.ctor()
0x22956  stloc.s  6
0x22958  ldarg.1
0x22959  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2295e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x22963  stloc.s  7
0x22965  br       loc_22A0A
0x2296a  ldloc.s  7
0x2296c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x22971  stloc.s  8
0x22973  ldloc.s  8
0x22975  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x2297a  stloc.s  9
0x2297c  ldloc.s  9
0x2297e  ldstr    aSteplabellabel// "stepLabelLabelId"
0x22983  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22988  brtrue.s loc_229A8
0x2298a  ldloc.s  9
0x2298c  ldstr    aSteplabeldescr// "stepLabelDescription"
0x22991  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22996  brtrue.s loc_229C4
0x22998  ldloc.s  9
0x2299a  ldstr    aSteplabellangu// "stepLabelLanguageCode"
0x2299f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x229a4  brtrue.s loc_229EF
0x229a6  br.s     loc_22A0A
0x229a8  ldloc.s  6
0x229aa  ldloc.s  8
0x229ac  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x229b1  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x229b6  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x229bb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_LabelId(string)
0x229c0  ldc.i4.1
0x229c1  stloc.3
0x229c2  br.s     loc_22A0A
0x229c4  ldloc.s  6
0x229c6  ldloc.s  8
0x229c8  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x229cd  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x229d2  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x229d7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_Description(string)
0x229dc  ldloc.s  6
0x229de  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_Description()
0x229e3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x229e8  brtrue.s loc_22A0A
0x229ea  ldc.i4.1
0x229eb  stloc.s  4
0x229ed  br.s     loc_22A0A
0x229ef  ldloc.s  6
0x229f1  ldloc.s  8
0x229f3  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x229f8  castclass class [System.Activities]System.Activities.Expressions.Literal`1<int32>
0x229fd  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<int32>::get_Value()
0x22a02  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_LanguageCode(int32)
0x22a07  ldc.i4.1
0x22a08  stloc.s  5
0x22a0a  ldloc.s  7
0x22a0c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22a11  brtrue   loc_2296A
0x22a16  leave.s  loc_22A24
0x22a18  ldloc.s  7
0x22a1a  brfalse.s loc_22A23
0x22a1c  ldloc.s  7
0x22a1e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22a23  endfinally
0x22a24  ldloc.3
0x22a25  ldloc.s  4
0x22a27  and
0x22a28  ldloc.s  5
0x22a2a  and
0x22a2b  brfalse.s loc_22A35
0x22a2d  ldloc.0
0x22a2e  ldloc.s  6
0x22a30  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddLabel(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel)
0x22a35  ldloc.0
0x22a36  ret
```
