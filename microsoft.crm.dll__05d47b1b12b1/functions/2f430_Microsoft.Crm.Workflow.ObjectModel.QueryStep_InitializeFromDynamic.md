# Microsoft.Crm.Workflow.ObjectModel.QueryStep::InitializeFromDynamic

- ea: `0x2f430`
- end: `0x2f7ee`
- name: `Microsoft.Crm.Workflow.ObjectModel.QueryStep::InitializeFromDynamic`
- size: `958`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2f430`
- `0x30ca0`
- `0x30ef0`

## string_xrefs

- `0x2f732`: `originalFetchXml`
- `0x2f77b`: `originalFetchXml`
- `0x2f790`: `originalLayoutXml`
- `0x2f7d9`: `originalLayoutXml`

## pseudocode

```c

```

## disassembly

```asm
0x2f430  ldarg.1
0x2f431  brfalse  loc_2F7ED
0x2f436  ldarg.0
0x2f437  ldarg.1
0x2f438  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> deserializedObject)
0x2f43d  ldarg.1
0x2f43e  ldstr    aFetchexpressio// "fetchExpression"
0x2f443  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2f448  brfalse  loc_2F5B4
0x2f44d  ldarg.0
0x2f44e  ldarg.1
0x2f44f  ldstr    aFetchexpressio// "fetchExpression"
0x2f454  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2f459  stloc.0
0x2f45a  ldarg.0
0x2f45b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__28::<>p__2
0x2f460  brtrue.s loc_2F486
0x2f462  ldc.i4.0
0x2f463  ldtoken  Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x2f468  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f46d  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f472  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f477  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f47c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Create(!!T0)
0x2f481  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__28::<>p__2
0x2f486  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__28::<>p__2
0x2f48b  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Target
0x2f490  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__28::<>p__2
0x2f495  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__1
0x2f49a  brtrue.s loc_2F4D7
0x2f49c  ldc.i4.0
0x2f49d  ldstr    aBuildexpressio// "BuildExpression"
0x2f4a2  ldnull
0x2f4a3  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f4a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f4ad  ldc.i4.2
0x2f4ae  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2f4b3  dup
0x2f4b4  ldc.i4.0
0x2f4b5  ldc.i4.s 0x21
0x2f4b7  ldnull
0x2f4b8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f4bd  stelem.ref
0x2f4be  dup
0x2f4bf  ldc.i4.1
0x2f4c0  ldc.i4.0
0x2f4c1  ldnull
0x2f4c2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f4c7  stelem.ref
0x2f4c8  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2f4cd  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x2f4d2  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__1
0x2f4d7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__1
0x2f4dc  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x2f4e1  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__1
0x2f4e6  ldtoken  Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory
0x2f4eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f4f0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__28::<>p__0
0x2f4f5  brtrue.s loc_2F52B
0x2f4f7  ldc.i4.0
0x2f4f8  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f4fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f502  ldc.i4.2
0x2f503  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2f508  dup
0x2f509  ldc.i4.0
0x2f50a  ldc.i4.0
0x2f50b  ldnull
0x2f50c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f511  stelem.ref
0x2f512  dup
0x2f513  ldc.i4.1
0x2f514  ldc.i4.3
0x2f515  ldnull
0x2f516  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f51b  stelem.ref
0x2f51c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetIndex(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2f521  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x2f526  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__28::<>p__0
0x2f52b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__28::<>p__0
0x2f530  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x2f535  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__28::<>p__0
0x2f53a  ldloc.0
0x2f53b  ldstr    aClass// "__class"
0x2f540  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x2f545  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x2f54a  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Invoke(bool, var<u1>)
0x2f54f  stfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.QueryStep::fetchExpression
0x2f554  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__28::<>p__3
0x2f559  brtrue.s loc_2F599
0x2f55b  ldc.i4   0x100
0x2f560  ldstr    aInitializefrom// "InitializeFromDynamic"
0x2f565  ldnull
0x2f566  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f56b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f570  ldc.i4.2
0x2f571  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2f576  dup
0x2f577  ldc.i4.0
0x2f578  ldc.i4.1
0x2f579  ldnull
0x2f57a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f57f  stelem.ref
0x2f580  dup
0x2f581  ldc.i4.1
0x2f582  ldc.i4.0
0x2f583  ldnull
0x2f584  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f589  stelem.ref
0x2f58a  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2f58f  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>>::Create(!!T0)
0x2f594  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__28::<>p__3
0x2f599  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__28::<>p__3
0x2f59e  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>>::Target
0x2f5a3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__28::<>p__3
0x2f5a8  ldarg.0
0x2f5a9  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.QueryStep::fetchExpression
0x2f5ae  ldloc.0
0x2f5af  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>::Invoke(var<u1>, !!T0, var<u1>)
0x2f5b4  ldarg.1
0x2f5b5  ldstr    aFetchcount// "fetchCount"
0x2f5ba  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2f5bf  brfalse  loc_2F675
0x2f5c4  ldarg.0
0x2f5c5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__28::<>p__5
0x2f5ca  brtrue.s loc_2F5F0
0x2f5cc  ldc.i4.0
0x2f5cd  ldtoken  [mscorlib]System.Int32
0x2f5d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f5d7  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f5dc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f5e1  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f5e6  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>>::Create(!!T0)
0x2f5eb  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__28::<>p__5
0x2f5f0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__28::<>p__5
0x2f5f5  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>>::Target
0x2f5fa  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__28::<>p__5
0x2f5ff  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__4
0x2f604  brtrue.s loc_2F641
0x2f606  ldc.i4.0
0x2f607  ldstr    aParse// "Parse"
0x2f60c  ldnull
0x2f60d  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f612  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f617  ldc.i4.2
0x2f618  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2f61d  dup
0x2f61e  ldc.i4.0
0x2f61f  ldc.i4.s 0x21
0x2f621  ldnull
0x2f622  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f627  stelem.ref
0x2f628  dup
0x2f629  ldc.i4.1
0x2f62a  ldc.i4.0
0x2f62b  ldnull
0x2f62c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2f631  stelem.ref
0x2f632  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2f637  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x2f63c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__4
0x2f641  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__4
0x2f646  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x2f64b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__28::<>p__4
0x2f650  ldtoken  [mscorlib]System.Int32
0x2f655  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f65a  ldarg.0
0x2f65b  ldarg.1
0x2f65c  ldstr    aFetchcount// "fetchCount"
0x2f661  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2f666  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x2f66b  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>::Invoke(bool, var<u1>)
0x2f670  stfld    int32 Microsoft.Crm.Workflow.ObjectModel.QueryStep::fetchCount
0x2f675  ldarg.1
0x2f676  ldstr    aAttributelist// "attributeList"
0x2f67b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2f680  brfalse.s loc_2F6D3
0x2f682  ldarg.0
0x2f683  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__6
0x2f688  brtrue.s loc_2F6AE
0x2f68a  ldc.i4.0
0x2f68b  ldtoken  [mscorlib]System.String
0x2f690  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f695  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f69a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f69f  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f6a4  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x2f6a9  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__6
0x2f6ae  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__6
0x2f6b3  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x2f6b8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__6
0x2f6bd  ldarg.0
0x2f6be  ldarg.1
0x2f6bf  ldstr    aAttributelist// "attributeList"
0x2f6c4  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2f6c9  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x2f6ce  stfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::attributeList
0x2f6d3  ldarg.1
0x2f6d4  ldstr    aEntityname// "entityName"
0x2f6d9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2f6de  brfalse.s loc_2F731
0x2f6e0  ldarg.0
0x2f6e1  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__7
0x2f6e6  brtrue.s loc_2F70C
0x2f6e8  ldc.i4.0
0x2f6e9  ldtoken  [mscorlib]System.String
0x2f6ee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f6f3  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f6f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f6fd  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f702  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x2f707  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__7
0x2f70c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__7
0x2f711  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x2f716  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__7
0x2f71b  ldarg.0
0x2f71c  ldarg.1
0x2f71d  ldstr    aEntityname// "entityName"
0x2f722  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2f727  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x2f72c  stfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::entityName
0x2f731  ldarg.1
0x2f732  ldstr    aOriginalfetchx// "originalFetchXml"
0x2f737  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2f73c  brfalse.s loc_2F78F
0x2f73e  ldarg.0
0x2f73f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__8
0x2f744  brtrue.s loc_2F76A
0x2f746  ldc.i4.0
0x2f747  ldtoken  [mscorlib]System.String
0x2f74c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f751  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f756  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f75b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f760  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x2f765  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__8
0x2f76a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__8
0x2f76f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x2f774  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__8
0x2f779  ldarg.0
0x2f77a  ldarg.1
0x2f77b  ldstr    aOriginalfetchx// "originalFetchXml"
0x2f780  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2f785  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x2f78a  stfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::originalFetchXml
0x2f78f  ldarg.1
0x2f790  ldstr    aOriginallayout// "originalLayoutXml"
0x2f795  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2f79a  brfalse.s loc_2F7ED
0x2f79c  ldarg.0
0x2f79d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__9
0x2f7a2  brtrue.s loc_2F7C8
0x2f7a4  ldc.i4.0
0x2f7a5  ldtoken  [mscorlib]System.String
0x2f7aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f7af  ldtoken  Microsoft.Crm.Workflow.ObjectModel.QueryStep
0x2f7b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f7b9  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2f7be  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x2f7c3  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__9
0x2f7c8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__9
0x2f7cd  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x2f7d2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__28::<>p__9
0x2f7d7  ldarg.0
0x2f7d8  ldarg.1
0x2f7d9  ldstr    aOriginallayout// "originalLayoutXml"
0x2f7de  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x2f7e3  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x2f7e8  stfld    string Microsoft.Crm.Workflow.ObjectModel.QueryStep::originalLayoutXml
0x2f7ed  ret
```
