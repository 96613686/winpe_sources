# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::ImportAndUpgrade

- ea: `0x14630`
- end: `0x14bd2`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::ImportAndUpgrade`
- size: `1442`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x144e0`

## callees

- `0x22e0`
- `0x41c0`
- `0x45a0`
- `0x7640`
- `0x82c0`
- `0x8630`
- `0x8650`
- `0x8670`
- `0x86e0`
- `0x8720`
- `0x8ab0`
- `0x8bd0`
- `0x8bf0`
- `0x8c70`
- `0x8eb0`
- `0x9b40`
- `0x9d30`
- `0x10f60`
- `0x13930`
- `0x13950`
- `0x13b50`
- `0x13b80`
- `0x13f30`
- `0x14630`
- `0x155c0`
- `0x16720`
- `0x17a20`
- `0x17bf0`
- `0x17c90`

## string_xrefs

- `0x14951`: `Organization.Import.UpdateUsers`
- `0x14822`: `Adding users to the config database`
- `0x1488a`: `Organization.Import.UpdateOrganization`
- `0x148af`: `Organization.Import.UpdateOrganization`
- `0x14a04`: `Performing GrantServiceAccountAccess on SqlServerName {0} where SqlServerMachineName={1}, reportServerUrl={2}`

## pseudocode

```c

```

## disassembly

```asm
0x14630  ldnull
0x14631  stloc.0
0x14632  ldarg.1
0x14633  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14638  ldarg.1
0x14639  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x1463e  call     string [Microsoft.Crm.DatabaseInstaller.Common]Microsoft.Crm.DatabaseInstaller.Common.SharedDatabaseUtility::GetConnectionString(string, string)
0x14643  stloc.1
0x14644  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x14649  stloc.2
0x1464a  ldarg.1
0x1464b  ldarg.1
0x1464c  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14651  ldarg.1
0x14652  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14657  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::GetCrmOrganizationId(string, string)
0x1465c  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x14661  call     class Microsoft.Crm.Tools.Admin.LicenseController Microsoft.Crm.Tools.Admin.LicenseController::get_Instance()
0x14666  callvirt instance class Microsoft.Crm.Tools.Admin.MultipleTenancy Microsoft.Crm.Tools.Admin.LicenseController::GetMultipleTenancy()
0x1466b  stloc.3
0x1466c  ldstr    aMultipletenanc// "multipleTenancy for the deployment is {"...
0x14671  ldc.i4.1
0x14672  newarr   [mscorlib]System.Object
0x14677  dup
0x14678  ldc.i4.0
0x14679  ldloc.3
0x1467a  callvirt instance bool Microsoft.Crm.Tools.Admin.MultipleTenancy::get_IsMultipleTenancy()
0x1467f  box      [mscorlib]System.Boolean
0x14684  stelem.ref
0x14685  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1468a  ldarg.1
0x1468b  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14690  ldarg.1
0x14691  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14696  call     bool [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::OrgIdExists(string, string)
0x1469b  brtrue.s loc_146CD
0x1469d  ldloc.2
0x1469e  ldarg.1
0x1469f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x146a4  ldarg.1
0x146a5  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x146aa  ldarg.1
0x146ab  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationFriendlyName()
0x146b0  ldarg.1
0x146b1  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x146b6  ldarg.1
0x146b7  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x146bc  ldloc.1
0x146bd  ldarg.1
0x146be  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x146c3  ldc.i4.2
0x146c4  ldc.i4.0
0x146c5  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Create(valuetype [mscorlib]System.Guid, string, string, string, string, string, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState, bool)
0x146ca  pop
0x146cb  br.s     loc_146F2
0x146cd  ldarg.1
0x146ce  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x146d3  ldarg.1
0x146d4  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x146d9  call     bool [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::IsOrgMarkedForDeletion(string, string)
0x146de  brfalse.s loc_146F2
0x146e0  ldarg.1
0x146e1  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x146e6  ldarg.1
0x146e7  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x146ec  ldc.i4.0
0x146ed  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::SetOrgMarkedForDeletion(string, string, bool)
0x146f2  ldarg.0
0x146f3  ldarg.1
0x146f4  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x146f9  ldarg.1
0x146fa  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x146ff  ldarg.1
0x14700  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x14705  call     instance void Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::UpdateOUGroupsInDatabase(string sqlServerName, string databaseName, valuetype [mscorlib]System.Guid organizationId)
0x1470a  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x1470f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::GetSecurityGroups()
0x14714  stloc.s  4
0x14716  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1471b  ldstr    aGuid0// "<GUID={0}>"
0x14720  ldc.i4.1
0x14721  newarr   [mscorlib]System.Object
0x14726  dup
0x14727  ldc.i4.0
0x14728  ldloc.s  4
0x1472a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x1472f  stloc.s  6
0x14731  ldloca.s 6
0x14733  ldstr    aD// "D"
0x14738  call     instance string [mscorlib]System.Guid::ToString(string)
0x1473d  stelem.ref
0x1473e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14743  stloc.s  5
0x14745  ldarg.0
0x14746  ldfld    bool Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsOnline
0x1474b  brtrue.s loc_147B1
0x1474d  ldarg.1
0x1474e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.OrganizationInfo::get_Users()
0x14753  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::get_Count()
0x14758  brtrue.s loc_147B1
0x1475a  ldstr    aNoUserMappingI// "No user mapping information found. Crea"...
0x1475f  ldc.i4.0
0x14760  newarr   [mscorlib]System.Object
0x14765  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1476a  ldarg.1
0x1476b  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x14770  ldarg.1
0x14771  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x14776  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.DBImportHelper::CreateDefaultMapping(string sqlServerName, string databaseName)
0x1477b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::GetEnumerator()
0x14780  stloc.s  7
0x14782  br.s     loc_1479A
0x14784  ldloc.s  7
0x14786  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::get_Current()
0x1478b  stloc.s  8
0x1478d  ldarg.1
0x1478e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.OrganizationInfo::get_Users()
0x14793  ldloc.s  8
0x14795  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::Add(var<u1>)
0x1479a  ldloc.s  7
0x1479c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x147a1  brtrue.s loc_14784
0x147a3  leave.s  loc_147B1
0x147a5  ldloc.s  7
0x147a7  brfalse.s loc_147B0
0x147a9  ldloc.s  7
0x147ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x147b0  endfinally
0x147b1  leave.s  loc_147C6
0x147b3  pop
0x147b4  ldstr    aAnErrorOccurre_3// "An error occurred while creating defaul"...
0x147b9  ldc.i4.0
0x147ba  newarr   [mscorlib]System.Object
0x147bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x147c4  rethrow
0x147c6  ldarg.1
0x147c7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x147cc  ldc.i4.0
0x147cd  ldc.i4.0
0x147ce  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x147d3  stloc.s  9
0x147d5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x147da  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x147df  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EnableReadCommittedTransactions()
0x147e4  ldloc.s  9
0x147e6  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x147eb  brfalse.s loc_147FB
0x147ed  ldloc.s  9
0x147ef  ldc.i4   0x1000
0x147f4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [System.Data]System.Data.IsolationLevel)
0x147f9  br.s     loc_14807
0x147fb  ldloc.s  9
0x147fd  ldc.i4   0x100000
0x14802  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [System.Data]System.Data.IsolationLevel)
0x14807  nop
0x14808  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LoadMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::get_LoadMethod()
0x1480d  stloc.s  0xA
0x1480f  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheLoadOption [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::get_LoadOption()
0x14814  stloc.s  0xB
0x14816  ldc.i4.1
0x14817  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadMethod(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LoadMethod)
0x1481c  ldc.i4.2
0x1481d  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadOption(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheLoadOption)
0x14822  ldstr    aAddingUsersToT// "Adding users to the config database"
0x14827  ldc.i4.0
0x14828  newarr   [mscorlib]System.Object
0x1482d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x14832  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.ActiveDirectoryUserValidationParameters::.ctor()
0x14837  stloc.s  0xC
0x14839  ldloc.s  0xC
0x1483b  ldloc.s  4
0x1483d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x14842  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x14847  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.ActiveDirectoryUserValidationParameters::set_ReportingGroupId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1484c  ldarg.1
0x1484d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.OrganizationInfo::get_Users()
0x14852  ldloc.s  0xC
0x14854  ldloc.s  9
0x14856  call     void Microsoft.Crm.Tools.Admin.DBImportHelper::AddUsersToConfigDB(class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> users, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserValidationParameters userValidationParameters, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1485b  ldloc.s  0xA
0x1485d  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadMethod(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LoadMethod)
0x14862  ldloc.s  0xB
0x14864  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadOption(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheLoadOption)
0x14869  ldloc.s  9
0x1486b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x14870  leave.s  loc_1487C
0x14872  pop
0x14873  ldloc.s  9
0x14875  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x1487a  rethrow
0x1487c  leave.s  loc_1488A
0x1487e  ldloc.s  9
0x14880  brfalse.s loc_14889
0x14882  ldloc.s  9
0x14884  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14889  endfinally
0x1488a  ldstr    aOrganizationIm_2// "Organization.Import.UpdateOrganization"
0x1488f  ldc.i4.0
0x14890  newarr   [mscorlib]System.Object
0x14895  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x1489a  ldc.i4.s 0x3C
0x1489c  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x148a1  stloc.0
0x148a2  ldarg.0
0x148a3  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x148a8  ldarg.0
0x148a9  ldloc.0
0x148aa  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x148af  ldstr    aOrganizationIm_2// "Organization.Import.UpdateOrganization"
0x148b4  ldc.i4.0
0x148b5  newarr   [mscorlib]System.Object
0x148ba  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x148bf  ldc.i4.0
0x148c0  newarr   [mscorlib]System.Object
0x148c5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x148ca  ldarg.1
0x148cb  ldc.i4.1
0x148cc  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_PublishCustomReports(bool value)
0x148d1  ldarg.1
0x148d2  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x148d7  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationUpgrader::.ctor(class [mscorlib]System.Collections.IDictionary parameters)
0x148dc  stloc.s  0xD
0x148de  ldarg.0
0x148df  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x148e4  dup
0x148e5  ldvirtftn instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x148eb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler::.ctor(object, native int)
0x148f0  stloc.s  0xE
0x148f2  ldloc.s  0xD
0x148f4  ldloc.s  0xE
0x148f6  ldnull
0x148f7  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::HookProgressHandlers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler installerProgressHandler, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource componentProgress)
0x148fc  ldloc.s  0xD
0x148fe  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x14903  leave.s  loc_14943
0x14905  stloc.s  0xF
0x14907  ldstr    aOrganizationUp// "Organization.Upgrade.Failed.Log"
0x1490c  ldc.i4.2
0x1490d  newarr   [mscorlib]System.Object
0x14912  dup
0x14913  ldc.i4.0
0x14914  ldarg.1
0x14915  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x1491a  box      [mscorlib]System.Guid
0x1491f  stelem.ref
0x14920  dup
0x14921  ldc.i4.1
0x14922  ldloc.s  0xF
0x14924  stelem.ref
0x14925  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x1492a  stloc.s  0x10
0x1492c  ldloc.s  0x10
0x1492e  ldc.i4.0
0x1492f  newarr   [mscorlib]System.Object
0x14934  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x14939  ldloc.s  0x10
0x1493b  ldloc.s  0xF
0x1493d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x14942  throw
0x14943  leave.s  loc_14951
0x14945  ldloc.s  0xD
0x14947  brfalse.s loc_14950
0x14949  ldloc.s  0xD
0x1494b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14950  endfinally
0x14951  ldstr    aOrganizationIm_0// "Organization.Import.UpdateUsers"
0x14956  ldc.i4.0
0x14957  newarr   [mscorlib]System.Object
0x1495c  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x14961  ldc.i4.s 0x28
0x14963  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string, int32)
0x14968  stloc.0
0x14969  ldarg.0
0x1496a  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x1496f  ldarg.0
0x14970  ldloc.0
0x14971  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x14976  ldarg.1
0x14977  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x1497c  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x14981  ldc.i4.0
0x14982  ldc.i4.0
0x14983  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x14988  ldarg.1
0x14989  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x1498e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x14993  stloc.s  0x11
0x14995  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1499a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1499f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EnableReadCommittedTransactions()
0x149a4  ldloc.s  0x11
0x149a6  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x149ab  brfalse.s loc_149BB
0x149ad  ldloc.s  0x11
0x149af  ldc.i4   0x1000
0x149b4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [System.Data]System.Data.IsolationLevel)
0x149b9  br.s     loc_149C7
0x149bb  ldloc.s  0x11
0x149bd  ldc.i4   0x100000
0x149c2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [System.Data]System.Data.IsolationLevel)
  ... truncated ...
```
