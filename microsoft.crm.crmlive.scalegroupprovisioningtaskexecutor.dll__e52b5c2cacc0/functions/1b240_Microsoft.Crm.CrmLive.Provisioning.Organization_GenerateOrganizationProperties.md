# Microsoft.Crm.CrmLive.Provisioning.Organization::GenerateOrganizationProperties

- ea: `0x1b240`
- end: `0x1b4f7`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::GenerateOrganizationProperties`
- size: `695`
- prototype: ``
- caller_count: `3`
- callee_count: `52`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a6d0`
- `0x1a8e0`
- `0x1acc0`

## callees

- `0x9110`
- `0x9140`
- `0x9160`
- `0x91a0`
- `0x91b0`
- `0x9240`
- `0x9250`
- `0x9260`
- `0x9280`
- `0x92a0`
- `0x92c0`
- `0x92e0`
- `0x9300`
- `0x9320`
- `0x9340`
- `0x9360`
- `0x9380`
- `0x9410`
- `0x9420`
- `0x9490`
- `0x94b0`
- `0x94d0`
- `0x1b0f0`
- `0x1b1b0`
- `0x1b1d0`
- `0x1b1f0`
- `0x1b210`
- `0x1b240`
- `0x1b500`
- `0x23e50`
- `0x23e90`
- `0x23eb0`
- `0x23ed0`
- `0x23ef0`
- `0x23f10`
- `0x23f30`
- `0x23f50`
- `0x23f70`
- `0x23f90`
- `0x23fb0`
- `0x23fd0`
- `0x23ff0`
- `0x24030`
- `0x24050`
- `0x24070`
- `0x24090`
- `0x240f0`
- `0x24110`
- `0x24130`
- `0x24150`

## string_xrefs

- `0x1b4a6`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Organization.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1b240  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::.ctor()
0x1b245  stloc.0
0x1b246  ldloc.0
0x1b247  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b24c  ldarg.1
0x1b24d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationId()
0x1b252  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x1b257  ldloc.0
0x1b258  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b25d  ldarg.1
0x1b25e  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationName()
0x1b263  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_UniqueName(string)
0x1b268  ldloc.0
0x1b269  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b26e  ldarg.1
0x1b26f  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationFriendlyName()
0x1b274  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b279  brtrue.s loc_1B283
0x1b27b  ldarg.1
0x1b27c  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationFriendlyName()
0x1b281  br.s     loc_1B289
0x1b283  ldarg.1
0x1b284  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationName()
0x1b289  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_FriendlyName(string)
0x1b28e  ldloc.0
0x1b28f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b294  ldarg.1
0x1b295  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrgType()
0x1b29a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Type(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType)
0x1b29f  ldloc.0
0x1b2a0  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b2a5  ldarg.1
0x1b2a6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_ScaleGroupId()
0x1b2ab  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x1b2b0  ldloc.0
0x1b2b1  ldarg.1
0x1b2b2  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_EnableInOrgLifecycle()
0x1b2b7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_EnableInOrgLifecycle(bool value)
0x1b2bc  ldloc.0
0x1b2bd  ldarg.1
0x1b2be  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_BaseLanguageCode()
0x1b2c3  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_BaseLanguageCode(int32 value)
0x1b2c8  ldloc.0
0x1b2c9  ldarg.1
0x1b2ca  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_UseMtpProvisioning()
0x1b2cf  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_UseMtpProvisioning(bool value)
0x1b2d4  ldloc.0
0x1b2d5  ldarg.1
0x1b2d6  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_CurrencyCode()
0x1b2db  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_CurrencyCode(string value)
0x1b2e0  ldloc.0
0x1b2e1  ldarg.1
0x1b2e2  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_CurrencyName()
0x1b2e7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_CurrencyName(string value)
0x1b2ec  ldloc.0
0x1b2ed  ldarg.1
0x1b2ee  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_CurrencySymbol()
0x1b2f3  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_CurrencySymbol(string value)
0x1b2f8  ldloc.0
0x1b2f9  ldarg.1
0x1b2fa  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_CurrencyPrecision()
0x1b2ff  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_CurrencyPrecision(int32 value)
0x1b304  ldloc.0
0x1b305  ldarg.1
0x1b306  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_PreferredCulture()
0x1b30b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_PreferredCulture(int32 value)
0x1b310  ldarg.0
0x1b311  ldloc.0
0x1b312  ldarg.1
0x1b313  call     instance void Microsoft.Crm.CrmLive.Provisioning.Organization::SetSqlServerPropertiesForOrganization(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties, class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal createInfo)
0x1b318  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::.ctor()
0x1b31d  ldarg.1
0x1b31e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_ScaleGroupId()
0x1b323  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Retrieve(valuetype [mscorlib]System.Guid)
0x1b328  stloc.1
0x1b329  ldloc.0
0x1b32a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b32f  ldloc.1
0x1b330  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x1b335  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SrsUrl(string)
0x1b33a  ldloc.0
0x1b33b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b340  ldloc.1
0x1b341  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_HelpContentServer()
0x1b346  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_HelpContentServerUrl(string)
0x1b34b  ldloc.0
0x1b34c  ldloc.1
0x1b34d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x1b352  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::IsXdbScaleGroup(valuetype [mscorlib]System.Guid)
0x1b357  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_IsBackedByXdb(bool value)
0x1b35c  ldloc.0
0x1b35d  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x1b362  brfalse.s loc_1B3A0
0x1b364  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x1b369  stloc.2
0x1b36a  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x1b36f  stloc.3
0x1b370  ldloc.3
0x1b371  ldarg.1
0x1b372  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationId()
0x1b377  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x1b37c  ldloc.3
0x1b37d  ldc.i4.1
0x1b37e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1b383  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_IsBackedByXdb(valuetype [mscorlib]System.Nullable`1<bool>)
0x1b388  ldloc.2
0x1b389  ldloc.3
0x1b38a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1b38f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetState(valuetype [mscorlib]System.Guid)
0x1b394  ldc.i4.1
0x1b395  beq.s    loc_1B3B7
0x1b397  ldloc.2
0x1b398  ldloc.3
0x1b399  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Update(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x1b39e  br.s     loc_1B3B7
0x1b3a0  ldarg.0
0x1b3a1  ldarg.1
0x1b3a2  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationName()
0x1b3a7  ldarg.1
0x1b3a8  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrgType()
0x1b3ad  call     string [Microsoft.Crm.DatabaseInstaller.Common]Microsoft.Crm.DatabaseInstaller.Common.SharedDatabaseUtility::GenerateDatabaseName(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType)
0x1b3b2  stfld    string Microsoft.Crm.CrmLive.Provisioning.Organization::databaseName
0x1b3b7  ldloc.0
0x1b3b8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1b3bd  ldarg.0
0x1b3be  ldfld    string Microsoft.Crm.CrmLive.Provisioning.Organization::databaseName
0x1b3c3  dup
0x1b3c4  brtrue.s loc_1B3CC
0x1b3c6  pop
0x1b3c7  ldstr    asc_361CC// ""
0x1b3cc  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_DatabaseName(string)
0x1b3d1  ldloc.0
0x1b3d2  ldarg.1
0x1b3d3  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserDomainName()
0x1b3d8  ldarg.1
0x1b3d9  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserFirstName()
0x1b3de  ldarg.1
0x1b3df  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserLastName()
0x1b3e4  ldarg.1
0x1b3e5  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserEmail()
0x1b3ea  ldarg.1
0x1b3eb  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserPuid()
0x1b3f0  ldarg.1
0x1b3f1  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserLiveId()
0x1b3f6  ldarg.1
0x1b3f7  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_MonitoringUserPassword()
0x1b3fc  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::.ctor(string, string, string, string, string, string, string)
0x1b401  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_InitialUser(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties value)
0x1b406  ldloc.0
0x1b407  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_InitialUser()
0x1b40c  ldarg.1
0x1b40d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserDirectoryObjectId()
0x1b412  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::set_DirectoryObjectId(valuetype [mscorlib]System.Guid)
0x1b417  ldloc.0
0x1b418  ldarg.1
0x1b419  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_IsInitialUserLicensed()
0x1b41e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_IsInitialUserLicensed(bool value)
0x1b423  ldloc.0
0x1b424  call     string Microsoft.Crm.CrmLive.Provisioning.Organization::get_PrivilegedUserGroupName()
0x1b429  call     string Microsoft.Crm.CrmLive.Provisioning.Organization::get_SqlAccessGroupName()
0x1b42e  call     string Microsoft.Crm.CrmLive.Provisioning.Organization::get_ReportingGroupName()
0x1b433  call     string Microsoft.Crm.CrmLive.Provisioning.Organization::get_PrivilegedReportingGroupName()
0x1b438  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.DirectoryGroups::.ctor(string, string, string, string)
0x1b43d  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_DirectoryGroups(class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.DirectoryGroups value)
0x1b442  ldloc.0
0x1b443  call     string Microsoft.Crm.CrmLive.Provisioning.Organization::get_ProvisioningInstallPath()
0x1b448  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_InstallPath(string value)
0x1b44d  ldloc.0
0x1b44e  ldc.i4.1
0x1b44f  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_ChangeInitialCrmUserId(bool value)
0x1b454  ldloc.0
0x1b455  ldarg.1
0x1b456  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationName()
0x1b45b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_DomainName(string value)
0x1b460  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1b465  stloc.s  4
0x1b467  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1b46c  stloc.s  5
0x1b46e  ldloc.s  5
0x1b470  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x1b475  ldarg.1
0x1b476  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_OrganizationId()
0x1b47b  box      [mscorlib]System.Guid
0x1b480  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1b485  ldloc.s  4
0x1b487  ldstr    aOrganizationli// "OrganizationLifecycle"
0x1b48c  ldc.i4.1
0x1b48d  newarr   [mscorlib]System.String
0x1b492  dup
0x1b493  ldc.i4.0
0x1b494  ldstr    aDomainname// "DomainName"
0x1b499  stelem.ref
0x1b49a  ldloc.s  5
0x1b49c  ldc.i4   0x8A3
0x1b4a1  ldstr    aGenerateorgani// "GenerateOrganizationProperties"
0x1b4a6  ldstr    aDDbsShDccm2110_30// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1b4ab  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1b4b0  stloc.s  6
0x1b4b2  ldloc.s  6
0x1b4b4  brfalse.s loc_1B4CD
0x1b4b6  ldloc.0
0x1b4b7  ldloc.s  6
0x1b4b9  ldstr    aDomainname// "DomainName"
0x1b4be  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1b4c3  castclass [mscorlib]System.String
0x1b4c8  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_DomainName(string value)
0x1b4cd  leave.s  loc_1B4DB
0x1b4cf  ldloc.s  4
0x1b4d1  brfalse.s loc_1B4DA
0x1b4d3  ldloc.s  4
0x1b4d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b4da  endfinally
0x1b4db  ldloc.0
0x1b4dc  ldarg.1
0x1b4dd  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_CreateTemplate()
0x1b4e2  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_CreateTemplateRequest(bool value)
0x1b4e7  ldloc.0
0x1b4e8  ldarg.1
0x1b4e9  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_OriginalCreateInfo(class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal value)
0x1b4ee  ldloc.0
0x1b4ef  ldarg.2
0x1b4f0  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_QueueItemId(valuetype [mscorlib]System.Guid value)
0x1b4f5  ldloc.0
0x1b4f6  ret
```
