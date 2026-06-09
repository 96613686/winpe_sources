# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::GetSuccessCondition

- ea: `0x19ff0`
- end: `0x1a0b3`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::GetSuccessCondition`
- size: `195`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x195d0`
- `0x19a90`
- `0x19cd0`

## callees

- `0x19ff0`

## pseudocode

```c

```

## disassembly

```asm
0x19ff0  ldarg.1
0x19ff1  ldc.i4.s 0xE
0x19ff3  ldc.i4.1
0x19ff4  newarr   [mscorlib]System.Object
0x19ff9  dup
0x19ffa  ldc.i4.0
0x19ffb  ldstr    aConversionscen// "ConversionScenario"
0x1a000  ldc.i4.5
0x1a001  ldc.i4.1
0x1a002  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x1a007  stelem.ref
0x1a008  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x1a00d  stloc.0
0x1a00e  ldarg.1
0x1a00f  ldc.i4.6
0x1a010  ldloc.0
0x1a011  ldc.i4.1
0x1a012  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x1a017  dup
0x1a018  ldc.i4.0
0x1a019  ldarg.1
0x1a01a  ldarg.3
0x1a01b  box      [mscorlib]System.Int32
0x1a020  ldc.i4.5
0x1a021  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1a026  stelem.ref
0x1a027  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[])
0x1a02c  stloc.1
0x1a02d  ldarg.2
0x1a02e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a033  brtrue.s loc_1A05B
0x1a035  ldarg.0
0x1a036  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::_organizationContext
0x1a03b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a040  ldarg.1
0x1a041  ldarg.2
0x1a042  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::CreateConditionExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x1a047  stloc.2
0x1a048  ldarg.1
0x1a049  ldc.i4.2
0x1a04a  ldloc.2
0x1a04b  ldc.i4.1
0x1a04c  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x1a051  dup
0x1a052  ldc.i4.0
0x1a053  ldloc.1
0x1a054  stelem.ref
0x1a055  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[])
0x1a05a  stloc.1
0x1a05b  ldarg.s  4
0x1a05d  brfalse.s loc_1A0B1
0x1a05f  ldarg.1
0x1a060  ldc.i4.s 0xE
0x1a062  ldc.i4.1
0x1a063  newarr   [mscorlib]System.Object
0x1a068  dup
0x1a069  ldc.i4.0
0x1a06a  ldstr    aAllowprimaryac// "AllowPrimaryActionBlockRecordCreation"
0x1a06f  ldc.i4.5
0x1a070  ldc.i4.1
0x1a071  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x1a076  stelem.ref
0x1a077  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x1a07c  stloc.3
0x1a07d  ldarg.1
0x1a07e  ldc.i4.6
0x1a07f  ldloc.3
0x1a080  ldc.i4.1
0x1a081  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x1a086  dup
0x1a087  ldc.i4.0
0x1a088  ldarg.1
0x1a089  ldc.i4.1
0x1a08a  box      [mscorlib]System.Int32
0x1a08f  ldc.i4.5
0x1a090  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1a095  stelem.ref
0x1a096  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[])
0x1a09b  stloc.s  4
0x1a09d  ldarg.1
0x1a09e  ldc.i4.2
0x1a09f  ldloc.1
0x1a0a0  ldc.i4.1
0x1a0a1  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x1a0a6  dup
0x1a0a7  ldc.i4.0
0x1a0a8  ldloc.s  4
0x1a0aa  stelem.ref
0x1a0ab  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase[])
0x1a0b0  stloc.1
0x1a0b1  ldloc.1
0x1a0b2  ret
```
