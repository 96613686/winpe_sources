# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepInputs

- ea: `0x21060`
- end: `0x2126c`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCustomStepInputs`
- size: `524`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x20a40`
- `0x20bc0`

## callees

- `0x21060`
- `0x214b0`

## pseudocode

```c

```

## disassembly

```asm
0x21060  ldarg.s  4
0x21062  ldstr    aInvokesdkmessa_0// "InvokeSdkMessage"
0x21067  ldc.i4.4
0x21068  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2106d  stloc.0
0x2106e  ldarg.1
0x2106f  stloc.1
0x21070  ldc.i4.0
0x21071  stloc.2
0x21072  br       loc_21262
0x21077  ldloc.1
0x21078  ldloc.2
0x21079  ldelem.ref
0x2107a  stloc.3
0x2107b  ldarg.2
0x2107c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference::get_Arguments()
0x21081  ldloc.3
0x21082  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x21087  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::ContainsKey(var<u1>)
0x2108c  brfalse  loc_2125E
0x21091  ldarg.2
0x21092  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomReference::get_Arguments()
0x21097  ldloc.3
0x21098  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x2109d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::get_Item(void)
0x210a2  stloc.s  4
0x210a4  ldloc.s  4
0x210a6  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Argument::get_Expression()
0x210ab  stloc.s  5
0x210ad  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__59::<>p__1
0x210b2  brtrue.s loc_210D9
0x210b4  ldc.i4.s 0x10
0x210b6  ldtoken  [mscorlib]System.String
0x210bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x210c0  ldtoken  Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator
0x210c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x210ca  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x210cf  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x210d4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__59::<>p__1
0x210d9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__59::<>p__1
0x210de  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x210e3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__59::<>p__1
0x210e8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__59::<>p__0
0x210ed  brtrue.s loc_2111E
0x210ef  ldc.i4.0
0x210f0  ldstr    aExpressiontext// "ExpressionText"
0x210f5  ldtoken  Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator
0x210fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x210ff  ldc.i4.1
0x21100  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x21105  dup
0x21106  ldc.i4.0
0x21107  ldc.i4.0
0x21108  ldnull
0x21109  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2110e  stelem.ref
0x2110f  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x21114  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x21119  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__59::<>p__0
0x2111e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__59::<>p__0
0x21123  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x21128  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__59::<>p__0
0x2112d  ldloc.s  5
0x2112f  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x21134  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x21139  stloc.s  6
0x2113b  ldloc.s  6
0x2113d  ldstr    aDirectcast// "DirectCast("
0x21142  ldc.i4.4
0x21143  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x21148  ldloc.s  6
0x2114a  ldstr    asc_33D74// ","
0x2114f  ldc.i4.4
0x21150  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x21155  stloc.s  7
0x21157  ldsfld   string [mscorlib]System.String::Empty
0x2115c  stloc.s  8
0x2115e  ldc.i4.m1
0x2115f  beq.s    loc_21183
0x21161  ldloc.s  7
0x21163  ldc.i4.m1
0x21164  beq.s    loc_21183
0x21166  ldloc.s  6
0x21168  ldc.i4.s 0xB
0x2116a  ldloc.s  6
0x2116c  ldstr    asc_33D74// ","
0x21171  ldc.i4.4
0x21172  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x21177  ldc.i4.s 0xB
0x21179  sub
0x2117a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2117f  stloc.s  8
0x21181  br.s     loc_21187
0x21183  ldloc.s  6
0x21185  stloc.s  8
0x21187  ldarg.0
0x21188  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x2118d  ldloc.s  8
0x2118f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x21194  brfalse  loc_2125E
0x21199  ldarg.0
0x2119a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x2119f  ldloc.s  8
0x211a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x211a6  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ActivityPropertyExpression
0x211ab  stloc.s  9
0x211ad  ldloc.s  9
0x211af  brfalse.s loc_211CA
0x211b1  ldloc.s  9
0x211b3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ActivityPropertyExpression::get_Step()
0x211b8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x211bd  ldarg.s  4
0x211bf  ldc.i4.4
0x211c0  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x211c5  brtrue   loc_2125E
0x211ca  ldarg.0
0x211cb  ldloc.s  4
0x211cd  ldloc.3
0x211ce  ldarg.3
0x211cf  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x211d4  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_IsNet4()
0x211d9  call     instance bool Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ArgumentSignatureMatches(class [System.Activities]System.Activities.Argument argument, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase output, bool isNet4)
0x211de  brtrue.s loc_2122F
0x211e0  ldloc.0
0x211e1  brfalse.s loc_21209
0x211e3  ldarg.0
0x211e4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x211e9  ldloc.s  8
0x211eb  ldarg.0
0x211ec  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x211f1  ldloc.s  8
0x211f3  ldc.i4.1
0x211f4  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep::.ctor(string, bool)
0x211f9  ldloc.s  8
0x211fb  ldc.i4.s 0xE
0x211fd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ActivityPropertyExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x21202  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x21207  br.s     loc_2125E
0x21209  ldarg.0
0x2120a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x2120f  ldloc.s  8
0x21211  ldarg.0
0x21212  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x21217  ldloc.s  8
0x21219  ldc.i4.1
0x2121a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep::.ctor(string, bool)
0x2121f  ldloc.s  8
0x21221  ldc.i4.s 0xE
0x21223  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ActivityPropertyExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x21228  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2122d  br.s     loc_2125E
0x2122f  ldarg.0
0x21230  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x21235  ldloc.s  8
0x21237  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2123c  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x21241  stloc.s  0xA
0x21243  ldloc.s  0xA
0x21245  ldloc.3
0x21246  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x2124b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::set_Type(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x21250  ldarg.3
0x21251  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x21256  ldloc.3
0x21257  ldloc.s  0xA
0x21259  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::set_Item(var<u1>, !!T0)
0x2125e  ldloc.2
0x2125f  ldc.i4.1
0x21260  add
0x21261  stloc.2
0x21262  ldloc.2
0x21263  ldloc.1
0x21264  ldlen
0x21265  conv.i4
0x21266  blt      loc_21077
0x2126b  ret
```
