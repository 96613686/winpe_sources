# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::InstallDynamicsPackageInternal

- ea: `0x6260`
- end: `0x64e2`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::InstallDynamicsPackageInternal`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x61f0`

## callees

- `0x6260`
- `0x6540`
- `0x6670`
- `0x66e0`
- `0x6c10`
- `0x6c30`
- `0x6c50`
- `0x6cc0`
- `0x16d30`
- `0x19470`

## string_xrefs

- `0x629f`: `Found {0} in cache {1}.`
- `0x6323`: `PackageDeployer: Starting {0} install.`
- `0x63d0`: `Failed to install package {0} on attempt {1} using Multi Tenant PD. `
- `0x640b`: `Failed to install package {0} on attempt {1}.`
- `0x6465`: `Failed to install package {0} on attempt {1}. Retrying in {2} seconds. Reason for retry: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x6260  newobj   instance void <>c__DisplayClass34_0::.ctor()
0x6265  stloc.0
0x6266  ldloc.0
0x6267  ldarg.0
0x6268  stfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass34_0::<>4__this
0x626d  ldloc.0
0x626e  ldarg.3
0x626f  stfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x6274  ldloc.0
0x6275  ldarg.1
0x6276  stfld    string <>c__DisplayClass34_0::solutionUniqueName
0x627b  ldarg.2
0x627c  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x6281  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6286  stloc.1
0x6287  ldloc.0
0x6288  ldloc.1
0x6289  ldloc.0
0x628a  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x628f  ldarg.2
0x6290  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x6295  call     string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.PackageDeployerUtility::UnzipPackageToCacheDirectory(string, string, string)
0x629a  stfld    string <>c__DisplayClass34_0::unzippedPackageDirectory
0x629f  ldstr    aFound0InCache1// "Found {0} in cache {1}."
0x62a4  ldloc.0
0x62a5  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x62aa  ldloc.0
0x62ab  ldfld    string <>c__DisplayClass34_0::unzippedPackageDirectory
0x62b0  call     string [mscorlib]System.String::Format(string, object, object)
0x62b5  ldc.i4.0
0x62b6  newarr   [mscorlib]System.Object
0x62bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x62c0  ldloc.0
0x62c1  ldsfld   class [mscorlib]System.Func`1<class Microsoft.Crm.Tools.Admin.ADInfo> <>c::<>9__34_0
0x62c6  dup
0x62c7  brtrue.s loc_62E0
0x62c9  pop
0x62ca  ldsfld   class <>c <>c::<>9
0x62cf  ldftn    instance class Microsoft.Crm.Tools.Admin.ADInfo <>c::<InstallDynamicsPackageInternal>b__34_0()
0x62d5  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.Tools.Admin.ADInfo>::.ctor(object, native int)
0x62da  dup
0x62db  stsfld   class [mscorlib]System.Func`1<class Microsoft.Crm.Tools.Admin.ADInfo> <>c::<>9__34_0
0x62e0  ldstr    aGetadinfo// "GetADInfo"
0x62e5  ldloc.0
0x62e6  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x62eb  ldarg.0
0x62ec  call     instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CancellationToken()
0x62f1  call     T0x2B000009
0x62f6  stfld    class Microsoft.Crm.Tools.Admin.ADInfo <>c__DisplayClass34_0::adInfo
0x62fb  ldloc.0
0x62fc  ldloc.0
0x62fd  ldftn    instance string[] <>c__DisplayClass34_0::<InstallDynamicsPackageInternal>b__1()
0x6303  newobj   instance void class [mscorlib]System.Func`1<string[]>::.ctor(object, native int)
0x6308  ldstr    aGetpdeargs// "GetPDEArgs"
0x630d  ldloc.0
0x630e  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x6313  ldarg.0
0x6314  call     instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CancellationToken()
0x6319  call     T0x2B00000A
0x631e  stfld    string[] <>c__DisplayClass34_0::PDEargs
0x6323  ldstr    aPackagedeploye// "PackageDeployer: Starting {0} install."
0x6328  ldloc.0
0x6329  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x632e  call     string [mscorlib]System.String::Format(string, object)
0x6333  ldc.i4.0
0x6334  newarr   [mscorlib]System.Object
0x6339  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x633e  ldc.i4.1
0x633f  stloc.2
0x6340  ldsfld   string [mscorlib]System.String::Empty
0x6345  stloc.3
0x6346  ldnull
0x6347  stloc.s  4
0x6349  ldloc.0
0x634a  ldc.i4.1
0x634b  stfld    bool <>c__DisplayClass34_0::allowMultiTenantPDUse
0x6350  ldc.i4.1
0x6351  stloc.2
0x6352  br       loc_64CB
0x6357  ldarg.0
0x6358  call     instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CancellationToken()
0x635d  stloc.s  7
0x635f  ldloca.s 7
0x6361  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x6366  ldloc.0
0x6367  ldfld    class [mscorlib]System.Func`1<class Microsoft.Crm.Tools.Admin.PackageDeployerResult> <>c__DisplayClass34_0::<>9__2
0x636c  dup
0x636d  brtrue.s loc_6387
0x636f  pop
0x6370  ldloc.0
0x6371  ldloc.0
0x6372  ldftn    instance class Microsoft.Crm.Tools.Admin.PackageDeployerResult <>c__DisplayClass34_0::<InstallDynamicsPackageInternal>b__2()
0x6378  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.Tools.Admin.PackageDeployerResult>::.ctor(object, native int)
0x637d  dup
0x637e  stloc.s  8
0x6380  stfld    class [mscorlib]System.Func`1<class Microsoft.Crm.Tools.Admin.PackageDeployerResult> <>c__DisplayClass34_0::<>9__2
0x6385  ldloc.s  8
0x6387  ldstr    aDeploypackage// "DeployPackage"
0x638c  ldloc.0
0x638d  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x6392  ldarg.0
0x6393  call     instance valuetype [mscorlib]System.Threading.CancellationToken [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CancellationToken()
0x6398  call     T0x2B00000B
0x639d  stloc.s  4
0x639f  ldloc.s  4
0x63a1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Tools.Admin.PackageDeployerResult::PDLogs
0x63a6  call     string Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::GetPDResultLogsForTrace(class [mscorlib]System.Collections.Generic.IList`1<string> list)
0x63ab  stloc.3
0x63ac  ldloc.s  4
0x63ae  ldfld    bool Microsoft.Crm.Tools.Admin.PackageDeployerResult::IsSuccess
0x63b3  brtrue   loc_64D2
0x63b8  ldloc.0
0x63b9  ldfld    bool <>c__DisplayClass34_0::allowMultiTenantPDUse
0x63be  brfalse.s loc_640B
0x63c0  ldloc.s  4
0x63c2  ldfld    bool Microsoft.Crm.Tools.Admin.PackageDeployerResult::IsCriticalServerFailure
0x63c7  brfalse.s loc_640B
0x63c9  ldloc.0
0x63ca  ldc.i4.0
0x63cb  stfld    bool <>c__DisplayClass34_0::allowMultiTenantPDUse
0x63d0  ldstr    aFailedToInstal_1// "Failed to install package {0} on attemp"...
0x63d5  ldloc.0
0x63d6  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x63db  ldloc.2
0x63dc  box      [mscorlib]System.Int32
0x63e1  call     string [mscorlib]System.String::Format(string, object, object)
0x63e6  ldstr    aRetryingUsingS// "Retrying using Single Tenant PD. Error:"...
0x63eb  ldloc.3
0x63ec  call     string [mscorlib]System.String::Format(string, object)
0x63f1  call     string [mscorlib]System.String::Concat(string, string)
0x63f6  stloc.s  9
0x63f8  ldloc.0
0x63f9  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x63fe  ldloc.s  9
0x6400  ldnull
0x6401  call     void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::LogInfoAsError(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, string message, class [mscorlib]System.Exception ex)
0x6406  br       loc_64C7
0x640b  ldstr    aFailedToInstal_2// "Failed to install package {0} on attemp"...
0x6410  ldloc.0
0x6411  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x6416  ldloc.2
0x6417  box      [mscorlib]System.Int32
0x641c  call     string [mscorlib]System.String::Format(string, object, object)
0x6421  stloc.s  5
0x6423  ldloc.0
0x6424  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x6429  ldloc.s  5
0x642b  ldnull
0x642c  call     void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::LogInfoAsError(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, string message, class [mscorlib]System.Exception ex)
0x6431  ldloc.3
0x6432  call     class Microsoft.Crm.Tools.Admin.PackageRetryInfo Microsoft.Crm.Tools.Admin.PackageRetryInfo::GetPackageRetryInfo(string pdLogs)
0x6437  stloc.s  6
0x6439  ldloc.s  6
0x643b  callvirt instance bool Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_ShouldRetry()
0x6440  brfalse  loc_64D2
0x6445  ldloc.s  6
0x6447  callvirt instance valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_RetryReason()
0x644c  ldc.i4.2
0x644d  ceq
0x644f  ldloc.0
0x6450  ldfld    bool <>c__DisplayClass34_0::allowMultiTenantPDUse
0x6455  and
0x6456  brfalse.s loc_6465
0x6458  ldloc.0
0x6459  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x645e  call     bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::UseMultiTenantPackageDeployer(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x6463  brtrue.s loc_64D2
0x6465  ldstr    aFailedToInstal_3// "Failed to install package {0} on attemp"...
0x646a  ldc.i4.4
0x646b  newarr   [mscorlib]System.Object
0x6470  dup
0x6471  ldc.i4.0
0x6472  ldloc.0
0x6473  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x6478  stelem.ref
0x6479  dup
0x647a  ldc.i4.1
0x647b  ldloc.2
0x647c  box      [mscorlib]System.Int32
0x6481  stelem.ref
0x6482  dup
0x6483  ldc.i4.2
0x6484  ldloc.s  6
0x6486  callvirt instance int32 Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_RetryInterval()
0x648b  ldc.i4   0x3E8
0x6490  div
0x6491  box      [mscorlib]System.Int32
0x6496  stelem.ref
0x6497  dup
0x6498  ldc.i4.3
0x6499  ldloc.s  6
0x649b  callvirt instance valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_RetryReason()
0x64a0  box      Microsoft.Crm.Tools.Admin.PackageRetryReason
0x64a5  stelem.ref
0x64a6  call     string [mscorlib]System.String::Format(string, object[])
0x64ab  stloc.s  5
0x64ad  ldloc.0
0x64ae  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x64b3  ldloc.s  5
0x64b5  ldnull
0x64b6  call     void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::LogInfoAsError(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, string message, class [mscorlib]System.Exception ex)
0x64bb  ldloc.s  6
0x64bd  callvirt instance int32 Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_RetryInterval()
0x64c2  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x64c7  ldloc.2
0x64c8  ldc.i4.1
0x64c9  add
0x64ca  stloc.2
0x64cb  ldloc.2
0x64cc  ldc.i4.3
0x64cd  ble      loc_6357
0x64d2  ldloc.s  4
0x64d4  ldloc.3
0x64d5  ldloc.0
0x64d6  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x64db  ldloc.2
0x64dc  call     void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::ProcessPackageDeploymentResult(class Microsoft.Crm.Tools.Admin.PackageDeployerResult result, string pdLogs, string solutionUniqueName, int32 attempt)
0x64e1  ret
```
