# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignOutputArgumentStep

- ea: `0x22210`
- end: `0x2239a`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignOutputArgumentStep`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22480`

## callees

- `0x1fef0`
- `0x22210`
- `0x22ce0`

## pseudocode

```c

```

## disassembly

```asm
0x22210  ldc.i4.0
0x22211  stloc.0
0x22212  ldarg.0
0x22213  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x22218  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2221d  stloc.1
0x2221e  ldc.i4.0
0x2221f  stloc.3
0x22220  ldsfld   string [mscorlib]System.String::Empty
0x22225  stloc.s  4
0x22227  ldarg.1
0x22228  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x2222d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x22232  stloc.s  5
0x22234  br.s     loc_22265
0x22236  ldloc.s  5
0x22238  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x2223d  stloc.s  6
0x2223f  ldloc.s  6
0x22241  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x22246  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TypeNameString
0x2224b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22250  brfalse.s loc_22265
0x22252  ldloc.s  6
0x22254  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x22259  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x2225e  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x22263  stloc.s  4
0x22265  ldloc.s  5
0x22267  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2226c  brtrue.s loc_22236
0x2226e  leave.s  loc_2227C
0x22270  ldloc.s  5
0x22272  brfalse.s loc_2227B
0x22274  ldloc.s  5
0x22276  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2227b  endfinally
0x2227c  ldarg.0
0x2227d  ldarg.1
0x2227e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x22283  ldc.i4.0
0x22284  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::FindFirstAssignActivity(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> collection, [opt] int32 startIndex)
0x22289  dup
0x2228a  stloc.2
0x2228b  brfalse  loc_22349
0x22290  ldtoken  [System.Activities]System.Activities.Statements.Assign`1
0x22295  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2229a  ldc.i4.1
0x2229b  newarr   [mscorlib]System.Type
0x222a0  dup
0x222a1  ldc.i4.0
0x222a2  ldloc.s  4
0x222a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x222a9  stelem.ref
0x222aa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x222af  stloc.s  7
0x222b1  ldtoken  [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1
0x222b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x222bb  ldc.i4.1
0x222bc  newarr   [mscorlib]System.Type
0x222c1  dup
0x222c2  ldc.i4.0
0x222c3  ldloc.s  4
0x222c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x222ca  stelem.ref
0x222cb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x222d0  stloc.s  8
0x222d2  ldtoken  [System.Activities]System.Activities.OutArgument`1
0x222d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x222dc  ldc.i4.1
0x222dd  newarr   [mscorlib]System.Type
0x222e2  dup
0x222e3  ldc.i4.0
0x222e4  ldloc.s  4
0x222e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x222eb  stelem.ref
0x222ec  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x222f1  ldloc.s  7
0x222f3  ldstr    aTo// "To"
0x222f8  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x222fd  ldloc.2
0x222fe  ldnull
0x222ff  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x22304  stloc.s  9
0x22306  ldstr    aExpression// "Expression"
0x2230b  ldtoken  [System.Activities]System.Activities.ActivityWithResult
0x22310  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x22315  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, class [mscorlib]System.Type)
0x2231a  ldloc.s  9
0x2231c  ldnull
0x2231d  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x22322  stloc.s  0xA
0x22324  ldloc.s  8
0x22326  ldstr    aExpressiontext// "ExpressionText"
0x2232b  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x22330  ldloc.s  0xA
0x22332  ldnull
0x22333  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x22338  castclass [mscorlib]System.String
0x2233d  stloc.s  0xB
0x2233f  ldloc.1
0x22340  ldloc.s  0xB
0x22342  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ArgumentName(string)
0x22347  ldc.i4.1
0x22348  stloc.3
0x22349  ldloc.3
0x2234a  brfalse.s loc_22398
0x2234c  ldloc.s  4
0x2234e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x22353  stloc.s  0xC
0x22355  ldloc.1
0x22356  ldloc.s  0xC
0x22358  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_DataType(class [mscorlib]System.Type)
0x2235d  ldloc.1
0x2235e  ldarg.0
0x2235f  ldarg.1
0x22360  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x22365  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<string>
0x2236a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2236f  ldc.i4.0
0x22370  ldloca.s 0
0x22372  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadExpression(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, class [mscorlib]System.Type endActivityType, bool customActivity, int32& activityIndex)
0x22377  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x2237c  ldloc.1
0x2237d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::get_ValueExpression()
0x22382  brtrue.s loc_22398
0x22384  ldloc.1
0x22385  ldarg.0
0x22386  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2238b  ldnull
0x2238c  ldc.i4.s 0xE
0x2238e  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x22393  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::set_ValueExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x22398  ldloc.1
0x22399  ret
```
