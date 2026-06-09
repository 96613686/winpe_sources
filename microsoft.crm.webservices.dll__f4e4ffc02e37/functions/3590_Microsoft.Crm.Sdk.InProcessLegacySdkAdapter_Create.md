# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Create

- ea: `0x3590`
- end: `0x37b6`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Create`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x3500`
- `0x3590`
- `0x83b0`
- `0xfc10`
- `0x10140`

## string_xrefs

- `0x35f5`: `Microsoft.Crm.SdkTypeProxy.CreateRequest`
- `0x3606`: `Microsoft.Crm.SdkTypeProxy.TargetCreateDynamic`

## pseudocode

```c

```

## disassembly

```asm
0x3590  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x3595  stloc.0
0x3596  ldloc.0
0x3597  ldarg.0
0x3598  stfld    class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter <>c__DisplayClass3_0::<>4__this
0x359d  ldloc.0
0x359e  ldarg.1
0x359f  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity <>c__DisplayClass3_0::entity
0x35a4  ldloc.0
0x35a5  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity <>c__DisplayClass3_0::entity
0x35aa  ldstr    aEntity_0// "entity"
0x35af  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x35b4  ldloc.0
0x35b5  ldloc.0
0x35b6  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity <>c__DisplayClass3_0::entity
0x35bb  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x35c0  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass3_0::de
0x35c5  ldloc.0
0x35c6  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass3_0::de
0x35cb  brtrue.s loc_35DF
0x35cd  ldarg.0
0x35ce  ldloc.0
0x35cf  ldftn    instance void <>c__DisplayClass3_0::<Create>b__0()
0x35d5  newobj   instance void ExecuteInProcessIdentityAction::.ctor(object object, native int method)
0x35da  call     instance void Microsoft.Crm.Sdk.LegacySdkAdapterBase::ExecuteInProcessIdentity(class ExecuteInProcessIdentityAction actions)
0x35df  ldloc.0
0x35e0  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass3_0::de
0x35e5  ldstr    aEntity_0// "entity"
0x35ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x35ef  ldarg.0
0x35f0  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly()
0x35f5  ldstr    aMicrosoftCrmSd_1// "Microsoft.Crm.SdkTypeProxy.CreateReques"...
0x35fa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x35ff  stloc.1
0x3600  ldarg.0
0x3601  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly()
0x3606  ldstr    aMicrosoftCrmSd_2// "Microsoft.Crm.SdkTypeProxy.TargetCreate"...
0x360b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x3610  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x3615  stloc.2
0x3616  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__3::<>p__0
0x361b  brtrue.s loc_3656
0x361d  ldc.i4.0
0x361e  ldstr    aEntity// "Entity"
0x3623  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3628  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x362d  ldc.i4.2
0x362e  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3633  dup
0x3634  ldc.i4.0
0x3635  ldc.i4.0
0x3636  ldnull
0x3637  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x363c  stelem.ref
0x363d  dup
0x363e  ldc.i4.1
0x363f  ldc.i4.1
0x3640  ldnull
0x3641  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3646  stelem.ref
0x3647  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x364c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>>::Create(!!T0)
0x3651  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__3::<>p__0
0x3656  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__3::<>p__0
0x365b  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>>::Target
0x3660  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__3::<>p__0
0x3665  ldloc.2
0x3666  ldloc.0
0x3667  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass3_0::de
0x366c  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>::Invoke(char, var<u1>, !!T0)
0x3671  pop
0x3672  ldloc.1
0x3673  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x3678  stloc.3
0x3679  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__3::<>p__1
0x367e  brtrue.s loc_36B9
0x3680  ldc.i4.0
0x3681  ldstr    aTarget// "Target"
0x3686  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x368b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3690  ldc.i4.2
0x3691  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3696  dup
0x3697  ldc.i4.0
0x3698  ldc.i4.0
0x3699  ldnull
0x369a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x369f  stelem.ref
0x36a0  dup
0x36a1  ldc.i4.1
0x36a2  ldc.i4.0
0x36a3  ldnull
0x36a4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x36a9  stelem.ref
0x36aa  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x36af  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Create(!!T0)
0x36b4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__3::<>p__1
0x36b9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__3::<>p__1
0x36be  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Target
0x36c3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__3::<>p__1
0x36c8  ldloc.3
0x36c9  ldloc.2
0x36ca  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>::Invoke(char, var<u1>, !!T0)
0x36cf  pop
0x36d0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object, object>> <>o__3::<>p__2
0x36d5  brtrue.s loc_3711
0x36d7  ldc.i4.2
0x36d8  ldstr    aExecute// "Execute"
0x36dd  ldnull
0x36de  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x36e3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36e8  ldc.i4.2
0x36e9  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x36ee  dup
0x36ef  ldc.i4.0
0x36f0  ldc.i4.1
0x36f1  ldnull
0x36f2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x36f7  stelem.ref
0x36f8  dup
0x36f9  ldc.i4.1
0x36fa  ldc.i4.0
0x36fb  ldnull
0x36fc  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3701  stelem.ref
0x3702  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3707  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object, object>>::Create(!!T0)
0x370c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object, object>> <>o__3::<>p__2
0x3711  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object, object>> <>o__3::<>p__2
0x3716  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object, object>>::Target
0x371b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object, object>> <>o__3::<>p__2
0x3720  ldarg.0
0x3721  ldloc.3
0x3722  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object, object>::Invoke(char, var<u1>, !!T0)
0x3727  stloc.s  4
0x3729  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid>> <>o__3::<>p__4
0x372e  brtrue.s loc_3755
0x3730  ldc.i4.s 0x10
0x3732  ldtoken  [mscorlib]System.Guid
0x3737  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x373c  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3741  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3746  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x374b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid>>::Create(!!T0)
0x3750  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid>> <>o__3::<>p__4
0x3755  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid>> <>o__3::<>p__4
0x375a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid>>::Target
0x375f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid>> <>o__3::<>p__4
0x3764  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__3::<>p__3
0x3769  brtrue.s loc_379A
0x376b  ldc.i4.0
0x376c  ldstr    aId// "id"
0x3771  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3776  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x377b  ldc.i4.1
0x377c  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3781  dup
0x3782  ldc.i4.0
0x3783  ldc.i4.0
0x3784  ldnull
0x3785  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x378a  stelem.ref
0x378b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3790  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x3795  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__3::<>p__3
0x379a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__3::<>p__3
0x379f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x37a4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__3::<>p__3
0x37a9  ldloc.s  4
0x37ab  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x37b0  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid>::Invoke(bool, var<u1>)
0x37b5  ret
```
