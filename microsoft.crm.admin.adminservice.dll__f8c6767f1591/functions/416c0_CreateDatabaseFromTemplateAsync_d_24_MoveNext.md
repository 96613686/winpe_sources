# <CreateDatabaseFromTemplateAsync>d__24::MoveNext

- ea: `0x416c0`
- end: `0x41d99`
- name: `<CreateDatabaseFromTemplateAsync>d__24::MoveNext`
- size: `1753`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x22ae0`
- `0x38ea0`
- `0x38ed0`
- `0x38ef0`
- `0x38f10`
- `0x38f30`
- `0x39520`
- `0x3a6f0`
- `0x3a8a0`
- `0x3f450`
- `0x416c0`

## string_xrefs

- `0x416fb`: `templateIdentifier`
- `0x41c32`: `SpartanTraceCompleted`
- `0x4180d`: `TemplateIdentifier`
- `0x41729`: `CreateDatabaseFromTemplateAsync`

## pseudocode

```c

```

## disassembly

```asm
0x416c0  ldarg.0
0x416c1  ldfld    int32 <CreateDatabaseFromTemplateAsync>d__24::<>1__state
0x416c6  stloc.0
0x416c7  ldarg.0
0x416c8  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanService <CreateDatabaseFromTemplateAsync>d__24::<>4__this
0x416cd  stloc.1
0x416ce  ldloc.0
0x416cf  ldc.i4.1
0x416d0  ble.un   loc_418C7
0x416d5  ldarg.0
0x416d6  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::operationId
0x416db  ldstr    aOperationid// "operationId"
0x416e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x416e5  ldarg.0
0x416e6  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::azureRegion
0x416eb  ldstr    aAzureregion_1// "azureRegion"
0x416f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x416f5  ldarg.0
0x416f6  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::templateIdentifier
0x416fb  ldstr    aTemplateidenti// "templateIdentifier"
0x41700  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x41705  ldarg.0
0x41706  ldflda   valuetype [mscorlib]System.Guid <CreateDatabaseFromTemplateAsync>d__24::scalegroupId
0x4170b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x41710  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x41715  brtrue.s loc_41728
0x41717  ldarg.0
0x41718  ldarg.0
0x41719  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseFromTemplateAsync>d__24::scalegroupId
0x4171e  call     string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::RetrieveTierGroupName(valuetype [mscorlib]System.Guid scaleGroupId)
0x41723  stfld    string <CreateDatabaseFromTemplateAsync>d__24::tierGroup
0x41728  ldarg.0
0x41729  ldstr    aCreatedatabase_1// "CreateDatabaseFromTemplateAsync"
0x4172e  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x41733  stfld    class SpartanFunctionLogger <CreateDatabaseFromTemplateAsync>d__24::<logger>5__2
0x41738  ldarg.0
0x41739  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x4173e  stfld    object <CreateDatabaseFromTemplateAsync>d__24::<inputData>5__3
0x41743  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__0
0x41748  brtrue.s loc_41783
0x4174a  ldc.i4.0
0x4174b  ldstr    aTargetazurereg// "TargetAzureRegion"
0x41750  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41755  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4175a  ldc.i4.2
0x4175b  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41760  dup
0x41761  ldc.i4.0
0x41762  ldc.i4.0
0x41763  ldnull
0x41764  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41769  stelem.ref
0x4176a  dup
0x4176b  ldc.i4.1
0x4176c  ldc.i4.1
0x4176d  ldnull
0x4176e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41773  stelem.ref
0x41774  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x41779  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x4177e  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__0
0x41783  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__0
0x41788  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x4178d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__0
0x41792  ldarg.0
0x41793  ldfld    object <CreateDatabaseFromTemplateAsync>d__24::<inputData>5__3
0x41798  ldarg.0
0x41799  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::azureRegion
0x4179e  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x417a3  pop
0x417a4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__1
0x417a9  brtrue.s loc_417E4
0x417ab  ldc.i4.0
0x417ac  ldstr    aTiergroup_1// "TierGroup"
0x417b1  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x417b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x417bb  ldc.i4.2
0x417bc  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x417c1  dup
0x417c2  ldc.i4.0
0x417c3  ldc.i4.0
0x417c4  ldnull
0x417c5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x417ca  stelem.ref
0x417cb  dup
0x417cc  ldc.i4.1
0x417cd  ldc.i4.1
0x417ce  ldnull
0x417cf  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x417d4  stelem.ref
0x417d5  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x417da  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x417df  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__1
0x417e4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__1
0x417e9  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x417ee  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__1
0x417f3  ldarg.0
0x417f4  ldfld    object <CreateDatabaseFromTemplateAsync>d__24::<inputData>5__3
0x417f9  ldarg.0
0x417fa  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::tierGroup
0x417ff  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41804  pop
0x41805  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__2
0x4180a  brtrue.s loc_41845
0x4180c  ldc.i4.0
0x4180d  ldstr    aTemplateidenti_0// "TemplateIdentifier"
0x41812  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41817  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4181c  ldc.i4.2
0x4181d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41822  dup
0x41823  ldc.i4.0
0x41824  ldc.i4.0
0x41825  ldnull
0x41826  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4182b  stelem.ref
0x4182c  dup
0x4182d  ldc.i4.1
0x4182e  ldc.i4.1
0x4182f  ldnull
0x41830  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41835  stelem.ref
0x41836  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4183b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x41840  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__2
0x41845  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__2
0x4184a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x4184f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__2
0x41854  ldarg.0
0x41855  ldfld    object <CreateDatabaseFromTemplateAsync>d__24::<inputData>5__3
0x4185a  ldarg.0
0x4185b  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::templateIdentifier
0x41860  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41865  pop
0x41866  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__24::<>p__3
0x4186b  brtrue.s loc_418A6
0x4186d  ldc.i4.0
0x4186e  ldstr    aScalegroupid// "scaleGroupId"
0x41873  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41878  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4187d  ldc.i4.2
0x4187e  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41883  dup
0x41884  ldc.i4.0
0x41885  ldc.i4.0
0x41886  ldnull
0x41887  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4188c  stelem.ref
0x4188d  dup
0x4188e  ldc.i4.1
0x4188f  ldc.i4.1
0x41890  ldnull
0x41891  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41896  stelem.ref
0x41897  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4189c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x418a1  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__24::<>p__3
0x418a6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__24::<>p__3
0x418ab  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x418b0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__24::<>p__3
0x418b5  ldarg.0
0x418b6  ldfld    object <CreateDatabaseFromTemplateAsync>d__24::<inputData>5__3
0x418bb  ldarg.0
0x418bc  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseFromTemplateAsync>d__24::scalegroupId
0x418c1  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x418c6  pop
0x418c7  nop
0x418c8  ldloc.0
0x418c9  brfalse  loc_41998
0x418ce  ldloc.0
0x418cf  ldc.i4.1
0x418d0  beq      loc_41C02
0x418d5  ldarg.0
0x418d6  ldarg.0
0x418d7  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseFromTemplateAsync>d__24::scalegroupId
0x418dc  call     string Microsoft.Crm.Admin.AdminService.LogicalGroupKeyProvider::CreateLogicalServerGroupKey(valuetype [mscorlib]System.Guid scalegroupId)
0x418e1  stfld    string <CreateDatabaseFromTemplateAsync>d__24::<logicalServerGroupKey>5__4
0x418e6  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x418eb  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseFromTemplateRequestProperty::.ctor()
0x418f0  dup
0x418f1  ldarg.0
0x418f2  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::operationId
0x418f7  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseFromTemplateRequestProperty::set_OperationId(string)
0x418fc  dup
0x418fd  ldarg.0
0x418fe  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::azureRegion
0x41903  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x41908  dup
0x41909  ldarg.0
0x4190a  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::tierGroup
0x4190f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x41914  brtrue.s loc_4191E
0x41916  ldarg.0
0x41917  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::tierGroup
0x4191c  br.s     loc_41923
0x4191e  ldsfld   string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::SpartanDefaultTierGroup
0x41923  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseFromTemplateRequestProperty::set_TargetDatabaseTierGroup(string)
0x41928  dup
0x41929  ldarg.0
0x4192a  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::templateIdentifier
0x4192f  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.TemplateDatabaseRequestProperty::set_TemplateKey(string)
0x41934  dup
0x41935  ldarg.0
0x41936  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::<logicalServerGroupKey>5__4
0x4193b  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseFromTemplateRequestProperty::set_LogicalServerGroupKey(string)
0x41940  ldloca.s 5
0x41942  initobj  [mscorlib]System.TimeSpan
0x41948  ldloc.s  5
0x4194a  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CreateDatabaseFromTemplateParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseFromTemplateRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x4194f  ldarg.0
0x41950  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CreateDatabaseFromTemplateAsync>d__24::cancellationToken
0x41955  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::CreateDatabaseFromTemplateAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CreateDatabaseFromTemplateParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x4195a  ldc.i4.0
0x4195b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::ConfigureAwait(!!T0)
0x41960  stloc.s  6
0x41962  ldloca.s 6
0x41964  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetAwaiter()
0x41969  stloc.s  4
0x4196b  ldloca.s 4
0x4196d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::get_IsCompleted()
0x41972  brtrue.s loc_419B5
0x41974  ldarg.0
0x41975  ldc.i4.0
0x41976  dup
0x41977  stloc.0
0x41978  stfld    int32 <CreateDatabaseFromTemplateAsync>d__24::<>1__state
0x4197d  ldarg.0
0x4197e  ldloc.s  4
0x41980  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <CreateDatabaseFromTemplateAsync>d__24::<>u__1
0x41985  ldarg.0
0x41986  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier> <CreateDatabaseFromTemplateAsync>d__24::<>t__builder
0x4198b  ldloca.s 4
0x4198d  ldarg.0
0x4198e  call     T0x2B0000F2
0x41993  leave    loc_41D98
0x41998  ldarg.0
0x41999  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <CreateDatabaseFromTemplateAsync>d__24::<>u__1
0x4199e  stloc.s  4
0x419a0  ldarg.0
0x419a1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <CreateDatabaseFromTemplateAsync>d__24::<>u__1
0x419a6  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>
0x419ac  ldarg.0
0x419ad  ldc.i4.m1
0x419ae  dup
0x419af  stloc.0
0x419b0  stfld    int32 <CreateDatabaseFromTemplateAsync>d__24::<>1__state
0x419b5  ldloca.s 4
0x419b7  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetResult()
0x419bc  stloc.3
0x419bd  ldloc.3
0x419be  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x419c3  ldarg.0
0x419c4  newobj   instance void Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier::.ctor()
0x419c9  stfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseFromTemplateAsync>d__24::<databaseIdentifier>5__5
0x419ce  ldarg.0
0x419cf  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x419d4  stfld    object <CreateDatabaseFromTemplateAsync>d__24::<outputData>5__6
0x419d9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__4
0x419de  brtrue.s loc_41A19
0x419e0  ldc.i4.0
0x419e1  ldstr    aTargetazurereg// "TargetAzureRegion"
0x419e6  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x419eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x419f0  ldc.i4.2
0x419f1  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x419f6  dup
0x419f7  ldc.i4.0
0x419f8  ldc.i4.0
0x419f9  ldnull
0x419fa  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x419ff  stelem.ref
0x41a00  dup
0x41a01  ldc.i4.1
0x41a02  ldc.i4.1
0x41a03  ldnull
0x41a04  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41a09  stelem.ref
0x41a0a  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x41a0f  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x41a14  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__4
0x41a19  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__4
0x41a1e  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x41a23  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__24::<>p__4
0x41a28  ldarg.0
0x41a29  ldfld    object <CreateDatabaseFromTemplateAsync>d__24::<outputData>5__6
0x41a2e  ldarg.0
0x41a2f  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseFromTemplateAsync>d__24::<databaseIdentifier>5__5
0x41a34  ldloc.3
0x41a35  callvirt instance class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseCreateResponseProperty [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse::get_ResponseProperty()
0x41a3a  callvirt instance string [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseResponseProperty::get_Location()
0x41a3f  dup
0x41a40  brtrue.s loc_41A49
0x41a42  pop
0x41a43  ldarg.0
0x41a44  ldfld    string <CreateDatabaseFromTemplateAsync>d__24::azureRegion
0x41a49  dup
0x41a4a  stloc.s  7
0x41a4c  callvirt instance void Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_AzureRegion(string value)
0x41a51  ldloc.s  7
0x41a53  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
  ... truncated ...
```
