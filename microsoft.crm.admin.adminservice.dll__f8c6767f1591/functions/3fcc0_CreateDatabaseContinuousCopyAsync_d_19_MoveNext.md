# <CreateDatabaseContinuousCopyAsync>d__19::MoveNext

- ea: `0x3fcc0`
- end: `0x404a9`
- name: `<CreateDatabaseContinuousCopyAsync>d__19::MoveNext`
- size: `2025`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x22ae0`
- `0x38e70`
- `0x38ec0`
- `0x38ed0`
- `0x38ee0`
- `0x38ef0`
- `0x38f00`
- `0x38f10`
- `0x38f30`
- `0x38f50`
- `0x39520`
- `0x3a6b0`
- `0x3f450`
- `0x3fcc0`

## string_xrefs

- `0x4034a`: `SpartanTraceCompleted`
- `0x3fd12`: `CreateDatabaseContinuousCopyAsync`

## pseudocode

```c

```

## disassembly

```asm
0x3fcc0  ldarg.0
0x3fcc1  ldfld    int32 <CreateDatabaseContinuousCopyAsync>d__19::<>1__state
0x3fcc6  stloc.0
0x3fcc7  ldloc.0
0x3fcc8  brfalse  loc_40065
0x3fccd  ldarg.0
0x3fcce  ldfld    string <CreateDatabaseContinuousCopyAsync>d__19::operationId
0x3fcd3  ldstr    aOperationid// "operationId"
0x3fcd8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3fcdd  ldarg.0
0x3fcde  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseContinuousCopyAsync>d__19::primaryDatabase
0x3fce3  ldstr    aPrimarydatabas// "primaryDatabase"
0x3fce8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3fced  ldarg.0
0x3fcee  ldfld    string <CreateDatabaseContinuousCopyAsync>d__19::targetAzureRegion
0x3fcf3  ldstr    aTargetazurereg_0// "targetAzureRegion"
0x3fcf8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3fcfd  ldarg.0
0x3fcfe  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseContinuousCopyAsync>d__19::scalegroupId
0x3fd03  call     bool Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::IsDisasterRecoveryForOrganizationsEnabled(valuetype [mscorlib]System.Guid scaleGroupId)
0x3fd08  brtrue.s loc_3FD11
0x3fd0a  ldnull
0x3fd0b  stloc.1
0x3fd0c  leave    loc_40494
0x3fd11  ldarg.0
0x3fd12  ldstr    aCreatedatabase_0// "CreateDatabaseContinuousCopyAsync"
0x3fd17  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x3fd1c  stfld    class SpartanFunctionLogger <CreateDatabaseContinuousCopyAsync>d__19::<logger>5__2
0x3fd21  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x3fd26  ldstr    aSpartanenviron// "SpartanEnvironment"
0x3fd2b  ldc.i4.1
0x3fd2c  callvirt T0x2B000014
0x3fd31  stloc.2
0x3fd32  ldarg.0
0x3fd33  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x3fd38  stfld    object <CreateDatabaseContinuousCopyAsync>d__19::<inputData>5__3
0x3fd3d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__0
0x3fd42  brtrue.s loc_3FD7D
0x3fd44  ldc.i4.0
0x3fd45  ldstr    aPrimarydatabas_0// "PrimaryDatabaseName"
0x3fd4a  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3fd4f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fd54  ldc.i4.2
0x3fd55  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3fd5a  dup
0x3fd5b  ldc.i4.0
0x3fd5c  ldc.i4.0
0x3fd5d  ldnull
0x3fd5e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fd63  stelem.ref
0x3fd64  dup
0x3fd65  ldc.i4.1
0x3fd66  ldc.i4.1
0x3fd67  ldnull
0x3fd68  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fd6d  stelem.ref
0x3fd6e  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3fd73  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3fd78  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__0
0x3fd7d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__0
0x3fd82  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3fd87  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__0
0x3fd8c  ldarg.0
0x3fd8d  ldfld    object <CreateDatabaseContinuousCopyAsync>d__19::<inputData>5__3
0x3fd92  ldarg.0
0x3fd93  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseContinuousCopyAsync>d__19::primaryDatabase
0x3fd98  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_DatabaseName()
0x3fd9d  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3fda2  pop
0x3fda3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__1
0x3fda8  brtrue.s loc_3FDE3
0x3fdaa  ldc.i4.0
0x3fdab  ldstr    aSourceazurereg// "SourceAzureRegion"
0x3fdb0  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3fdb5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fdba  ldc.i4.2
0x3fdbb  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3fdc0  dup
0x3fdc1  ldc.i4.0
0x3fdc2  ldc.i4.0
0x3fdc3  ldnull
0x3fdc4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fdc9  stelem.ref
0x3fdca  dup
0x3fdcb  ldc.i4.1
0x3fdcc  ldc.i4.1
0x3fdcd  ldnull
0x3fdce  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fdd3  stelem.ref
0x3fdd4  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3fdd9  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3fdde  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__1
0x3fde3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__1
0x3fde8  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3fded  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__1
0x3fdf2  ldarg.0
0x3fdf3  ldfld    object <CreateDatabaseContinuousCopyAsync>d__19::<inputData>5__3
0x3fdf8  ldarg.0
0x3fdf9  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseContinuousCopyAsync>d__19::primaryDatabase
0x3fdfe  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x3fe03  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3fe08  pop
0x3fe09  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__2
0x3fe0e  brtrue.s loc_3FE49
0x3fe10  ldc.i4.0
0x3fe11  ldstr    aPrimarydatabas_1// "PrimaryDatabaseLogicalServer"
0x3fe16  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3fe1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fe20  ldc.i4.2
0x3fe21  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3fe26  dup
0x3fe27  ldc.i4.0
0x3fe28  ldc.i4.0
0x3fe29  ldnull
0x3fe2a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fe2f  stelem.ref
0x3fe30  dup
0x3fe31  ldc.i4.1
0x3fe32  ldc.i4.1
0x3fe33  ldnull
0x3fe34  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fe39  stelem.ref
0x3fe3a  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3fe3f  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3fe44  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__2
0x3fe49  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__2
0x3fe4e  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3fe53  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__2
0x3fe58  ldarg.0
0x3fe59  ldfld    object <CreateDatabaseContinuousCopyAsync>d__19::<inputData>5__3
0x3fe5e  ldarg.0
0x3fe5f  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseContinuousCopyAsync>d__19::primaryDatabase
0x3fe64  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_LogicalServer()
0x3fe69  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3fe6e  pop
0x3fe6f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__3
0x3fe74  brtrue.s loc_3FEAF
0x3fe76  ldc.i4.0
0x3fe77  ldstr    aTargetazurereg// "TargetAzureRegion"
0x3fe7c  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3fe81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fe86  ldc.i4.2
0x3fe87  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3fe8c  dup
0x3fe8d  ldc.i4.0
0x3fe8e  ldc.i4.0
0x3fe8f  ldnull
0x3fe90  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fe95  stelem.ref
0x3fe96  dup
0x3fe97  ldc.i4.1
0x3fe98  ldc.i4.1
0x3fe99  ldnull
0x3fe9a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fe9f  stelem.ref
0x3fea0  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3fea5  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3feaa  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__3
0x3feaf  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__3
0x3feb4  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3feb9  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__3
0x3febe  ldarg.0
0x3febf  ldfld    object <CreateDatabaseContinuousCopyAsync>d__19::<inputData>5__3
0x3fec4  ldarg.0
0x3fec5  ldfld    string <CreateDatabaseContinuousCopyAsync>d__19::targetAzureRegion
0x3feca  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3fecf  pop
0x3fed0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__19::<>p__4
0x3fed5  brtrue.s loc_3FF10
0x3fed7  ldc.i4.0
0x3fed8  ldstr    aScalegroupid_0// "ScaleGroupId"
0x3fedd  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3fee2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fee7  ldc.i4.2
0x3fee8  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3feed  dup
0x3feee  ldc.i4.0
0x3feef  ldc.i4.0
0x3fef0  ldnull
0x3fef1  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fef6  stelem.ref
0x3fef7  dup
0x3fef8  ldc.i4.1
0x3fef9  ldc.i4.1
0x3fefa  ldnull
0x3fefb  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3ff00  stelem.ref
0x3ff01  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3ff06  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x3ff0b  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__19::<>p__4
0x3ff10  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__19::<>p__4
0x3ff15  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x3ff1a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__19::<>p__4
0x3ff1f  ldarg.0
0x3ff20  ldfld    object <CreateDatabaseContinuousCopyAsync>d__19::<inputData>5__3
0x3ff25  ldarg.0
0x3ff26  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseContinuousCopyAsync>d__19::scalegroupId
0x3ff2b  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x3ff30  pop
0x3ff31  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__5
0x3ff36  brtrue.s loc_3FF71
0x3ff38  ldc.i4.0
0x3ff39  ldstr    aSpartanenviron// "SpartanEnvironment"
0x3ff3e  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3ff43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ff48  ldc.i4.2
0x3ff49  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3ff4e  dup
0x3ff4f  ldc.i4.0
0x3ff50  ldc.i4.0
0x3ff51  ldnull
0x3ff52  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3ff57  stelem.ref
0x3ff58  dup
0x3ff59  ldc.i4.1
0x3ff5a  ldc.i4.1
0x3ff5b  ldnull
0x3ff5c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3ff61  stelem.ref
0x3ff62  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x3ff67  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x3ff6c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__5
0x3ff71  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__5
0x3ff76  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x3ff7b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__19::<>p__5
0x3ff80  ldarg.0
0x3ff81  ldfld    object <CreateDatabaseContinuousCopyAsync>d__19::<inputData>5__3
0x3ff86  ldloc.2
0x3ff87  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x3ff8c  pop
0x3ff8d  ldarg.0
0x3ff8e  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier <CreateDatabaseContinuousCopyAsync>d__19::primaryDatabase
0x3ff93  callvirt instance string Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::get_AzureRegion()
0x3ff98  ldarg.0
0x3ff99  ldfld    string <CreateDatabaseContinuousCopyAsync>d__19::targetAzureRegion
0x3ff9e  ldc.i4.5
0x3ff9f  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x3ffa4  brfalse  loc_40065
0x3ffa9  ldstr    aTargetAzureReg// "Target azure region of "
0x3ffae  ldarg.0
0x3ffaf  ldfld    string <CreateDatabaseContinuousCopyAsync>d__19::targetAzureRegion
0x3ffb4  ldstr    aCannotMatchSou// " cannot match source region of primary "...
0x3ffb9  call     string [mscorlib]System.String::Concat(string, string, string)
0x3ffbe  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3ffc3  stloc.3
0x3ffc4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.ArgumentException>> <>o__19::<>p__6
0x3ffc9  brtrue.s loc_40031
0x3ffcb  ldc.i4   0x100
0x3ffd0  ldstr    aSpartantraceer// "SpartanTraceError"
0x3ffd5  ldnull
0x3ffd6  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x3ffdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ffe0  ldc.i4.6
0x3ffe1  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x3ffe6  dup
0x3ffe7  ldc.i4.0
0x3ffe8  ldc.i4.1
0x3ffe9  ldnull
0x3ffea  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3ffef  stelem.ref
0x3fff0  dup
0x3fff1  ldc.i4.1
0x3fff2  ldc.i4.1
0x3fff3  ldnull
0x3fff4  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x3fff9  stelem.ref
0x3fffa  dup
0x3fffb  ldc.i4.2
0x3fffc  ldc.i4.1
0x3fffd  ldnull
0x3fffe  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40003  stelem.ref
0x40004  dup
0x40005  ldc.i4.3
0x40006  ldc.i4.0
0x40007  ldnull
0x40008  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4000d  stelem.ref
0x4000e  dup
0x4000f  ldc.i4.4
0x40010  ldc.i4.1
0x40011  ldnull
0x40012  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40017  stelem.ref
0x40018  dup
0x40019  ldc.i4.5
0x4001a  ldc.i4.1
0x4001b  ldnull
0x4001c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x40021  stelem.ref
0x40022  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::InvokeMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x40027  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.ArgumentException>>::Create(!!T0)
0x4002c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.ArgumentException>> <>o__19::<>p__6
0x40031  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.ArgumentException>> <>o__19::<>p__6
0x40036  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.ArgumentException>>::Target
0x4003b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Action`7<class [System.Core]System.Runtime.CompilerServices.CallSite, class SpartanFunctionLogger, valuetype [mscorlib]System.Guid, string, object, class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject, class [mscorlib]System.ArgumentException>> <>o__19::<>p__6
0x40040  ldarg.0
0x40041  ldfld    class SpartanFunctionLogger <CreateDatabaseContinuousCopyAsync>d__19::<logger>5__2
0x40046  ldarg.0
0x40047  ldfld    valuetype [mscorlib]System.Guid <CreateDatabaseContinuousCopyAsync>d__19::organizationId
  ... truncated ...
```
