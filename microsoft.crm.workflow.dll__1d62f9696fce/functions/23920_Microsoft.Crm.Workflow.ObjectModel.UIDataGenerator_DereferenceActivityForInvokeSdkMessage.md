# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceActivityForInvokeSdkMessage

- ea: `0x23920`
- end: `0x23d1b`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceActivityForInvokeSdkMessage`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x1f130`

## callees

- `0x23770`
- `0x23920`
- `0x2d4f0`
- `0x2d510`
- `0x2d530`
- `0x2d550`
- `0x2d560`
- `0x2d600`
- `0x2d620`
- `0x2d640`
- `0x2d690`
- `0x2d850`
- `0x2d870`
- `0x2d890`
- `0x2d8e0`
- `0x2d910`
- `0x2d930`
- `0x2d950`
- `0x2d970`
- `0x2d980`
- `0x2d9f0`
- `0x2da10`
- `0x2da30`
- `0x2da50`
- `0x2da60`
- `0x2dad0`
- `0x2daf0`
- `0x2db10`
- `0x2db30`
- `0x2dba0`
- `0x2e050`
- `0x2e070`
- `0x2e090`
- `0x2e0c0`
- `0x2e2e0`
- `0x2e2f0`

## string_xrefs

- `0x23b3e`: `Composite`
- `0x23b50`: `StageComposite`
- `0x23b62`: `StepComposite`
- `0x23b74`: `EntityComposite`

## pseudocode

```c

```

## disassembly

```asm
0x23920  ldarg.1
0x23921  isinst   Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity
0x23926  stloc.0
0x23927  ldnull
0x23928  stloc.1
0x23929  ldloc.0
0x2392a  brfalse  loc_23D19
0x2392f  ldarg.1
0x23930  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23935  ldstr    aEvaluateexpres// "EvaluateExpression"
0x2393a  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2393f  brfalse.s loc_239B8
0x23941  newobj   instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::.ctor()
0x23946  dup
0x23947  ldloc.0
0x23948  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x2394d  ldstr    aExpressionoper// "ExpressionOperator"
0x23952  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23957  isinst   class [System.Activities]System.Activities.InArgument`1<string>
0x2395c  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::set_ExpressionOperator(class [System.Activities]System.Activities.InArgument`1<string> value)
0x23961  dup
0x23962  ldloc.0
0x23963  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23968  ldstr    aParameters_0// "Parameters"
0x2396d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23972  isinst   class [System.Activities]System.Activities.InArgument`1<object[]>
0x23977  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::set_Parameters(class [System.Activities]System.Activities.InArgument`1<object[]> value)
0x2397c  dup
0x2397d  ldloc.0
0x2397e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23983  ldstr    aTargettype// "TargetType"
0x23988  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x2398d  isinst   class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type>
0x23992  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::set_TargetType(class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type> value)
0x23997  dup
0x23998  ldloc.0
0x23999  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x2399e  ldstr    aResult_0// "Result"
0x239a3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x239a8  isinst   class [System.Activities]System.Activities.OutArgument`1<object>
0x239ad  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::set_Result(class [System.Activities]System.Activities.OutArgument`1<object> value)
0x239b2  stloc.1
0x239b3  br       loc_23D0B
0x239b8  ldarg.1
0x239b9  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x239be  ldstr    aEvaluatecondit// "EvaluateCondition"
0x239c3  callvirt instance bool [mscorlib]System.String::Contains(string)
0x239c8  brfalse.s loc_23A41
0x239ca  newobj   instance void Microsoft.Crm.Workflow.Activities.EvaluateCondition::.ctor()
0x239cf  dup
0x239d0  ldloc.0
0x239d1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x239d6  ldstr    aConditionopera// "ConditionOperator"
0x239db  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x239e0  isinst   class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>
0x239e5  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateCondition::set_ConditionOperator(class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator> value)
0x239ea  dup
0x239eb  ldloc.0
0x239ec  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x239f1  ldstr    aParameters_0// "Parameters"
0x239f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x239fb  isinst   class [System.Activities]System.Activities.InArgument`1<object[]>
0x23a00  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateCondition::set_Parameters(class [System.Activities]System.Activities.InArgument`1<object[]> value)
0x23a05  dup
0x23a06  ldloc.0
0x23a07  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23a0c  ldstr    aOperand// "Operand"
0x23a11  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23a16  isinst   class [System.Activities]System.Activities.InArgument`1<object>
0x23a1b  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateCondition::set_Operand(class [System.Activities]System.Activities.InArgument`1<object> value)
0x23a20  dup
0x23a21  ldloc.0
0x23a22  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23a27  ldstr    aResult_0// "Result"
0x23a2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23a31  isinst   class [System.Activities]System.Activities.OutArgument`1<bool>
0x23a36  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateCondition::set_Result(class [System.Activities]System.Activities.OutArgument`1<bool> value)
0x23a3b  stloc.1
0x23a3c  br       loc_23D0B
0x23a41  ldarg.1
0x23a42  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23a47  ldstr    aEvaluatelogica// "EvaluateLogicalCondition"
0x23a4c  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23a51  brfalse.s loc_23ACA
0x23a53  newobj   instance void Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::.ctor()
0x23a58  dup
0x23a59  ldloc.0
0x23a5a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23a5f  ldstr    aLogicaloperato// "LogicalOperator"
0x23a64  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23a69  isinst   class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator>
0x23a6e  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::set_LogicalOperator(class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator> value)
0x23a73  dup
0x23a74  ldloc.0
0x23a75  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23a7a  ldstr    aLeftoperand// "LeftOperand"
0x23a7f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23a84  isinst   class [System.Activities]System.Activities.InArgument`1<bool>
0x23a89  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::set_LeftOperand(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x23a8e  dup
0x23a8f  ldloc.0
0x23a90  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23a95  ldstr    aRightoperand// "RightOperand"
0x23a9a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23a9f  isinst   class [System.Activities]System.Activities.InArgument`1<bool>
0x23aa4  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::set_RightOperand(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x23aa9  dup
0x23aaa  ldloc.0
0x23aab  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23ab0  ldstr    aResult_0// "Result"
0x23ab5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23aba  isinst   class [System.Activities]System.Activities.OutArgument`1<bool>
0x23abf  callvirt instance void Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::set_Result(class [System.Activities]System.Activities.OutArgument`1<bool> value)
0x23ac4  stloc.1
0x23ac5  br       loc_23D0B
0x23aca  ldarg.1
0x23acb  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23ad0  ldstr    aConvertcrmxrmt// "ConvertCrmXrmTypes"
0x23ad5  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23ada  brfalse.s loc_23B38
0x23adc  newobj   instance void Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::.ctor()
0x23ae1  dup
0x23ae2  ldloc.0
0x23ae3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23ae8  ldstr    aValue_0// "Value"
0x23aed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23af2  isinst   class [System.Activities]System.Activities.InArgument`1<object>
0x23af7  callvirt instance void Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::set_Value(class [System.Activities]System.Activities.InArgument`1<object> value)
0x23afc  dup
0x23afd  ldloc.0
0x23afe  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23b03  ldstr    aTargettype// "TargetType"
0x23b08  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23b0d  isinst   class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type>
0x23b12  callvirt instance void Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::set_TargetType(class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type> value)
0x23b17  dup
0x23b18  ldloc.0
0x23b19  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23b1e  ldstr    aResult_0// "Result"
0x23b23  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23b28  isinst   class [System.Activities]System.Activities.OutArgument`1<object>
0x23b2d  callvirt instance void Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::set_Result(class [System.Activities]System.Activities.OutArgument`1<object> value)
0x23b32  stloc.1
0x23b33  br       loc_23D0B
0x23b38  ldarg.1
0x23b39  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23b3e  ldstr    aComposite// "Composite"
0x23b43  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23b48  brtrue.s loc_23B80
0x23b4a  ldarg.1
0x23b4b  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23b50  ldstr    aStagecomposite// "StageComposite"
0x23b55  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23b5a  brtrue.s loc_23B80
0x23b5c  ldarg.1
0x23b5d  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23b62  ldstr    aStepcomposite// "StepComposite"
0x23b67  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23b6c  brtrue.s loc_23B80
0x23b6e  ldarg.1
0x23b6f  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23b74  ldstr    aEntitycomposit// "EntityComposite"
0x23b79  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23b7e  brfalse.s loc_23B8D
0x23b80  ldarg.0
0x23b81  ldloc.0
0x23b82  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceCompositeActivityForInvokeSdkMessage(class Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity reference)
0x23b87  stloc.1
0x23b88  br       loc_23D0B
0x23b8d  ldarg.1
0x23b8e  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23b93  ldstr    aConditionbranc_0// "ConditionBranch"
0x23b98  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23b9d  brfalse  loc_23C33
0x23ba2  newobj   instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::.ctor()
0x23ba7  dup
0x23ba8  ldloc.0
0x23ba9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23bae  ldstr    aCondition// "Condition"
0x23bb3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23bb8  isinst   class [System.Activities]System.Activities.InArgument`1<bool>
0x23bbd  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Condition(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x23bc2  dup
0x23bc3  ldloc.0
0x23bc4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23bc9  ldstr    aThen// "Then"
0x23bce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23bd3  isinst   [System.Activities]System.Activities.Activity
0x23bd8  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Then(class [System.Activities]System.Activities.Activity value)
0x23bdd  dup
0x23bde  ldloc.0
0x23bdf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23be4  ldstr    aElse// "Else"
0x23be9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23bee  isinst   [System.Activities]System.Activities.Activity
0x23bf3  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Else(class [System.Activities]System.Activities.Activity value)
0x23bf8  stloc.1
0x23bf9  ldloc.0
0x23bfa  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23bff  ldstr    aDescription_0// "Description"
0x23c04  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x23c09  brfalse  loc_23D0B
0x23c0e  ldloc.1
0x23c0f  isinst   Microsoft.Crm.Workflow.Activities.ConditionBranch
0x23c14  ldloc.0
0x23c15  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23c1a  ldstr    aDescription_0// "Description"
0x23c1f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23c24  isinst   [mscorlib]System.String
0x23c29  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionBranch::set_Description(string value)
0x23c2e  br       loc_23D0B
0x23c33  ldarg.1
0x23c34  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23c39  ldstr    aConditionseque// "ConditionSequence"
0x23c3e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23c43  brfalse.s loc_23C9E
0x23c45  newobj   instance void Microsoft.Crm.Workflow.Activities.ConditionSequence::.ctor()
0x23c4a  dup
0x23c4b  ldloc.0
0x23c4c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23c51  ldstr    aWait// "Wait"
0x23c56  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23c5b  isinst   class [System.Activities]System.Activities.InArgument`1<bool>
0x23c60  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionSequence::set_Wait(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x23c65  dup
0x23c66  ldloc.0
0x23c67  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23c6c  ldstr    aVariables// "Variables"
0x23c71  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23c76  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>
0x23c7b  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionSequence::set_Variables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> value)
0x23c80  dup
0x23c81  ldloc.0
0x23c82  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23c87  ldstr    aActivities// "Activities"
0x23c8c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23c91  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>
0x23c96  callvirt instance void Microsoft.Crm.Workflow.Activities.ConditionSequence::set_Activities(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> value)
0x23c9b  stloc.1
0x23c9c  br.s     loc_23D0B
0x23c9e  ldarg.1
0x23c9f  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23ca4  ldstr    aInteractionpag_2// "InteractionPage"
0x23ca9  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23cae  brfalse.s loc_23D09
0x23cb0  newobj   instance void Microsoft.Crm.Workflow.Activities.InteractionPage::.ctor()
0x23cb5  dup
0x23cb6  ldloc.0
0x23cb7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x23cbc  ldstr    aAllowback// "AllowBack"
0x23cc1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x23cc6  isinst   class [System.Activities]System.Activities.InArgument`1<bool>
0x23ccb  callvirt instance void Microsoft.Crm.Workflow.Activities.InteractionPage::set_AllowBack(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x23cd0  dup
0x23cd1  ldloc.0
0x23cd2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23cd7  ldstr    aVariables// "Variables"
0x23cdc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23ce1  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>
0x23ce6  callvirt instance void Microsoft.Crm.Workflow.Activities.InteractionPage::set_Variables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> value)
0x23ceb  dup
0x23cec  ldloc.0
0x23ced  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x23cf2  ldstr    aActivities// "Activities"
0x23cf7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23cfc  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>
0x23d01  callvirt instance void Microsoft.Crm.Workflow.Activities.InteractionPage::set_Activities(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> value)
0x23d06  stloc.1
0x23d07  br.s     loc_23D0B
0x23d09  ldarg.1
0x23d0a  stloc.1
0x23d0b  ldloc.1
0x23d0c  ldarg.1
0x23d0d  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x23d12  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x23d17  ldloc.1
0x23d18  ret
0x23d19  ldarg.1
0x23d1a  ret
```
