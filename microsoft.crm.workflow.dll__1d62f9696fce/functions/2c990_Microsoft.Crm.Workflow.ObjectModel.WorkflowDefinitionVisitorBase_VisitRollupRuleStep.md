# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitRollupRuleStep

- ea: `0x2c990`
- end: `0x2cbf7`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitRollupRuleStep`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1a8c0`
- `0x1a8e0`
- `0x1a910`
- `0x2ab00`
- `0x2c990`

## string_xrefs

- `0x2cb04`: `TargetLinked`

## pseudocode

```c

```

## disassembly

```asm
0x2c990  ldarg.0
0x2c991  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2c996  stloc.0
0x2c997  ldarg.0
0x2c998  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2c99d  stloc.1
0x2c99e  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x2c9a3  stloc.2
0x2c9a4  ldloc.2
0x2c9a5  ldarg.1
0x2c9a6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2c9ab  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2c9b0  ldarg.1
0x2c9b1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2c9b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c9bb  brtrue.s loc_2C9D9
0x2c9bd  ldloc.2
0x2c9be  dup
0x2c9bf  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x2c9c4  ldstr    asc_3C24E// ": "
0x2c9c9  ldarg.1
0x2c9ca  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2c9cf  call     string [mscorlib]System.String::Concat(string, string, string)
0x2c9d4  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2c9d9  ldarg.0
0x2c9da  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2c9df  ldloc.2
0x2c9e0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2c9e5  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x2c9ea  stloc.3
0x2c9eb  ldloc.3
0x2c9ec  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2c9f1  ldstr    aHierarchicalre// "HierarchicalRelationshipName"
0x2c9f6  ldarg.1
0x2c9f7  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_HierarchicalRelationshipName()
0x2c9fc  newobj   instance void class [System.Activities]System.Activities.Variable`1<string>::.ctor(string, var<u1>)
0x2ca01  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::Add(var<u1>)
0x2ca06  ldloc.3
0x2ca07  ldstr    aSource// "Source"
0x2ca0c  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2ca11  ldarg.0
0x2ca12  ldloc.3
0x2ca13  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2ca18  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2ca1d  ldarg.0
0x2ca1e  ldloc.3
0x2ca1f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2ca24  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2ca29  ldarg.1
0x2ca2a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_SourceFilter()
0x2ca2f  brfalse.s loc_2CA3D
0x2ca31  ldarg.1
0x2ca32  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_SourceFilter()
0x2ca37  ldarg.0
0x2ca38  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x2ca3d  ldloc.2
0x2ca3e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2ca43  ldloc.3
0x2ca44  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2ca49  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x2ca4e  stloc.s  4
0x2ca50  ldloc.s  4
0x2ca52  ldstr    aTarget// "Target"
0x2ca57  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2ca5c  ldarg.0
0x2ca5d  ldloc.s  4
0x2ca5f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2ca64  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2ca69  ldarg.0
0x2ca6a  ldloc.s  4
0x2ca6c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2ca71  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2ca76  ldarg.1
0x2ca77  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationship()
0x2ca7c  brfalse.s loc_2CAE3
0x2ca7e  newobj   instance void Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::.ctor()
0x2ca83  stloc.s  6
0x2ca85  ldloc.s  6
0x2ca87  ldarg.0
0x2ca88  ldarg.1
0x2ca89  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationship()
0x2ca8e  ldc.i4.1
0x2ca8f  call     instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetEntityAsInOutArgument(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase entity, bool temporaryEntity)
0x2ca94  callvirt instance void Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::set_Entity(class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> value)
0x2ca99  ldloc.s  6
0x2ca9b  ldarg.1
0x2ca9c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationship()
0x2caa1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_UIXmlName()
0x2caa6  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2caab  ldloc.s  6
0x2caad  ldarg.1
0x2caae  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationship()
0x2cab3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x2cab8  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2cabd  callvirt instance void Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::set_EntityName(class [System.Activities]System.Activities.InArgument`1<string> value)
0x2cac2  ldarg.0
0x2cac3  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2cac8  ldloc.s  6
0x2caca  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2cacf  ldarg.1
0x2cad0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetFilter()
0x2cad5  brfalse.s loc_2CAE3
0x2cad7  ldarg.1
0x2cad8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetFilter()
0x2cadd  ldarg.0
0x2cade  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x2cae3  ldloc.2
0x2cae4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2cae9  ldloc.s  4
0x2caeb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2caf0  ldarg.1
0x2caf1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationshipLinked()
0x2caf6  brfalse  loc_2CB9A
0x2cafb  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x2cb00  stloc.s  7
0x2cb02  ldloc.s  7
0x2cb04  ldstr    aTargetlinked// "TargetLinked"
0x2cb09  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2cb0e  ldarg.0
0x2cb0f  ldloc.s  7
0x2cb11  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2cb16  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2cb1b  ldarg.0
0x2cb1c  ldloc.s  7
0x2cb1e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2cb23  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2cb28  newobj   instance void Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::.ctor()
0x2cb2d  stloc.s  8
0x2cb2f  ldloc.s  8
0x2cb31  ldarg.0
0x2cb32  ldarg.1
0x2cb33  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationshipLinked()
0x2cb38  ldc.i4.1
0x2cb39  call     instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetEntityAsInOutArgument(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase entity, bool temporaryEntity)
0x2cb3e  callvirt instance void Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::set_Entity(class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> value)
0x2cb43  ldloc.s  8
0x2cb45  ldarg.1
0x2cb46  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationshipLinked()
0x2cb4b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_UIXmlName()
0x2cb50  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2cb55  ldloc.s  8
0x2cb57  ldarg.1
0x2cb58  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetRelationshipLinked()
0x2cb5d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x2cb62  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::op_Implicit(!!T0)
0x2cb67  callvirt instance void Microsoft.Crm.Workflow.ClientActivities.SetAttributeValue::set_EntityName(class [System.Activities]System.Activities.InArgument`1<string> value)
0x2cb6c  ldarg.0
0x2cb6d  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2cb72  ldloc.s  8
0x2cb74  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2cb79  ldarg.1
0x2cb7a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetLinkedFilter()
0x2cb7f  brfalse.s loc_2CB8D
0x2cb81  ldarg.1
0x2cb82  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_TargetLinkedFilter()
0x2cb87  ldarg.0
0x2cb88  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x2cb8d  ldloc.2
0x2cb8e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2cb93  ldloc.s  7
0x2cb95  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2cb9a  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x2cb9f  stloc.s  5
0x2cba1  ldloc.s  5
0x2cba3  ldstr    aAggregate// "Aggregate"
0x2cba8  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2cbad  ldarg.0
0x2cbae  ldloc.s  5
0x2cbb0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2cbb5  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2cbba  ldarg.0
0x2cbbb  ldloc.s  5
0x2cbbd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2cbc2  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2cbc7  ldarg.1
0x2cbc8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_Aggregate()
0x2cbcd  brfalse.s loc_2CBDB
0x2cbcf  ldarg.1
0x2cbd0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::get_Aggregate()
0x2cbd5  ldarg.0
0x2cbd6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x2cbdb  ldloc.2
0x2cbdc  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x2cbe1  ldloc.s  5
0x2cbe3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2cbe8  ldarg.0
0x2cbe9  ldloc.0
0x2cbea  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2cbef  ldarg.0
0x2cbf0  ldloc.1
0x2cbf1  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2cbf6  ret
```
