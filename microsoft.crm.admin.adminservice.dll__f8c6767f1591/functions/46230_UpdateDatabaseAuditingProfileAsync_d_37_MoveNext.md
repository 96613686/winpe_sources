# <UpdateDatabaseAuditingProfileAsync>d__37::MoveNext

- ea: `0x46230`
- end: `0x469f7`
- name: `<UpdateDatabaseAuditingProfileAsync>d__37::MoveNext`
- size: `1991`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x391c0`
- `0x391e0`
- `0x39200`
- `0x39220`
- `0x39240`
- `0x392e0`
- `0x39520`
- `0x3f450`
- `0x46230`

## string_xrefs

- `0x46896`: `SpartanTraceCompleted`
- `0x4629b`: `UpdateDatabaseAuditingProfileAsync`

## pseudocode

```c

```

## disassembly

```asm
0x46230  ldarg.0
0x46231  ldfld    int32 <UpdateDatabaseAuditingProfileAsync>d__37::<>1__state
0x46236  stloc.0
0x46237  ldloc.0
0x46238  brfalse  loc_46567
0x4623d  ldarg.0
0x4623e  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::azureRegion
0x46243  ldstr    aAzureregion_1// "azureRegion"
0x46248  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4624d  ldarg.0
0x4624e  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::logicalServerName
0x46253  ldstr    aLogicalservern// "logicalServerName"
0x46258  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4625d  ldarg.0
0x4625e  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::databaseName
0x46263  ldstr    aDatabasename_0// "databaseName"
0x46268  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4626d  ldarg.0
0x4626e  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::auditingProfileName
0x46273  ldstr    aAuditingprofil_0// "auditingProfileName"
0x46278  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x4627d  ldarg.0
0x4627e  ldfld    valuetype [mscorlib]System.DateTime <UpdateDatabaseAuditingProfileAsync>d__37::expireTimeUtc
0x46283  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x46288  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4628d  brfalse.s loc_4629A
0x4628f  ldstr    aSpecifiedExpir// "Specified expireTimeUtc is past date ti"...
0x46294  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x46299  throw
0x4629a  ldarg.0
0x4629b  ldstr    aUpdatedatabase// "UpdateDatabaseAuditingProfileAsync"
0x462a0  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x462a5  stfld    class SpartanFunctionLogger <UpdateDatabaseAuditingProfileAsync>d__37::<logger>5__2
0x462aa  ldarg.0
0x462ab  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x462b0  stfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x462b5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__0
0x462ba  brtrue.s loc_462F5
0x462bc  ldc.i4.0
0x462bd  ldstr    aOperationid_0// "OperationId"
0x462c2  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x462c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x462cc  ldc.i4.2
0x462cd  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x462d2  dup
0x462d3  ldc.i4.0
0x462d4  ldc.i4.0
0x462d5  ldnull
0x462d6  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x462db  stelem.ref
0x462dc  dup
0x462dd  ldc.i4.1
0x462de  ldc.i4.1
0x462df  ldnull
0x462e0  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x462e5  stelem.ref
0x462e6  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x462eb  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x462f0  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__0
0x462f5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__0
0x462fa  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x462ff  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__0
0x46304  ldarg.0
0x46305  ldfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x4630a  ldarg.0
0x4630b  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::operationId
0x46310  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x46315  pop
0x46316  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__1
0x4631b  brtrue.s loc_46356
0x4631d  ldc.i4.0
0x4631e  ldstr    aAzureregion_0// "AzureRegion"
0x46323  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x46328  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4632d  ldc.i4.2
0x4632e  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x46333  dup
0x46334  ldc.i4.0
0x46335  ldc.i4.0
0x46336  ldnull
0x46337  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4633c  stelem.ref
0x4633d  dup
0x4633e  ldc.i4.1
0x4633f  ldc.i4.1
0x46340  ldnull
0x46341  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x46346  stelem.ref
0x46347  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4634c  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x46351  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__1
0x46356  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__1
0x4635b  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x46360  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__1
0x46365  ldarg.0
0x46366  ldfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x4636b  ldarg.0
0x4636c  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::azureRegion
0x46371  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x46376  pop
0x46377  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__2
0x4637c  brtrue.s loc_463B7
0x4637e  ldc.i4.0
0x4637f  ldstr    aLogicalservern_0// "LogicalServerName"
0x46384  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x46389  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4638e  ldc.i4.2
0x4638f  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x46394  dup
0x46395  ldc.i4.0
0x46396  ldc.i4.0
0x46397  ldnull
0x46398  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4639d  stelem.ref
0x4639e  dup
0x4639f  ldc.i4.1
0x463a0  ldc.i4.1
0x463a1  ldnull
0x463a2  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x463a7  stelem.ref
0x463a8  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x463ad  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x463b2  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__2
0x463b7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__2
0x463bc  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x463c1  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__2
0x463c6  ldarg.0
0x463c7  ldfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x463cc  ldarg.0
0x463cd  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::logicalServerName
0x463d2  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x463d7  pop
0x463d8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__3
0x463dd  brtrue.s loc_46418
0x463df  ldc.i4.0
0x463e0  ldstr    aDatabasename// "DatabaseName"
0x463e5  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x463ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x463ef  ldc.i4.2
0x463f0  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x463f5  dup
0x463f6  ldc.i4.0
0x463f7  ldc.i4.0
0x463f8  ldnull
0x463f9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x463fe  stelem.ref
0x463ff  dup
0x46400  ldc.i4.1
0x46401  ldc.i4.1
0x46402  ldnull
0x46403  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x46408  stelem.ref
0x46409  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4640e  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x46413  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__3
0x46418  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__3
0x4641d  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x46422  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__3
0x46427  ldarg.0
0x46428  ldfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x4642d  ldarg.0
0x4642e  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::databaseName
0x46433  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x46438  pop
0x46439  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__4
0x4643e  brtrue.s loc_46479
0x46440  ldc.i4.0
0x46441  ldstr    aAuditingprofil_1// "AuditingProfileName"
0x46446  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x4644b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46450  ldc.i4.2
0x46451  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x46456  dup
0x46457  ldc.i4.0
0x46458  ldc.i4.0
0x46459  ldnull
0x4645a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4645f  stelem.ref
0x46460  dup
0x46461  ldc.i4.1
0x46462  ldc.i4.1
0x46463  ldnull
0x46464  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x46469  stelem.ref
0x4646a  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4646f  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x46474  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__4
0x46479  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__4
0x4647e  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x46483  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__4
0x46488  ldarg.0
0x46489  ldfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x4648e  ldarg.0
0x4648f  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::auditingProfileName
0x46494  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x46499  pop
0x4649a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.DateTime, object>> <>o__37::<>p__5
0x4649f  brtrue.s loc_464DA
0x464a1  ldc.i4.0
0x464a2  ldstr    aExpiretimeutc// "ExpireTimeUtc"
0x464a7  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x464ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x464b1  ldc.i4.2
0x464b2  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x464b7  dup
0x464b8  ldc.i4.0
0x464b9  ldc.i4.0
0x464ba  ldnull
0x464bb  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x464c0  stelem.ref
0x464c1  dup
0x464c2  ldc.i4.1
0x464c3  ldc.i4.1
0x464c4  ldnull
0x464c5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x464ca  stelem.ref
0x464cb  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x464d0  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.DateTime, object>>::Create(!!T0)
0x464d5  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.DateTime, object>> <>o__37::<>p__5
0x464da  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.DateTime, object>> <>o__37::<>p__5
0x464df  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.DateTime, object>>::Target
0x464e4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.DateTime, object>> <>o__37::<>p__5
0x464e9  ldarg.0
0x464ea  ldfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x464ef  ldarg.0
0x464f0  ldfld    valuetype [mscorlib]System.DateTime <UpdateDatabaseAuditingProfileAsync>d__37::expireTimeUtc
0x464f5  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.DateTime, object>::Invoke(char, var<u1>, !!T0)
0x464fa  pop
0x464fb  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__6
0x46500  brtrue.s loc_4653B
0x46502  ldc.i4.0
0x46503  ldstr    aRequestername// "RequesterName"
0x46508  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x4650d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46512  ldc.i4.2
0x46513  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x46518  dup
0x46519  ldc.i4.0
0x4651a  ldc.i4.0
0x4651b  ldnull
0x4651c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x46521  stelem.ref
0x46522  dup
0x46523  ldc.i4.1
0x46524  ldc.i4.1
0x46525  ldnull
0x46526  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4652b  stelem.ref
0x4652c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x46531  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x46536  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__6
0x4653b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__6
0x46540  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x46545  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__37::<>p__6
0x4654a  ldarg.0
0x4654b  ldfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<inputData>5__3
0x46550  ldarg.0
0x46551  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::requesterName
0x46556  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x4655b  pop
0x4655c  ldarg.0
0x4655d  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x46562  stfld    object <UpdateDatabaseAuditingProfileAsync>d__37::<outputData>5__4
0x46567  nop
0x46568  ldloc.0
0x46569  brfalse  loc_46624
0x4656e  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x46573  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseAuditingProfileRequestProperty::.ctor()
0x46578  dup
0x46579  ldarg.0
0x4657a  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::operationId
0x4657f  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_OperationId(string)
0x46584  dup
0x46585  ldarg.0
0x46586  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::azureRegion
0x4658b  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x46590  dup
0x46591  ldarg.0
0x46592  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::logicalServerName
0x46597  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_LogicalServerName(string)
0x4659c  dup
0x4659d  ldarg.0
0x4659e  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::databaseName
0x465a3  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseRequestProperty::set_DatabaseName(string)
0x465a8  dup
0x465a9  ldarg.0
0x465aa  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::auditingProfileName
0x465af  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseAuditingProfileRequestProperty::set_AuditingProfileName(string)
0x465b4  dup
0x465b5  ldarg.0
0x465b6  ldfld    valuetype [mscorlib]System.DateTime <UpdateDatabaseAuditingProfileAsync>d__37::expireTimeUtc
0x465bb  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseAuditingProfileRequestProperty::set_ExpireTimeUtc(valuetype [mscorlib]System.DateTime)
0x465c0  dup
0x465c1  ldarg.0
0x465c2  ldfld    string <UpdateDatabaseAuditingProfileAsync>d__37::requesterName
0x465c7  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseAuditingProfileRequestProperty::set_RequesterName(string)
0x465cc  ldloca.s 5
0x465ce  initobj  [mscorlib]System.TimeSpan
0x465d4  ldloc.s  5
0x465d6  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.UpdateDatabaseAuditingProfileParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.UpdateDatabaseAuditingProfileRequestProperty, valuetype [mscorlib]System.TimeSpan)
  ... truncated ...
```
