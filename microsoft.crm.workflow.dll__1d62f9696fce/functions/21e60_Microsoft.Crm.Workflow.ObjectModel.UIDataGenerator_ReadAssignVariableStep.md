# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignVariableStep

- ea: `0x21e60`
- end: `0x2220a`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignVariableStep`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x21e30`
- `0x21e60`
- `0x22ce0`
- `0x2cd80`
- `0x2cda0`

## pseudocode

```c

```

## disassembly

```asm
0x21e60  ldc.i4.0
0x21e61  stloc.0
0x21e62  ldarg.0
0x21e63  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21e68  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x21e6d  stloc.1
0x21e6e  ldarg.0
0x21e6f  ldarg.1
0x21e70  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21e75  ldc.i4.0
0x21e76  call     T0x2B000034
0x21e7b  stloc.2
0x21e7c  ldloc.2
0x21e7d  brfalse.s loc_21EBD
0x21e7f  ldloc.2
0x21e80  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.AssignVariable::get_Direction()
0x21e85  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>::get_Expression()
0x21e8a  castclass class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>
0x21e8f  stloc.s  0xB
0x21e91  ldloc.2
0x21e92  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.BusinessProcessFlowActivities.AssignVariable::get_ReadOnly()
0x21e97  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x21e9c  castclass class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x21ea1  stloc.s  0xC
0x21ea3  ldloc.1
0x21ea4  ldloc.s  0xB
0x21ea6  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection>::get_Value()
0x21eab  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_Direction(valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection)
0x21eb0  ldloc.1
0x21eb1  ldloc.s  0xC
0x21eb3  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x21eb8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ReadOnly(bool)
0x21ebd  ldtoken  [mscorlib]System.String
0x21ec2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21ec7  stloc.s  9
0x21ec9  ldc.i4.0
0x21eca  stloc.s  0xA
0x21ecc  ldarg.0
0x21ecd  ldarg.1
0x21ece  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21ed3  ldc.i4.0
0x21ed4  call     T0x2B000035
0x21ed9  dup
0x21eda  stloc.3
0x21edb  brfalse.s loc_21F0C
0x21edd  ldloc.1
0x21ede  ldloc.3
0x21edf  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<string>::get_To()
0x21ee4  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<string>::get_Expression()
0x21ee9  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<string>
0x21eee  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<string>::get_ExpressionText()
0x21ef3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x21ef8  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<string>
0x21efd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21f02  stloc.s  9
0x21f04  ldc.i4.1
0x21f05  stloc.s  0xA
0x21f07  br       loc_22138
0x21f0c  ldarg.0
0x21f0d  ldarg.1
0x21f0e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21f13  ldc.i4.0
0x21f14  call     T0x2B000036
0x21f19  dup
0x21f1a  stloc.s  4
0x21f1c  brfalse.s loc_21F4E
0x21f1e  ldloc.1
0x21f1f  ldloc.s  4
0x21f21  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<int32>::get_To()
0x21f26  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<int32>::get_Expression()
0x21f2b  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<int32>
0x21f30  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<int32>::get_ExpressionText()
0x21f35  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x21f3a  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<int32>
0x21f3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21f44  stloc.s  9
0x21f46  ldc.i4.1
0x21f47  stloc.s  0xA
0x21f49  br       loc_22138
0x21f4e  ldarg.0
0x21f4f  ldarg.1
0x21f50  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21f55  ldc.i4.0
0x21f56  call     T0x2B000037
0x21f5b  dup
0x21f5c  stloc.s  5
0x21f5e  brfalse.s loc_21F90
0x21f60  ldloc.1
0x21f61  ldloc.s  5
0x21f63  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<float64>::get_To()
0x21f68  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<float64>::get_Expression()
0x21f6d  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<float64>
0x21f72  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<float64>::get_ExpressionText()
0x21f77  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x21f7c  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<float64>
0x21f81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21f86  stloc.s  9
0x21f88  ldc.i4.1
0x21f89  stloc.s  0xA
0x21f8b  br       loc_22138
0x21f90  ldarg.0
0x21f91  ldarg.1
0x21f92  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21f97  ldc.i4.0
0x21f98  call     T0x2B000038
0x21f9d  dup
0x21f9e  stloc.s  6
0x21fa0  brfalse.s loc_21FD8
0x21fa2  ldloc.1
0x21fa3  ldarg.0
0x21fa4  ldloc.s  6
0x21fa6  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_To()
0x21fab  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Expression()
0x21fb0  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>
0x21fb5  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_ExpressionText()
0x21fba  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetIdentifierNameFromAssignExpression(string expressionText)
0x21fbf  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x21fc4  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>
0x21fc9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21fce  stloc.s  9
0x21fd0  ldc.i4.1
0x21fd1  stloc.s  0xA
0x21fd3  br       loc_22138
0x21fd8  ldarg.0
0x21fd9  ldarg.1
0x21fda  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x21fdf  ldc.i4.0
0x21fe0  call     T0x2B000039
0x21fe5  dup
0x21fe6  stloc.s  8
0x21fe8  brfalse.s loc_22035
0x21fea  ldloc.s  8
0x21fec  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.Statements.If::get_Else()
0x21ff1  isinst   class [System.Activities]System.Activities.Statements.Assign`1<valuetype [mscorlib]System.DateTime>
0x21ff6  stloc.s  7
0x21ff8  ldloc.s  7
0x21ffa  brfalse  loc_22138
0x21fff  ldloc.1
0x22000  ldarg.0
0x22001  ldloc.s  7
0x22003  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<valuetype [mscorlib]System.DateTime>::get_To()
0x22008  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<valuetype [mscorlib]System.DateTime>::get_Expression()
0x2200d  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<valuetype [mscorlib]System.DateTime>
0x22012  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<valuetype [mscorlib]System.DateTime>::get_ExpressionText()
0x22017  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetIdentifierNameFromAssignExpression(string expressionText)
0x2201c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x22021  ldtoken  [System.Activities]System.Activities.Statements.If
0x22026  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2202b  stloc.s  9
0x2202d  ldc.i4.1
0x2202e  stloc.s  0xA
0x22030  br       loc_22138
0x22035  ldloc.2
0x22036  brfalse  loc_22138
0x2203b  ldarg.0
0x2203c  ldarg.1
0x2203d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x22042  ldc.i4.0
0x22043  call     T0x2B00003A
0x22048  dup
0x22049  stloc.s  0xD
0x2204b  brfalse.s loc_2207D
0x2204d  ldloc.1
0x2204e  ldloc.s  0xD
0x22050  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<bool>::get_To()
0x22055  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<bool>::get_Expression()
0x2205a  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<bool>
0x2205f  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<bool>::get_ExpressionText()
0x22064  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x22069  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<bool>
0x2206e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22073  stloc.s  9
0x22075  ldc.i4.1
0x22076  stloc.s  0xA
0x22078  br       loc_22138
0x2207d  ldarg.0
0x2207e  ldarg.1
0x2207f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x22084  ldc.i4.0
0x22085  call     T0x2B00003B
0x2208a  dup
0x2208b  stloc.s  0xE
0x2208d  brfalse.s loc_220BC
0x2208f  ldloc.1
0x22090  ldloc.s  0xE
0x22092  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<valuetype [mscorlib]System.Decimal>::get_To()
0x22097  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<valuetype [mscorlib]System.Decimal>::get_Expression()
0x2209c  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<valuetype [mscorlib]System.Decimal>
0x220a1  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<valuetype [mscorlib]System.Decimal>::get_ExpressionText()
0x220a6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x220ab  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<valuetype [mscorlib]System.Decimal>
0x220b0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x220b5  stloc.s  9
0x220b7  ldc.i4.1
0x220b8  stloc.s  0xA
0x220ba  br.s     loc_22138
0x220bc  ldarg.0
0x220bd  ldarg.1
0x220be  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x220c3  ldc.i4.0
0x220c4  call     T0x2B00003C
0x220c9  dup
0x220ca  stloc.s  0xF
0x220cc  brfalse.s loc_220FB
0x220ce  ldloc.1
0x220cf  ldloc.s  0xF
0x220d1  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money>::get_To()
0x220d6  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money>::get_Expression()
0x220db  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money>
0x220e0  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money>::get_ExpressionText()
0x220e5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x220ea  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money>
0x220ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x220f4  stloc.s  9
0x220f6  ldc.i4.1
0x220f7  stloc.s  0xA
0x220f9  br.s     loc_22138
0x220fb  ldarg.0
0x220fc  ldarg.1
0x220fd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x22102  ldc.i4.0
0x22103  call     T0x2B00003D
0x22108  dup
0x22109  stloc.s  0x10
0x2210b  brfalse.s loc_22138
0x2210d  ldloc.1
0x2210e  ldloc.s  0x10
0x22110  callvirt instance class [System.Activities]System.Activities.OutArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue>::get_To()
0x22115  callvirt instance class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>> class [System.Activities]System.Activities.OutArgument`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue>::get_Expression()
0x2211a  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue>
0x2211f  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue>::get_ExpressionText()
0x22124  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x22129  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue>
0x2212e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22133  stloc.s  9
0x22135  ldc.i4.1
0x22136  stloc.s  0xA
0x22138  ldloc.s  0xA
0x2213a  brfalse  loc_22208
0x2213f  ldsfld   string [mscorlib]System.String::Empty
0x22144  stloc.s  0x11
0x22146  ldarg.1
0x22147  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2214c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x22151  stloc.s  0x13
0x22153  br.s     loc_22184
0x22155  ldloc.s  0x13
0x22157  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x2215c  stloc.s  0x14
0x2215e  ldloc.s  0x14
0x22160  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x22165  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TypeNameString
0x2216a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2216f  brfalse.s loc_22184
0x22171  ldloc.s  0x14
0x22173  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x22178  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2217d  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x22182  stloc.s  0x11
0x22184  ldloc.s  0x13
0x22186  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2218b  brtrue.s loc_22155
0x2218d  leave.s  loc_2219B
0x2218f  ldloc.s  0x13
0x22191  brfalse.s loc_2219A
0x22193  ldloc.s  0x13
0x22195  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2219a  endfinally
0x2219b  ldloc.s  0x11
0x2219d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x221a2  brfalse.s loc_221C4
0x221a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x221a9  ldstr    aTypename0NotFo_0// "Typename {0} not found in sequence for "...
0x221ae  ldc.i4.1
0x221af  newarr   [mscorlib]System.Object
0x221b4  dup
0x221b5  ldc.i4.0
0x221b6  ldloc.s  0x11
0x221b8  stelem.ref
0x221b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x221be  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x221c3  throw
0x221c4  ldloc.s  0x11
0x221c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x221cb  stloc.s  0x12
0x221cd  ldloc.1
0x221ce  ldloc.s  0x12
0x221d0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_DataType(class [mscorlib]System.Type)
0x221d5  ldloc.1
0x221d6  ldarg.0
0x221d7  ldarg.1
0x221d8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x221dd  ldloc.s  9
0x221df  ldc.i4.0
0x221e0  ldloca.s 0
0x221e2  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x221e7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x221ec  ldloc.1
0x221ed  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_ValueExpression()
0x221f2  brtrue.s loc_22208
  ... truncated ...
```
