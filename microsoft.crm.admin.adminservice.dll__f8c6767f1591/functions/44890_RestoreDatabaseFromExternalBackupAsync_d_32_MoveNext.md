# <RestoreDatabaseFromExternalBackupAsync>d__32::MoveNext

- ea: `0x44890`
- end: `0x450b1`
- name: `<RestoreDatabaseFromExternalBackupAsync>d__32::MoveNext`
- size: `2081`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
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
- `0x3a830`
- `0x3a8a0`
- `0x3f450`
- `0x44890`

## string_xrefs

- `0x44f4a`: `SpartanTraceCompleted`
- `0x448db`: `storageUri`
- `0x448eb`: `sasToken`
- `0x449ba`: `StorageUri`

## pseudocode

```c

```

## disassembly

```asm
0x44890  ldarg.0
0x44891  ldfld    int32 <RestoreDatabaseFromExternalBackupAsync>d__32::<>1__state
0x44896  stloc.0
0x44897  ldarg.0
0x44898  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanService <RestoreDatabaseFromExternalBackupAsync>d__32::<>4__this
0x4489d  stloc.1
0x4489e  ldloc.0
0x4489f  ldc.i4.1
0x448a0  ble.un   loc_44B36
0x448a5  ldarg.0
0x448a6  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::operationId
0x448ab  ldstr    aOperationid// "operationId"
0x448b0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x448b5  ldarg.0
0x448b6  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::azureRegion
0x448bb  ldstr    aAzureregion_1// "azureRegion"
0x448c0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x448c5  ldarg.0
0x448c6  ldfld    valuetype [mscorlib]System.Guid <RestoreDatabaseFromExternalBackupAsync>d__32::scaleGroupId
0x448cb  ldstr    aScalegroupid// "scaleGroupId"
0x448d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x448d5  ldarg.0
0x448d6  ldfld    class [System]System.Uri <RestoreDatabaseFromExternalBackupAsync>d__32::storageUri
0x448db  ldstr    aStorageuri// "storageUri"
0x448e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x448e5  ldarg.0
0x448e6  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::sasToken
0x448eb  ldstr    aSastoken// "sasToken"
0x448f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x448f5  ldarg.0
0x448f6  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::backupName
0x448fb  ldstr    aBackupname// "backupName"
0x44900  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x44905  ldarg.0
0x44906  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::databaseCollation
0x4490b  ldstr    aDatabasecollat// "databaseCollation"
0x44910  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x44915  ldarg.0
0x44916  ldfld    valuetype [mscorlib]System.Guid <RestoreDatabaseFromExternalBackupAsync>d__32::organizationId
0x4491b  ldstr    aOrganizationid// "organizationId"
0x44920  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x44925  ldarg.0
0x44926  ldarg.0
0x44927  ldfld    valuetype [mscorlib]System.Guid <RestoreDatabaseFromExternalBackupAsync>d__32::scaleGroupId
0x4492c  call     string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::RetrieveTierGroupName(valuetype [mscorlib]System.Guid scaleGroupId)
0x44931  stfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::<tierGroup>5__2
0x44936  ldarg.0
0x44937  ldstr    aRestoredatabas_0// "RestoreDatabaseFromExternalBackupAsync"
0x4493c  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x44941  stfld    class SpartanFunctionLogger <RestoreDatabaseFromExternalBackupAsync>d__32::<logger>5__3
0x44946  ldarg.0
0x44947  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x4494c  stfld    object <RestoreDatabaseFromExternalBackupAsync>d__32::<inputData>5__4
0x44951  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__0
0x44956  brtrue.s loc_44991
0x44958  ldc.i4.0
0x44959  ldstr    aTargetazurereg// "TargetAzureRegion"
0x4495e  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x44963  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x44968  ldc.i4.2
0x44969  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x4496e  dup
0x4496f  ldc.i4.0
0x44970  ldc.i4.0
0x44971  ldnull
0x44972  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44977  stelem.ref
0x44978  dup
0x44979  ldc.i4.1
0x4497a  ldc.i4.1
0x4497b  ldnull
0x4497c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44981  stelem.ref
0x44982  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x44987  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x4498c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__0
0x44991  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__0
0x44996  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x4499b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__0
0x449a0  ldarg.0
0x449a1  ldfld    object <RestoreDatabaseFromExternalBackupAsync>d__32::<inputData>5__4
0x449a6  ldarg.0
0x449a7  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::azureRegion
0x449ac  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x449b1  pop
0x449b2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [System]System.Uri, object>> <>o__32::<>p__1
0x449b7  brtrue.s loc_449F2
0x449b9  ldc.i4.0
0x449ba  ldstr    aStorageuri_0// "StorageUri"
0x449bf  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x449c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x449c9  ldc.i4.2
0x449ca  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x449cf  dup
0x449d0  ldc.i4.0
0x449d1  ldc.i4.0
0x449d2  ldnull
0x449d3  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x449d8  stelem.ref
0x449d9  dup
0x449da  ldc.i4.1
0x449db  ldc.i4.1
0x449dc  ldnull
0x449dd  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x449e2  stelem.ref
0x449e3  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x449e8  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [System]System.Uri, object>>::Create(!!T0)
0x449ed  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [System]System.Uri, object>> <>o__32::<>p__1
0x449f2  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [System]System.Uri, object>> <>o__32::<>p__1
0x449f7  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [System]System.Uri, object>>::Target
0x449fc  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [System]System.Uri, object>> <>o__32::<>p__1
0x44a01  ldarg.0
0x44a02  ldfld    object <RestoreDatabaseFromExternalBackupAsync>d__32::<inputData>5__4
0x44a07  ldarg.0
0x44a08  ldfld    class [System]System.Uri <RestoreDatabaseFromExternalBackupAsync>d__32::storageUri
0x44a0d  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, class [System]System.Uri, object>::Invoke(char, var<u1>, !!T0)
0x44a12  pop
0x44a13  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__2
0x44a18  brtrue.s loc_44A53
0x44a1a  ldc.i4.0
0x44a1b  ldstr    aScalegroupid_0// "ScaleGroupId"
0x44a20  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x44a25  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x44a2a  ldc.i4.2
0x44a2b  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x44a30  dup
0x44a31  ldc.i4.0
0x44a32  ldc.i4.0
0x44a33  ldnull
0x44a34  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44a39  stelem.ref
0x44a3a  dup
0x44a3b  ldc.i4.1
0x44a3c  ldc.i4.1
0x44a3d  ldnull
0x44a3e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44a43  stelem.ref
0x44a44  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x44a49  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x44a4e  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__2
0x44a53  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__2
0x44a58  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x44a5d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__32::<>p__2
0x44a62  ldarg.0
0x44a63  ldfld    object <RestoreDatabaseFromExternalBackupAsync>d__32::<inputData>5__4
0x44a68  ldarg.0
0x44a69  ldfld    valuetype [mscorlib]System.Guid <RestoreDatabaseFromExternalBackupAsync>d__32::scaleGroupId
0x44a6e  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x44a73  pop
0x44a74  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__3
0x44a79  brtrue.s loc_44AB4
0x44a7b  ldc.i4.0
0x44a7c  ldstr    aBackupname_0// "BackupName"
0x44a81  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x44a86  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x44a8b  ldc.i4.2
0x44a8c  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x44a91  dup
0x44a92  ldc.i4.0
0x44a93  ldc.i4.0
0x44a94  ldnull
0x44a95  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44a9a  stelem.ref
0x44a9b  dup
0x44a9c  ldc.i4.1
0x44a9d  ldc.i4.1
0x44a9e  ldnull
0x44a9f  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44aa4  stelem.ref
0x44aa5  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x44aaa  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x44aaf  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__3
0x44ab4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__3
0x44ab9  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x44abe  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__3
0x44ac3  ldarg.0
0x44ac4  ldfld    object <RestoreDatabaseFromExternalBackupAsync>d__32::<inputData>5__4
0x44ac9  ldarg.0
0x44aca  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::backupName
0x44acf  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x44ad4  pop
0x44ad5  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__4
0x44ada  brtrue.s loc_44B15
0x44adc  ldc.i4.0
0x44add  ldstr    aTiergroup_1// "TierGroup"
0x44ae2  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x44ae7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x44aec  ldc.i4.2
0x44aed  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x44af2  dup
0x44af3  ldc.i4.0
0x44af4  ldc.i4.0
0x44af5  ldnull
0x44af6  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44afb  stelem.ref
0x44afc  dup
0x44afd  ldc.i4.1
0x44afe  ldc.i4.1
0x44aff  ldnull
0x44b00  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44b05  stelem.ref
0x44b06  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x44b0b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x44b10  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__4
0x44b15  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__4
0x44b1a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x44b1f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__32::<>p__4
0x44b24  ldarg.0
0x44b25  ldfld    object <RestoreDatabaseFromExternalBackupAsync>d__32::<inputData>5__4
0x44b2a  ldarg.0
0x44b2b  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::<tierGroup>5__2
0x44b30  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x44b35  pop
0x44b36  nop
0x44b37  ldloc.0
0x44b38  brfalse  loc_44C28
0x44b3d  ldloc.0
0x44b3e  ldc.i4.1
0x44b3f  beq      loc_44F1A
0x44b44  ldarg.0
0x44b45  ldarg.0
0x44b46  ldfld    valuetype [mscorlib]System.Guid <RestoreDatabaseFromExternalBackupAsync>d__32::scaleGroupId
0x44b4b  call     string Microsoft.Crm.Admin.AdminService.LogicalGroupKeyProvider::CreateLogicalServerGroupKey(valuetype [mscorlib]System.Guid scalegroupId)
0x44b50  stfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::<logicalServerGroupKey>5__5
0x44b55  ldstr    aTier1// "Tier1"
0x44b5a  stloc.3
0x44b5b  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::.ctor()
0x44b60  dup
0x44b61  ldarg.0
0x44b62  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::operationId
0x44b67  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_OperationId(string)
0x44b6c  dup
0x44b6d  ldarg.0
0x44b6e  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::azureRegion
0x44b73  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x44b78  dup
0x44b79  ldarg.0
0x44b7a  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::<logicalServerGroupKey>5__5
0x44b7f  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_LogicalServerGroupKey(string)
0x44b84  dup
0x44b85  ldarg.0
0x44b86  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::<tierGroup>5__2
0x44b8b  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_TargetDatabaseTierGroup(string)
0x44b90  dup
0x44b91  ldloc.3
0x44b92  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_TargetDatabaseTierName(string)
0x44b97  dup
0x44b98  ldarg.0
0x44b99  ldfld    class [System]System.Uri <RestoreDatabaseFromExternalBackupAsync>d__32::storageUri
0x44b9e  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x44ba3  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_StorageUri(string)
0x44ba8  dup
0x44ba9  ldarg.0
0x44baa  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::sasToken
0x44baf  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_StorageSasToken(string)
0x44bb4  dup
0x44bb5  ldarg.0
0x44bb6  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::backupName
0x44bbb  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_LastBackupName(string)
0x44bc0  dup
0x44bc1  ldarg.0
0x44bc2  ldfld    string <RestoreDatabaseFromExternalBackupAsync>d__32::databaseCollation
0x44bc7  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty::set_Collation(string)
0x44bcc  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::GetSpartanRestoreExternalTimeout()
0x44bd1  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.RestoreDatabaseFromExternalBackupParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.RestoreDatabaseFromExternalBackupRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x44bd6  stloc.s  4
0x44bd8  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x44bdd  ldloc.s  4
0x44bdf  ldarg.0
0x44be0  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <RestoreDatabaseFromExternalBackupAsync>d__32::cancellationToken
0x44be5  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::RestoreDatabaseFromExternalBackupAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.RestoreDatabaseFromExternalBackupParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x44bea  ldc.i4.0
0x44beb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::ConfigureAwait(!!T0)
0x44bf0  stloc.s  7
0x44bf2  ldloca.s 7
0x44bf4  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetAwaiter()
0x44bf9  stloc.s  6
0x44bfb  ldloca.s 6
0x44bfd  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::get_IsCompleted()
0x44c02  brtrue.s loc_44C45
0x44c04  ldarg.0
0x44c05  ldc.i4.0
0x44c06  dup
0x44c07  stloc.0
0x44c08  stfld    int32 <RestoreDatabaseFromExternalBackupAsync>d__32::<>1__state
0x44c0d  ldarg.0
0x44c0e  ldloc.s  6
0x44c10  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <RestoreDatabaseFromExternalBackupAsync>d__32::<>u__1
0x44c15  ldarg.0
0x44c16  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier> <RestoreDatabaseFromExternalBackupAsync>d__32::<>t__builder
0x44c1b  ldloca.s 6
0x44c1d  ldarg.0
0x44c1e  call     T0x2B0000FE
0x44c23  leave    loc_450B0
0x44c28  ldarg.0
0x44c29  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <RestoreDatabaseFromExternalBackupAsync>d__32::<>u__1
0x44c2e  stloc.s  6
0x44c30  ldarg.0
0x44c31  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <RestoreDatabaseFromExternalBackupAsync>d__32::<>u__1
0x44c36  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>
  ... truncated ...
```
