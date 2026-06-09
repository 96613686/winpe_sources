# <ExportDatabaseAsync>d__30::MoveNext

- ea: `0x43c30`
- end: `0x4408b`
- name: `<ExportDatabaseAsync>d__30::MoveNext`
- size: `1115`
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
- `0x43c30`

## string_xrefs

- `0x43f2b`: `SpartanTraceCompleted`
- `0x43c63`: `storageUri`
- `0x43c73`: `sasToken`
- `0x43dd2`: `StorageUri`
- `0x43e99`: `SharedAccessKey`

## pseudocode

```c

```

## disassembly

```asm
0x43c30  ldarg.0
0x43c31  ldfld    int32 <ExportDatabaseAsync>d__30::<>1__state
0x43c36  stloc.0
0x43c37  ldloc.0
0x43c38  brfalse  loc_43E2B
0x43c3d  ldarg.0
0x43c3e  ldfld    string <ExportDatabaseAsync>d__30::operationId
0x43c43  ldstr    aOperationid// "operationId"
0x43c48  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x43c4d  ldarg.0
0x43c4e  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <ExportDatabaseAsync>d__30::databaseIdentifier
0x43c53  ldstr    aDatabaseidenti// "databaseIdentifier"
0x43c58  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x43c5d  ldarg.0
0x43c5e  ldfld    string <ExportDatabaseAsync>d__30::storageUri
0x43c63  ldstr    aStorageuri// "storageUri"
0x43c68  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x43c6d  ldarg.0
0x43c6e  ldfld    string <ExportDatabaseAsync>d__30::sasToken
0x43c73  ldstr    aSastoken// "sasToken"
0x43c78  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x43c7d  ldarg.0
0x43c7e  ldstr    aExportdatabase// "ExportDatabaseAsync"
0x43c83  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x43c88  stfld    class SpartanFunctionLogger <ExportDatabaseAsync>d__30::<logger>5__2
0x43c8d  ldarg.0
0x43c8e  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x43c93  stfld    object <ExportDatabaseAsync>d__30::<inputData>5__3
0x43c98  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__0
0x43c9d  brtrue.s loc_43CD8
0x43c9f  ldc.i4.0
0x43ca0  ldstr    aDatabasename// "DatabaseName"
0x43ca5  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x43caa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43caf  ldc.i4.2
0x43cb0  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x43cb5  dup
0x43cb6  ldc.i4.0
0x43cb7  ldc.i4.0
0x43cb8  ldnull
0x43cb9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43cbe  stelem.ref
0x43cbf  dup
0x43cc0  ldc.i4.1
0x43cc1  ldc.i4.1
0x43cc2  ldnull
0x43cc3  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43cc8  stelem.ref
0x43cc9  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x43cce  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x43cd3  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__0
0x43cd8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__0
0x43cdd  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x43ce2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__0
0x43ce7  ldarg.0
0x43ce8  ldfld    object <ExportDatabaseAsync>d__30::<inputData>5__3
0x43ced  ldarg.0
0x43cee  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <ExportDatabaseAsync>d__30::databaseIdentifier
0x43cf3  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x43cf8  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x43cfd  pop
0x43cfe  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__1
0x43d03  brtrue.s loc_43D3E
0x43d05  ldc.i4.0
0x43d06  ldstr    aTargetazurereg// "TargetAzureRegion"
0x43d0b  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x43d10  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43d15  ldc.i4.2
0x43d16  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x43d1b  dup
0x43d1c  ldc.i4.0
0x43d1d  ldc.i4.0
0x43d1e  ldnull
0x43d1f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43d24  stelem.ref
0x43d25  dup
0x43d26  ldc.i4.1
0x43d27  ldc.i4.1
0x43d28  ldnull
0x43d29  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43d2e  stelem.ref
0x43d2f  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x43d34  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x43d39  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__1
0x43d3e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__1
0x43d43  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x43d48  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__1
0x43d4d  ldarg.0
0x43d4e  ldfld    object <ExportDatabaseAsync>d__30::<inputData>5__3
0x43d53  ldarg.0
0x43d54  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <ExportDatabaseAsync>d__30::databaseIdentifier
0x43d59  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x43d5e  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x43d63  pop
0x43d64  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__2
0x43d69  brtrue.s loc_43DA4
0x43d6b  ldc.i4.0
0x43d6c  ldstr    aLogicalserver_0// "LogicalServer"
0x43d71  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x43d76  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43d7b  ldc.i4.2
0x43d7c  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x43d81  dup
0x43d82  ldc.i4.0
0x43d83  ldc.i4.0
0x43d84  ldnull
0x43d85  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43d8a  stelem.ref
0x43d8b  dup
0x43d8c  ldc.i4.1
0x43d8d  ldc.i4.1
0x43d8e  ldnull
0x43d8f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43d94  stelem.ref
0x43d95  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x43d9a  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x43d9f  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__2
0x43da4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__2
0x43da9  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x43dae  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__2
0x43db3  ldarg.0
0x43db4  ldfld    object <ExportDatabaseAsync>d__30::<inputData>5__3
0x43db9  ldarg.0
0x43dba  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <ExportDatabaseAsync>d__30::databaseIdentifier
0x43dbf  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x43dc4  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x43dc9  pop
0x43dca  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__3
0x43dcf  brtrue.s loc_43E0A
0x43dd1  ldc.i4.0
0x43dd2  ldstr    aStorageuri_0// "StorageUri"
0x43dd7  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x43ddc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43de1  ldc.i4.2
0x43de2  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x43de7  dup
0x43de8  ldc.i4.0
0x43de9  ldc.i4.0
0x43dea  ldnull
0x43deb  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43df0  stelem.ref
0x43df1  dup
0x43df2  ldc.i4.1
0x43df3  ldc.i4.1
0x43df4  ldnull
0x43df5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43dfa  stelem.ref
0x43dfb  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x43e00  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x43e05  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__3
0x43e0a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__3
0x43e0f  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x43e14  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__30::<>p__3
0x43e19  ldarg.0
0x43e1a  ldfld    object <ExportDatabaseAsync>d__30::<inputData>5__3
0x43e1f  ldarg.0
0x43e20  ldfld    string <ExportDatabaseAsync>d__30::storageUri
0x43e25  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x43e2a  pop
0x43e2b  nop
0x43e2c  ldloc.0
0x43e2d  brfalse  loc_43EF7
0x43e32  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x43e37  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ExportDatabaseRequestProperty::.ctor()
0x43e3c  dup
0x43e3d  ldarg.0
0x43e3e  ldfld    string <ExportDatabaseAsync>d__30::operationId
0x43e43  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_OperationId(string)
0x43e48  dup
0x43e49  ldarg.0
0x43e4a  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <ExportDatabaseAsync>d__30::databaseIdentifier
0x43e4f  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x43e54  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x43e59  dup
0x43e5a  ldarg.0
0x43e5b  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <ExportDatabaseAsync>d__30::databaseIdentifier
0x43e60  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x43e65  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_LogicalServerName(string)
0x43e6a  dup
0x43e6b  ldarg.0
0x43e6c  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <ExportDatabaseAsync>d__30::databaseIdentifier
0x43e71  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x43e76  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_DatabaseName(string)
0x43e7b  dup
0x43e7c  ldarg.0
0x43e7d  ldfld    string <ExportDatabaseAsync>d__30::storageUri
0x43e82  newobj   instance void [System]System.Uri::.ctor(string)
0x43e87  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ExportDatabaseRequestProperty::set_StorageUri(class [System]System.Uri)
0x43e8c  dup
0x43e8d  ldarg.0
0x43e8e  ldfld    string <ExportDatabaseAsync>d__30::sasToken
0x43e93  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ExportDatabaseRequestProperty::set_StorageKey(string)
0x43e98  dup
0x43e99  ldstr    aSharedaccesske// "SharedAccessKey"
0x43e9e  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ExportDatabaseRequestProperty::set_StorageKeyType(string)
0x43ea3  ldloca.s 2
0x43ea5  initobj  [mscorlib]System.TimeSpan
0x43eab  ldloc.2
0x43eac  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ExportDatabaseParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ExportDatabaseRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x43eb1  ldarg.0
0x43eb2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExportDatabaseAsync>d__30::cancellationToken
0x43eb7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::ExportDatabaseAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ExportDatabaseParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x43ebc  ldc.i4.0
0x43ebd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::ConfigureAwait(!!T0)
0x43ec2  stloc.3
0x43ec3  ldloca.s 3
0x43ec5  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetAwaiter()
0x43eca  stloc.1
0x43ecb  ldloca.s 1
0x43ecd  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::get_IsCompleted()
0x43ed2  brtrue.s loc_43F13
0x43ed4  ldarg.0
0x43ed5  ldc.i4.0
0x43ed6  dup
0x43ed7  stloc.0
0x43ed8  stfld    int32 <ExportDatabaseAsync>d__30::<>1__state
0x43edd  ldarg.0
0x43ede  ldloc.1
0x43edf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <ExportDatabaseAsync>d__30::<>u__1
0x43ee4  ldarg.0
0x43ee5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ExportDatabaseAsync>d__30::<>t__builder
0x43eea  ldloca.s 1
0x43eec  ldarg.0
0x43eed  call     T0x2B0000FB
0x43ef2  leave    loc_4408A
0x43ef7  ldarg.0
0x43ef8  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <ExportDatabaseAsync>d__30::<>u__1
0x43efd  stloc.1
0x43efe  ldarg.0
0x43eff  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse> <ExportDatabaseAsync>d__30::<>u__1
0x43f04  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>
0x43f0a  ldarg.0
0x43f0b  ldc.i4.m1
0x43f0c  dup
0x43f0d  stloc.0
0x43f0e  stfld    int32 <ExportDatabaseAsync>d__30::<>1__state
0x43f13  ldloca.s 1
0x43f15  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.MessageResponse>::GetResult()
0x43f1a  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x43f1f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__30::<>p__4
0x43f24  brtrue.s loc_43F82
0x43f26  ldc.i4   0x100
0x43f2b  ldstr    aSpartantraceco// "SpartanTraceCompleted"
0x43f30  ldnull
0x43f31  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x43f36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x43f3b  ldc.i4.5
0x43f3c  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x43f41  dup
0x43f42  ldc.i4.0
0x43f43  ldc.i4.1
0x43f44  ldnull
0x43f45  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43f4a  stelem.ref
0x43f4b  dup
0x43f4c  ldc.i4.1
0x43f4d  ldc.i4.1
0x43f4e  ldnull
0x43f4f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43f54  stelem.ref
0x43f55  dup
0x43f56  ldc.i4.2
0x43f57  ldc.i4.1
0x43f58  ldnull
0x43f59  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43f5e  stelem.ref
0x43f5f  dup
0x43f60  ldc.i4.3
0x43f61  ldc.i4.0
0x43f62  ldnull
0x43f63  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43f68  stelem.ref
0x43f69  dup
0x43f6a  ldc.i4.4
0x43f6b  ldc.i4.1
0x43f6c  ldnull
0x43f6d  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x43f72  stelem.ref
0x43f73  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x43f78  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>>::Create(!!T0)
0x43f7d  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__30::<>p__4
0x43f82  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__30::<>p__4
0x43f87  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>>::Target
0x43f8c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>> <>o__30::<>p__4
0x43f91  ldarg.0
0x43f92  ldfld    class SpartanFunctionLogger <ExportDatabaseAsync>d__30::<logger>5__2
0x43f97  ldarg.0
0x43f98  ldfld    valuetype [mscorlib]System.Guid <ExportDatabaseAsync>d__30::organizationId
0x43f9d  ldarg.0
0x43f9e  ldfld    string <ExportDatabaseAsync>d__30::operationId
0x43fa3  ldarg.0
0x43fa4  ldfld    object <ExportDatabaseAsync>d__30::<inputData>5__3
0x43fa9  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x43fae  callvirt instance void class [mscorlib]System.Action`6<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject>::Invoke(var<u1>, !!T0, var<u1>, void, var<u1>, bool)
0x43fb3  leave    loc_4405C
0x43fb8  stloc.s  4
0x43fba  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.Exception>> <>o__30::<>p__5
0x43fbf  brtrue.s loc_44027
0x43fc1  ldc.i4   0x100
0x43fc6  ldstr    aSpartantraceer// "SpartanTraceError"
  ... truncated ...
```
