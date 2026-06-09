# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStartChildInteractiveWorkflowStep

- ea: `0x1f710`
- end: `0x1f985`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStartChildInteractiveWorkflowStep`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1f710`
- `0x223a0`
- `0x22a40`
- `0x22ce0`
- `0x25150`
- `0x2d000`
- `0x2d020`
- `0x2d040`

## pseudocode

```c

```

## disassembly

```asm
0x1f710  ldarg.0
0x1f711  ldarg.1
0x1f712  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1f717  ldc.i4.0
0x1f718  call     T0x2B000020
0x1f71d  dup
0x1f71e  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.Activities.StartChildInteractiveWorkflow::get_EntityId()
0x1f723  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::get_Expression()
0x1f728  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>
0x1f72d  stloc.0
0x1f72e  dup
0x1f72f  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.StartChildInteractiveWorkflow::get_EntityName()
0x1f734  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1f739  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1f73e  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1f743  stloc.1
0x1f744  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.Activities.StartChildInteractiveWorkflow::get_WorkflowId()
0x1f749  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.Guid>::get_Expression()
0x1f74e  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [mscorlib]System.Guid>
0x1f753  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1f758  stloc.2
0x1f759  ldarg.0
0x1f75a  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f75f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x1f764  stloc.3
0x1f765  ldloc.2
0x1f766  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f76b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f770  brfalse.s loc_1F7B0
0x1f772  ldarg.0
0x1f773  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f778  ldloc.2
0x1f779  box      [mscorlib]System.Guid
0x1f77e  ldc.i4.s 0xF
0x1f780  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1f785  stloc.s  4
0x1f787  ldarg.0
0x1f788  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1f78d  ldloc.s  4
0x1f78f  ldc.i4.6
0x1f790  ldarg.0
0x1f791  ldfld    class Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_uiDataHelper
0x1f796  ldc.i4.0
0x1f797  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper::GetObjectName(valuetype Microsoft.Crm.Workflow.ObjectModel.ObjectName objectName)
0x1f79c  ldsfld   string [mscorlib]System.String::Empty
0x1f7a1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x1f7a6  stloc.s  5
0x1f7a8  ldloc.3
0x1f7a9  ldloc.s  5
0x1f7ab  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::set_ChildWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x1f7b0  ldloc.3
0x1f7b1  ldarg.0
0x1f7b2  ldloc.0
0x1f7b3  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<valuetype [mscorlib]System.Guid>::get_ExpressionText()
0x1f7b8  ldloc.1
0x1f7b9  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity(string entityInfo, string entityName)
0x1f7be  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x1f7c3  ldarg.1
0x1f7c4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1f7c9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::GetEnumerator()
0x1f7ce  stloc.s  6
0x1f7d0  br       loc_1F969
0x1f7d5  ldloc.s  6
0x1f7d7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Activity>::get_Current()
0x1f7dc  isinst   [System.Activities]System.Activities.Statements.Sequence
0x1f7e1  stloc.s  7
0x1f7e3  ldloca.s 8
0x1f7e5  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x1f7eb  ldloc.s  7
0x1f7ed  brfalse  loc_1F969
0x1f7f2  ldc.i4.0
0x1f7f3  stloc.s  9
0x1f7f5  ldarg.0
0x1f7f6  ldloc.s  7
0x1f7f8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x1f7fd  call     instance void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadVariables(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> variables)
0x1f802  ldarg.0
0x1f803  ldloc.s  7
0x1f805  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1f80a  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<object>
0x1f80f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f814  ldc.i4.0
0x1f815  ldloca.s 9
0x1f817  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x1f81c  stloc.s  0xA
0x1f81e  ldloc.s  7
0x1f820  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1f825  stloc.s  0xB
0x1f827  ldsfld   string [mscorlib]System.String::Empty
0x1f82c  stloc.s  0xC
0x1f82e  ldloc.s  7
0x1f830  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x1f835  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x1f83a  stloc.s  0xF
0x1f83c  br.s     loc_1F89A
0x1f83e  ldloc.s  0xF
0x1f840  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x1f845  stloc.s  0x10
0x1f847  ldloc.s  0x10
0x1f849  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x1f84e  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TypeNameString
0x1f853  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f858  brfalse.s loc_1F86F
0x1f85a  ldloc.s  0x10
0x1f85c  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x1f861  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1f866  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1f86b  stloc.s  0xC
0x1f86d  br.s     loc_1F89A
0x1f86f  ldloc.s  0x10
0x1f871  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x1f876  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::IdentifierDefinitionVariableString
0x1f87b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f880  brfalse.s loc_1F89A
0x1f882  ldloc.s  0x10
0x1f884  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x1f889  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x1f88e  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x1f893  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x1f898  stloc.s  8
0x1f89a  ldloc.s  0xF
0x1f89c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f8a1  brtrue.s loc_1F83E
0x1f8a3  leave.s  loc_1F8B1
0x1f8a5  ldloc.s  0xF
0x1f8a7  brfalse.s loc_1F8B0
0x1f8a9  ldloc.s  0xF
0x1f8ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f8b0  endfinally
0x1f8b1  ldloc.s  0xC
0x1f8b3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f8b8  brfalse.s loc_1F8DF
0x1f8ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f8bf  ldstr    aTypename0NotFo// "Typename {0} not found in sequence for "...
0x1f8c4  ldc.i4.2
0x1f8c5  newarr   [mscorlib]System.Object
0x1f8ca  dup
0x1f8cb  ldc.i4.0
0x1f8cc  ldloc.s  0xC
0x1f8ce  stelem.ref
0x1f8cf  dup
0x1f8d0  ldc.i4.1
0x1f8d1  ldloc.s  0xB
0x1f8d3  stelem.ref
0x1f8d4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f8d9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1f8de  throw
0x1f8df  ldloc.s  0xC
0x1f8e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x1f8e6  stloc.s  0xD
0x1f8e8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo::.ctor()
0x1f8ed  stloc.s  0xE
0x1f8ef  ldloc.s  0xE
0x1f8f1  ldloc.s  0xB
0x1f8f3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Name(string)
0x1f8f8  ldloc.s  0xE
0x1f8fa  ldloc.s  0xE
0x1f8fc  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Name()
0x1f901  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DependencyPropertyName(string)
0x1f906  ldloc.s  0xE
0x1f908  ldc.i4.1
0x1f909  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Required(bool)
0x1f90e  ldloc.s  0xE
0x1f910  ldloc.s  0xD
0x1f912  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type)
0x1f917  ldloca.s 8
0x1f919  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_HasValue()
0x1f91e  brfalse.s loc_1F94C
0x1f920  ldloc.s  0xE
0x1f922  ldloca.s 8
0x1f924  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x1f929  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::.ctor(var<u1>)
0x1f92e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_IdentifierDefinition(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>)
0x1f933  ldloc.s  0xE
0x1f935  ldloca.s 8
0x1f937  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x1f93c  stloc.s  0x11
0x1f93e  ldloca.s 0x11
0x1f940  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetWorkflowDataType()
0x1f945  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1f94a  br.s     loc_1F95A
0x1f94c  ldloc.s  0xE
0x1f94e  ldloc.s  0xD
0x1f950  call     valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::GetWorkflowAttributeType(class [mscorlib]System.Type)
0x1f955  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_WorkflowAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x1f95a  ldloc.3
0x1f95b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_Inputs()
0x1f960  ldloc.s  0xE
0x1f962  ldloc.s  0xA
0x1f964  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x1f969  ldloc.s  6
0x1f96b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f970  brtrue   loc_1F7D5
0x1f975  leave.s  loc_1F983
0x1f977  ldloc.s  6
0x1f979  brfalse.s loc_1F982
0x1f97b  ldloc.s  6
0x1f97d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f982  endfinally
0x1f983  ldloc.3
0x1f984  ret
```
