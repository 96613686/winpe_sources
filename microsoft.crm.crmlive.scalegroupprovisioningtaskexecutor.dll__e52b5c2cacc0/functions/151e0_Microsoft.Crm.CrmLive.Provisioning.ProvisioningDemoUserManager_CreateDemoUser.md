# Microsoft.Crm.CrmLive.Provisioning.ProvisioningDemoUserManager::CreateDemoUser

- ea: `0x151e0`
- end: `0x15342`
- name: `Microsoft.Crm.CrmLive.Provisioning.ProvisioningDemoUserManager::CreateDemoUser`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x54c0`

## callees

- `0x151e0`
- `0x1bd60`
- `0x1c2e0`
- `0x1c3b0`

## string_xrefs

- `0x152ab`: `Attempting to fix MailboxBase approval for user : `
- `0x15300`: `Update MailboxBase set IsEmailAddressApprovedByO365Admin = 1, EmailRouterAccessApproval = 1 where RegardingObjectId = @systemuserid`

## pseudocode

```c

```

## disassembly

```asm
0x151e0  ldarg.1
0x151e1  call     bool [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::IsDemoUserUpn(string)
0x151e6  brtrue.s loc_151F9
0x151e8  ldstr    aInvalidDemouse// "Invalid DemoUser UPN : "
0x151ed  ldarg.1
0x151ee  call     string [mscorlib]System.String::Concat(string, string)
0x151f3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x151f8  throw
0x151f9  ldarg.0
0x151fa  ldstr    aOrgid// "orgId"
0x151ff  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x15204  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x15209  stloc.0
0x1520a  ldstr    aSystemuser// "SystemUser"
0x1520f  ldarg.0
0x15210  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, valuetype [mscorlib]System.Guid)
0x15215  stloc.1
0x15216  ldloc.1
0x15217  ldstr    aFirstname// "firstname"
0x1521c  ldstr    aDemo// "Demo"
0x15221  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x15226  ldloc.1
0x15227  ldstr    aLastname// "lastname"
0x1522c  ldstr    aUser_0// "User"
0x15231  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x15236  ldloc.1
0x15237  ldstr    aFullname// "fullname"
0x1523c  ldstr    aDemoUser// "Demo User"
0x15241  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x15246  ldloc.1
0x15247  ldstr    aInternalemaila// "internalemailaddress"
0x1524c  ldarg.1
0x1524d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x15252  ldloc.1
0x15253  ldstr    aWindowsliveid// "windowsliveid"
0x15258  ldarg.1
0x15259  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1525e  ldloc.1
0x1525f  ldstr    aDomainname_0// "domainname"
0x15264  ldarg.1
0x15265  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1526a  ldstr    aUselegacydemou// "UseLegacyDemoUserRoleBehavior"
0x1526f  call     bool [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClientHelper::IsGeoFeatureEnabled(string)
0x15274  brfalse.s loc_15296
0x15276  ldloc.0
0x15277  ldarg.0
0x15278  ldloc.1
0x15279  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpCreateUserBehavior::.ctor()
0x1527e  dup
0x1527f  ldstr    a627090ff40a340// "{627090FF-40A3-4053-8790-584EDC5BE201}"
0x15284  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x15289  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpCreateUserBehavior::set_RoleIdToAssign(valuetype [mscorlib]System.Guid)
0x1528e  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::CreateUnmappedLicensedCrmUser(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity newUser, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpCreateUserBehavior role)
0x15293  stloc.2
0x15294  br.s     loc_152AB
0x15296  ldloc.0
0x15297  ldarg.0
0x15298  ldloc.1
0x15299  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpCreateUserBehavior::.ctor()
0x1529e  dup
0x1529f  ldc.i4.1
0x152a0  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpCreateUserBehavior::set_DoNotAssignAnyRole(bool)
0x152a5  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::CreateUnmappedLicensedCrmUser(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity newUser, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpCreateUserBehavior role)
0x152aa  stloc.2
0x152ab  ldstr    aAttemptingToFi// "Attempting to fix MailboxBase approval "...
0x152b0  ldloc.2
0x152b1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult::get_SystemUserId()
0x152b6  box      [mscorlib]System.Guid
0x152bb  call     string [mscorlib]System.String::Concat(object, object)
0x152c0  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x152c5  ldarg.0
0x152c6  ldc.i4.0
0x152c7  ldc.i4.0
0x152c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x152cd  stloc.3
0x152ce  ldloc.3
0x152cf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x152d4  ldloc.3
0x152d5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x152da  stloc.s  4
0x152dc  ldloc.s  4
0x152de  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x152e3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x152e8  ldstr    aSystemuserid_1// "@systemuserid"
0x152ed  ldloc.2
0x152ee  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult::get_SystemUserId()
0x152f3  box      [mscorlib]System.Guid
0x152f8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x152fd  pop
0x152fe  ldloc.s  4
0x15300  ldstr    aUpdateMailboxb// "Update MailboxBase set IsEmailAddressAp"...
0x15305  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1530a  ldloc.s  4
0x1530c  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x15311  stloc.s  5
0x15313  ldstr    aRowsAffected// "Rows affected : "
0x15318  ldloc.s  5
0x1531a  box      [mscorlib]System.Int32
0x1531f  call     string [mscorlib]System.String::Concat(object, object)
0x15324  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x15329  leave.s  loc_15341
0x1532b  ldloc.s  4
0x1532d  brfalse.s loc_15336
0x1532f  ldloc.s  4
0x15331  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15336  endfinally
0x15337  ldloc.3
0x15338  brfalse.s loc_15340
0x1533a  ldloc.3
0x1533b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15340  endfinally
0x15341  ret
```
