# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateCondition

- ea: `0x24920`
- end: `0x249fe`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateCondition`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x22ce0`

## callees

- `0x246a0`
- `0x248b0`
- `0x24920`
- `0x24dc0`
- `0x2d900`
- `0x2d920`
- `0x2d940`

## pseudocode

```c

```

## disassembly

```asm
0x24920  ldnull
0x24921  stloc.0
0x24922  ldarg.1
0x24923  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_ConditionOperator()
0x24928  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::get_Expression()
0x2492d  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>
0x24932  ldarg.1
0x24933  callvirt instance class [System.Activities]System.Activities.InArgument`1<object> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_Operand()
0x24938  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<object>::get_Expression()
0x2493d  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>
0x24942  stloc.1
0x24943  ldsfld   string [mscorlib]System.String::Empty
0x24948  stloc.2
0x24949  ldarg.1
0x2494a  callvirt instance class [System.Activities]System.Activities.InArgument`1<object[]> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_Parameters()
0x2494f  brfalse.s loc_24967
0x24951  ldarg.1
0x24952  callvirt instance class [System.Activities]System.Activities.InArgument`1<object[]> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_Parameters()
0x24957  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<object[]>::get_Expression()
0x2495c  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>
0x24961  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>::get_ExpressionText()
0x24966  stloc.2
0x24967  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::get_Value()
0x2496c  stloc.3
0x2496d  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_ConditionOperatorToExpressionMap()
0x24972  ldloc.3
0x24973  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator>::get_Item(void)
0x24978  stloc.s  4
0x2497a  ldloc.1
0x2497b  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>::get_ExpressionText()
0x24980  stloc.s  5
0x24982  ldarg.0
0x24983  ldloc.2
0x24984  ldc.i4.1
0x24985  newarr   [mscorlib]System.String
0x2498a  dup
0x2498b  ldc.i4.0
0x2498c  ldstr    asc_39DD8// ", "
0x24991  stelem.ref
0x24992  call     instance string[] Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::SplitParameters(string parametersFlat, string[] delimiters)
0x24997  stloc.s  6
0x24999  ldloc.s  6
0x2499b  ldlen
0x2499c  brtrue.s loc_249B6
0x2499e  ldarg.0
0x2499f  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x249a4  ldloc.s  4
0x249a6  ldarg.0
0x249a7  ldloc.s  5
0x249a9  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetStepVariable(string variableName)
0x249ae  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.UnaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x249b3  stloc.0
0x249b4  br.s     loc_249FC
0x249b6  ldloc.s  6
0x249b8  ldlen
0x249b9  conv.i4
0x249ba  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x249bf  stloc.s  7
0x249c1  ldc.i4.0
0x249c2  stloc.s  8
0x249c4  br.s     loc_249DC
0x249c6  ldloc.s  7
0x249c8  ldloc.s  8
0x249ca  ldarg.0
0x249cb  ldloc.s  6
0x249cd  ldloc.s  8
0x249cf  ldelem.ref
0x249d0  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetStepVariable(string variableName)
0x249d5  stelem.ref
0x249d6  ldloc.s  8
0x249d8  ldc.i4.1
0x249d9  add
0x249da  stloc.s  8
0x249dc  ldloc.s  8
0x249de  ldloc.s  6
0x249e0  ldlen
0x249e1  conv.i4
0x249e2  blt.s    loc_249C6
0x249e4  ldarg.0
0x249e5  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x249ea  ldloc.s  4
0x249ec  ldarg.0
0x249ed  ldloc.s  5
0x249ef  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetStepVariable(string variableName)
0x249f4  ldloc.s  7
0x249f6  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[])
0x249fb  stloc.0
0x249fc  ldloc.0
0x249fd  ret
```
