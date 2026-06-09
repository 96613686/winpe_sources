# <>c__DisplayClass34_0::<InstallDynamicsPackageInternal>b__1

- ea: `0x19480`
- end: `0x19525`
- name: `<>c__DisplayClass34_0::<InstallDynamicsPackageInternal>b__1`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5dc0`
- `0x5e00`
- `0x68d0`
- `0x6980`
- `0x6fd0`
- `0x71d0`
- `0x8630`
- `0x8670`
- `0x17d50`
- `0x17e10`
- `0x19480`

## pseudocode

```c

```

## disassembly

```asm
0x19480  ldarg.0
0x19481  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass34_0::<>4__this
0x19486  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x1948b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x19490  ldarg.0
0x19491  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass34_0::<>4__this
0x19496  ldarg.0
0x19497  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x1949c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::GetUserIdForPackageInstall(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x194a1  ldarg.0
0x194a2  ldfld    string <>c__DisplayClass34_0::unzippedPackageDirectory
0x194a7  ldarg.0
0x194a8  ldfld    string <>c__DisplayClass34_0::solutionUniqueName
0x194ad  ldc.i4.1
0x194ae  ldsfld   bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::IsLive
0x194b3  ldarg.0
0x194b4  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass34_0::<>4__this
0x194b9  call     instance bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::get_IsSystemConverted()
0x194be  brfalse.s loc_194CD
0x194c0  ldarg.0
0x194c1  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass34_0::<>4__this
0x194c6  call     instance bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::get_IsUpgrade()
0x194cb  br.s     loc_194CE
0x194cd  ldc.i4.0
0x194ce  ldc.i4.1
0x194cf  ldarg.0
0x194d0  ldfld    class Microsoft.Crm.Tools.Admin.OrganizationInfo <>c__DisplayClass34_0::organizationInfo
0x194d5  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x194da  ldarg.0
0x194db  ldfld    class Microsoft.Crm.Tools.Admin.ADInfo <>c__DisplayClass34_0::adInfo
0x194e0  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADRootDomainScheme()
0x194e5  ldstr    aHttps// "https"
0x194ea  callvirt instance bool [mscorlib]System.String::Equals(string)
0x194ef  ldarg.0
0x194f0  ldfld    class Microsoft.Crm.Tools.Admin.ADInfo <>c__DisplayClass34_0::adInfo
0x194f5  callvirt instance string Microsoft.Crm.Tools.Admin.ADInfo::get_ADDiscoveryRootDomain()
0x194fa  ldstr    aOriginaldbvers// "OriginalDBVersion={0}|IsUpgrade={1}"
0x194ff  ldarg.0
0x19500  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass34_0::<>4__this
0x19505  call     instance string Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::GetDatabaseVersionString()
0x1950a  ldarg.0
0x1950b  ldfld    class Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction <>c__DisplayClass34_0::<>4__this
0x19510  call     instance bool Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::get_IsUpgrade()
0x19515  box      [mscorlib]System.Boolean
0x1951a  call     string [mscorlib]System.String::Format(string, object, object)
0x1951f  call     string[] Microsoft.Crm.Tools.Admin.PackageDeployerSetupUtility::CreatePackageDeploymentExecutorArgs(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, string packageLocation, string packageName, bool allowCodeExecution, bool isLive, bool isSystemConvertedSolutionUpgrade, bool isInternalCrmAppsInstall, string organizationUniqueName, bool useSSL, string hostname, string payload)
0x19524  ret
```
