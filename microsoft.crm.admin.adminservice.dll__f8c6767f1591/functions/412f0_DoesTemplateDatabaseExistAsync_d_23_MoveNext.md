# <DoesTemplateDatabaseExistAsync>d__23::MoveNext

- ea: `0x412f0`
- end: `0x41679`
- name: `<DoesTemplateDatabaseExistAsync>d__23::MoveNext`
- size: `905`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x39520`
- `0x3f450`
- `0x412f0`

## string_xrefs

- `0x41313`: `templateIdentifier`
- `0x41511`: `SpartanTraceCompleted`
- `0x413a1`: `TemplateIdentifier`
- `0x4131e`: `DoesTemplateDatabaseExistAsync`

## pseudocode

```c

```

## disassembly

```asm
0x412f0  ldarg.0
0x412f1  ldfld    int32 <DoesTemplateDatabaseExistAsync>d__23::<>1__state
0x412f6  stloc.0
0x412f7  ldloc.0
0x412f8  brfalse  loc_413FA
0x412fd  ldarg.0
0x412fe  ldfld    string <DoesTemplateDatabaseExistAsync>d__23::azureRegion
0x41303  ldstr    aAzureregion_1// "azureRegion"
0x41308  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4130d  ldarg.0
0x4130e  ldfld    string <DoesTemplateDatabaseExistAsync>d__23::templateIdentifier
0x41313  ldstr    aTemplateidenti// "templateIdentifier"
0x41318  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4131d  ldarg.0
0x4131e  ldstr    aDoestemplateda// "DoesTemplateDatabaseExistAsync"
0x41323  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x41328  stfld    class SpartanFunctionLogger <DoesTemplateDatabaseExistAsync>d__23::<logger>5__2
0x4132d  ldarg.0
0x4132e  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x41333  stfld    object <DoesTemplateDatabaseExistAsync>d__23::<inputData>5__3
0x41338  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__0
0x4133d  brtrue.s loc_41378
0x4133f  ldc.i4.0
0x41340  ldstr    aTargetazurereg// "TargetAzureRegion"
0x41345  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x4134a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4134f  ldc.i4.2
0x41350  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41355  dup
0x41356  ldc.i4.0
0x41357  ldc.i4.0
0x41358  ldnull
0x41359  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4135e  stelem.ref
0x4135f  dup
0x41360  ldc.i4.1
0x41361  ldc.i4.1
0x41362  ldnull
0x41363  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41368  stelem.ref
0x41369  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4136e  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x41373  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__0
0x41378  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__0
0x4137d  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x41382  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__0
0x41387  ldarg.0
0x41388  ldfld    object <DoesTemplateDatabaseExistAsync>d__23::<inputData>5__3
0x4138d  ldarg.0
0x4138e  ldfld    string <DoesTemplateDatabaseExistAsync>d__23::azureRegion
0x41393  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41398  pop
0x41399  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__1
0x4139e  brtrue.s loc_413D9
0x413a0  ldc.i4.0
0x413a1  ldstr    aTemplateidenti_0// "TemplateIdentifier"
0x413a6  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x413ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x413b0  ldc.i4.2
0x413b1  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x413b6  dup
0x413b7  ldc.i4.0
0x413b8  ldc.i4.0
0x413b9  ldnull
0x413ba  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x413bf  stelem.ref
0x413c0  dup
0x413c1  ldc.i4.1
0x413c2  ldc.i4.1
0x413c3  ldnull
0x413c4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x413c9  stelem.ref
0x413ca  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x413cf  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x413d4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__1
0x413d9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__1
0x413de  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x413e3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__1
0x413e8  ldarg.0
0x413e9  ldfld    object <DoesTemplateDatabaseExistAsync>d__23::<inputData>5__3
0x413ee  ldarg.0
0x413ef  ldfld    string <DoesTemplateDatabaseExistAsync>d__23::templateIdentifier
0x413f4  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x413f9  pop
0x413fa  nop
0x413fb  ldloc.0
0x413fc  brfalse.s loc_41478
0x413fe  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x41403  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CheckTemplateDatabaseRequestProperty::.ctor()
0x41408  dup
0x41409  ldarg.0
0x4140a  ldfld    string <DoesTemplateDatabaseExistAsync>d__23::azureRegion
0x4140f  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x41414  dup
0x41415  ldarg.0
0x41416  ldfld    string <DoesTemplateDatabaseExistAsync>d__23::templateIdentifier
0x4141b  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.TemplateDatabaseRequestProperty::set_TemplateKey(string)
0x41420  ldloca.s 5
0x41422  initobj  [mscorlib]System.TimeSpan
0x41428  ldloc.s  5
0x4142a  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CheckTemplateDatabaseParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CheckTemplateDatabaseRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x4142f  ldarg.0
0x41430  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DoesTemplateDatabaseExistAsync>d__23::cancellationToken
0x41435  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::CheckIfTemplateExistsAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CheckTemplateDatabaseParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x4143a  ldc.i4.0
0x4143b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::ConfigureAwait(!!T0)
0x41440  stloc.s  6
0x41442  ldloca.s 6
0x41444  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetAwaiter()
0x41449  stloc.s  4
0x4144b  ldloca.s 4
0x4144d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::get_IsCompleted()
0x41452  brtrue.s loc_41495
0x41454  ldarg.0
0x41455  ldc.i4.0
0x41456  dup
0x41457  stloc.0
0x41458  stfld    int32 <DoesTemplateDatabaseExistAsync>d__23::<>1__state
0x4145d  ldarg.0
0x4145e  ldloc.s  4
0x41460  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <DoesTemplateDatabaseExistAsync>d__23::<>u__1
0x41465  ldarg.0
0x41466  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <DoesTemplateDatabaseExistAsync>d__23::<>t__builder
0x4146b  ldloca.s 4
0x4146d  ldarg.0
0x4146e  call     T0x2B0000F1
0x41473  leave    loc_41678
0x41478  ldarg.0
0x41479  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <DoesTemplateDatabaseExistAsync>d__23::<>u__1
0x4147e  stloc.s  4
0x41480  ldarg.0
0x41481  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <DoesTemplateDatabaseExistAsync>d__23::<>u__1
0x41486  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>
0x4148c  ldarg.0
0x4148d  ldc.i4.m1
0x4148e  dup
0x4148f  stloc.0
0x41490  stfld    int32 <DoesTemplateDatabaseExistAsync>d__23::<>1__state
0x41495  ldloca.s 4
0x41497  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetResult()
0x4149c  stloc.2
0x4149d  ldloc.2
0x4149e  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x414a3  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x414a8  stloc.3
0x414a9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__2
0x414ae  brtrue.s loc_414E9
0x414b0  ldc.i4.0
0x414b1  ldstr    aMessage// "Message"
0x414b6  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x414bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x414c0  ldc.i4.2
0x414c1  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x414c6  dup
0x414c7  ldc.i4.0
0x414c8  ldc.i4.0
0x414c9  ldnull
0x414ca  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x414cf  stelem.ref
0x414d0  dup
0x414d1  ldc.i4.1
0x414d2  ldc.i4.1
0x414d3  ldnull
0x414d4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x414d9  stelem.ref
0x414da  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x414df  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x414e4  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__2
0x414e9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__2
0x414ee  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x414f3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__23::<>p__2
0x414f8  ldloc.3
0x414f9  ldloc.2
0x414fa  callvirt instance string [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty::get_Message()
0x414ff  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41504  pop
0x41505  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__23::<>p__3
0x4150a  brtrue.s loc_41568
0x4150c  ldc.i4   0x100
0x41511  ldstr    aSpartantraceco// "SpartanTraceCompleted"
0x41516  ldnull
0x41517  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x4151c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x41521  ldc.i4.5
0x41522  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41527  dup
0x41528  ldc.i4.0
0x41529  ldc.i4.1
0x4152a  ldnull
0x4152b  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41530  stelem.ref
0x41531  dup
0x41532  ldc.i4.1
0x41533  ldc.i4.1
0x41534  ldnull
0x41535  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4153a  stelem.ref
0x4153b  dup
0x4153c  ldc.i4.2
0x4153d  ldc.i4.1
0x4153e  ldnull
0x4153f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41544  stelem.ref
0x41545  dup
0x41546  ldc.i4.3
0x41547  ldc.i4.0
0x41548  ldnull
0x41549  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4154e  stelem.ref
0x4154f  dup
0x41550  ldc.i4.4
0x41551  ldc.i4.0
0x41552  ldnull
0x41553  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41558  stelem.ref
0x41559  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4155e  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>>::Create(!!T0)
0x41563  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__23::<>p__3
0x41568  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__23::<>p__3
0x4156d  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>>::Target
0x41572  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__23::<>p__3
0x41577  ldarg.0
0x41578  ldfld    class SpartanFunctionLogger <DoesTemplateDatabaseExistAsync>d__23::<logger>5__2
0x4157d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x41582  ldsfld   string [mscorlib]System.String::Empty
0x41587  ldarg.0
0x41588  ldfld    object <DoesTemplateDatabaseExistAsync>d__23::<inputData>5__3
0x4158d  ldloc.3
0x4158e  callvirt instance void class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>::Invoke(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x41593  ldloc.2
0x41594  callvirt instance string [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty::get_Message()
0x41599  ldstr    aTrue// "True"
0x4159e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x415a3  stloc.1
0x415a4  leave    loc_41664
0x415a9  stloc.s  7
0x415ab  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>> <>o__23::<>p__4
0x415b0  brtrue.s loc_41618
0x415b2  ldc.i4   0x100
0x415b7  ldstr    aSpartantraceer// "SpartanTraceError"
0x415bc  ldnull
0x415bd  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x415c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x415c7  ldc.i4.6
0x415c8  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x415cd  dup
0x415ce  ldc.i4.0
0x415cf  ldc.i4.1
0x415d0  ldnull
0x415d1  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x415d6  stelem.ref
0x415d7  dup
0x415d8  ldc.i4.1
0x415d9  ldc.i4.1
0x415da  ldnull
0x415db  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x415e0  stelem.ref
0x415e1  dup
0x415e2  ldc.i4.2
0x415e3  ldc.i4.1
0x415e4  ldnull
0x415e5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x415ea  stelem.ref
0x415eb  dup
0x415ec  ldc.i4.3
0x415ed  ldc.i4.0
0x415ee  ldnull
0x415ef  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x415f4  stelem.ref
0x415f5  dup
0x415f6  ldc.i4.4
0x415f7  ldc.i4.1
0x415f8  ldnull
0x415f9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x415fe  stelem.ref
0x415ff  dup
0x41600  ldc.i4.5
0x41601  ldc.i4.1
0x41602  ldnull
0x41603  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41608  stelem.ref
0x41609  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4160e  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>>::Create(!!T0)
0x41613  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>> <>o__23::<>p__4
0x41618  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>> <>o__23::<>p__4
0x4161d  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>>::Target
0x41622  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>> <>o__23::<>p__4
0x41627  ldarg.0
0x41628  ldfld    class SpartanFunctionLogger <DoesTemplateDatabaseExistAsync>d__23::<logger>5__2
0x4162d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x41632  ldsfld   string [mscorlib]System.String::Empty
0x41637  ldarg.0
0x41638  ldfld    object <DoesTemplateDatabaseExistAsync>d__23::<inputData>5__3
0x4163d  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x41642  ldloc.s  7
0x41644  callvirt instance void class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>::Invoke(var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>)
0x41649  rethrow
0x4164b  stloc.s  8
0x4164d  ldarg.0
0x4164e  ldc.i4.s 0xFE
  ... truncated ...
```
