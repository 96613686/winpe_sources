# Microsoft.Crm.Workflow.ObjectModel.ControlStep::InitializeFromDynamic

- ea: `0x34a90`
- end: `0x34f9a`
- name: `Microsoft.Crm.Workflow.ObjectModel.ControlStep::InitializeFromDynamic`
- size: `1290`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x30ca0`
- `0x30ef0`
- `0x34a90`

## string_xrefs

- `0x34b2b`: `classId`

## pseudocode

```c

```

## disassembly

```asm
0x34a90  ldarg.1
0x34a91  brfalse  loc_34F99
0x34a96  ldarg.0
0x34a97  ldarg.1
0x34a98  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::InitializeFromDynamic(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> deserializedObject)
0x34a9d  ldarg.0
0x34a9e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__0
0x34aa3  brtrue.s loc_34AC9
0x34aa5  ldc.i4.0
0x34aa6  ldtoken  [mscorlib]System.String
0x34aab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34ab0  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34ab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34aba  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34abf  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x34ac4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__0
0x34ac9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__0
0x34ace  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x34ad3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__0
0x34ad8  ldarg.0
0x34ad9  ldarg.1
0x34ada  ldstr    aControlid// "controlId"
0x34adf  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34ae4  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x34ae9  stfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::controlId
0x34aee  ldarg.0
0x34aef  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__1
0x34af4  brtrue.s loc_34B1A
0x34af6  ldc.i4.0
0x34af7  ldtoken  [mscorlib]System.String
0x34afc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34b01  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34b06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34b0b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34b10  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x34b15  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__1
0x34b1a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__1
0x34b1f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x34b24  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__1
0x34b29  ldarg.0
0x34b2a  ldarg.1
0x34b2b  ldstr    aClassid// "classId"
0x34b30  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34b35  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x34b3a  stfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::classId
0x34b3f  ldarg.0
0x34b40  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__2
0x34b45  brtrue.s loc_34B6B
0x34b47  ldc.i4.0
0x34b48  ldtoken  [mscorlib]System.String
0x34b4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34b52  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34b57  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34b5c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34b61  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x34b66  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__2
0x34b6b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__2
0x34b70  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x34b75  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__2
0x34b7a  ldarg.0
0x34b7b  ldarg.1
0x34b7c  ldstr    aDatafieldname// "dataFieldName"
0x34b81  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34b86  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x34b8b  stfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::dataFieldName
0x34b90  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep>> <>o__46::<>p__3
0x34b95  brtrue.s loc_34BE1
0x34b97  ldc.i4   0x100
0x34b9c  ldstr    aTryparse// "TryParse"
0x34ba1  ldnull
0x34ba2  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34ba7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34bac  ldc.i4.3
0x34bad  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x34bb2  dup
0x34bb3  ldc.i4.0
0x34bb4  ldc.i4.s 0x21
0x34bb6  ldnull
0x34bb7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x34bbc  stelem.ref
0x34bbd  dup
0x34bbe  ldc.i4.1
0x34bbf  ldc.i4.0
0x34bc0  ldnull
0x34bc1  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x34bc6  stelem.ref
0x34bc7  dup
0x34bc8  ldc.i4.2
0x34bc9  ldc.i4.s 0x11
0x34bcb  ldnull
0x34bcc  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x34bd1  stelem.ref
0x34bd2  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x34bd7  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep>>::Create(!!T0)
0x34bdc  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep>> <>o__46::<>p__3
0x34be1  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep>> <>o__46::<>p__3
0x34be6  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep>>::Target
0x34beb  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep>> <>o__46::<>p__3
0x34bf0  ldtoken  Microsoft.Crm.Workflow.ObjectModel.SystemStep
0x34bf5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34bfa  ldarg.0
0x34bfb  ldarg.1
0x34bfc  ldstr    aSystemsteptype// "systemStepType"
0x34c01  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34c06  ldarg.0
0x34c07  ldflda   valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep Microsoft.Crm.Workflow.ObjectModel.ControlStep::systemStepType
0x34c0c  callvirt instance void class <>A{00000008}`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, valuetype Microsoft.Crm.Workflow.ObjectModel.SystemStep>::Invoke(var<u1>, !!T0, var<u1>, void)
0x34c11  ldarg.0
0x34c12  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__4
0x34c17  brtrue.s loc_34C3D
0x34c19  ldc.i4.0
0x34c1a  ldtoken  [mscorlib]System.Boolean
0x34c1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34c24  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34c29  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34c2e  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34c33  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x34c38  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__4
0x34c3d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__4
0x34c42  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x34c47  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__4
0x34c4c  ldarg.0
0x34c4d  ldarg.1
0x34c4e  ldstr    aIssystemcontro// "isSystemControl"
0x34c53  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34c58  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x34c5d  stfld    bool Microsoft.Crm.Workflow.ObjectModel.ControlStep::isSystemControl
0x34c62  ldarg.0
0x34c63  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__5
0x34c68  brtrue.s loc_34C8E
0x34c6a  ldc.i4.0
0x34c6b  ldtoken  [mscorlib]System.String
0x34c70  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34c75  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34c7a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34c7f  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34c84  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x34c89  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__5
0x34c8e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__5
0x34c93  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x34c98  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__5
0x34c9d  ldarg.0
0x34c9e  ldarg.1
0x34c9f  ldstr    aParameters// "parameters"
0x34ca4  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34ca9  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x34cae  stfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::parameters
0x34cb3  ldarg.0
0x34cb4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__6
0x34cb9  brtrue.s loc_34CDF
0x34cbb  ldc.i4.0
0x34cbc  ldtoken  [mscorlib]System.String
0x34cc1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34cc6  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34ccb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34cd0  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34cd5  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x34cda  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__6
0x34cdf  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__6
0x34ce4  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x34ce9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__46::<>p__6
0x34cee  ldarg.0
0x34cef  ldarg.1
0x34cf0  ldstr    aControldisplay// "controlDisplayName"
0x34cf5  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34cfa  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>::Invoke(bool, var<u1>)
0x34cff  stfld    string Microsoft.Crm.Workflow.ObjectModel.ControlStep::controlDisplayName
0x34d04  ldarg.1
0x34d05  ldstr    aControltype// "controlType"
0x34d0a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x34d0f  brfalse  loc_34DC5
0x34d14  ldarg.0
0x34d15  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__46::<>p__8
0x34d1a  brtrue.s loc_34D40
0x34d1c  ldc.i4.0
0x34d1d  ldtoken  [mscorlib]System.Int32
0x34d22  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d27  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34d2c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d31  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34d36  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>>::Create(!!T0)
0x34d3b  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__46::<>p__8
0x34d40  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__46::<>p__8
0x34d45  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>>::Target
0x34d4a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>> <>o__46::<>p__8
0x34d4f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__7
0x34d54  brtrue.s loc_34D91
0x34d56  ldc.i4.0
0x34d57  ldstr    aParse// "Parse"
0x34d5c  ldnull
0x34d5d  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34d62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34d67  ldc.i4.2
0x34d68  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x34d6d  dup
0x34d6e  ldc.i4.0
0x34d6f  ldc.i4.s 0x21
0x34d71  ldnull
0x34d72  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x34d77  stelem.ref
0x34d78  dup
0x34d79  ldc.i4.1
0x34d7a  ldc.i4.0
0x34d7b  ldnull
0x34d7c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x34d81  stelem.ref
0x34d82  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x34d87  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x34d8c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__7
0x34d91  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__7
0x34d96  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x34d9b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__7
0x34da0  ldtoken  [mscorlib]System.Int32
0x34da5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34daa  ldarg.0
0x34dab  ldarg.1
0x34dac  ldstr    aControltype// "controlType"
0x34db1  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34db6  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>::Invoke(char, var<u1>, !!T0)
0x34dbb  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, int32>::Invoke(bool, var<u1>)
0x34dc0  stfld    int32 Microsoft.Crm.Workflow.ObjectModel.ControlStep::controlType
0x34dc5  ldarg.1
0x34dc6  ldstr    aIsunbound// "isUnbound"
0x34dcb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x34dd0  brfalse.s loc_34E23
0x34dd2  ldarg.0
0x34dd3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__9
0x34dd8  brtrue.s loc_34DFE
0x34dda  ldc.i4.0
0x34ddb  ldtoken  [mscorlib]System.Boolean
0x34de0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34de5  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34dea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34def  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34df4  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x34df9  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__9
0x34dfe  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__9
0x34e03  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x34e08  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__46::<>p__9
0x34e0d  ldarg.0
0x34e0e  ldarg.1
0x34e0f  ldstr    aIsunbound// "isUnbound"
0x34e14  call     instance object Microsoft.Crm.Workflow.ObjectModel.StepBase::GetProperty(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string deserializedObject)
0x34e19  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x34e1e  stfld    bool Microsoft.Crm.Workflow.ObjectModel.ControlStep::isUnbound
0x34e23  ldarg.1
0x34e24  ldstr    aEntity// "entity"
0x34e29  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x34e2e  brfalse  loc_34F99
0x34e33  ldarg.1
0x34e34  ldstr    aEntity// "entity"
0x34e39  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x34e3e  stloc.0
0x34e3f  ldarg.0
0x34e40  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__46::<>p__12
0x34e45  brtrue.s loc_34E6B
0x34e47  ldc.i4.0
0x34e48  ldtoken  Microsoft.Crm.Workflow.Expressions.EntityBase
0x34e4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e52  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34e57  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e5c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34e61  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>>::Create(!!T0)
0x34e66  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__46::<>p__12
0x34e6b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__46::<>p__12
0x34e70  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>>::Target
0x34e75  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class Microsoft.Crm.Workflow.Expressions.EntityBase>> <>o__46::<>p__12
0x34e7a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__11
0x34e7f  brtrue.s loc_34EBC
0x34e81  ldc.i4.0
0x34e82  ldstr    aBuildentity// "BuildEntity"
0x34e87  ldnull
0x34e88  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x34e8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e92  ldc.i4.2
0x34e93  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x34e98  dup
0x34e99  ldc.i4.0
0x34e9a  ldc.i4.s 0x21
0x34e9c  ldnull
0x34e9d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x34ea2  stelem.ref
0x34ea3  dup
0x34ea4  ldc.i4.1
0x34ea5  ldc.i4.0
0x34ea6  ldnull
0x34ea7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x34eac  stelem.ref
0x34ead  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x34eb2  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Create(!!T0)
0x34eb7  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__11
0x34ebc  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__11
0x34ec1  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>>::Target
0x34ec6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, class [mscorlib]System.Type, object, object>> <>o__46::<>p__11
0x34ecb  ldtoken  Microsoft.Crm.Workflow.ObjectModel.NullObjectsFactory
0x34ed0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34ed5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__46::<>p__10
0x34eda  brtrue.s loc_34F10
0x34edc  ldc.i4.0
0x34edd  ldtoken  Microsoft.Crm.Workflow.ObjectModel.ControlStep
  ... truncated ...
```
