# <DropTemplateDatabaseAsync>d__22::MoveNext

- ea: `0x40d10`
- end: `0x412bb`
- name: `<DropTemplateDatabaseAsync>d__22::MoveNext`
- size: `1451`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x39520`
- `0x39bf0`
- `0x3f450`
- `0x40d10`

## string_xrefs

- `0x40d41`: `templateIdentifier`
- `0x40ede`: `SpartanTraceCompleted`
- `0x4108e`: `SpartanTraceCompleted`
- `0x40dcf`: `TemplateIdentifier`
- `0x40d4c`: `DropTemplateDatabaseAsync`
- `0x4102a`: `TemplateExists`

## pseudocode

```c

```

## disassembly

```asm
0x40d10  ldarg.0
0x40d11  ldfld    int32 <DropTemplateDatabaseAsync>d__22::<>1__state
0x40d16  stloc.0
0x40d17  ldarg.0
0x40d18  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanService <DropTemplateDatabaseAsync>d__22::<>4__this
0x40d1d  stloc.1
0x40d1e  ldloc.0
0x40d1f  brfalse  loc_40E2F
0x40d24  ldloc.0
0x40d25  ldc.i4.1
0x40d26  beq      loc_40F9A
0x40d2b  ldarg.0
0x40d2c  ldfld    string <DropTemplateDatabaseAsync>d__22::azureRegion
0x40d31  ldstr    aAzureregion_1// "azureRegion"
0x40d36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x40d3b  ldarg.0
0x40d3c  ldfld    string <DropTemplateDatabaseAsync>d__22::templateIdentifier
0x40d41  ldstr    aTemplateidenti// "templateIdentifier"
0x40d46  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x40d4b  ldarg.0
0x40d4c  ldstr    aDroptemplateda// "DropTemplateDatabaseAsync"
0x40d51  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x40d56  stfld    class SpartanFunctionLogger <DropTemplateDatabaseAsync>d__22::<logger>5__2
0x40d5b  ldarg.0
0x40d5c  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x40d61  stfld    object <DropTemplateDatabaseAsync>d__22::<inputData>5__3
0x40d66  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__0
0x40d6b  brtrue.s loc_40DA6
0x40d6d  ldc.i4.0
0x40d6e  ldstr    aTargetazurereg// "TargetAzureRegion"
0x40d73  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x40d78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40d7d  ldc.i4.2
0x40d7e  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40d83  dup
0x40d84  ldc.i4.0
0x40d85  ldc.i4.0
0x40d86  ldnull
0x40d87  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40d8c  stelem.ref
0x40d8d  dup
0x40d8e  ldc.i4.1
0x40d8f  ldc.i4.1
0x40d90  ldnull
0x40d91  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40d96  stelem.ref
0x40d97  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x40d9c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x40da1  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__0
0x40da6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__0
0x40dab  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x40db0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__0
0x40db5  ldarg.0
0x40db6  ldfld    object <DropTemplateDatabaseAsync>d__22::<inputData>5__3
0x40dbb  ldarg.0
0x40dbc  ldfld    string <DropTemplateDatabaseAsync>d__22::azureRegion
0x40dc1  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x40dc6  pop
0x40dc7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__1
0x40dcc  brtrue.s loc_40E07
0x40dce  ldc.i4.0
0x40dcf  ldstr    aTemplateidenti_0// "TemplateIdentifier"
0x40dd4  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x40dd9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40dde  ldc.i4.2
0x40ddf  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40de4  dup
0x40de5  ldc.i4.0
0x40de6  ldc.i4.0
0x40de7  ldnull
0x40de8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40ded  stelem.ref
0x40dee  dup
0x40def  ldc.i4.1
0x40df0  ldc.i4.1
0x40df1  ldnull
0x40df2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40df7  stelem.ref
0x40df8  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x40dfd  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x40e02  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__1
0x40e07  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__1
0x40e0c  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x40e11  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__22::<>p__1
0x40e16  ldarg.0
0x40e17  ldfld    object <DropTemplateDatabaseAsync>d__22::<inputData>5__3
0x40e1c  ldarg.0
0x40e1d  ldfld    string <DropTemplateDatabaseAsync>d__22::templateIdentifier
0x40e22  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x40e27  pop
0x40e28  ldarg.0
0x40e29  ldc.i4.0
0x40e2a  stfld    int32 <DropTemplateDatabaseAsync>d__22::<>7__wrap4
0x40e2f  nop
0x40e30  ldloc.0
0x40e31  brfalse.s loc_40EAA
0x40e33  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x40e38  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DropTemplateDatabaseRequestProperty::.ctor()
0x40e3d  dup
0x40e3e  ldarg.0
0x40e3f  ldfld    string <DropTemplateDatabaseAsync>d__22::azureRegion
0x40e44  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x40e49  dup
0x40e4a  ldarg.0
0x40e4b  ldfld    string <DropTemplateDatabaseAsync>d__22::templateIdentifier
0x40e50  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.TemplateDatabaseRequestProperty::set_TemplateKey(string)
0x40e55  ldloca.s 3
0x40e57  initobj  [mscorlib]System.TimeSpan
0x40e5d  ldloc.3
0x40e5e  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DropTemplateDatabaseParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DropTemplateDatabaseRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x40e63  ldarg.0
0x40e64  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DropTemplateDatabaseAsync>d__22::cancellationToken
0x40e69  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::DropTemplateDatabaseAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DropTemplateDatabaseParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x40e6e  ldc.i4.0
0x40e6f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::ConfigureAwait(!!T0)
0x40e74  stloc.s  4
0x40e76  ldloca.s 4
0x40e78  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetAwaiter()
0x40e7d  stloc.2
0x40e7e  ldloca.s 2
0x40e80  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::get_IsCompleted()
0x40e85  brtrue.s loc_40EC6
0x40e87  ldarg.0
0x40e88  ldc.i4.0
0x40e89  dup
0x40e8a  stloc.0
0x40e8b  stfld    int32 <DropTemplateDatabaseAsync>d__22::<>1__state
0x40e90  ldarg.0
0x40e91  ldloc.2
0x40e92  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <DropTemplateDatabaseAsync>d__22::<>u__1
0x40e97  ldarg.0
0x40e98  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DropTemplateDatabaseAsync>d__22::<>t__builder
0x40e9d  ldloca.s 2
0x40e9f  ldarg.0
0x40ea0  call     T0x2B0000EF
0x40ea5  leave    loc_412BA
0x40eaa  ldarg.0
0x40eab  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <DropTemplateDatabaseAsync>d__22::<>u__1
0x40eb0  stloc.2
0x40eb1  ldarg.0
0x40eb2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <DropTemplateDatabaseAsync>d__22::<>u__1
0x40eb7  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>
0x40ebd  ldarg.0
0x40ebe  ldc.i4.m1
0x40ebf  dup
0x40ec0  stloc.0
0x40ec1  stfld    int32 <DropTemplateDatabaseAsync>d__22::<>1__state
0x40ec6  ldloca.s 2
0x40ec8  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetResult()
0x40ecd  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x40ed2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__22::<>p__2
0x40ed7  brtrue.s loc_40F35
0x40ed9  ldc.i4   0x100
0x40ede  ldstr    aSpartantraceco// "SpartanTraceCompleted"
0x40ee3  ldnull
0x40ee4  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x40ee9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40eee  ldc.i4.5
0x40eef  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40ef4  dup
0x40ef5  ldc.i4.0
0x40ef6  ldc.i4.1
0x40ef7  ldnull
0x40ef8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40efd  stelem.ref
0x40efe  dup
0x40eff  ldc.i4.1
0x40f00  ldc.i4.1
0x40f01  ldnull
0x40f02  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40f07  stelem.ref
0x40f08  dup
0x40f09  ldc.i4.2
0x40f0a  ldc.i4.1
0x40f0b  ldnull
0x40f0c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40f11  stelem.ref
0x40f12  dup
0x40f13  ldc.i4.3
0x40f14  ldc.i4.0
0x40f15  ldnull
0x40f16  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40f1b  stelem.ref
0x40f1c  dup
0x40f1d  ldc.i4.4
0x40f1e  ldc.i4.1
0x40f1f  ldnull
0x40f20  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40f25  stelem.ref
0x40f26  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x40f2b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>>::Create(!!T0)
0x40f30  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__22::<>p__2
0x40f35  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__22::<>p__2
0x40f3a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>>::Target
0x40f3f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__22::<>p__2
0x40f44  ldarg.0
0x40f45  ldfld    class SpartanFunctionLogger <DropTemplateDatabaseAsync>d__22::<logger>5__2
0x40f4a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40f4f  ldsfld   string [mscorlib]System.String::Empty
0x40f54  ldarg.0
0x40f55  ldfld    object <DropTemplateDatabaseAsync>d__22::<inputData>5__3
0x40f5a  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x40f5f  callvirt instance void class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>::Invoke(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x40f64  leave.s  loc_40F79
0x40f66  stloc.s  5
0x40f68  ldarg.0
0x40f69  ldloc.s  5
0x40f6b  stfld    object <DropTemplateDatabaseAsync>d__22::<>7__wrap3
0x40f70  ldarg.0
0x40f71  ldc.i4.1
0x40f72  stfld    int32 <DropTemplateDatabaseAsync>d__22::<>7__wrap4
0x40f77  leave.s  loc_40F79
0x40f79  ldarg.0
0x40f7a  ldfld    int32 <DropTemplateDatabaseAsync>d__22::<>7__wrap4
0x40f7f  stloc.s  6
0x40f81  ldloc.s  6
0x40f83  ldc.i4.1
0x40f84  bne.un   loc_41285
0x40f89  ldarg.0
0x40f8a  ldarg.0
0x40f8b  ldfld    object <DropTemplateDatabaseAsync>d__22::<>7__wrap3
0x40f90  castclass [mscorlib]System.Exception
0x40f95  stfld    class [mscorlib]System.Exception <DropTemplateDatabaseAsync>d__22::<ex>5__6
0x40f9a  nop
0x40f9b  ldloc.0
0x40f9c  ldc.i4.1
0x40f9d  beq.s    loc_40FF5
0x40f9f  ldloc.1
0x40fa0  ldarg.0
0x40fa1  ldfld    string <DropTemplateDatabaseAsync>d__22::azureRegion
0x40fa6  ldarg.0
0x40fa7  ldfld    string <DropTemplateDatabaseAsync>d__22::templateIdentifier
0x40fac  ldarg.0
0x40fad  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DropTemplateDatabaseAsync>d__22::cancellationToken
0x40fb2  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::DoesTemplateDatabaseExistAsync(string azureRegion, string templateIdentifier, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x40fb7  ldc.i4.0
0x40fb8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x40fbd  stloc.s  0xA
0x40fbf  ldloca.s 0xA
0x40fc1  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x40fc6  stloc.s  9
0x40fc8  ldloca.s 9
0x40fca  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x40fcf  brtrue.s loc_41012
0x40fd1  ldarg.0
0x40fd2  ldc.i4.1
0x40fd3  dup
0x40fd4  stloc.0
0x40fd5  stfld    int32 <DropTemplateDatabaseAsync>d__22::<>1__state
0x40fda  ldarg.0
0x40fdb  ldloc.s  9
0x40fdd  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <DropTemplateDatabaseAsync>d__22::<>u__2
0x40fe2  ldarg.0
0x40fe3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DropTemplateDatabaseAsync>d__22::<>t__builder
0x40fe8  ldloca.s 9
0x40fea  ldarg.0
0x40feb  call     T0x2B0000F0
0x40ff0  leave    loc_412BA
0x40ff5  ldarg.0
0x40ff6  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <DropTemplateDatabaseAsync>d__22::<>u__2
0x40ffb  stloc.s  9
0x40ffd  ldarg.0
0x40ffe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <DropTemplateDatabaseAsync>d__22::<>u__2
0x41003  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x41009  ldarg.0
0x4100a  ldc.i4.m1
0x4100b  dup
0x4100c  stloc.0
0x4100d  stfld    int32 <DropTemplateDatabaseAsync>d__22::<>1__state
0x41012  ldloca.s 9
0x41014  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x41019  stloc.s  7
0x4101b  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x41020  stloc.s  8
0x41022  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool, object>> <>o__22::<>p__3
0x41027  brtrue.s loc_41062
0x41029  ldc.i4.0
0x4102a  ldstr    aTemplateexists// "TemplateExists"
0x4102f  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41034  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x41039  ldc.i4.2
0x4103a  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x4103f  dup
0x41040  ldc.i4.0
0x41041  ldc.i4.0
0x41042  ldnull
0x41043  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41048  stelem.ref
0x41049  dup
0x4104a  ldc.i4.1
0x4104b  ldc.i4.1
0x4104c  ldnull
0x4104d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41052  stelem.ref
0x41053  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x41058  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool, object>>::Create(!!T0)
0x4105d  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool, object>> <>o__22::<>p__3
0x41062  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool, object>> <>o__22::<>p__3
0x41067  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool, object>>::Target
0x4106c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool, object>> <>o__22::<>p__3
  ... truncated ...
```
