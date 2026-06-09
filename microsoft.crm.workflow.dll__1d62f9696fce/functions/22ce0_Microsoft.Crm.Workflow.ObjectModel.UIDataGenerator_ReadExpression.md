# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression

- ea: `0x22ce0`
- end: `0x22f81`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression`
- size: `673`
- prototype: ``
- caller_count: `13`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1f710`
- `0x1f990`
- `0x1ffb0`
- `0x206f0`
- `0x20a40`
- `0x20bc0`
- `0x21830`
- `0x21a20`
- `0x21d50`
- `0x21e60`
- `0x22210`
- `0x228e0`
- `0x22c90`

## callees

- `0x22a40`
- `0x22c50`
- `0x22ce0`
- `0x22f90`
- `0x23d20`
- `0x23fa0`
- `0x24920`
- `0x24a00`
- `0x24c10`
- `0x2d860`
- `0x2d960`
- `0x2da40`
- `0x2db00`

## pseudocode

```c

```

## disassembly

```asm
0x22ce0  ldnull
0x22ce1  stloc.0
0x22ce2  ldnull
0x22ce3  stloc.1
0x22ce4  br       loc_22F71
0x22ce9  ldarg.0
0x22cea  ldarg.1
0x22ceb  ldarg.s  4
0x22ced  ldind.i4
0x22cee  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x22cf3  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x22cf8  stloc.1
0x22cf9  ldloc.1
0x22cfa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22cff  ldarg.2
0x22d00  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22d05  brfalse.s loc_22D09
0x22d07  ldloc.0
0x22d08  ret
0x22d09  ldnull
0x22d0a  stloc.2
0x22d0b  ldnull
0x22d0c  stloc.3
0x22d0d  ldnull
0x22d0e  stloc.s  4
0x22d10  ldnull
0x22d11  stloc.s  5
0x22d13  ldnull
0x22d14  stloc.s  6
0x22d16  ldloc.1
0x22d17  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty
0x22d1c  dup
0x22d1d  stloc.2
0x22d1e  brfalse.s loc_22D52
0x22d20  ldloc.2
0x22d21  callvirt instance class [System.Activities]System.Activities.OutArgument`1<object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::get_Value()
0x22d26  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<object>::get_Expression()
0x22d2b  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>
0x22d30  stloc.s  7
0x22d32  ldarg.0
0x22d33  ldloc.2
0x22d34  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntityAttributeExression(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty activity)
0x22d39  stloc.0
0x22d3a  ldarg.0
0x22d3b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22d40  ldloc.s  7
0x22d42  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::get_ExpressionText()
0x22d47  ldloc.0
0x22d48  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x22d4d  br       loc_22F69
0x22d52  ldloc.1
0x22d53  isinst   Microsoft.Crm.Workflow.Activities.EvaluateExpression
0x22d58  dup
0x22d59  stloc.3
0x22d5a  brfalse  loc_22E1B
0x22d5f  ldloc.3
0x22d60  callvirt instance class [System.Activities]System.Activities.OutArgument`1<object> Microsoft.Crm.Workflow.Activities.EvaluateExpression::get_Result()
0x22d65  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<object>::get_Expression()
0x22d6a  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>
0x22d6f  stloc.s  8
0x22d71  ldnull
0x22d72  stloc.s  9
0x22d74  ldnull
0x22d75  stloc.s  0xA
0x22d77  ldarg.s  4
0x22d79  ldind.i4
0x22d7a  ldc.i4.1
0x22d7b  add
0x22d7c  ldarg.1
0x22d7d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x22d82  bge.s    loc_22DF7
0x22d84  ldarg.1
0x22d85  ldarg.s  4
0x22d87  ldind.i4
0x22d88  ldc.i4.1
0x22d89  add
0x22d8a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x22d8f  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty
0x22d94  stloc.s  0xB
0x22d96  ldloc.s  0xB
0x22d98  brfalse.s loc_22DF7
0x22d9a  ldloc.s  0xB
0x22d9c  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_Attribute()
0x22da1  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x22da6  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x22dab  stloc.s  0xC
0x22dad  ldloc.s  0xB
0x22daf  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_EntityName()
0x22db4  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x22db9  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x22dbe  stloc.s  0xD
0x22dc0  ldloc.s  0xB
0x22dc2  callvirt instance class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetEntityProperty::get_Entity()
0x22dc7  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.InOutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Expression()
0x22dcc  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x22dd1  stloc.s  0xE
0x22dd3  ldarg.0
0x22dd4  ldloc.s  0xE
0x22dd6  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_ExpressionText()
0x22ddb  ldloc.s  0xD
0x22ddd  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x22de2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x22de7  ldloc.s  0xC
0x22de9  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x22dee  stloc.s  9
0x22df0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x22df5  stloc.s  0xA
0x22df7  ldarg.0
0x22df8  ldloc.3
0x22df9  ldloc.s  9
0x22dfb  ldloc.s  0xA
0x22dfd  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateExression(class Microsoft.Crm.Workflow.Activities.EvaluateExpression activity, string attributeName, string targetEntityName)
0x22e02  stloc.0
0x22e03  ldarg.0
0x22e04  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22e09  ldloc.s  8
0x22e0b  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::get_ExpressionText()
0x22e10  ldloc.0
0x22e11  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x22e16  br       loc_22F69
0x22e1b  ldloc.1
0x22e1c  isinst   Microsoft.Crm.Workflow.Activities.EvaluateCondition
0x22e21  dup
0x22e22  stloc.s  4
0x22e24  brfalse.s loc_22E5A
0x22e26  ldloc.s  4
0x22e28  callvirt instance class [System.Activities]System.Activities.OutArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateCondition::get_Result()
0x22e2d  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<bool>::get_Expression()
0x22e32  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<bool>
0x22e37  stloc.s  0xF
0x22e39  ldarg.0
0x22e3a  ldloc.s  4
0x22e3c  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateCondition(class Microsoft.Crm.Workflow.Activities.EvaluateCondition activity)
0x22e41  stloc.0
0x22e42  ldarg.0
0x22e43  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22e48  ldloc.s  0xF
0x22e4a  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<bool>::get_ExpressionText()
0x22e4f  ldloc.0
0x22e50  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x22e55  br       loc_22F69
0x22e5a  ldloc.1
0x22e5b  isinst   Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition
0x22e60  dup
0x22e61  stloc.s  5
0x22e63  brfalse.s loc_22E99
0x22e65  ldloc.s  5
0x22e67  callvirt instance class [System.Activities]System.Activities.OutArgument`1<bool> Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition::get_Result()
0x22e6c  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<bool>::get_Expression()
0x22e71  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<bool>
0x22e76  stloc.s  0x10
0x22e78  ldarg.0
0x22e79  ldloc.s  5
0x22e7b  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateLogicalCondition(class Microsoft.Crm.Workflow.Activities.EvaluateLogicalCondition activity)
0x22e80  stloc.0
0x22e81  ldarg.0
0x22e82  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22e87  ldloc.s  0x10
0x22e89  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<bool>::get_ExpressionText()
0x22e8e  ldloc.0
0x22e8f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x22e94  br       loc_22F69
0x22e99  ldarg.0
0x22e9a  ldloc.1
0x22e9b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22ea0  call     instance bool Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::IsAssignType(class [mscorlib]System.Type type)
0x22ea5  brfalse.s loc_22EC0
0x22ea7  ldarg.0
0x22ea8  ldloc.1
0x22ea9  ldarg.3
0x22eaa  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignActivity(class [System.Activities]System.Activities.Activity activity, bool customActivity)
0x22eaf  stloc.s  0x11
0x22eb1  ldloc.s  0x11
0x22eb3  brfalse  loc_22F69
0x22eb8  ldloc.s  0x11
0x22eba  stloc.0
0x22ebb  br       loc_22F69
0x22ec0  ldloc.1
0x22ec1  isinst   Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes
0x22ec6  dup
0x22ec7  stloc.s  6
0x22ec9  ldnull
0x22eca  cgt.un
0x22ecc  ldarg.3
0x22ecd  and
0x22ece  brfalse.s loc_22F33
0x22ed0  ldloc.s  6
0x22ed2  callvirt instance class [System.Activities]System.Activities.OutArgument`1<object> Microsoft.Crm.Workflow.Activities.ConvertCrmXrmTypes::get_Result()
0x22ed7  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<object>::get_Expression()
0x22edc  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>
0x22ee1  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::get_ExpressionText()
0x22ee6  stloc.s  0x12
0x22ee8  ldloc.s  0x12
0x22eea  ldstr    aConverted// "_converted"
0x22eef  ldc.i4.4
0x22ef0  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x22ef5  stloc.s  0x13
0x22ef7  ldloc.s  0x13
0x22ef9  ldc.i4.m1
0x22efa  beq.s    loc_22F69
0x22efc  ldloc.s  0x12
0x22efe  ldc.i4.0
0x22eff  ldloc.s  0x13
0x22f01  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22f06  stloc.s  0x14
0x22f08  ldarg.0
0x22f09  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22f0e  ldloc.s  0x14
0x22f10  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x22f15  brfalse.s loc_22F69
0x22f17  ldarg.0
0x22f18  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22f1d  ldloc.s  0x12
0x22f1f  ldarg.0
0x22f20  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22f25  ldloc.s  0x14
0x22f27  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x22f2c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x22f31  br.s     loc_22F69
0x22f33  ldloc.1
0x22f34  isinst   [System.Activities]System.Activities.Statements.Persist
0x22f39  brtrue.s loc_22F69
0x22f3b  ldloc.s  6
0x22f3d  brtrue.s loc_22F69
0x22f3f  ldloc.1
0x22f40  isinst   Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity
0x22f45  brfalse.s loc_22F49
0x22f47  ldloc.0
0x22f48  ret
0x22f49  ldarg.3
0x22f4a  brfalse.s loc_22F4E
0x22f4c  ldloc.0
0x22f4d  ret
0x22f4e  ldstr    aUnexpectedActi// "Unexpected activity: "
0x22f53  ldloc.1
0x22f54  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x22f59  call     string [mscorlib]System.String::Concat(string, string)
0x22f5e  ldc.i4   0x80040216
0x22f63  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22f68  throw
0x22f69  ldarg.s  4
0x22f6b  ldarg.s  4
0x22f6d  ldind.i4
0x22f6e  ldc.i4.1
0x22f6f  add
0x22f70  stind.i4
0x22f71  ldarg.s  4
0x22f73  ldind.i4
0x22f74  ldarg.1
0x22f75  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x22f7a  blt      loc_22CE9
0x22f7f  ldloc.0
0x22f80  ret
```
