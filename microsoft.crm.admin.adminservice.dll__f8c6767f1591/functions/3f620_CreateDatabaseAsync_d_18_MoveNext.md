# <CreateDatabaseAsync>d__18::MoveNext

- ea: `0x3f620`
- end: `0x3fc8c`
- name: `<CreateDatabaseAsync>d__18::MoveNext`
- size: `1644`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x22ae0`
- `0x38ea0`
- `0x38ed0`
- `0x38ef0`
- `0x38f10`
- `0x38f30`
- `0x38f50`
- `0x39520`
- `0x395e0`
- `0x3a6f0`
- `0x3f450`
- `0x3f620`

## string_xrefs

- `0x3f65e`: `CreateDatabaseAsync`
- `0x3fb2d`: `SpartanTraceCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x3f620  ldarg.0
0x3f621  ldfld    int32 <CreateDatabaseAsync>d__18::<>1__state
0x3f626  stloc.0
0x3f627  ldloc.0
0x3f628  brfalse  loc_3F81F
0x3f62d  ldarg.0
0x3f62e  ldfld    string <CreateDatabaseAsync>d__18::operationId
0x3f633  ldstr    aOperationid// "operationId"
0x3f638  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3f63d  ldarg.0
0x3f63e  ldfld    string <CreateDatabaseAsync>d__18::databaseCollation
0x3f643  ldstr    aDatabasecollat// "databaseCollation"
0x3f648  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3f64d  ldarg.0
0x3f64e  ldfld    string <CreateDatabaseAsync>d__18::azureRegion
0x3f653  ldstr    aAzureregion_1// "azureRegion"
0x3f658  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3f65d  ldarg.0
0x3f65e  ldstr    aCreatedatabase// "CreateDatabaseAsync"
0x3f663  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x3f668  stfld    class SpartanFunctionLogger <CreateDatabaseAsync>d__18::<logger>5__2
0x3f66d  ldarg.0
0x3f66e  ldflda   valuetype [mscorlib]System.Guid <CreateDatabaseAsync>d__18::scalegroupId
0x3f673  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f678  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x3f67d  brtrue.s loc_3F690
0x3f67f  ldarg.0
0x3f680  ldarg.0
0x3f681  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseAsync>d__18::scalegroupId
0x3f686  call     string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::RetrieveTierGroupName(valuetype [mscorlib]System.Guid scaleGroupId)
0x3f68b  stfld    string <CreateDatabaseAsync>d__18::tierGroup
0x3f690  ldarg.0
0x3f691  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x3f696  stfld    object <CreateDatabaseAsync>d__18::<inputData>5__3
0x3f69b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__0
0x3f6a0  brtrue.s loc_3F6DB
0x3f6a2  ldc.i4.0
0x3f6a3  ldstr    aCollation// "Collation"
0x3f6a8  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3f6ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f6b2  ldc.i4.2
0x3f6b3  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3f6b8  dup
0x3f6b9  ldc.i4.0
0x3f6ba  ldc.i4.0
0x3f6bb  ldnull
0x3f6bc  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f6c1  stelem.ref
0x3f6c2  dup
0x3f6c3  ldc.i4.1
0x3f6c4  ldc.i4.1
0x3f6c5  ldnull
0x3f6c6  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f6cb  stelem.ref
0x3f6cc  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3f6d1  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3f6d6  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__0
0x3f6db  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__0
0x3f6e0  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3f6e5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__0
0x3f6ea  ldarg.0
0x3f6eb  ldfld    object <CreateDatabaseAsync>d__18::<inputData>5__3
0x3f6f0  ldarg.0
0x3f6f1  ldfld    string <CreateDatabaseAsync>d__18::databaseCollation
0x3f6f6  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3f6fb  pop
0x3f6fc  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__1
0x3f701  brtrue.s loc_3F73C
0x3f703  ldc.i4.0
0x3f704  ldstr    aTiergroup_1// "TierGroup"
0x3f709  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3f70e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f713  ldc.i4.2
0x3f714  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3f719  dup
0x3f71a  ldc.i4.0
0x3f71b  ldc.i4.0
0x3f71c  ldnull
0x3f71d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f722  stelem.ref
0x3f723  dup
0x3f724  ldc.i4.1
0x3f725  ldc.i4.1
0x3f726  ldnull
0x3f727  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f72c  stelem.ref
0x3f72d  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3f732  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3f737  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__1
0x3f73c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__1
0x3f741  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3f746  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__1
0x3f74b  ldarg.0
0x3f74c  ldfld    object <CreateDatabaseAsync>d__18::<inputData>5__3
0x3f751  ldarg.0
0x3f752  ldfld    string <CreateDatabaseAsync>d__18::tierGroup
0x3f757  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3f75c  pop
0x3f75d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__2
0x3f762  brtrue.s loc_3F79D
0x3f764  ldc.i4.0
0x3f765  ldstr    aTargetazurereg// "TargetAzureRegion"
0x3f76a  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3f76f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f774  ldc.i4.2
0x3f775  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3f77a  dup
0x3f77b  ldc.i4.0
0x3f77c  ldc.i4.0
0x3f77d  ldnull
0x3f77e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f783  stelem.ref
0x3f784  dup
0x3f785  ldc.i4.1
0x3f786  ldc.i4.1
0x3f787  ldnull
0x3f788  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f78d  stelem.ref
0x3f78e  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3f793  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3f798  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__2
0x3f79d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__2
0x3f7a2  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3f7a7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__2
0x3f7ac  ldarg.0
0x3f7ad  ldfld    object <CreateDatabaseAsync>d__18::<inputData>5__3
0x3f7b2  ldarg.0
0x3f7b3  ldfld    string <CreateDatabaseAsync>d__18::azureRegion
0x3f7b8  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3f7bd  pop
0x3f7be  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__18::<>p__3
0x3f7c3  brtrue.s loc_3F7FE
0x3f7c5  ldc.i4.0
0x3f7c6  ldstr    aScalegroupid_0// "ScaleGroupId"
0x3f7cb  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3f7d0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f7d5  ldc.i4.2
0x3f7d6  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3f7db  dup
0x3f7dc  ldc.i4.0
0x3f7dd  ldc.i4.0
0x3f7de  ldnull
0x3f7df  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f7e4  stelem.ref
0x3f7e5  dup
0x3f7e6  ldc.i4.1
0x3f7e7  ldc.i4.1
0x3f7e8  ldnull
0x3f7e9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f7ee  stelem.ref
0x3f7ef  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3f7f4  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x3f7f9  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__18::<>p__3
0x3f7fe  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__18::<>p__3
0x3f803  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x3f808  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__18::<>p__3
0x3f80d  ldarg.0
0x3f80e  ldfld    object <CreateDatabaseAsync>d__18::<inputData>5__3
0x3f813  ldarg.0
0x3f814  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseAsync>d__18::scalegroupId
0x3f819  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x3f81e  pop
0x3f81f  nop
0x3f820  ldloc.0
0x3f821  brfalse  loc_3F904
0x3f826  ldarg.0
0x3f827  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty::.ctor()
0x3f82c  stfld    class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty <CreateDatabaseAsync>d__18::<property>5__4
0x3f831  ldarg.0
0x3f832  ldfld    class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty <CreateDatabaseAsync>d__18::<property>5__4
0x3f837  ldarg.0
0x3f838  ldfld    string <CreateDatabaseAsync>d__18::operationId
0x3f83d  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty::set_OperationId(string)
0x3f842  ldarg.0
0x3f843  ldfld    class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty <CreateDatabaseAsync>d__18::<property>5__4
0x3f848  ldarg.0
0x3f849  ldfld    string <CreateDatabaseAsync>d__18::databaseCollation
0x3f84e  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty::set_Collation(string)
0x3f853  ldarg.0
0x3f854  ldfld    class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty <CreateDatabaseAsync>d__18::<property>5__4
0x3f859  ldarg.0
0x3f85a  ldfld    string <CreateDatabaseAsync>d__18::tierGroup
0x3f85f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3f864  brtrue.s loc_3F86E
0x3f866  ldarg.0
0x3f867  ldfld    string <CreateDatabaseAsync>d__18::tierGroup
0x3f86c  br.s     loc_3F873
0x3f86e  ldsfld   string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::SpartanDefaultTierGroup
0x3f873  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty::set_TargetDatabaseTierGroup(string)
0x3f878  ldarg.0
0x3f879  ldfld    class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty <CreateDatabaseAsync>d__18::<property>5__4
0x3f87e  ldarg.0
0x3f87f  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseAsync>d__18::scalegroupId
0x3f884  call     string Microsoft.Crm.Admin.AdminService.LogicalGroupKeyProvider::CreateLogicalServerGroupKey(valuetype [mscorlib]System.Guid scalegroupId)
0x3f889  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty::set_LogicalServerGroupKey(string)
0x3f88e  ldarg.0
0x3f88f  ldfld    class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty <CreateDatabaseAsync>d__18::<property>5__4
0x3f894  ldarg.0
0x3f895  ldfld    string <CreateDatabaseAsync>d__18::azureRegion
0x3f89a  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x3f89f  ldarg.0
0x3f8a0  ldfld    class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty <CreateDatabaseAsync>d__18::<property>5__4
0x3f8a5  ldloca.s 6
0x3f8a7  initobj  [mscorlib]System.TimeSpan
0x3f8ad  ldloc.s  6
0x3f8af  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CreateDatabaseParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x3f8b4  stloc.2
0x3f8b5  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x3f8ba  ldloc.2
0x3f8bb  ldarg.0
0x3f8bc  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CreateDatabaseAsync>d__18::cancellationToken
0x3f8c1  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::CreateDatabaseAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CreateDatabaseParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x3f8c6  ldc.i4.0
0x3f8c7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::ConfigureAwait(!!T0)
0x3f8cc  stloc.s  8
0x3f8ce  ldloca.s 8
0x3f8d0  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetAwaiter()
0x3f8d5  stloc.s  7
0x3f8d7  ldloca.s 7
0x3f8d9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::get_IsCompleted()
0x3f8de  brtrue.s loc_3F921
0x3f8e0  ldarg.0
0x3f8e1  ldc.i4.0
0x3f8e2  dup
0x3f8e3  stloc.0
0x3f8e4  stfld    int32 <CreateDatabaseAsync>d__18::<>1__state
0x3f8e9  ldarg.0
0x3f8ea  ldloc.s  7
0x3f8ec  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <CreateDatabaseAsync>d__18::<>u__1
0x3f8f1  ldarg.0
0x3f8f2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier> <CreateDatabaseAsync>d__18::<>t__builder
0x3f8f7  ldloca.s 7
0x3f8f9  ldarg.0
0x3f8fa  call     T0x2B0000EB
0x3f8ff  leave    loc_3FC8B
0x3f904  ldarg.0
0x3f905  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <CreateDatabaseAsync>d__18::<>u__1
0x3f90a  stloc.s  7
0x3f90c  ldarg.0
0x3f90d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <CreateDatabaseAsync>d__18::<>u__1
0x3f912  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>
0x3f918  ldarg.0
0x3f919  ldc.i4.m1
0x3f91a  dup
0x3f91b  stloc.0
0x3f91c  stfld    int32 <CreateDatabaseAsync>d__18::<>1__state
0x3f921  ldloca.s 7
0x3f923  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetResult()
0x3f928  stloc.3
0x3f929  ldloc.3
0x3f92a  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x3f92f  ldloc.3
0x3f930  callvirt instance class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseCreateResponseProperty [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse::get_ResponseProperty()
0x3f935  callvirt instance string [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseCreateResponseProperty::get_ConnectionString()
0x3f93a  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::AddDevTestPrincipalToDatabase(string connectionstring)
0x3f93f  newobj   instance void Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier::.ctor()
0x3f944  stloc.s  4
0x3f946  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x3f94b  stloc.s  5
0x3f94d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__4
0x3f952  brtrue.s loc_3F98D
0x3f954  ldc.i4.0
0x3f955  ldstr    aDatabasename// "DatabaseName"
0x3f95a  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3f95f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f964  ldc.i4.2
0x3f965  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3f96a  dup
0x3f96b  ldc.i4.0
0x3f96c  ldc.i4.0
0x3f96d  ldnull
0x3f96e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f973  stelem.ref
0x3f974  dup
0x3f975  ldc.i4.1
0x3f976  ldc.i4.1
0x3f977  ldnull
0x3f978  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3f97d  stelem.ref
0x3f97e  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3f983  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3f988  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__4
0x3f98d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__4
0x3f992  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3f997  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__4
0x3f99c  ldloc.s  5
0x3f99e  ldloc.s  4
0x3f9a0  ldloc.3
0x3f9a1  callvirt instance class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseCreateResponseProperty [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse::get_ResponseProperty()
0x3f9a6  callvirt instance string [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseResponseProperty::get_DatabaseName()
0x3f9ab  dup
0x3f9ac  stloc.s  9
0x3f9ae  callvirt instance void Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_DatabaseName(string value)
0x3f9b3  ldloc.s  9
0x3f9b5  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3f9ba  pop
0x3f9bb  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__18::<>p__5
0x3f9c0  brtrue.s loc_3F9FB
0x3f9c2  ldc.i4.0
0x3f9c3  ldstr    aTargetazurereg// "TargetAzureRegion"
  ... truncated ...
```
