# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::UpdateParentActivities

- ea: `0x25dc0`
- end: `0x26058`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::UpdateParentActivities`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x25d60`
- `0x25d90`

## callees

- `0x25dc0`
- `0x2ba20`
- `0x2bd20`

## pseudocode

```c

```

## disassembly

```asm
0x25dc0  ldarg.0
0x25dc1  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x25dc6  stloc.0
0x25dc7  ldarg.0
0x25dc8  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x25dcd  stloc.1
0x25dce  ldarg.0
0x25dcf  ldstr    aNewDictionaryO// "New Dictionary(Of System.String, System"...
0x25dd4  ldnull
0x25dd5  ldnull
0x25dd6  call     T0x2B000045
0x25ddb  stloc.2
0x25ddc  ldarg.1
0x25ddd  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::GetEnumerator()
0x25de2  stloc.3
0x25de3  br       loc_2603A
0x25de8  ldloca.s 3
0x25dea  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Current()
0x25def  stloc.s  4
0x25df1  newobj   instance void [System.Activities]System.Activities.Statements.Sequence::.ctor()
0x25df6  stloc.s  5
0x25df8  ldarg.0
0x25df9  ldloc.s  5
0x25dfb  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x25e00  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x25e05  ldarg.0
0x25e06  ldloc.s  5
0x25e08  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x25e0d  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x25e12  ldarg.0
0x25e13  ldfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentTargetType
0x25e18  stloc.s  6
0x25e1a  ldarg.0
0x25e1b  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::get_AttributeToCrmTypeMapping()
0x25e20  ldloca.s 4
0x25e22  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x25e27  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x25e2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, class [mscorlib]System.Type>::get_Item(void)
0x25e31  stfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentTargetType
0x25e36  ldarg.0
0x25e37  ldarg.0
0x25e38  ldfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentTargetType
0x25e3d  stfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_settingPropertyType
0x25e42  ldloca.s 4
0x25e44  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Value()
0x25e49  ldarg.0
0x25e4a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::Accept(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.IExpressionVisitor)
0x25e4f  ldarg.0
0x25e50  ldnull
0x25e51  stfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_settingPropertyType
0x25e56  ldarg.0
0x25e57  ldloc.s  6
0x25e59  stfld    class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_currentTargetType
0x25e5e  ldarg.0
0x25e5f  ldloca.s 4
0x25e61  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Value()
0x25e66  call     instance string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::GetVariable(object key)
0x25e6b  stloc.s  7
0x25e6d  ldloca.s 4
0x25e6f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x25e74  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Name()
0x25e79  stloc.s  8
0x25e7b  ldloca.s 4
0x25e7d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x25e82  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x25e87  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x25e8c  stloc.s  9
0x25e8e  ldloca.s 4
0x25e90  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x25e95  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_IdentifierDefinition()
0x25e9a  stloc.s  0xB
0x25e9c  ldloca.s 0xB
0x25e9e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_HasValue()
0x25ea3  brfalse  loc_25F94
0x25ea8  newobj   instance void class [System.Activities]System.Activities.Variable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor()
0x25ead  dup
0x25eae  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::IdentifierDefinitionVariableString
0x25eb3  callvirt instance void [System.Activities]System.Activities.Variable::set_Name(string)
0x25eb8  dup
0x25eb9  ldloca.s 4
0x25ebb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x25ec0  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_IdentifierDefinition()
0x25ec5  stloc.s  0xB
0x25ec7  ldloca.s 0xB
0x25ec9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x25ece  call     class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.Activity`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::op_Implicit(!!T0)
0x25ed3  callvirt instance void class [System.Activities]System.Activities.Variable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::set_Default(class [System.Activities]System.Activities.Activity`1<var<u1>>)
0x25ed8  stloc.s  0xC
0x25eda  ldloc.s  5
0x25edc  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x25ee1  ldloc.s  0xC
0x25ee3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::Add(var<u1>)
0x25ee8  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::.ctor()
0x25eed  dup
0x25eee  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::.ctor()
0x25ef3  dup
0x25ef4  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::IdentifierDefinitionVariableString
0x25ef9  ldstr    aValue_1// ".Value"
0x25efe  call     string [mscorlib]System.String::Concat(string, string)
0x25f03  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::set_ExpressionText(string)
0x25f08  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<object>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x25f0d  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x25f12  dup
0x25f13  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>::.ctor()
0x25f18  dup
0x25f19  ldloc.s  7
0x25f1b  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>::set_ExpressionText(string)
0x25f20  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<object>::op_Implicit(!!T0)
0x25f25  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x25f2a  stloc.s  0xD
0x25f2c  ldloc.s  5
0x25f2e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x25f33  ldloc.s  0xD
0x25f35  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x25f3a  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::.ctor()
0x25f3f  dup
0x25f40  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::.ctor()
0x25f45  dup
0x25f46  ldloc.2
0x25f47  ldstr    asc_3C35A// "(\""
0x25f4c  ldloc.s  8
0x25f4e  ldstr    asc_3C360// "\")"
0x25f53  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x25f58  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::set_ExpressionText(string)
0x25f5d  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<object>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x25f62  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x25f67  dup
0x25f68  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>::.ctor()
0x25f6d  dup
0x25f6e  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::IdentifierDefinitionVariableString
0x25f73  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>::set_ExpressionText(string)
0x25f78  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<object>::op_Implicit(!!T0)
0x25f7d  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x25f82  stloc.s  0xE
0x25f84  ldloc.s  5
0x25f86  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x25f8b  ldloc.s  0xE
0x25f8d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x25f92  br.s     loc_25FE9
0x25f94  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::.ctor()
0x25f99  dup
0x25f9a  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::.ctor()
0x25f9f  dup
0x25fa0  ldloc.2
0x25fa1  ldstr    asc_3C35A// "(\""
0x25fa6  ldloc.s  8
0x25fa8  ldstr    asc_3C360// "\")"
0x25fad  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x25fb2  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<object>::set_ExpressionText(string)
0x25fb7  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<object>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x25fbc  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x25fc1  dup
0x25fc2  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>::.ctor()
0x25fc7  dup
0x25fc8  ldloc.s  7
0x25fca  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object>::set_ExpressionText(string)
0x25fcf  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<object>::op_Implicit(!!T0)
0x25fd4  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<object>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x25fd9  stloc.s  0xF
0x25fdb  ldloc.s  5
0x25fdd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x25fe2  ldloc.s  0xF
0x25fe4  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x25fe9  ldloc.s  5
0x25feb  ldloc.s  8
0x25fed  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x25ff2  newobj   instance void class [System.Activities]System.Activities.Variable`1<string>::.ctor()
0x25ff7  dup
0x25ff8  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TypeNameString
0x25ffd  callvirt instance void [System.Activities]System.Activities.Variable::set_Name(string)
0x26002  dup
0x26003  ldloc.s  9
0x26005  call     class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.Activity`1<string>::op_Implicit(!!T0)
0x2600a  callvirt instance void class [System.Activities]System.Activities.Variable`1<string>::set_Default(class [System.Activities]System.Activities.Activity`1<var<u1>>)
0x2600f  stloc.s  0xA
0x26011  ldloc.s  5
0x26013  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x26018  ldloc.s  0xA
0x2601a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::Add(var<u1>)
0x2601f  ldarg.0
0x26020  ldloc.0
0x26021  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x26026  ldarg.0
0x26027  ldloc.1
0x26028  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2602d  ldarg.0
0x2602e  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x26033  ldloc.s  5
0x26035  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2603a  ldloca.s 3
0x2603c  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::MoveNext()
0x26041  brtrue   loc_25DE8
0x26046  leave.s  loc_26056
0x26048  ldloca.s 3
0x2604a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>
0x26050  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26055  endfinally
0x26056  ldloc.2
0x26057  ret
```
