# Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::InstallPackage

- ea: `0x51e0`
- end: `0x5425`
- name: `Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::InstallPackage`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x4f70`

## callees

- `0x4e70`
- `0x4e80`
- `0x4e90`
- `0x4ea0`
- `0x4eb0`
- `0x4f40`
- `0x50d0`
- `0x51e0`
- `0x5430`
- `0x54c0`
- `0x55a0`
- `0x64b0`
- `0x91b0`
- `0x15380`
- `0x153e0`
- `0x1c060`
- `0x1c3b0`
- `0x233b0`
- `0x23590`
- `0x23600`

## string_xrefs

- `0x51e6`: `Starting InstallPackage for User [{0}] SolutionId [{1}] PackageUrl [{2}]`
- `0x5254`: `SampleDataConfig.json`
- `0x5273`: `Found SampleDataConfig.json : `
- `0x52a2`: `Using hard-coded FreeTrialBase configuration`
- `0x5348`: `IsTemplateProvisioning=True`
- `0x53ae`: `PackageDeployer Second Attempt Log : `
- `0x53ce`: `PackageDeployer failed on second attempt for solutionId [`

## pseudocode

```c

```

## disassembly

```asm
0x51e0  ldarg.0
0x51e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51e6  ldstr    aStartingInstal// "Starting InstallPackage for User [{0}] "...
0x51eb  ldc.i4.3
0x51ec  newarr   [mscorlib]System.Object
0x51f1  dup
0x51f2  ldc.i4.0
0x51f3  ldarg.1
0x51f4  box      [mscorlib]System.Guid
0x51f9  stelem.ref
0x51fa  dup
0x51fb  ldc.i4.1
0x51fc  ldarg.2
0x51fd  box      [mscorlib]System.Guid
0x5202  stelem.ref
0x5203  dup
0x5204  ldc.i4.2
0x5205  ldarg.3
0x5206  stelem.ref
0x5207  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x520c  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x5211  call     class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::get_Instance()
0x5216  ldarg.2
0x5217  ldarg.3
0x5218  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::PreparePackageWithUniqueFolder(valuetype [mscorlib]System.Guid packageId, string packageUrl)
0x521d  stloc.0
0x521e  ldloc.0
0x521f  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x5224  stloc.1
0x5225  ldloc.0
0x5226  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x522b  stloc.2
0x522c  ldloc.2
0x522d  ldstr    aPackagename// "packageName"
0x5232  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string, string)
0x5237  ldarg.0
0x5238  ldstr    aPackagename_0// "PackageName ["
0x523d  ldloc.2
0x523e  ldstr    asc_36586// "]"
0x5243  call     string [mscorlib]System.String::Concat(string, string, string)
0x5248  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x524d  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SampleDataConfig::.ctor()
0x5252  stloc.3
0x5253  ldloc.1
0x5254  ldstr    aSampledataconf// "SampleDataConfig.json"
0x5259  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x525e  stloc.s  4
0x5260  ldloc.s  4
0x5262  call     bool [mscorlib]System.IO.File::Exists(string)
0x5267  brfalse.s loc_5293
0x5269  ldloc.s  4
0x526b  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x5270  stloc.s  6
0x5272  ldarg.0
0x5273  ldstr    aFoundSampledat// "Found SampleDataConfig.json : "
0x5278  ldloc.s  6
0x527a  call     string [mscorlib]System.String::Concat(string, string)
0x527f  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x5284  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x5289  ldloc.s  6
0x528b  call     T0x2B00001D
0x5290  stloc.3
0x5291  br.s     loc_52C0
0x5293  ldloc.2
0x5294  ldstr    aTestdrivepacka// "TestDrivePackage"
0x5299  ldc.i4.3
0x529a  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x529f  brfalse.s loc_52C0
0x52a1  ldarg.0
0x52a2  ldstr    aUsingHardCoded// "Using hard-coded FreeTrialBase configur"...
0x52a7  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x52ac  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SampleDataConfig::.ctor()
0x52b1  dup
0x52b2  ldc.i4.1
0x52b3  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SampleDataConfig::set_ProcessUsers(bool value)
0x52b8  dup
0x52b9  ldc.i4.1
0x52ba  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SampleDataConfig::set_ProcessOfficeSampleData(bool value)
0x52bf  stloc.3
0x52c0  ldloc.3
0x52c1  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SampleDataConfig::get_ProcessUsers()
0x52c6  stloc.s  5
0x52c8  ldnull
0x52c9  stloc.s  7
0x52cb  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x52d0  ldarg.0
0x52d1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x52d6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x52db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x52e0  ldarg.1
0x52e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RetrieveSystemUserById(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid systemUserId)
0x52e6  ldstr    aDomainname_0// "domainname"
0x52eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x52f0  isinst   [mscorlib]System.String
0x52f5  stloc.s  8
0x52f7  ldloc.s  8
0x52f9  ldstr    aInitialuserupn// "initialUserUpn"
0x52fe  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string, string)
0x5303  ldarg.0
0x5304  ldloc.1
0x5305  ldloc.s  5
0x5307  ldloc.s  8
0x5309  call     instance class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageDataReport Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::ProcessImportConfigAndDataFiles(string packagePath, bool processUsers, string initialUserUpn)
0x530e  stloc.s  7
0x5310  newobj   instance void [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments::.ctor()
0x5315  dup
0x5316  ldarg.0
0x5317  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x531c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5321  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5326  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments::OrganizationId
0x532b  dup
0x532c  ldarg.1
0x532d  stfld    valuetype [mscorlib]System.Guid [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments::UserId
0x5332  dup
0x5333  ldloc.1
0x5334  stfld    string [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageLocation
0x5339  dup
0x533a  ldloc.2
0x533b  stfld    string [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0x5340  dup
0x5341  ldc.i4.1
0x5342  stfld    bool [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments::AllowPackageCodeExecution
0x5347  dup
0x5348  ldstr    aIstemplateprov// "IsTemplateProvisioning=True"
0x534d  stfld    string [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments::Payload
0x5352  stloc.s  9
0x5354  ldloc.s  9
0x5356  call     class Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapperResult Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::DoImport(class [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments arguments)
0x535b  dup
0x535c  ldarg.0
0x535d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5362  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5367  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x536c  ldloc.2
0x536d  call     string Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::ProcessAndGetBriefLog(class Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapperResult result, valuetype [mscorlib]System.Guid orgId, string packageName)
0x5372  stloc.s  0xA
0x5374  ldarg.0
0x5375  ldstr    aPackagedeploye// "PackageDeployer Log : "
0x537a  ldloc.s  0xA
0x537c  call     string [mscorlib]System.String::Concat(string, string)
0x5381  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x5386  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapperResult::get_Successful()
0x538b  brtrue.s loc_53F5
0x538d  ldloc.s  9
0x538f  call     class Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapperResult Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapper::DoImport(class [Microsoft.Crm.PackageDeployment]Microsoft.Crm.PackageDeployment.PackageDeployerArguments arguments)
0x5394  dup
0x5395  ldarg.0
0x5396  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x539b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x53a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x53a5  ldloc.2
0x53a6  call     string Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::ProcessAndGetBriefLog(class Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapperResult result, valuetype [mscorlib]System.Guid orgId, string packageName)
0x53ab  stloc.s  0xA
0x53ad  ldarg.0
0x53ae  ldstr    aPackagedeploye_0// "PackageDeployer Second Attempt Log : "
0x53b3  ldloc.s  0xA
0x53b5  call     string [mscorlib]System.String::Concat(string, string)
0x53ba  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x53bf  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.PackageDeployerExecutableWrapperResult::get_Successful()
0x53c4  brtrue.s loc_53F5
0x53c6  ldc.i4.4
0x53c7  newarr   [mscorlib]System.Object
0x53cc  dup
0x53cd  ldc.i4.0
0x53ce  ldstr    aPackagedeploye_1// "PackageDeployer failed on second attemp"...
0x53d3  stelem.ref
0x53d4  dup
0x53d5  ldc.i4.1
0x53d6  ldarg.2
0x53d7  box      [mscorlib]System.Guid
0x53dc  stelem.ref
0x53dd  dup
0x53de  ldc.i4.2
0x53df  ldstr    aLog// "]. Log : "
0x53e4  stelem.ref
0x53e5  dup
0x53e6  ldc.i4.3
0x53e7  ldloc.s  0xA
0x53e9  stelem.ref
0x53ea  call     string [mscorlib]System.String::Concat(object[])
0x53ef  newobj   instance void [mscorlib]System.ApplicationException::.ctor(string)
0x53f4  throw
0x53f5  ldloc.3
0x53f6  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SampleDataConfig::get_ProcessOfficeSampleData()
0x53fb  brfalse.s loc_5408
0x53fd  ldarg.0
0x53fe  ldloc.s  7
0x5400  ldloc.1
0x5401  call     instance class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageDataReport Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::GetO365SampleData(class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageDataReport dataReport, string packagePath)
0x5406  stloc.s  7
0x5408  ldarg.0
0x5409  ldloc.s  7
0x540b  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::RecordImportedData(class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageDataReport dataReport)
0x5410  ldloc.s  7
0x5412  stloc.s  0xB
0x5414  leave.s  loc_5422
0x5416  call     class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::get_Instance()
0x541b  ldloc.0
0x541c  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::TryCleanupPackageFolder(string packageAssemblyPath)
0x5421  endfinally
0x5422  ldloc.s  0xB
0x5424  ret
```
