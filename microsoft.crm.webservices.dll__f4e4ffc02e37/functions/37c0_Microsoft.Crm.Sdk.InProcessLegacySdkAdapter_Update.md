# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Update

- ea: `0x37c0`
- end: `0x395c`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Update`
- size: `412`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3500`
- `0x37c0`
- `0x83b0`
- `0xfc60`
- `0x10140`

## string_xrefs

- `0x3825`: `Microsoft.Crm.SdkTypeProxy.UpdateRequest`
- `0x3836`: `Microsoft.Crm.SdkTypeProxy.TargetUpdateDynamic`

## pseudocode

```c

```

## disassembly

```asm
0x37c0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x37c5  stloc.0
0x37c6  ldloc.0
0x37c7  ldarg.0
0x37c8  stfld    class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter <>c__DisplayClass4_0::<>4__this
0x37cd  ldloc.0
0x37ce  ldarg.1
0x37cf  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity <>c__DisplayClass4_0::entity
0x37d4  ldloc.0
0x37d5  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity <>c__DisplayClass4_0::entity
0x37da  ldstr    aEntity_0// "entity"
0x37df  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x37e4  ldloc.0
0x37e5  ldloc.0
0x37e6  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity <>c__DisplayClass4_0::entity
0x37eb  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x37f0  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass4_0::de
0x37f5  ldloc.0
0x37f6  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass4_0::de
0x37fb  brtrue.s loc_380F
0x37fd  ldarg.0
0x37fe  ldloc.0
0x37ff  ldftn    instance void <>c__DisplayClass4_0::<Update>b__0()
0x3805  newobj   instance void ExecuteInProcessIdentityAction::.ctor(object object, native int method)
0x380a  call     instance void Microsoft.Crm.Sdk.LegacySdkAdapterBase::ExecuteInProcessIdentity(class ExecuteInProcessIdentityAction actions)
0x380f  ldloc.0
0x3810  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass4_0::de
0x3815  ldstr    aEntity_0// "entity"
0x381a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x381f  ldarg.0
0x3820  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly()
0x3825  ldstr    aMicrosoftCrmSd_3// "Microsoft.Crm.SdkTypeProxy.UpdateReques"...
0x382a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x382f  stloc.1
0x3830  ldarg.0
0x3831  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly()
0x3836  ldstr    aMicrosoftCrmSd_4// "Microsoft.Crm.SdkTypeProxy.TargetUpdate"...
0x383b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x3840  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x3845  stloc.2
0x3846  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__4::<>p__0
0x384b  brtrue.s loc_3886
0x384d  ldc.i4.0
0x384e  ldstr    aEntity// "Entity"
0x3853  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3858  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x385d  ldc.i4.2
0x385e  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3863  dup
0x3864  ldc.i4.0
0x3865  ldc.i4.0
0x3866  ldnull
0x3867  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x386c  stelem.ref
0x386d  dup
0x386e  ldc.i4.1
0x386f  ldc.i4.1
0x3870  ldnull
0x3871  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3876  stelem.ref
0x3877  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x387c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>>::Create(!!T0)
0x3881  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__4::<>p__0
0x3886  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__4::<>p__0
0x388b  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>>::Target
0x3890  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>> <>o__4::<>p__0
0x3895  ldloc.2
0x3896  ldloc.0
0x3897  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity <>c__DisplayClass4_0::de
0x389c  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity, object>::Invoke(char, var<u1>, !!T0)
0x38a1  pop
0x38a2  ldloc.1
0x38a3  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x38a8  stloc.3
0x38a9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__4::<>p__1
0x38ae  brtrue.s loc_38E9
0x38b0  ldc.i4.0
0x38b1  ldstr    aTarget// "Target"
0x38b6  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x38bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38c0  ldc.i4.2
0x38c1  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x38c6  dup
0x38c7  ldc.i4.0
0x38c8  ldc.i4.0
0x38c9  ldnull
0x38ca  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x38cf  stelem.ref
0x38d0  dup
0x38d1  ldc.i4.1
0x38d2  ldc.i4.0
0x38d3  ldnull
0x38d4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x38d9  stelem.ref
0x38da  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x38df  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Create(!!T0)
0x38e4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__4::<>p__1
0x38e9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__4::<>p__1
0x38ee  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Target
0x38f3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__4::<>p__1
0x38f8  ldloc.3
0x38f9  ldloc.2
0x38fa  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>::Invoke(char, var<u1>, !!T0)
0x38ff  pop
0x3900  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__4::<>p__2
0x3905  brtrue.s loc_3945
0x3907  ldc.i4   0x102
0x390c  ldstr    aExecute// "Execute"
0x3911  ldnull
0x3912  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3917  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x391c  ldc.i4.2
0x391d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3922  dup
0x3923  ldc.i4.0
0x3924  ldc.i4.1
0x3925  ldnull
0x3926  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x392b  stelem.ref
0x392c  dup
0x392d  ldc.i4.1
0x392e  ldc.i4.0
0x392f  ldnull
0x3930  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3935  stelem.ref
0x3936  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x393b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>>::Create(!!T0)
0x3940  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__4::<>p__2
0x3945  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__4::<>p__2
0x394a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>>::Target
0x394f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__4::<>p__2
0x3954  ldarg.0
0x3955  ldloc.3
0x3956  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>::Invoke(var<u1>, !!T0, var<u1>)
0x395b  ret
```
