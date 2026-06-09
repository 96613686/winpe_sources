# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateLogicalCondition

- ea: `0x24a00`
- end: `0x24ad4`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateLogicalCondition`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x22ce0`

## callees

- `0x246a0`
- `0x248b0`
- `0x24a00`
- `0x24de0`
- `0x2d9e0`
- `0x2da00`
- `0x2da20`

## pseudocode

```c

```

## disassembly

```asm
0x24a00  ldnull
0x24a01  stloc.0
0x24a02  ldarg.1
0x24a03  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_LogicalOperator()
0x24a08  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator>::get_Expression()
0x24a0d  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator>
0x24a12  ldarg.1
0x24a13  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_LeftOperand()
0x24a18  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x24a1d  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>
0x24a22  stloc.1
0x24a23  ldarg.1
0x24a24  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_RightOperand()
0x24a29  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x24a2e  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>
0x24a33  stloc.2
0x24a34  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator>::get_Value()
0x24a39  stloc.3
0x24a3a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_LogicalOperatorToExpressionMap()
0x24a3f  ldloc.3
0x24a40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator>::get_Item(void)
0x24a45  stloc.s  4
0x24a47  ldloc.1
0x24a48  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>::get_ExpressionText()
0x24a4d  stloc.s  5
0x24a4f  ldloc.2
0x24a50  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>::get_ExpressionText()
0x24a55  stloc.s  6
0x24a57  ldarg.0
0x24a58  ldloc.s  6
0x24a5a  ldc.i4.1
0x24a5b  newarr   [mscorlib]System.String
0x24a60  dup
0x24a61  ldc.i4.0
0x24a62  ldstr    asc_39DD8// ", "
0x24a67  stelem.ref
0x24a68  call     instance string[] Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::SplitParameters(string parametersFlat, string[] delimiters)
0x24a6d  stloc.s  7
0x24a6f  ldloc.s  7
0x24a71  ldlen
0x24a72  brtrue.s loc_24A8C
0x24a74  ldarg.0
0x24a75  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24a7a  ldloc.s  4
0x24a7c  ldarg.0
0x24a7d  ldloc.s  5
0x24a7f  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetStepVariable(string variableName)
0x24a84  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.UnaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x24a89  stloc.0
0x24a8a  br.s     loc_24AD2
0x24a8c  ldloc.s  7
0x24a8e  ldlen
0x24a8f  conv.i4
0x24a90  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x24a95  stloc.s  8
0x24a97  ldc.i4.0
0x24a98  stloc.s  9
0x24a9a  br.s     loc_24AB2
0x24a9c  ldloc.s  8
0x24a9e  ldloc.s  9
0x24aa0  ldarg.0
0x24aa1  ldloc.s  7
0x24aa3  ldloc.s  9
0x24aa5  ldelem.ref
0x24aa6  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetStepVariable(string variableName)
0x24aab  stelem.ref
0x24aac  ldloc.s  9
0x24aae  ldc.i4.1
0x24aaf  add
0x24ab0  stloc.s  9
0x24ab2  ldloc.s  9
0x24ab4  ldloc.s  7
0x24ab6  ldlen
0x24ab7  conv.i4
0x24ab8  blt.s    loc_24A9C
0x24aba  ldarg.0
0x24abb  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24ac0  ldloc.s  4
0x24ac2  ldarg.0
0x24ac3  ldloc.s  5
0x24ac5  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetStepVariable(string variableName)
0x24aca  ldloc.s  8
0x24acc  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[])
0x24ad1  stloc.0
0x24ad2  ldloc.0
0x24ad3  ret
```
