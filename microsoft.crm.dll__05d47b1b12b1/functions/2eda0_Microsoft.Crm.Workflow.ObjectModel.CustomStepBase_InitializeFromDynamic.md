# Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::InitializeFromDynamic

- ea: `0x2eda0`
- end: `0x2ef81`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::InitializeFromDynamic`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2e6d0`
- `0x2ec00`
- `0x2ec10`
- `0x2ec30`
- `0x2ec50`
- `0x2ec70`
- `0x2eda0`
- `0x30ca0`
- `0x35990`

## string_xrefs

- `0x2ef0b`: `isWebPluginActivity`

## pseudocode

```c

```

## disassembly

```asm
0x2eda0  ldarg.1
0x2eda1  brfalse  loc_2EF80
0x2eda6  ldarg.0
0x2eda7  ldarg.1
0x2eda8  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> deserializedObject)
0x2edad  ldarg.1
0x2edae  ldstr    aActivityinfo// "activityInfo"
0x2edb3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2edb8  brfalse.s loc_2EE2F
0x2edba  ldarg.0
0x2edbb  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo::.ctor()
0x2edc0  call     instance void Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_ActivityInfo(class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase value)
0x2edc5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase, object>> <>o__32::<>p__0
0x2edca  brtrue.s loc_2EE0A
0x2edcc  ldc.i4   0x100
0x2edd1  ldstr    aInitializefrom// "InitializeFromDynamic"
0x2edd6  ldnull
0x2edd7  ldtoken  Microsoft.Crm.Workflow.ObjectModel.CustomStepBase
0x2eddc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ede1  ldc.i4.2
0x2ede2  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x2ede7  dup
0x2ede8  ldc.i4.0
0x2ede9  ldc.i4.1
0x2edea  ldnull
0x2edeb  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2edf0  stelem.ref
0x2edf1  dup
0x2edf2  ldc.i4.1
0x2edf3  ldc.i4.0
0x2edf4  ldnull
0x2edf5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x2edfa  stelem.ref
0x2edfb  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x2ee00  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase, object>>::Create(!!T0)
0x2ee05  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase, object>> <>o__32::<>p__0
0x2ee0a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase, object>> <>o__32::<>p__0
0x2ee0f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase, object>>::Target
0x2ee14  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase, object>> <>o__32::<>p__0
0x2ee19  ldarg.0
0x2ee1a  call     instance class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x2ee1f  ldarg.1
0x2ee20  ldstr    aActivityinfo// "activityInfo"
0x2ee25  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2ee2a  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase, object>::Invoke(var<u1>, !!T0, var<u1>)
0x2ee2f  ldarg.0
0x2ee30  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__1
0x2ee35  brtrue.s loc_2EE5B
0x2ee37  ldc.i4.0
0x2ee38  ldtoken  [mscorlib]System.Boolean
0x2ee3d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ee42  ldtoken  Microsoft.Crm.Workflow.ObjectModel.CustomStepBase
0x2ee47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ee4c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ee51  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x2ee56  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__1
0x2ee5b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__1
0x2ee60  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x2ee65  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__1
0x2ee6a  ldarg.1
0x2ee6b  ldstr    aHasoutputs// "hasOutputs"
0x2ee70  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2ee75  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x2ee7a  call     instance void Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_HasOutputs(bool value)
0x2ee7f  ldarg.0
0x2ee80  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__2
0x2ee85  brtrue.s loc_2EEAB
0x2ee87  ldc.i4.0
0x2ee88  ldtoken  [mscorlib]System.Boolean
0x2ee8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ee92  ldtoken  Microsoft.Crm.Workflow.ObjectModel.CustomStepBase
0x2ee97  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ee9c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2eea1  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x2eea6  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__2
0x2eeab  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__2
0x2eeb0  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x2eeb5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__2
0x2eeba  ldarg.1
0x2eebb  ldstr    aIsinvalid// "isInvalid"
0x2eec0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2eec5  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x2eeca  call     instance void Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_IsInvalid(bool value)
0x2eecf  ldarg.0
0x2eed0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__3
0x2eed5  brtrue.s loc_2EEFB
0x2eed7  ldc.i4.0
0x2eed8  ldtoken  [mscorlib]System.Boolean
0x2eedd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2eee2  ldtoken  Microsoft.Crm.Workflow.ObjectModel.CustomStepBase
0x2eee7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2eeec  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2eef1  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x2eef6  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__3
0x2eefb  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__3
0x2ef00  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x2ef05  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__32::<>p__3
0x2ef0a  ldarg.1
0x2ef0b  ldstr    aIswebpluginact// "isWebPluginActivity"
0x2ef10  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2ef15  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x2ef1a  call     instance void Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_IsWebPluginActivity(bool value)
0x2ef1f  ldarg.1
0x2ef20  ldstr    aOutputs_0// "outputs"
0x2ef25  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2ef2a  brfalse.s loc_2EF80
0x2ef2c  ldarg.0
0x2ef2d  ldarg.1
0x2ef2e  ldstr    aOutputs_0// "outputs"
0x2ef33  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2ef38  ldsfld   class [mscorlib]System.Func`2<object, string> <>c::<>9__32_0
0x2ef3d  dup
0x2ef3e  brtrue.s loc_2EF57
0x2ef40  pop
0x2ef41  ldsfld   class <>c <>c::<>9
0x2ef46  ldftn    instance string <>c::<InitializeFromDynamic>b__32_0(object property)
0x2ef4c  newobj   instance void class [mscorlib]System.Func`2<object, string>::.ctor(object, native int)
0x2ef51  dup
0x2ef52  stsfld   class [mscorlib]System.Func`2<object, string> <>c::<>9__32_0
0x2ef57  ldsfld   class [mscorlib]System.Func`2<object, class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> <>c::<>9__32_1
0x2ef5c  dup
0x2ef5d  brtrue.s loc_2EF76
0x2ef5f  pop
0x2ef60  ldsfld   class <>c <>c::<>9
0x2ef65  ldftn    instance class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase <>c::<InitializeFromDynamic>b__32_1(object parameterObject)
0x2ef6b  newobj   instance void class [mscorlib]System.Func`2<object, class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::.ctor(object, native int)
0x2ef70  dup
0x2ef71  stsfld   class [mscorlib]System.Func`2<object, class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> <>c::<>9__32_1
0x2ef76  call     T0x2B00002D
0x2ef7b  call     instance void Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_Outputs(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> value)
0x2ef80  ret
```
