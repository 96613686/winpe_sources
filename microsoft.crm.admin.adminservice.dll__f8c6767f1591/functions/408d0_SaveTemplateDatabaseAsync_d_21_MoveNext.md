# <SaveTemplateDatabaseAsync>d__21::MoveNext

- ea: `0x408d0`
- end: `0x40cdf`
- name: `<SaveTemplateDatabaseAsync>d__21::MoveNext`
- size: `1039`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x38ec0`
- `0x38ee0`
- `0x38f00`
- `0x39520`
- `0x3f450`
- `0x408d0`

## string_xrefs

- `0x408f3`: `templateIdentifier`
- `0x40b83`: `SpartanTraceCompleted`
- `0x408fe`: `SaveTemplateDatabaseAsync`
- `0x40a52`: `TemplateIdentifier`

## pseudocode

```c

```

## disassembly

```asm
0x408d0  ldarg.0
0x408d1  ldfld    int32 <SaveTemplateDatabaseAsync>d__21::<>1__state
0x408d6  stloc.0
0x408d7  ldloc.0
0x408d8  brfalse  loc_40AAB
0x408dd  ldarg.0
0x408de  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <SaveTemplateDatabaseAsync>d__21::database
0x408e3  ldstr    aDatabase// "database"
0x408e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x408ed  ldarg.0
0x408ee  ldfld    string <SaveTemplateDatabaseAsync>d__21::templateIdentifier
0x408f3  ldstr    aTemplateidenti// "templateIdentifier"
0x408f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x408fd  ldarg.0
0x408fe  ldstr    aSavetemplateda// "SaveTemplateDatabaseAsync"
0x40903  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x40908  stfld    class SpartanFunctionLogger <SaveTemplateDatabaseAsync>d__21::<logger>5__2
0x4090d  ldarg.0
0x4090e  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x40913  stfld    object <SaveTemplateDatabaseAsync>d__21::<inputData>5__3
0x40918  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__0
0x4091d  brtrue.s loc_40958
0x4091f  ldc.i4.0
0x40920  ldstr    aDatabasename// "DatabaseName"
0x40925  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x4092a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4092f  ldc.i4.2
0x40930  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40935  dup
0x40936  ldc.i4.0
0x40937  ldc.i4.0
0x40938  ldnull
0x40939  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4093e  stelem.ref
0x4093f  dup
0x40940  ldc.i4.1
0x40941  ldc.i4.1
0x40942  ldnull
0x40943  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40948  stelem.ref
0x40949  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4094e  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x40953  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__0
0x40958  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__0
0x4095d  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x40962  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__0
0x40967  ldarg.0
0x40968  ldfld    object <SaveTemplateDatabaseAsync>d__21::<inputData>5__3
0x4096d  ldarg.0
0x4096e  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <SaveTemplateDatabaseAsync>d__21::database
0x40973  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x40978  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x4097d  pop
0x4097e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__1
0x40983  brtrue.s loc_409BE
0x40985  ldc.i4.0
0x40986  ldstr    aLogicalserver_0// "LogicalServer"
0x4098b  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x40990  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40995  ldc.i4.2
0x40996  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x4099b  dup
0x4099c  ldc.i4.0
0x4099d  ldc.i4.0
0x4099e  ldnull
0x4099f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x409a4  stelem.ref
0x409a5  dup
0x409a6  ldc.i4.1
0x409a7  ldc.i4.1
0x409a8  ldnull
0x409a9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x409ae  stelem.ref
0x409af  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x409b4  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x409b9  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__1
0x409be  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__1
0x409c3  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x409c8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__1
0x409cd  ldarg.0
0x409ce  ldfld    object <SaveTemplateDatabaseAsync>d__21::<inputData>5__3
0x409d3  ldarg.0
0x409d4  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <SaveTemplateDatabaseAsync>d__21::database
0x409d9  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x409de  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x409e3  pop
0x409e4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__2
0x409e9  brtrue.s loc_40A24
0x409eb  ldc.i4.0
0x409ec  ldstr    aTargetazurereg// "TargetAzureRegion"
0x409f1  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x409f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x409fb  ldc.i4.2
0x409fc  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40a01  dup
0x40a02  ldc.i4.0
0x40a03  ldc.i4.0
0x40a04  ldnull
0x40a05  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40a0a  stelem.ref
0x40a0b  dup
0x40a0c  ldc.i4.1
0x40a0d  ldc.i4.1
0x40a0e  ldnull
0x40a0f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40a14  stelem.ref
0x40a15  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x40a1a  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x40a1f  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__2
0x40a24  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__2
0x40a29  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x40a2e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__2
0x40a33  ldarg.0
0x40a34  ldfld    object <SaveTemplateDatabaseAsync>d__21::<inputData>5__3
0x40a39  ldarg.0
0x40a3a  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <SaveTemplateDatabaseAsync>d__21::database
0x40a3f  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x40a44  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x40a49  pop
0x40a4a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x40a4f  brtrue.s loc_40A8A
0x40a51  ldc.i4.0
0x40a52  ldstr    aTemplateidenti_0// "TemplateIdentifier"
0x40a57  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x40a5c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40a61  ldc.i4.2
0x40a62  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40a67  dup
0x40a68  ldc.i4.0
0x40a69  ldc.i4.0
0x40a6a  ldnull
0x40a6b  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40a70  stelem.ref
0x40a71  dup
0x40a72  ldc.i4.1
0x40a73  ldc.i4.1
0x40a74  ldnull
0x40a75  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40a7a  stelem.ref
0x40a7b  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x40a80  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x40a85  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x40a8a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x40a8f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x40a94  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__21::<>p__3
0x40a99  ldarg.0
0x40a9a  ldfld    object <SaveTemplateDatabaseAsync>d__21::<inputData>5__3
0x40a9f  ldarg.0
0x40aa0  ldfld    string <SaveTemplateDatabaseAsync>d__21::templateIdentifier
0x40aa5  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x40aaa  pop
0x40aab  nop
0x40aac  ldloc.0
0x40aad  brfalse  loc_40B4F
0x40ab2  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x40ab7  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.SaveTemplateDatabaseRequestProperty::.ctor()
0x40abc  dup
0x40abd  ldarg.0
0x40abe  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <SaveTemplateDatabaseAsync>d__21::database
0x40ac3  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x40ac8  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x40acd  dup
0x40ace  ldarg.0
0x40acf  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <SaveTemplateDatabaseAsync>d__21::database
0x40ad4  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x40ad9  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.SaveTemplateDatabaseRequestProperty::set_LogicalServerName(string)
0x40ade  dup
0x40adf  ldarg.0
0x40ae0  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <SaveTemplateDatabaseAsync>d__21::database
0x40ae5  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x40aea  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.SaveTemplateDatabaseRequestProperty::set_DatabaseName(string)
0x40aef  dup
0x40af0  ldarg.0
0x40af1  ldfld    string <SaveTemplateDatabaseAsync>d__21::templateIdentifier
0x40af6  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.TemplateDatabaseRequestProperty::set_TemplateKey(string)
0x40afb  ldloca.s 2
0x40afd  initobj  [mscorlib]System.TimeSpan
0x40b03  ldloc.2
0x40b04  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.SaveTemplateDatabaseParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.SaveTemplateDatabaseRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x40b09  ldarg.0
0x40b0a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SaveTemplateDatabaseAsync>d__21::cancellationToken
0x40b0f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::SaveDatabaseTemplateAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.SaveTemplateDatabaseParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x40b14  ldc.i4.0
0x40b15  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::ConfigureAwait(!!T0)
0x40b1a  stloc.3
0x40b1b  ldloca.s 3
0x40b1d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetAwaiter()
0x40b22  stloc.1
0x40b23  ldloca.s 1
0x40b25  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::get_IsCompleted()
0x40b2a  brtrue.s loc_40B6B
0x40b2c  ldarg.0
0x40b2d  ldc.i4.0
0x40b2e  dup
0x40b2f  stloc.0
0x40b30  stfld    int32 <SaveTemplateDatabaseAsync>d__21::<>1__state
0x40b35  ldarg.0
0x40b36  ldloc.1
0x40b37  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <SaveTemplateDatabaseAsync>d__21::<>u__1
0x40b3c  ldarg.0
0x40b3d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SaveTemplateDatabaseAsync>d__21::<>t__builder
0x40b42  ldloca.s 1
0x40b44  ldarg.0
0x40b45  call     T0x2B0000EE
0x40b4a  leave    loc_40CDE
0x40b4f  ldarg.0
0x40b50  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <SaveTemplateDatabaseAsync>d__21::<>u__1
0x40b55  stloc.1
0x40b56  ldarg.0
0x40b57  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <SaveTemplateDatabaseAsync>d__21::<>u__1
0x40b5c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>
0x40b62  ldarg.0
0x40b63  ldc.i4.m1
0x40b64  dup
0x40b65  stloc.0
0x40b66  stfld    int32 <SaveTemplateDatabaseAsync>d__21::<>1__state
0x40b6b  ldloca.s 1
0x40b6d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetResult()
0x40b72  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x40b77  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__21::<>p__4
0x40b7c  brtrue.s loc_40BDA
0x40b7e  ldc.i4   0x100
0x40b83  ldstr    aSpartantraceco// "SpartanTraceCompleted"
0x40b88  ldnull
0x40b89  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x40b8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40b93  ldc.i4.5
0x40b94  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40b99  dup
0x40b9a  ldc.i4.0
0x40b9b  ldc.i4.1
0x40b9c  ldnull
0x40b9d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40ba2  stelem.ref
0x40ba3  dup
0x40ba4  ldc.i4.1
0x40ba5  ldc.i4.1
0x40ba6  ldnull
0x40ba7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40bac  stelem.ref
0x40bad  dup
0x40bae  ldc.i4.2
0x40baf  ldc.i4.1
0x40bb0  ldnull
0x40bb1  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40bb6  stelem.ref
0x40bb7  dup
0x40bb8  ldc.i4.3
0x40bb9  ldc.i4.0
0x40bba  ldnull
0x40bbb  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40bc0  stelem.ref
0x40bc1  dup
0x40bc2  ldc.i4.4
0x40bc3  ldc.i4.1
0x40bc4  ldnull
0x40bc5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40bca  stelem.ref
0x40bcb  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x40bd0  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>>::Create(!!T0)
0x40bd5  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__21::<>p__4
0x40bda  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__21::<>p__4
0x40bdf  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>>::Target
0x40be4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__21::<>p__4
0x40be9  ldarg.0
0x40bea  ldfld    class SpartanFunctionLogger <SaveTemplateDatabaseAsync>d__21::<logger>5__2
0x40bef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40bf4  ldsfld   string [mscorlib]System.String::Empty
0x40bf9  ldarg.0
0x40bfa  ldfld    object <SaveTemplateDatabaseAsync>d__21::<inputData>5__3
0x40bff  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x40c04  callvirt instance void class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>::Invoke(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x40c09  leave    loc_40CB0
0x40c0e  stloc.s  4
0x40c10  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>> <>o__21::<>p__5
0x40c15  brtrue.s loc_40C7D
0x40c17  ldc.i4   0x100
0x40c1c  ldstr    aSpartantraceer// "SpartanTraceError"
0x40c21  ldnull
0x40c22  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x40c27  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40c2c  ldc.i4.6
0x40c2d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x40c32  dup
0x40c33  ldc.i4.0
0x40c34  ldc.i4.1
0x40c35  ldnull
0x40c36  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40c3b  stelem.ref
0x40c3c  dup
0x40c3d  ldc.i4.1
0x40c3e  ldc.i4.1
0x40c3f  ldnull
0x40c40  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40c45  stelem.ref
0x40c46  dup
0x40c47  ldc.i4.2
0x40c48  ldc.i4.1
0x40c49  ldnull
0x40c4a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
  ... truncated ...
```
