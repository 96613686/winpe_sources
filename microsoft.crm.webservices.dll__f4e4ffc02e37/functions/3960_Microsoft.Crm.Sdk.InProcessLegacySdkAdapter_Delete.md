# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Delete

- ea: `0x3960`
- end: `0x3b05`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Delete`
- size: `421`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x3500`
- `0x3960`

## string_xrefs

- `0x397c`: `Microsoft.Crm.SdkTypeProxy.DeleteRequest`
- `0x398d`: `Microsoft.Crm.SdkTypeProxy.TargetDeleteDynamic`

## pseudocode

```c

```

## disassembly

```asm
0x3960  ldarg.1
0x3961  ldstr    aEntityname_0// "entityName"
0x3966  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x396b  ldarg.2
0x396c  ldstr    aId// "id"
0x3971  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3976  ldarg.0
0x3977  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly()
0x397c  ldstr    aMicrosoftCrmSd_5// "Microsoft.Crm.SdkTypeProxy.DeleteReques"...
0x3981  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x3986  stloc.0
0x3987  ldarg.0
0x3988  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly()
0x398d  ldstr    aMicrosoftCrmSd_6// "Microsoft.Crm.SdkTypeProxy.TargetDelete"...
0x3992  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x3997  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x399c  stloc.1
0x399d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__5::<>p__0
0x39a2  brtrue.s loc_39DD
0x39a4  ldc.i4.0
0x39a5  ldstr    aEntityid// "EntityId"
0x39aa  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x39af  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39b4  ldc.i4.2
0x39b5  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x39ba  dup
0x39bb  ldc.i4.0
0x39bc  ldc.i4.0
0x39bd  ldnull
0x39be  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x39c3  stelem.ref
0x39c4  dup
0x39c5  ldc.i4.1
0x39c6  ldc.i4.1
0x39c7  ldnull
0x39c8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x39cd  stelem.ref
0x39ce  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x39d3  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x39d8  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__5::<>p__0
0x39dd  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__5::<>p__0
0x39e2  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x39e7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__5::<>p__0
0x39ec  ldloc.1
0x39ed  ldarg.2
0x39ee  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x39f3  pop
0x39f4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__5::<>p__1
0x39f9  brtrue.s loc_3A34
0x39fb  ldc.i4.0
0x39fc  ldstr    aEntityname// "EntityName"
0x3a01  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3a06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a0b  ldc.i4.2
0x3a0c  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3a11  dup
0x3a12  ldc.i4.0
0x3a13  ldc.i4.0
0x3a14  ldnull
0x3a15  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3a1a  stelem.ref
0x3a1b  dup
0x3a1c  ldc.i4.1
0x3a1d  ldc.i4.1
0x3a1e  ldnull
0x3a1f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3a24  stelem.ref
0x3a25  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3a2a  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3a2f  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__5::<>p__1
0x3a34  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__5::<>p__1
0x3a39  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3a3e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__5::<>p__1
0x3a43  ldloc.1
0x3a44  ldarg.1
0x3a45  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3a4a  pop
0x3a4b  ldloc.0
0x3a4c  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x3a51  stloc.2
0x3a52  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__5::<>p__2
0x3a57  brtrue.s loc_3A92
0x3a59  ldc.i4.0
0x3a5a  ldstr    aTarget// "Target"
0x3a5f  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3a64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a69  ldc.i4.2
0x3a6a  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3a6f  dup
0x3a70  ldc.i4.0
0x3a71  ldc.i4.0
0x3a72  ldnull
0x3a73  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3a78  stelem.ref
0x3a79  dup
0x3a7a  ldc.i4.1
0x3a7b  ldc.i4.0
0x3a7c  ldnull
0x3a7d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3a82  stelem.ref
0x3a83  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3a88  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Create(!!T0)
0x3a8d  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__5::<>p__2
0x3a92  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__5::<>p__2
0x3a97  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Target
0x3a9c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__5::<>p__2
0x3aa1  ldloc.2
0x3aa2  ldloc.1
0x3aa3  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>::Invoke(char, var<u1>, !!T0)
0x3aa8  pop
0x3aa9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__5::<>p__3
0x3aae  brtrue.s loc_3AEE
0x3ab0  ldc.i4   0x102
0x3ab5  ldstr    aExecute// "Execute"
0x3aba  ldnull
0x3abb  ldtoken  Microsoft.Crm.Sdk.InProcessLegacySdkAdapter
0x3ac0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ac5  ldc.i4.2
0x3ac6  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3acb  dup
0x3acc  ldc.i4.0
0x3acd  ldc.i4.1
0x3ace  ldnull
0x3acf  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3ad4  stelem.ref
0x3ad5  dup
0x3ad6  ldc.i4.1
0x3ad7  ldc.i4.0
0x3ad8  ldnull
0x3ad9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3ade  stelem.ref
0x3adf  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3ae4  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>>::Create(!!T0)
0x3ae9  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__5::<>p__3
0x3aee  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__5::<>p__3
0x3af3  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>>::Target
0x3af8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>> <>o__5::<>p__3
0x3afd  ldarg.0
0x3afe  ldloc.2
0x3aff  callvirt instance void class [mscorlib]System.Action`3<class [System.Core]System.Runtime.CompilerServices.CallSite, class Microsoft.Crm.Sdk.InProcessLegacySdkAdapter, object>::Invoke(var<u1>, !!T0, var<u1>)
0x3b04  ret
```
