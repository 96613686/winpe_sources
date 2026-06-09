# Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::InitializeFromDynamic

- ea: `0x2b9b0`
- end: `0x2c2e8`
- name: `Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::InitializeFromDynamic`
- size: `2360`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2b9b0`
- `0x30ca0`

## string_xrefs

- `0x2bff5`: `targetLinkedFilter`
- `0x2c005`: `targetLinkedFilter`
- `0x2be7e`: `targetRelationshipLinked`
- `0x2be8e`: `targetRelationshipLinked`

## pseudocode

```c

```

## disassembly

```asm
0x2b9b0  ldarg.1
0x2b9b1  brfalse  loc_2C2E7
0x2b9b6  ldarg.0
0x2b9b7  ldarg.1
0x2b9b8  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> deserializedObject)
0x2b9bd  ldarg.1
0x2b9be  ldstr    aHierarchicalre// "hierarchicalRelationshipName"
0x2b9c3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2b9c8  brfalse.s loc_2BA1A
0x2b9ca  ldarg.0
0x2b9cb  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__39::<>p__0
0x2b9d0  brtrue.s loc_2B9F6
0x2b9d2  ldc.i4.0
0x2b9d3  ldtoken  [mscorlib]System.String
0x2b9d8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b9dd  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2b9e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b9e7  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2b9ec  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x2b9f1  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__39::<>p__0
0x2b9f6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__39::<>p__0
0x2b9fb  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x2ba00  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__39::<>p__0
0x2ba05  ldarg.1
0x2ba06  ldstr    aHierarchicalre// "hierarchicalRelationshipName"
0x2ba0b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2ba10  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x2ba15  stfld    string Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::hierarchicalRelationshipName
0x2ba1a  ldarg.1
0x2ba1b  ldstr    aSourcefilter// "sourceFilter"
0x2ba20  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2ba25  brfalse  loc_2BB90
0x2ba2a  ldarg.1
0x2ba2b  ldstr    aSourcefilter// "sourceFilter"
0x2ba30  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2ba35  stloc.0
0x2ba36  ldarg.0
0x2ba37  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__3
0x2ba3c  brtrue.s loc_2BA62
0x2ba3e  ldc.i4.0
0x2ba3f  ldtoken  Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x2ba44  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ba49  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2ba4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ba53  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ba58  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Create(!!T0)
0x2ba5d  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__3
0x2ba62  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__3
0x2ba67  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Target
0x2ba6c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__3
0x2ba71  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__2
0x2ba76  brtrue.s loc_2BAB3
0x2ba78  ldc.i4.0
0x2ba79  ldstr    aBuildexpressio// "BuildExpression"
0x2ba7e  ldnull
0x2ba7f  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2ba84  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ba89  ldc.i4.2
0x2ba8a  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2ba8f  dup
0x2ba90  ldc.i4.0
0x2ba91  ldc.i4.s 0x21
0x2ba93  ldnull
0x2ba94  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2ba99  stelem.ref
0x2ba9a  dup
0x2ba9b  ldc.i4.1
0x2ba9c  ldc.i4.0
0x2ba9d  ldnull
0x2ba9e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2baa3  stelem.ref
0x2baa4  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2baa9  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x2baae  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__2
0x2bab3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__2
0x2bab8  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x2babd  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__2
0x2bac2  ldtoken  Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory
0x2bac7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bacc  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__1
0x2bad1  brtrue.s loc_2BB07
0x2bad3  ldc.i4.0
0x2bad4  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bad9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bade  ldc.i4.2
0x2badf  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2bae4  dup
0x2bae5  ldc.i4.0
0x2bae6  ldc.i4.0
0x2bae7  ldnull
0x2bae8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2baed  stelem.ref
0x2baee  dup
0x2baef  ldc.i4.1
0x2baf0  ldc.i4.3
0x2baf1  ldnull
0x2baf2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2baf7  stelem.ref
0x2baf8  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetIndex(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2bafd  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x2bb02  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__1
0x2bb07  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__1
0x2bb0c  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x2bb11  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__1
0x2bb16  ldloc.0
0x2bb17  ldstr    aClass// "__class"
0x2bb1c  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x2bb21  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x2bb26  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Invoke(bool, var<u1>)
0x2bb2b  stfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::sourceFilter
0x2bb30  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__39::<>p__4
0x2bb35  brtrue.s loc_2BB75
0x2bb37  ldc.i4   0x100
0x2bb3c  ldstr    aInitializefrom// "InitializeFromDynamic"
0x2bb41  ldnull
0x2bb42  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bb47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bb4c  ldc.i4.2
0x2bb4d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2bb52  dup
0x2bb53  ldc.i4.0
0x2bb54  ldc.i4.1
0x2bb55  ldnull
0x2bb56  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bb5b  stelem.ref
0x2bb5c  dup
0x2bb5d  ldc.i4.1
0x2bb5e  ldc.i4.0
0x2bb5f  ldnull
0x2bb60  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bb65  stelem.ref
0x2bb66  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2bb6b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>>::Create(!!T0)
0x2bb70  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__39::<>p__4
0x2bb75  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__39::<>p__4
0x2bb7a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>>::Target
0x2bb7f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>> <>o__39::<>p__4
0x2bb84  ldarg.0
0x2bb85  ldfld    class Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::sourceFilter
0x2bb8a  ldloc.0
0x2bb8b  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.ExpressionBase, object>::Invoke(var<u1>, !!T0, var<u1>)
0x2bb90  ldarg.1
0x2bb91  ldstr    aTargetrelation// "targetRelationship"
0x2bb96  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2bb9b  brfalse  loc_2BD07
0x2bba0  ldarg.1
0x2bba1  ldstr    aTargetrelation// "targetRelationship"
0x2bba6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2bbab  stloc.1
0x2bbac  ldarg.0
0x2bbad  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked>> <>o__39::<>p__7
0x2bbb2  brtrue.s loc_2BBD9
0x2bbb4  ldc.i4.s 0x10
0x2bbb6  ldtoken  Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked
0x2bbbb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bbc0  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bbc5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bbca  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2bbcf  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked>>::Create(!!T0)
0x2bbd4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked>> <>o__39::<>p__7
0x2bbd9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked>> <>o__39::<>p__7
0x2bbde  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked>>::Target
0x2bbe3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked>> <>o__39::<>p__7
0x2bbe8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__6
0x2bbed  brtrue.s loc_2BC2A
0x2bbef  ldc.i4.0
0x2bbf0  ldstr    aBuildentity// "BuildEntity"
0x2bbf5  ldnull
0x2bbf6  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bbfb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bc00  ldc.i4.2
0x2bc01  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2bc06  dup
0x2bc07  ldc.i4.0
0x2bc08  ldc.i4.s 0x21
0x2bc0a  ldnull
0x2bc0b  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bc10  stelem.ref
0x2bc11  dup
0x2bc12  ldc.i4.1
0x2bc13  ldc.i4.0
0x2bc14  ldnull
0x2bc15  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bc1a  stelem.ref
0x2bc1b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2bc20  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x2bc25  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__6
0x2bc2a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__6
0x2bc2f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x2bc34  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__6
0x2bc39  ldtoken  Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory
0x2bc3e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bc43  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__5
0x2bc48  brtrue.s loc_2BC7E
0x2bc4a  ldc.i4.0
0x2bc4b  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bc50  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bc55  ldc.i4.2
0x2bc56  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2bc5b  dup
0x2bc5c  ldc.i4.0
0x2bc5d  ldc.i4.0
0x2bc5e  ldnull
0x2bc5f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bc64  stelem.ref
0x2bc65  dup
0x2bc66  ldc.i4.1
0x2bc67  ldc.i4.3
0x2bc68  ldnull
0x2bc69  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bc6e  stelem.ref
0x2bc6f  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetIndex(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2bc74  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x2bc79  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__5
0x2bc7e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__5
0x2bc83  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x2bc88  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__39::<>p__5
0x2bc8d  ldloc.1
0x2bc8e  ldstr    aClass// "__class"
0x2bc93  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x2bc98  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x2bc9d  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked>::Invoke(bool, var<u1>)
0x2bca2  stfld    class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetRelationship
0x2bca7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked, object>> <>o__39::<>p__8
0x2bcac  brtrue.s loc_2BCEC
0x2bcae  ldc.i4   0x100
0x2bcb3  ldstr    aInitializefrom// "InitializeFromDynamic"
0x2bcb8  ldnull
0x2bcb9  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bcbe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bcc3  ldc.i4.2
0x2bcc4  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2bcc9  dup
0x2bcca  ldc.i4.0
0x2bccb  ldc.i4.1
0x2bccc  ldnull
0x2bccd  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bcd2  stelem.ref
0x2bcd3  dup
0x2bcd4  ldc.i4.1
0x2bcd5  ldc.i4.0
0x2bcd6  ldnull
0x2bcd7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bcdc  stelem.ref
0x2bcdd  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2bce2  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked, object>>::Create(!!T0)
0x2bce7  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked, object>> <>o__39::<>p__8
0x2bcec  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked, object>> <>o__39::<>p__8
0x2bcf1  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked, object>>::Target
0x2bcf6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked, object>> <>o__39::<>p__8
0x2bcfb  ldarg.0
0x2bcfc  ldfld    class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep::targetRelationship
0x2bd01  ldloc.1
0x2bd02  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked, object>::Invoke(var<u1>, !!T0, var<u1>)
0x2bd07  ldarg.1
0x2bd08  ldstr    aTargetfilter// "targetFilter"
0x2bd0d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2bd12  brfalse  loc_2BE7D
0x2bd17  ldarg.1
0x2bd18  ldstr    aTargetfilter// "targetFilter"
0x2bd1d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2bd22  stloc.2
0x2bd23  ldarg.0
0x2bd24  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__11
0x2bd29  brtrue.s loc_2BD4F
0x2bd2b  ldc.i4.0
0x2bd2c  ldtoken  Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x2bd31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bd36  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bd3b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bd40  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2bd45  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Create(!!T0)
0x2bd4a  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__11
0x2bd4f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__11
0x2bd54  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>>::Target
0x2bd59  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.ExpressionBase>> <>o__39::<>p__11
0x2bd5e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__10
0x2bd63  brtrue.s loc_2BDA0
0x2bd65  ldc.i4.0
0x2bd66  ldstr    aBuildexpressio// "BuildExpression"
0x2bd6b  ldnull
0x2bd6c  ldtoken  Microsoft.Crm.Workflow.ObjectModel.RollupRuleStep
0x2bd71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bd76  ldc.i4.2
0x2bd77  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2bd7c  dup
0x2bd7d  ldc.i4.0
0x2bd7e  ldc.i4.s 0x21
0x2bd80  ldnull
0x2bd81  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bd86  stelem.ref
0x2bd87  dup
0x2bd88  ldc.i4.1
0x2bd89  ldc.i4.0
0x2bd8a  ldnull
0x2bd8b  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2bd90  stelem.ref
0x2bd91  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2bd96  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x2bd9b  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__39::<>p__10
  ... truncated ...
```
