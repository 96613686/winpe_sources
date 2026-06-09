# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity

- ea: `0x29e50`
- end: `0x2a22a`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity`
- size: `986`
- prototype: ``
- caller_count: `13`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x25860`
- `0x26320`
- `0x27f50`
- `0x280d0`
- `0x28560`
- `0x288d0`
- `0x28a40`
- `0x29210`
- `0x29d50`
- `0x2a950`
- `0x2b4c0`
- `0x2bb10`
- `0x2bbd0`

## callees

- `0x29e50`
- `0x2a230`
- `0x2d4e0`
- `0x2d500`
- `0x2d520`
- `0x2d540`
- `0x2d5f0`
- `0x2d610`
- `0x2d630`
- `0x2d670`
- `0x2d840`
- `0x2d860`
- `0x2d880`
- `0x2d900`
- `0x2d920`
- `0x2d940`
- `0x2d960`
- `0x2d9e0`
- `0x2da00`
- `0x2da20`
- `0x2da40`
- `0x2dac0`
- `0x2dae0`
- `0x2db00`
- `0x2db20`
- `0x2e040`
- `0x2e060`
- `0x2e080`

## pseudocode

```c

```

## disassembly

```asm
0x29e50  ldarg.1
0x29e51  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x29e56  stloc.0
0x29e57  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::.ctor()
0x29e5c  dup
0x29e5d  ldloc.0
0x29e5e  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x29e63  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::set_AssemblyQualifiedName(string)
0x29e68  dup
0x29e69  ldarg.1
0x29e6a  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x29e6f  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x29e74  stloc.1
0x29e75  ldloc.0
0x29e76  ldtoken  Microsoft.Crm.Workflow.Activities.EvaluateExpression
0x29e7b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29e80  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29e85  brfalse.s loc_29EEB
0x29e87  ldarg.1
0x29e88  castclass Microsoft.Crm.Workflow.Activities.EvaluateExpression
0x29e8d  stloc.2
0x29e8e  ldloc.1
0x29e8f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29e94  ldstr    aExpressionoper// "ExpressionOperator"
0x29e99  ldloc.2
0x29e9a  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.EvaluateExpression::get_ExpressionOperator()
0x29e9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29ea4  ldloc.1
0x29ea5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29eaa  ldstr    aParameters_0// "Parameters"
0x29eaf  ldloc.2
0x29eb0  callvirt instance class [System.Activities]System.Activities.InArgument`1<object[]> Microsoft.Crm.Workflow.Activities.EvaluateExpression::get_Parameters()
0x29eb5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29eba  ldloc.1
0x29ebb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29ec0  ldstr    aTargettype// "TargetType"
0x29ec5  ldloc.2
0x29ec6  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type> Microsoft.Crm.Workflow.Activities.EvaluateExpression::get_TargetType()
0x29ecb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29ed0  ldloc.1
0x29ed1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29ed6  ldstr    aResult_0// "Result"
0x29edb  ldloc.2
0x29edc  callvirt instance class [System.Activities]System.Activities.OutArgument`1<object> Microsoft.Crm.Workflow.Activities.EvaluateExpression::get_Result()
0x29ee1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29ee6  br       loc_2A228
0x29eeb  ldloc.0
0x29eec  ldtoken  Microsoft.Crm.Workflow.Activities.EvaluateCondition
0x29ef1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29ef6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29efb  brfalse.s loc_29F61
0x29efd  ldarg.1
0x29efe  castclass Microsoft.Crm.Workflow.Activities.EvaluateCondition
0x29f03  stloc.3
0x29f04  ldloc.1
0x29f05  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29f0a  ldstr    aConditionopera// "ConditionOperator"
0x29f0f  ldloc.3
0x29f10  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_ConditionOperator()
0x29f15  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29f1a  ldloc.1
0x29f1b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29f20  ldstr    aParameters_0// "Parameters"
0x29f25  ldloc.3
0x29f26  callvirt instance class [System.Activities]System.Activities.InArgument`1<object[]> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_Parameters()
0x29f2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29f30  ldloc.1
0x29f31  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29f36  ldstr    aOperand// "Operand"
0x29f3b  ldloc.3
0x29f3c  callvirt instance class [System.Activities]System.Activities.InArgument`1<object> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_Operand()
0x29f41  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29f46  ldloc.1
0x29f47  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29f4c  ldstr    aResult_0// "Result"
0x29f51  ldloc.3
0x29f52  callvirt instance class [System.Activities]System.Activities.OutArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_Result()
0x29f57  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29f5c  br       loc_2A228
0x29f61  ldloc.0
0x29f62  ldtoken  Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition
0x29f67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29f6c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29f71  brfalse.s loc_29FDC
0x29f73  ldarg.1
0x29f74  castclass Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition
0x29f79  stloc.s  4
0x29f7b  ldloc.1
0x29f7c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29f81  ldstr    aLogicaloperato// "LogicalOperator"
0x29f86  ldloc.s  4
0x29f88  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_LogicalOperator()
0x29f8d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29f92  ldloc.1
0x29f93  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29f98  ldstr    aLeftoperand// "LeftOperand"
0x29f9d  ldloc.s  4
0x29f9f  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_LeftOperand()
0x29fa4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29fa9  ldloc.1
0x29faa  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29faf  ldstr    aRightoperand// "RightOperand"
0x29fb4  ldloc.s  4
0x29fb6  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_RightOperand()
0x29fbb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29fc0  ldloc.1
0x29fc1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29fc6  ldstr    aResult_0// "Result"
0x29fcb  ldloc.s  4
0x29fcd  callvirt instance class [System.Activities]System.Activities.OutArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_Result()
0x29fd2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x29fd7  br       loc_2A228
0x29fdc  ldloc.0
0x29fdd  ldtoken  Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes
0x29fe2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29fe7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x29fec  brfalse.s loc_2A040
0x29fee  ldarg.1
0x29fef  castclass Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes
0x29ff4  stloc.s  5
0x29ff6  ldloc.1
0x29ff7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x29ffc  ldstr    aValue_0// "Value"
0x2a001  ldloc.s  5
0x2a003  callvirt instance class [System.Activities]System.Activities.InArgument`1<object> Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::get_Value()
0x2a008  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x2a00d  ldloc.1
0x2a00e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x2a013  ldstr    aTargettype// "TargetType"
0x2a018  ldloc.s  5
0x2a01a  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Type> Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::get_TargetType()
0x2a01f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x2a024  ldloc.1
0x2a025  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x2a02a  ldstr    aResult_0// "Result"
0x2a02f  ldloc.s  5
0x2a031  callvirt instance class [System.Activities]System.Activities.OutArgument`1<object> Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::get_Result()
0x2a036  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x2a03b  br       loc_2A228
0x2a040  ldloc.0
0x2a041  ldtoken  Microsoft.Crm.Workflow.Activities.Composite
0x2a046  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a04b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a050  brtrue.s loc_2A0BE
0x2a052  ldloc.0
0x2a053  ldtoken  Microsoft.Crm.Workflow.Activities.StageComposite
0x2a058  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a05d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a062  brtrue.s loc_2A0BE
0x2a064  ldloc.0
0x2a065  ldtoken  Microsoft.Crm.Workflow.Activities.PageComposite
0x2a06a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a06f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a074  brtrue.s loc_2A0BE
0x2a076  ldloc.0
0x2a077  ldtoken  Microsoft.Crm.Workflow.Activities.StepComposite
0x2a07c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a081  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a086  brtrue.s loc_2A0BE
0x2a088  ldloc.0
0x2a089  ldtoken  Microsoft.Crm.Workflow.Activities.EntityComposite
0x2a08e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a093  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a098  brtrue.s loc_2A0BE
0x2a09a  ldloc.0
0x2a09b  ldtoken  Microsoft.Crm.Workflow.BusinessProcessFlowActivities.StageRelationshipCollectionComposite
0x2a0a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a0a5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a0aa  brtrue.s loc_2A0BE
0x2a0ac  ldloc.0
0x2a0ad  ldtoken  Microsoft.Crm.Workflow.Activities.ActionComposite
0x2a0b2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a0b7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a0bc  brfalse.s loc_2A0D1
0x2a0be  ldarg.0
0x2a0bf  ldarg.1
0x2a0c0  castclass Microsoft.Crm.Workflow.Activities.Composite
0x2a0c5  ldloc.0
0x2a0c6  ldloc.1
0x2a0c7  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivityForComposite(class Microsoft.Crm.Workflow.Activities.Composite composite, class [mscorlib]System.Type compositeType, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference reference)
0x2a0cc  br       loc_2A228
0x2a0d1  ldloc.0
0x2a0d2  ldtoken  Microsoft.Crm.Workflow.Activities.ConditionBranch
0x2a0d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a0dc  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a0e1  brfalse.s loc_2A14C
0x2a0e3  ldarg.1
0x2a0e4  castclass Microsoft.Crm.Workflow.Activities.ConditionBranch
0x2a0e9  stloc.s  6
0x2a0eb  ldloc.1
0x2a0ec  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x2a0f1  ldstr    aCondition// "Condition"
0x2a0f6  ldloc.s  6
0x2a0f8  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Condition()
0x2a0fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x2a102  ldloc.1
0x2a103  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a108  ldstr    aThen// "Then"
0x2a10d  ldloc.s  6
0x2a10f  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Then()
0x2a114  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a119  ldloc.1
0x2a11a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a11f  ldstr    aElse// "Else"
0x2a124  ldloc.s  6
0x2a126  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Else()
0x2a12b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a130  ldloc.1
0x2a131  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a136  ldstr    aDescription_0// "Description"
0x2a13b  ldloc.s  6
0x2a13d  callvirt instance string Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Description()
0x2a142  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a147  br       loc_2A228
0x2a14c  ldloc.0
0x2a14d  ldtoken  Microsoft.Crm.Workflow.Activities.ConditionSequence
0x2a152  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a157  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a15c  brfalse.s loc_2A1C9
0x2a15e  ldarg.1
0x2a15f  castclass Microsoft.Crm.Workflow.Activities.ConditionSequence
0x2a164  stloc.s  7
0x2a166  ldloc.1
0x2a167  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x2a16c  ldstr    aWait// "Wait"
0x2a171  ldloc.s  7
0x2a173  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Wait()
0x2a178  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x2a17d  ldloc.1
0x2a17e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a183  ldstr    aVariables// "Variables"
0x2a188  ldloc.s  7
0x2a18a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Variables()
0x2a18f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a194  ldloc.1
0x2a195  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a19a  ldstr    aActivities// "Activities"
0x2a19f  ldloc.s  7
0x2a1a1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x2a1a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a1ab  ldloc.1
0x2a1ac  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a1b1  ldstr    aContainselsebr// "ContainsElseBranch"
0x2a1b6  ldloc.s  7
0x2a1b8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_ContainsElseBranch()
0x2a1bd  box      valuetype [mscorlib]System.Nullable`1<bool>
0x2a1c2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a1c7  br.s     loc_2A228
0x2a1c9  ldloc.0
0x2a1ca  ldtoken  Microsoft.Crm.Workflow.Activities.InteractionPage
0x2a1cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a1d4  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a1d9  brfalse.s loc_2A228
0x2a1db  ldarg.1
0x2a1dc  castclass Microsoft.Crm.Workflow.Activities.InteractionPage
0x2a1e1  stloc.s  8
0x2a1e3  ldloc.1
0x2a1e4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Arguments()
0x2a1e9  ldstr    aAllowback// "AllowBack"
0x2a1ee  ldloc.s  8
0x2a1f0  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.InteractionPage::get_AllowBack()
0x2a1f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x2a1fa  ldloc.1
0x2a1fb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a200  ldstr    aVariables// "Variables"
0x2a205  ldloc.s  8
0x2a207  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Variables()
0x2a20c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a211  ldloc.1
0x2a212  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x2a217  ldstr    aActivities// "Activities"
0x2a21c  ldloc.s  8
0x2a21e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Activities()
0x2a223  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2a228  ldloc.1
0x2a229  ret
```
