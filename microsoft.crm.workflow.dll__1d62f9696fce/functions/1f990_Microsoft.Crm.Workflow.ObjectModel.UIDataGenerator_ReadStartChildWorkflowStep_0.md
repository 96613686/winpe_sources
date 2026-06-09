# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStartChildWorkflowStep_0

- ea: `0x1f990`
- end: `0x1fc05`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStartChildWorkflowStep_0`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1f990`
- `0x223a0`
- `0x22a40`
- `0x22ce0`
- `0x25150`

## pseudocode

```c

```

## disassembly

```asm
0x1f990  ldarg.0
0x1f991  ldarg.1
0x1f992  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1f997  ldc.i4.0
0x1f998  call     T0x2B000021
0x1f99d  dup
0x1f99e  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.StartChildWorkflow::get_EntityId()
0x1f9a3  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::get_Expression()
0x1f9a8  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>
0x1f9ad  stloc.0
0x1f9ae  dup
0x1f9af  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.StartChildWorkflow::get_EntityName()
0x1f9b4  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1f9b9  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1f9be  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1f9c3  stloc.1
0x1f9c4  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.StartChildWorkflow::get_WorkflowId()
0x1f9c9  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::get_Expression()
0x1f9ce  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [mscorlib]System.Guid>
0x1f9d3  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1f9d8  stloc.2
0x1f9d9  ldarg.0
0x1f9da  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f9df  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1f9e4  stloc.3
0x1f9e5  ldloc.2
0x1f9e6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f9eb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f9f0  brfalse.s loc_1FA30
0x1f9f2  ldarg.0
0x1f9f3  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f9f8  ldloc.2
0x1f9f9  box      [mscorlib]System.Guid
0x1f9fe  ldc.i4.s 0xF
0x1fa00  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1fa05  stloc.s  4
0x1fa07  ldarg.0
0x1fa08  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1fa0d  ldloc.s  4
0x1fa0f  ldc.i4.6
0x1fa10  ldarg.0
0x1fa11  ldfld    class Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_uiDataHelper
0x1fa16  ldc.i4.0
0x1fa17  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper::GetObjectName(valuetype Microsoft.Crm.Workflow.ObjectModel.ObjectName objectName)
0x1fa1c  ldsfld   string [mscorlib]System.String::Empty
0x1fa21  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x1fa26  stloc.s  5
0x1fa28  ldloc.3
0x1fa29  ldloc.s  5
0x1fa2b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x1fa30  ldloc.3
0x1fa31  ldarg.0
0x1fa32  ldloc.0
0x1fa33  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>::get_ExpressionText()
0x1fa38  ldloc.1
0x1fa39  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x1fa3e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x1fa43  ldarg.1
0x1fa44  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1fa49  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::GetEnumerator()
0x1fa4e  stloc.s  6
0x1fa50  br       loc_1FBE9
0x1fa55  ldloc.s  6
0x1fa57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Activity>::get_Current()
0x1fa5c  isinst   [System.Activities]System.Activities.Statements.Sequence
0x1fa61  stloc.s  7
0x1fa63  ldloca.s 8
0x1fa65  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x1fa6b  ldloc.s  7
0x1fa6d  brfalse  loc_1FBE9
0x1fa72  ldc.i4.0
0x1fa73  stloc.s  9
0x1fa75  ldarg.0
0x1fa76  ldloc.s  7
0x1fa78  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x1fa7d  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadVariables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> variables)
0x1fa82  ldarg.0
0x1fa83  ldloc.s  7
0x1fa85  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1fa8a  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<object>
0x1fa8f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fa94  ldc.i4.0
0x1fa95  ldloca.s 9
0x1fa97  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x1fa9c  stloc.s  0xA
0x1fa9e  ldloc.s  7
0x1faa0  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1faa5  stloc.s  0xB
0x1faa7  ldsfld   string [mscorlib]System.String::Empty
0x1faac  stloc.s  0xC
0x1faae  ldloc.s  7
0x1fab0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x1fab5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x1faba  stloc.s  0xF
0x1fabc  br.s     loc_1FB1A
0x1fabe  ldloc.s  0xF
0x1fac0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x1fac5  stloc.s  0x10
0x1fac7  ldloc.s  0x10
0x1fac9  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x1face  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TypeNameString
0x1fad3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fad8  brfalse.s loc_1FAEF
0x1fada  ldloc.s  0x10
0x1fadc  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x1fae1  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1fae6  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1faeb  stloc.s  0xC
0x1faed  br.s     loc_1FB1A
0x1faef  ldloc.s  0x10
0x1faf1  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x1faf6  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::IdentifierDefinitionVariableString
0x1fafb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fb00  brfalse.s loc_1FB1A
0x1fb02  ldloc.s  0x10
0x1fb04  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x1fb09  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x1fb0e  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x1fb13  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x1fb18  stloc.s  8
0x1fb1a  ldloc.s  0xF
0x1fb1c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1fb21  brtrue.s loc_1FABE
0x1fb23  leave.s  loc_1FB31
0x1fb25  ldloc.s  0xF
0x1fb27  brfalse.s loc_1FB30
0x1fb29  ldloc.s  0xF
0x1fb2b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fb30  endfinally
0x1fb31  ldloc.s  0xC
0x1fb33  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fb38  brfalse.s loc_1FB5F
0x1fb3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fb3f  ldstr    aTypename0NotFo// "Typename {0} not found in sequence for "...
0x1fb44  ldc.i4.2
0x1fb45  newarr   [mscorlib]System.Object
0x1fb4a  dup
0x1fb4b  ldc.i4.0
0x1fb4c  ldloc.s  0xC
0x1fb4e  stelem.ref
0x1fb4f  dup
0x1fb50  ldc.i4.1
0x1fb51  ldloc.s  0xB
0x1fb53  stelem.ref
0x1fb54  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1fb59  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1fb5e  throw
0x1fb5f  ldloc.s  0xC
0x1fb61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x1fb66  stloc.s  0xD
0x1fb68  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo::.ctor()
0x1fb6d  stloc.s  0xE
0x1fb6f  ldloc.s  0xE
0x1fb71  ldloc.s  0xB
0x1fb73  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Name(string)
0x1fb78  ldloc.s  0xE
0x1fb7a  ldloc.s  0xE
0x1fb7c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Name()
0x1fb81  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DependencyPropertyName(string)
0x1fb86  ldloc.s  0xE
0x1fb88  ldc.i4.1
0x1fb89  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Required(bool)
0x1fb8e  ldloc.s  0xE
0x1fb90  ldloc.s  0xD
0x1fb92  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type)
0x1fb97  ldloca.s 8
0x1fb99  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_HasValue()
0x1fb9e  brfalse.s loc_1FBCC
0x1fba0  ldloc.s  0xE
0x1fba2  ldloca.s 8
0x1fba4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x1fba9  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x1fbae  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_IdentifierDefinition(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>)
0x1fbb3  ldloc.s  0xE
0x1fbb5  ldloca.s 8
0x1fbb7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x1fbbc  stloc.s  0x11
0x1fbbe  ldloca.s 0x11
0x1fbc0  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetWorkflowDataType()
0x1fbc5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1fbca  br.s     loc_1FBDA
0x1fbcc  ldloc.s  0xE
0x1fbce  ldloc.s  0xD
0x1fbd0  call     valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::GetWorkflowAttributeType(class [mscorlib]System.Type)
0x1fbd5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1fbda  ldloc.3
0x1fbdb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::get_Inputs()
0x1fbe0  ldloc.s  0xE
0x1fbe2  ldloc.s  0xA
0x1fbe4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x1fbe9  ldloc.s  6
0x1fbeb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1fbf0  brtrue   loc_1FA55
0x1fbf5  leave.s  loc_1FC03
0x1fbf7  ldloc.s  6
0x1fbf9  brfalse.s loc_1FC02
0x1fbfb  ldloc.s  6
0x1fbfd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fc02  endfinally
0x1fc03  ldloc.3
0x1fc04  ret
```
