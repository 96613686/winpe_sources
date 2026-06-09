# <CreateDatabaseCopyAsync>d__25::MoveNext

- ea: `0x41de0`
- end: `0x4260c`
- name: `<CreateDatabaseCopyAsync>d__25::MoveNext`
- size: `2092`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x22ae0`
- `0x38ea0`
- `0x38ec0`
- `0x38ed0`
- `0x38ee0`
- `0x38ef0`
- `0x38f00`
- `0x38f10`
- `0x38f30`
- `0x38f50`
- `0x39520`
- `0x3a6f0`
- `0x3a8a0`
- `0x3f450`
- `0x41de0`

## string_xrefs

- `0x424a5`: `SpartanTraceCompleted`
- `0x41e47`: `CreateDatabaseCopyAsync`

## pseudocode

```c

```

## disassembly

```asm
0x41de0  ldarg.0
0x41de1  ldfld    int32 <CreateDatabaseCopyAsync>d__25::<>1__state
0x41de6  stloc.0
0x41de7  ldarg.0
0x41de8  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanService <CreateDatabaseCopyAsync>d__25::<>4__this
0x41ded  stloc.1
0x41dee  ldloc.0
0x41def  ldc.i4.1
0x41df0  ble.un   loc_420B6
0x41df5  ldarg.0
0x41df6  ldfld    string <CreateDatabaseCopyAsync>d__25::operationId
0x41dfb  ldstr    aOperationid// "operationId"
0x41e00  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x41e05  ldarg.0
0x41e06  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseCopyAsync>d__25::databaseIdentifier
0x41e0b  ldstr    aDatabaseidenti// "databaseIdentifier"
0x41e10  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x41e15  ldarg.0
0x41e16  ldfld    string <CreateDatabaseCopyAsync>d__25::targetRegion
0x41e1b  ldstr    aTargetregion// "targetRegion"
0x41e20  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x41e25  ldarg.0
0x41e26  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseCopyAsync>d__25::scalegroupId
0x41e2b  ldstr    aScalegroupid_2// "scalegroupId"
0x41e30  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x41e35  ldarg.0
0x41e36  ldarg.0
0x41e37  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseCopyAsync>d__25::scalegroupId
0x41e3c  call     string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::RetrieveTierGroupName(valuetype [mscorlib]System.Guid scaleGroupId)
0x41e41  stfld    string <CreateDatabaseCopyAsync>d__25::<tierGroup>5__2
0x41e46  ldarg.0
0x41e47  ldstr    aCreatedatabase_2// "CreateDatabaseCopyAsync"
0x41e4c  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x41e51  stfld    class SpartanFunctionLogger <CreateDatabaseCopyAsync>d__25::<logger>5__3
0x41e56  ldarg.0
0x41e57  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x41e5c  stfld    object <CreateDatabaseCopyAsync>d__25::<inputData>5__4
0x41e61  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__0
0x41e66  brtrue.s loc_41EA1
0x41e68  ldc.i4.0
0x41e69  ldstr    aDatabasename// "DatabaseName"
0x41e6e  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41e73  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x41e78  ldc.i4.2
0x41e79  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41e7e  dup
0x41e7f  ldc.i4.0
0x41e80  ldc.i4.0
0x41e81  ldnull
0x41e82  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41e87  stelem.ref
0x41e88  dup
0x41e89  ldc.i4.1
0x41e8a  ldc.i4.1
0x41e8b  ldnull
0x41e8c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41e91  stelem.ref
0x41e92  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x41e97  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x41e9c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__0
0x41ea1  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__0
0x41ea6  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x41eab  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__0
0x41eb0  ldarg.0
0x41eb1  ldfld    object <CreateDatabaseCopyAsync>d__25::<inputData>5__4
0x41eb6  ldarg.0
0x41eb7  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseCopyAsync>d__25::databaseIdentifier
0x41ebc  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x41ec1  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41ec6  pop
0x41ec7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__1
0x41ecc  brtrue.s loc_41F07
0x41ece  ldc.i4.0
0x41ecf  ldstr    aSourceazurereg// "SourceAzureRegion"
0x41ed4  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41ed9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x41ede  ldc.i4.2
0x41edf  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41ee4  dup
0x41ee5  ldc.i4.0
0x41ee6  ldc.i4.0
0x41ee7  ldnull
0x41ee8  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41eed  stelem.ref
0x41eee  dup
0x41eef  ldc.i4.1
0x41ef0  ldc.i4.1
0x41ef1  ldnull
0x41ef2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41ef7  stelem.ref
0x41ef8  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x41efd  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x41f02  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__1
0x41f07  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__1
0x41f0c  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x41f11  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__1
0x41f16  ldarg.0
0x41f17  ldfld    object <CreateDatabaseCopyAsync>d__25::<inputData>5__4
0x41f1c  ldarg.0
0x41f1d  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseCopyAsync>d__25::databaseIdentifier
0x41f22  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x41f27  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41f2c  pop
0x41f2d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__2
0x41f32  brtrue.s loc_41F6D
0x41f34  ldc.i4.0
0x41f35  ldstr    aLogicalserver_0// "LogicalServer"
0x41f3a  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41f3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x41f44  ldc.i4.2
0x41f45  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41f4a  dup
0x41f4b  ldc.i4.0
0x41f4c  ldc.i4.0
0x41f4d  ldnull
0x41f4e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41f53  stelem.ref
0x41f54  dup
0x41f55  ldc.i4.1
0x41f56  ldc.i4.1
0x41f57  ldnull
0x41f58  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41f5d  stelem.ref
0x41f5e  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x41f63  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x41f68  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__2
0x41f6d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__2
0x41f72  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x41f77  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__2
0x41f7c  ldarg.0
0x41f7d  ldfld    object <CreateDatabaseCopyAsync>d__25::<inputData>5__4
0x41f82  ldarg.0
0x41f83  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseCopyAsync>d__25::databaseIdentifier
0x41f88  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x41f8d  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41f92  pop
0x41f93  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__3
0x41f98  brtrue.s loc_41FD3
0x41f9a  ldc.i4.0
0x41f9b  ldstr    aTargetazurereg// "TargetAzureRegion"
0x41fa0  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x41fa5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x41faa  ldc.i4.2
0x41fab  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x41fb0  dup
0x41fb1  ldc.i4.0
0x41fb2  ldc.i4.0
0x41fb3  ldnull
0x41fb4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41fb9  stelem.ref
0x41fba  dup
0x41fbb  ldc.i4.1
0x41fbc  ldc.i4.1
0x41fbd  ldnull
0x41fbe  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x41fc3  stelem.ref
0x41fc4  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x41fc9  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x41fce  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__3
0x41fd3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__3
0x41fd8  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x41fdd  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__3
0x41fe2  ldarg.0
0x41fe3  ldfld    object <CreateDatabaseCopyAsync>d__25::<inputData>5__4
0x41fe8  ldarg.0
0x41fe9  ldfld    string <CreateDatabaseCopyAsync>d__25::targetRegion
0x41fee  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x41ff3  pop
0x41ff4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__25::<>p__4
0x41ff9  brtrue.s loc_42034
0x41ffb  ldc.i4.0
0x41ffc  ldstr    aTargetscalegro// "TargetScaleGroupId"
0x42001  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x42006  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4200b  ldc.i4.2
0x4200c  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x42011  dup
0x42012  ldc.i4.0
0x42013  ldc.i4.0
0x42014  ldnull
0x42015  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4201a  stelem.ref
0x4201b  dup
0x4201c  ldc.i4.1
0x4201d  ldc.i4.1
0x4201e  ldnull
0x4201f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x42024  stelem.ref
0x42025  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4202a  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x4202f  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__25::<>p__4
0x42034  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__25::<>p__4
0x42039  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x4203e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__25::<>p__4
0x42043  ldarg.0
0x42044  ldfld    object <CreateDatabaseCopyAsync>d__25::<inputData>5__4
0x42049  ldarg.0
0x4204a  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseCopyAsync>d__25::scalegroupId
0x4204f  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x42054  pop
0x42055  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__5
0x4205a  brtrue.s loc_42095
0x4205c  ldc.i4.0
0x4205d  ldstr    aTiergroup_1// "TierGroup"
0x42062  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x42067  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4206c  ldc.i4.2
0x4206d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x42072  dup
0x42073  ldc.i4.0
0x42074  ldc.i4.0
0x42075  ldnull
0x42076  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4207b  stelem.ref
0x4207c  dup
0x4207d  ldc.i4.1
0x4207e  ldc.i4.1
0x4207f  ldnull
0x42080  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x42085  stelem.ref
0x42086  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4208b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x42090  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__5
0x42095  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__5
0x4209a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x4209f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__25::<>p__5
0x420a4  ldarg.0
0x420a5  ldfld    object <CreateDatabaseCopyAsync>d__25::<inputData>5__4
0x420aa  ldarg.0
0x420ab  ldfld    string <CreateDatabaseCopyAsync>d__25::<tierGroup>5__2
0x420b0  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x420b5  pop
0x420b6  nop
0x420b7  ldloc.0
0x420b8  brfalse  loc_4219A
0x420bd  ldloc.0
0x420be  ldc.i4.1
0x420bf  beq      loc_42475
0x420c4  ldarg.0
0x420c5  ldarg.0
0x420c6  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseCopyAsync>d__25::scalegroupId
0x420cb  call     string Microsoft.Crm.Admin.AdminService.LogicalGroupKeyProvider::CreateLogicalServerGroupKey(valuetype [mscorlib]System.Guid scalegroupId)
0x420d0  stfld    string <CreateDatabaseCopyAsync>d__25::<targetLogicalServerGroupKey>5__5
0x420d5  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x420da  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseCopyRequestProperty::.ctor()
0x420df  dup
0x420e0  ldarg.0
0x420e1  ldfld    string <CreateDatabaseCopyAsync>d__25::operationId
0x420e6  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_OperationId(string)
0x420eb  dup
0x420ec  ldarg.0
0x420ed  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseCopyAsync>d__25::databaseIdentifier
0x420f2  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x420f7  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x420fc  dup
0x420fd  ldarg.0
0x420fe  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseCopyAsync>d__25::databaseIdentifier
0x42103  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x42108  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_LogicalServerName(string)
0x4210d  dup
0x4210e  ldarg.0
0x4210f  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseCopyAsync>d__25::databaseIdentifier
0x42114  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x42119  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_DatabaseName(string)
0x4211e  dup
0x4211f  ldarg.0
0x42120  ldfld    string <CreateDatabaseCopyAsync>d__25::targetRegion
0x42125  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseInTargetLocationRequestProperty::set_TargetLocation(string)
0x4212a  dup
0x4212b  ldarg.0
0x4212c  ldfld    string <CreateDatabaseCopyAsync>d__25::<tierGroup>5__2
0x42131  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseInTargetLocationRequestProperty::set_TargetDatabaseTierGroup(string)
0x42136  dup
0x42137  ldarg.0
0x42138  ldfld    string <CreateDatabaseCopyAsync>d__25::<targetLogicalServerGroupKey>5__5
0x4213d  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseInTargetLocationRequestProperty::set_TargetLogicalServerGroupKey(string)
0x42142  ldloca.s 5
0x42144  initobj  [mscorlib]System.TimeSpan
0x4214a  ldloc.s  5
0x4214c  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CreateDatabaseCopyParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CreateDatabaseCopyRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x42151  ldarg.0
0x42152  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CreateDatabaseCopyAsync>d__25::cancellationToken
0x42157  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::CreateDatabaseCopyAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.CreateDatabaseCopyParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x4215c  ldc.i4.0
0x4215d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::ConfigureAwait(!!T0)
0x42162  stloc.s  6
0x42164  ldloca.s 6
0x42166  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetAwaiter()
0x4216b  stloc.s  4
0x4216d  ldloca.s 4
0x4216f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::get_IsCompleted()
0x42174  brtrue.s loc_421B7
0x42176  ldarg.0
0x42177  ldc.i4.0
0x42178  dup
0x42179  stloc.0
0x4217a  stfld    int32 <CreateDatabaseCopyAsync>d__25::<>1__state
0x4217f  ldarg.0
0x42180  ldloc.s  4
0x42182  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <CreateDatabaseCopyAsync>d__25::<>u__1
  ... truncated ...
```
