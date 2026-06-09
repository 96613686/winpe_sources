# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignActivity

- ea: `0x23d20`
- end: `0x23f92`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadAssignActivity`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x22ce0`

## callees

- `0x23d20`

## pseudocode

```c

```

## disassembly

```asm
0x23d20  ldnull
0x23d21  stloc.0
0x23d22  ldarg.2
0x23d23  brfalse  loc_23EA9
0x23d28  ldarg.1
0x23d29  castclass [System.Activities]System.Activities.Statements.Assign
0x23d2e  stloc.1
0x23d2f  ldloc.1
0x23d30  callvirt instance class [System.Activities]System.Activities.OutArgument [System.Activities]System.Activities.Statements.Assign::get_To()
0x23d35  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Argument::get_Expression()
0x23d3a  stloc.2
0x23d3b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__1
0x23d40  brtrue.s loc_23D66
0x23d42  ldc.i4.0
0x23d43  ldtoken  [mscorlib]System.String
0x23d48  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23d4d  ldtoken  Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator
0x23d52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23d57  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x23d5c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x23d61  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__1
0x23d66  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__1
0x23d6b  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x23d70  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__1
0x23d75  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__0
0x23d7a  brtrue.s loc_23DAB
0x23d7c  ldc.i4.0
0x23d7d  ldstr    aExpressiontext// "ExpressionText"
0x23d82  ldtoken  Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator
0x23d87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23d8c  ldc.i4.1
0x23d8d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x23d92  dup
0x23d93  ldc.i4.0
0x23d94  ldc.i4.0
0x23d95  ldnull
0x23d96  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x23d9b  stelem.ref
0x23d9c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x23da1  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x23da6  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__0
0x23dab  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__0
0x23db0  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x23db5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__0
0x23dba  ldloc.2
0x23dbb  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x23dc0  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x23dc5  stloc.3
0x23dc6  ldloc.1
0x23dc7  callvirt instance class [System.Activities]System.Activities.InArgument [System.Activities]System.Activities.Statements.Assign::get_Value()
0x23dcc  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Argument::get_Expression()
0x23dd1  stloc.2
0x23dd2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__3
0x23dd7  brtrue.s loc_23DFD
0x23dd9  ldc.i4.0
0x23dda  ldtoken  [mscorlib]System.String
0x23ddf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23de4  ldtoken  Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator
0x23de9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23dee  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x23df3  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x23df8  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__3
0x23dfd  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__3
0x23e02  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x23e07  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__86::<>p__3
0x23e0c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__2
0x23e11  brtrue.s loc_23E42
0x23e13  ldc.i4.0
0x23e14  ldstr    aExpressiontext// "ExpressionText"
0x23e19  ldtoken  Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator
0x23e1e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23e23  ldc.i4.1
0x23e24  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x23e29  dup
0x23e2a  ldc.i4.0
0x23e2b  ldc.i4.0
0x23e2c  ldnull
0x23e2d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x23e32  stelem.ref
0x23e33  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x23e38  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x23e3d  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__2
0x23e42  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__2
0x23e47  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x23e4c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__86::<>p__2
0x23e51  ldloc.2
0x23e52  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x23e57  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x23e5c  stloc.s  4
0x23e5e  ldloc.s  4
0x23e60  ldc.i4.s 0xB
0x23e62  ldloc.s  4
0x23e64  ldstr    asc_33D74// ","
0x23e69  ldc.i4.4
0x23e6a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x23e6f  ldc.i4.s 0xB
0x23e71  sub
0x23e72  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23e77  stloc.s  5
0x23e79  ldarg.0
0x23e7a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x23e7f  ldloc.s  5
0x23e81  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x23e86  brfalse  loc_23F90
0x23e8b  ldarg.0
0x23e8c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x23e91  ldloc.3
0x23e92  ldarg.0
0x23e93  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x23e98  ldloc.s  5
0x23e9a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23e9f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x23ea4  br       loc_23F90
0x23ea9  ldarg.1
0x23eaa  isinst   class [System.Activities]System.Activities.Statements.Assign`1<bool>
0x23eaf  stloc.s  6
0x23eb1  ldloc.s  6
0x23eb3  brfalse  loc_23F90
0x23eb8  ldloc.s  6
0x23eba  callvirt instance class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.Statements.Assign`1<bool>::get_Value()
0x23ebf  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<bool>::get_Expression()
0x23ec4  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>
0x23ec9  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<bool>::get_ExpressionText()
0x23ece  stloc.s  7
0x23ed0  ldstr    aDatetimeUtcnow_0// "DateTime.UtcNow >= "
0x23ed5  stloc.s  8
0x23ed7  ldloc.s  7
0x23ed9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23ede  brtrue   loc_23F90
0x23ee3  ldloc.s  7
0x23ee5  ldloc.s  8
0x23ee7  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23eec  brfalse  loc_23F90
0x23ef1  ldloc.s  7
0x23ef3  ldstr    aAdd_0// ".Add("
0x23ef8  ldc.i4.4
0x23ef9  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x23efe  stloc.s  9
0x23f00  ldloc.s  9
0x23f02  ldc.i4.m1
0x23f03  beq.s    loc_23F34
0x23f05  ldloc.s  7
0x23f07  ldloc.s  8
0x23f09  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23f0e  ldloc.s  9
0x23f10  ldloc.s  8
0x23f12  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23f17  sub
0x23f18  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23f1d  stloc.s  0xA
0x23f1f  ldarg.0
0x23f20  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x23f25  ldloc.s  0xA
0x23f27  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23f2c  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x23f31  stloc.0
0x23f32  br.s     loc_23F90
0x23f34  ldstr    aDatetimeUtcnow_1// "DateTime.UtcNow >= DirectCast("
0x23f39  stloc.s  8
0x23f3b  ldloc.s  7
0x23f3d  ldstr    aCustomactivity_0// "CustomActivityStep"
0x23f42  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23f47  brfalse.s loc_23F90
0x23f49  ldloc.s  7
0x23f4b  ldloc.s  8
0x23f4d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23f52  brfalse.s loc_23F90
0x23f54  ldloc.s  7
0x23f56  ldstr    asc_33D74// ","
0x23f5b  ldc.i4.4
0x23f5c  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x23f61  stloc.s  9
0x23f63  ldloc.s  7
0x23f65  ldloc.s  8
0x23f67  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23f6c  ldloc.s  9
0x23f6e  ldloc.s  8
0x23f70  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23f75  sub
0x23f76  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23f7b  stloc.s  0xB
0x23f7d  ldarg.0
0x23f7e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x23f83  ldloc.s  0xB
0x23f85  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x23f8a  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x23f8f  stloc.0
0x23f90  ldloc.0
0x23f91  ret
```
