# <ListAllDeletedDatabasesAsync>d__35::MoveNext

- ea: `0x45970`
- end: `0x45d42`
- name: `<ListAllDeletedDatabasesAsync>d__35::MoveNext`
- size: `978`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x39520`
- `0x3f450`
- `0x45970`

## string_xrefs

- `0x45bc8`: `SpartanTraceCompleted`
- `0x45a6b`: `ListAllDeletedDatabasesAsync`
- `0x45bac`: `DeletedDatabases`

## pseudocode

```c

```

## disassembly

```asm
0x45970  ldarg.0
0x45971  ldfld    int32 <ListAllDeletedDatabasesAsync>d__35::<>1__state
0x45976  stloc.0
0x45977  ldloc.0
0x45978  brfalse  loc_45A7A
0x4597d  ldarg.0
0x4597e  ldfld    string <ListAllDeletedDatabasesAsync>d__35::azureRegion
0x45983  ldstr    aAzureregion_1// "azureRegion"
0x45988  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4598d  ldarg.0
0x4598e  ldfld    string <ListAllDeletedDatabasesAsync>d__35::logicalServerName
0x45993  ldstr    aLogicalservern// "logicalServerName"
0x45998  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4599d  ldarg.0
0x4599e  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x459a3  stfld    object <ListAllDeletedDatabasesAsync>d__35::<inputData>5__2
0x459a8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__0
0x459ad  brtrue.s loc_459E8
0x459af  ldc.i4.0
0x459b0  ldstr    aTargetazurereg// "TargetAzureRegion"
0x459b5  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x459ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x459bf  ldc.i4.2
0x459c0  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x459c5  dup
0x459c6  ldc.i4.0
0x459c7  ldc.i4.0
0x459c8  ldnull
0x459c9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x459ce  stelem.ref
0x459cf  dup
0x459d0  ldc.i4.1
0x459d1  ldc.i4.1
0x459d2  ldnull
0x459d3  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x459d8  stelem.ref
0x459d9  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x459de  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x459e3  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__0
0x459e8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__0
0x459ed  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x459f2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__0
0x459f7  ldarg.0
0x459f8  ldfld    object <ListAllDeletedDatabasesAsync>d__35::<inputData>5__2
0x459fd  ldarg.0
0x459fe  ldfld    string <ListAllDeletedDatabasesAsync>d__35::azureRegion
0x45a03  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x45a08  pop
0x45a09  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__1
0x45a0e  brtrue.s loc_45A49
0x45a10  ldc.i4.0
0x45a11  ldstr    aLogicalserver_0// "LogicalServer"
0x45a16  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x45a1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45a20  ldc.i4.2
0x45a21  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x45a26  dup
0x45a27  ldc.i4.0
0x45a28  ldc.i4.0
0x45a29  ldnull
0x45a2a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45a2f  stelem.ref
0x45a30  dup
0x45a31  ldc.i4.1
0x45a32  ldc.i4.1
0x45a33  ldnull
0x45a34  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45a39  stelem.ref
0x45a3a  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x45a3f  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x45a44  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__1
0x45a49  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__1
0x45a4e  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x45a53  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__35::<>p__1
0x45a58  ldarg.0
0x45a59  ldfld    object <ListAllDeletedDatabasesAsync>d__35::<inputData>5__2
0x45a5e  ldarg.0
0x45a5f  ldfld    string <ListAllDeletedDatabasesAsync>d__35::logicalServerName
0x45a64  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x45a69  pop
0x45a6a  ldarg.0
0x45a6b  ldstr    aListalldeleted// "ListAllDeletedDatabasesAsync"
0x45a70  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x45a75  stfld    class SpartanFunctionLogger <ListAllDeletedDatabasesAsync>d__35::<logger>5__3
0x45a7a  nop
0x45a7b  ldloc.0
0x45a7c  brfalse.s loc_45AF8
0x45a7e  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x45a83  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ListResourceWithinServerRequestProperty::.ctor()
0x45a88  dup
0x45a89  ldarg.0
0x45a8a  ldfld    string <ListAllDeletedDatabasesAsync>d__35::azureRegion
0x45a8f  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x45a94  dup
0x45a95  ldarg.0
0x45a96  ldfld    string <ListAllDeletedDatabasesAsync>d__35::logicalServerName
0x45a9b  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ListResourceWithinServerRequestProperty::set_LogicalServerName(string)
0x45aa0  ldloca.s 6
0x45aa2  initobj  [mscorlib]System.TimeSpan
0x45aa8  ldloc.s  6
0x45aaa  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ListResourceWithinServerRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x45aaf  ldarg.0
0x45ab0  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ListAllDeletedDatabasesAsync>d__35::cancellationToken
0x45ab5  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::ListDroppedDatabasesAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x45aba  ldc.i4.0
0x45abb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse>::ConfigureAwait(!!T0)
0x45ac0  stloc.s  7
0x45ac2  ldloca.s 7
0x45ac4  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse>::GetAwaiter()
0x45ac9  stloc.s  5
0x45acb  ldloca.s 5
0x45acd  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse>::get_IsCompleted()
0x45ad2  brtrue.s loc_45B15
0x45ad4  ldarg.0
0x45ad5  ldc.i4.0
0x45ad6  dup
0x45ad7  stloc.0
0x45ad8  stfld    int32 <ListAllDeletedDatabasesAsync>d__35::<>1__state
0x45add  ldarg.0
0x45ade  ldloc.s  5
0x45ae0  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse> <ListAllDeletedDatabasesAsync>d__35::<>u__1
0x45ae5  ldarg.0
0x45ae6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseInfo>> <ListAllDeletedDatabasesAsync>d__35::<>t__builder
0x45aeb  ldloca.s 5
0x45aed  ldarg.0
0x45aee  call     T0x2B000106
0x45af3  leave    loc_45D41
0x45af8  ldarg.0
0x45af9  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse> <ListAllDeletedDatabasesAsync>d__35::<>u__1
0x45afe  stloc.s  5
0x45b00  ldarg.0
0x45b01  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse> <ListAllDeletedDatabasesAsync>d__35::<>u__1
0x45b06  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse>
0x45b0c  ldarg.0
0x45b0d  ldc.i4.m1
0x45b0e  dup
0x45b0f  stloc.0
0x45b10  stfld    int32 <ListAllDeletedDatabasesAsync>d__35::<>1__state
0x45b15  ldloca.s 5
0x45b17  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse>::GetResult()
0x45b1c  stloc.2
0x45b1d  ldloc.2
0x45b1e  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x45b23  ldloc.2
0x45b24  callvirt instance class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ListDatabaseResponseProperty [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse::get_ResponseProperty()
0x45b29  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseGetResponseProperty> [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ListDatabaseResponseProperty::get_DatabaseList()
0x45b2e  ldnull
0x45b2f  ldftn    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseInfo Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::FromResponseProperty(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseGetResponseProperty property)
0x45b35  newobj   instance void class [mscorlib]System.Func`2<class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseGetResponseProperty, class Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseInfo>::.ctor(object, native int)
0x45b3a  call     T0x2B000104
0x45b3f  call     T0x2B000105
0x45b44  stloc.3
0x45b45  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x45b4a  stloc.s  4
0x45b4c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray>> <>o__35::<>p__2
0x45b51  brtrue.s loc_45B9B
0x45b53  ldc.i4   0x100
0x45b58  ldstr    aPut// "put"
0x45b5d  ldnull
0x45b5e  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x45b63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45b68  ldc.i4.3
0x45b69  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x45b6e  dup
0x45b6f  ldc.i4.0
0x45b70  ldc.i4.0
0x45b71  ldnull
0x45b72  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45b77  stelem.ref
0x45b78  dup
0x45b79  ldc.i4.1
0x45b7a  ldc.i4.3
0x45b7b  ldnull
0x45b7c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45b81  stelem.ref
0x45b82  dup
0x45b83  ldc.i4.2
0x45b84  ldc.i4.1
0x45b85  ldnull
0x45b86  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45b8b  stelem.ref
0x45b8c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x45b91  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray>>::Create(!!T0)
0x45b96  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray>> <>o__35::<>p__2
0x45b9b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray>> <>o__35::<>p__2
0x45ba0  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray>>::Target
0x45ba5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray>> <>o__35::<>p__2
0x45baa  ldloc.s  4
0x45bac  ldstr    aDeleteddatabas// "DeletedDatabases"
0x45bb1  ldloc.3
0x45bb2  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::.ctor(object)
0x45bb7  callvirt instance void class [mscorlib]System.Action`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray>::Invoke(var<u1>, !!T0, var<u1>, void)
0x45bbc  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__35::<>p__3
0x45bc1  brtrue.s loc_45C1F
0x45bc3  ldc.i4   0x100
0x45bc8  ldstr    aSpartantraceco// "SpartanTraceCompleted"
0x45bcd  ldnull
0x45bce  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x45bd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45bd8  ldc.i4.5
0x45bd9  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x45bde  dup
0x45bdf  ldc.i4.0
0x45be0  ldc.i4.1
0x45be1  ldnull
0x45be2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45be7  stelem.ref
0x45be8  dup
0x45be9  ldc.i4.1
0x45bea  ldc.i4.1
0x45beb  ldnull
0x45bec  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45bf1  stelem.ref
0x45bf2  dup
0x45bf3  ldc.i4.2
0x45bf4  ldc.i4.1
0x45bf5  ldnull
0x45bf6  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45bfb  stelem.ref
0x45bfc  dup
0x45bfd  ldc.i4.3
0x45bfe  ldc.i4.0
0x45bff  ldnull
0x45c00  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45c05  stelem.ref
0x45c06  dup
0x45c07  ldc.i4.4
0x45c08  ldc.i4.0
0x45c09  ldnull
0x45c0a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45c0f  stelem.ref
0x45c10  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x45c15  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>>::Create(!!T0)
0x45c1a  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__35::<>p__3
0x45c1f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__35::<>p__3
0x45c24  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>>::Target
0x45c29  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>> <>o__35::<>p__3
0x45c2e  ldarg.0
0x45c2f  ldfld    class SpartanFunctionLogger <ListAllDeletedDatabasesAsync>d__35::<logger>5__3
0x45c34  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x45c39  ldsfld   string [mscorlib]System.String::Empty
0x45c3e  ldarg.0
0x45c3f  ldfld    object <ListAllDeletedDatabasesAsync>d__35::<inputData>5__2
0x45c44  ldloc.s  4
0x45c46  callvirt instance void class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, object>::Invoke(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x45c4b  ldloc.2
0x45c4c  callvirt instance class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ListDatabaseResponseProperty [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ListDatabasesResponse::get_ResponseProperty()
0x45c51  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseGetResponseProperty> [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ListDatabaseResponseProperty::get_DatabaseList()
0x45c56  ldnull
0x45c57  ldftn    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseInfo Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::FromResponseProperty(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseGetResponseProperty property)
0x45c5d  newobj   instance void class [mscorlib]System.Func`2<class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseGetResponseProperty, class Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseInfo>::.ctor(object, native int)
0x45c62  call     T0x2B000104
0x45c67  call     T0x2B000105
0x45c6c  stloc.1
0x45c6d  leave    loc_45D2D
0x45c72  stloc.s  8
0x45c74  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>> <>o__35::<>p__4
0x45c79  brtrue.s loc_45CE1
0x45c7b  ldc.i4   0x100
0x45c80  ldstr    aSpartantraceer// "SpartanTraceError"
0x45c85  ldnull
0x45c86  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x45c8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45c90  ldc.i4.6
0x45c91  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x45c96  dup
0x45c97  ldc.i4.0
0x45c98  ldc.i4.1
0x45c99  ldnull
0x45c9a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45c9f  stelem.ref
0x45ca0  dup
0x45ca1  ldc.i4.1
0x45ca2  ldc.i4.1
0x45ca3  ldnull
0x45ca4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45ca9  stelem.ref
0x45caa  dup
0x45cab  ldc.i4.2
0x45cac  ldc.i4.1
0x45cad  ldnull
0x45cae  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45cb3  stelem.ref
0x45cb4  dup
0x45cb5  ldc.i4.3
0x45cb6  ldc.i4.0
0x45cb7  ldnull
0x45cb8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45cbd  stelem.ref
0x45cbe  dup
0x45cbf  ldc.i4.4
0x45cc0  ldc.i4.1
0x45cc1  ldnull
0x45cc2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x45cc7  stelem.ref
0x45cc8  dup
0x45cc9  ldc.i4.5
0x45cca  ldc.i4.1
0x45ccb  ldnull
0x45ccc  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
  ... truncated ...
```
