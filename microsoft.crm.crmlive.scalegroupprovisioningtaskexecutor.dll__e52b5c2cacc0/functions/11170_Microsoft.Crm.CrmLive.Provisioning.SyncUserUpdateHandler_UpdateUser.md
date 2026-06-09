# Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::UpdateUser

- ea: `0x11170`
- end: `0x11507`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::UpdateUser`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x11110`

## callees

- `0xc630`
- `0xff10`
- `0xff50`
- `0xff70`
- `0xff90`
- `0xffb0`
- `0xffd0`
- `0xfff0`
- `0x10050`
- `0x10070`
- `0x100d0`
- `0x10f60`
- `0x11170`
- `0x11510`
- `0x115b0`
- `0x11600`
- `0x11680`
- `0x116c0`
- `0x117a0`
- `0x118a0`
- `0x1c1f0`
- `0x2ecd0`
- `0x2ef20`

## string_xrefs

- `0x112dd`: `accessmode`
- `0x111f5`: `SyncUserUpdateHandler.UpdateUser: crmUser is null; removing from Config DB.`
- `0x11294`: `SyncUserUpdateHandler.UpdateUser: UpdateUserRole, `
- `0x1130f`: `SyncUserUpdateHandler.UpdateUser: SetAdminModeForTenantAdminInCrm, wasTenantOrCrmServiceAdmin = `
- `0x113a4`: `SyncUserUpdateHandler.UpdateUser: Setting user license in the org, clearing IsLicensed attribute on crmUser object.`
- `0x113ee`: `SyncUserUpdateHandler.UpdateUser: NOT setting user license in the org for disabled (in CRM) user.`
- `0x11413`: `SyncUserUpdateHandler.UpdateUser: Setting user state in the org, clearing Disabled attribute on crmUser object.`
- `0x11453`: `SyncUserUpdateHandler.UpdateUser: NOT setting license state or user state.`
- `0x11478`: `SyncUserUpdateHandler.UpdateUser: Calling UpdateCrmUser`
- `0x114bf`: `SyncUserUpdateHandler.UpdateUser: Calling UpdateLicenseStatus`
- `0x114ef`: `SyncUserUpdateHandler.UpdateUser: Finished. publicationRequired = `

## pseudocode

```c

```

## disassembly

```asm
0x11170  ldc.i4.0
0x11171  stloc.0
0x11172  ldarg.0
0x11173  ldarg.1
0x11174  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.CrmLive.Provisioning.SyncUserHandlerBase::GetCrmUser(class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto data)
0x11179  stloc.1
0x1117a  ldloca.s 2
0x1117c  ldarg.1
0x1117d  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x11182  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_ContextId()
0x11187  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1118c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11191  stloc.3
0x11192  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x11197  stloc.s  4
0x11199  ldc.i4.0
0x1119a  stloc.s  5
0x1119c  ldc.i4.0
0x1119d  stloc.s  6
0x1119f  ldc.i4.0
0x111a0  stloc.s  7
0x111a2  ldc.i4.0
0x111a3  stloc.s  8
0x111a5  ldc.i4.0
0x111a6  stloc.s  9
0x111a8  ldarg.1
0x111a9  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x111ae  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyBooleanSingle [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_AccountEnabled()
0x111b3  callvirt instance bool[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyBoolean::get_Value()
0x111b8  ldc.i4.0
0x111b9  ldelem.u1
0x111ba  ldc.i4.0
0x111bb  ceq
0x111bd  stloc.s  0xA
0x111bf  ldarg.1
0x111c0  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsCrmServiceAdmin()
0x111c5  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x111ca  brfalse.s loc_111D4
0x111cc  ldarg.1
0x111cd  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_ShouldSync()
0x111d2  br.s     loc_111D5
0x111d4  ldc.i4.0
0x111d5  stloc.s  0xB
0x111d7  ldloc.1
0x111d8  brtrue.s loc_11207
0x111da  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x111df  ldloc.3
0x111e0  ldloc.s  4
0x111e2  ldloc.2
0x111e3  ldarg.1
0x111e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x111e9  ldarg.1
0x111ea  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x111ef  ldarg.1
0x111f0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x111f5  ldstr    aSyncuserupdate// "SyncUserUpdateHandler.UpdateUser: crmUs"...
0x111fa  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x111ff  ldarg.1
0x11200  call     void Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::RemoveUserFromConfigDb(class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto data)
0x11205  ldloc.0
0x11206  ret
0x11207  ldloc.1
0x11208  ldstr    aIsdisabled// "isdisabled"
0x1120d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x11212  unbox.any [mscorlib]System.Boolean
0x11217  stloc.s  5
0x11219  ldloc.1
0x1121a  ldstr    aIslicensed// "islicensed"
0x1121f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x11224  unbox.any [mscorlib]System.Boolean
0x11229  stloc.s  6
0x1122b  ldarg.1
0x1122c  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x11231  callvirt instance bool [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject::get_Deleted()
0x11236  stloc.s  7
0x11238  ldarg.1
0x11239  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsSoftDelete()
0x1123e  stloc.s  8
0x11240  ldarg.1
0x11241  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x11246  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_AssignedPlan()
0x1124b  ldarg.1
0x1124c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x11251  call     bool Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::IsUserCapabilityValidAndCapabilityEnabled(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan assignedPlan, valuetype [mscorlib]System.Guid organizationId)
0x11256  stloc.s  9
0x11258  ldarg.1
0x11259  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_ShouldSync()
0x1125e  ldloc.s  6
0x11260  ldloc.s  5
0x11262  ldarg.1
0x11263  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsLicensed()
0x11268  ldloc.s  0xA
0x1126a  ldloc.s  0xB
0x1126c  ldloc.s  7
0x1126e  ldloc.s  8
0x11270  ldloc.s  9
0x11272  call     string Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::FormatEventSourceMessage(bool shouldSync, bool isLicensedInOrg, bool isDisabledInOrg, bool isLicensedInCloudSync, bool isDisabledInCloudSync, bool crmServiceAdminInTheOrg, bool isDeleted, bool isSoftDeleted, bool isUserCapabilityValidAndCapabilityEnabled)
0x11277  stloc.s  0xC
0x11279  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x1127e  ldloc.3
0x1127f  ldloc.s  4
0x11281  ldloc.2
0x11282  ldarg.1
0x11283  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x11288  ldarg.1
0x11289  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x1128e  ldarg.1
0x1128f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x11294  ldstr    aSyncuserupdate_0// "SyncUserUpdateHandler.UpdateUser: Updat"...
0x11299  ldloc.s  0xC
0x1129b  call     string [mscorlib]System.String::Concat(string, string)
0x112a0  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x112a5  ldarg.0
0x112a6  ldarg.1
0x112a7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x112ac  ldarg.1
0x112ad  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x112b2  ldarg.1
0x112b3  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_AdminState()
0x112b8  ldarg.1
0x112b9  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x112be  ldloc.s  0xB
0x112c0  ldarg.2
0x112c1  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::UpdateUserRole(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmUserId, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState> adminState, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, bool crmServiceAdminForOrg, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider)
0x112c6  ldloc.1
0x112c7  ldstr    aIsdisabled// "isdisabled"
0x112cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x112d1  unbox.any [mscorlib]System.Boolean
0x112d6  brtrue.s loc_112F1
0x112d8  ldloc.s  6
0x112da  brtrue.s loc_112F1
0x112dc  ldloc.1
0x112dd  ldstr    aAccessmode// "accessmode"
0x112e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x112e7  unbox.any [mscorlib]System.Int32
0x112ec  ldc.i4.1
0x112ed  ceq
0x112ef  br.s     loc_112F2
0x112f1  ldc.i4.0
0x112f2  stloc.s  0xD
0x112f4  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x112f9  ldloc.3
0x112fa  ldloc.s  4
0x112fc  ldloc.2
0x112fd  ldarg.1
0x112fe  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x11303  ldarg.1
0x11304  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x11309  ldarg.1
0x1130a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x1130f  ldstr    aSyncuserupdate_1// "SyncUserUpdateHandler.UpdateUser: SetAd"...
0x11314  ldloca.s 0xD
0x11316  call     instance string [mscorlib]System.Boolean::ToString()
0x1131b  ldstr    aIstenantadmin// ", IsTenantAdmin = "
0x11320  ldarg.1
0x11321  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x11326  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x1132b  stloc.s  0xE
0x1132d  ldloca.s 0xE
0x1132f  call     instance string [mscorlib]System.Boolean::ToString()
0x11334  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x11339  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x1133e  ldloc.1
0x1133f  ldarg.1
0x11340  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsLicensed()
0x11345  ldarg.1
0x11346  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x1134b  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x11350  ldloc.s  0xB
0x11352  or
0x11353  call     void Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::SetAdminModeForTenantAdminInCrm(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity crmUser, bool userLicensedInOsdp, bool isTenantOrCrmServiceAdmin)
0x11358  ldloc.s  5
0x1135a  brfalse  loc_11438
0x1135f  ldarg.1
0x11360  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x11365  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x1136a  brtrue.s loc_11374
0x1136c  ldarg.1
0x1136d  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsLicensed()
0x11372  br.s     loc_11375
0x11374  ldc.i4.1
0x11375  ldloc.s  0xB
0x11377  or
0x11378  brfalse  loc_11438
0x1137d  ldarg.1
0x1137e  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsLicensed()
0x11383  brfalse.s loc_113D3
0x11385  ldloc.s  6
0x11387  brtrue.s loc_113D3
0x11389  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x1138e  ldloc.3
0x1138f  ldloc.s  4
0x11391  ldloc.2
0x11392  ldarg.1
0x11393  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x11398  ldarg.1
0x11399  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x1139e  ldarg.1
0x1139f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x113a4  ldstr    aSyncuserupdate_2// "SyncUserUpdateHandler.UpdateUser: Setti"...
0x113a9  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x113ae  ldarg.0
0x113af  ldfld    class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.SyncUserHandlerBase::_orgAccess
0x113b4  ldarg.1
0x113b5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x113ba  ldarg.1
0x113bb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x113c0  ldc.i4.1
0x113c1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::SetUserLicenseState(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, bool isLicensed)
0x113c6  ldloc.1
0x113c7  ldstr    aIslicensed// "islicensed"
0x113cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::ClearAttribute(string)
0x113d1  br.s     loc_113F8
0x113d3  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x113d8  ldloc.3
0x113d9  ldloc.s  4
0x113db  ldloc.2
0x113dc  ldarg.1
0x113dd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x113e2  ldarg.1
0x113e3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x113e8  ldarg.1
0x113e9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x113ee  ldstr    aSyncuserupdate_3// "SyncUserUpdateHandler.UpdateUser: NOT s"...
0x113f3  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x113f8  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x113fd  ldloc.3
0x113fe  ldloc.s  4
0x11400  ldloc.2
0x11401  ldarg.1
0x11402  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x11407  ldarg.1
0x11408  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x1140d  ldarg.1
0x1140e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x11413  ldstr    aSyncuserupdate_4// "SyncUserUpdateHandler.UpdateUser: Setti"...
0x11418  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x1141d  ldarg.0
0x1141e  ldarg.1
0x1141f  ldc.i4.1
0x11420  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AdminGroupState>::.ctor(var<u1>)
0x11425  call     instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::SetUserStateInOrg(class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto data, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.AdminGroupState> adminState)
0x1142a  stloc.0
0x1142b  ldloc.1
0x1142c  ldstr    aIsdisabled// "isdisabled"
0x11431  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::ClearAttribute(string)
0x11436  br.s     loc_1145D
0x11438  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x1143d  ldloc.3
0x1143e  ldloc.s  4
0x11440  ldloc.2
0x11441  ldarg.1
0x11442  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x11447  ldarg.1
0x11448  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x1144d  ldarg.1
0x1144e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x11453  ldstr    aSyncuserupdate_5// "SyncUserUpdateHandler.UpdateUser: NOT s"...
0x11458  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x1145d  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x11462  ldloc.3
0x11463  ldloc.s  4
0x11465  ldloc.2
0x11466  ldarg.1
0x11467  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x1146c  ldarg.1
0x1146d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x11472  ldarg.1
0x11473  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x11478  ldstr    aSyncuserupdate_6// "SyncUserUpdateHandler.UpdateUser: Calli"...
0x1147d  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x11482  ldarg.0
0x11483  ldloc.1
0x11484  ldarg.1
0x11485  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x1148a  ldarg.1
0x1148b  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x11490  ldarg.1
0x11491  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x11496  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x1149b  ldloc.s  0xB
0x1149d  or
0x1149e  ldarg.2
0x1149f  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::UpdateCrmUser(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity crmUser, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, bool isTenantOrCrmServiceAdmin, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider)
0x114a4  call     class Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::get_Instance()
0x114a9  ldloc.3
0x114aa  ldloc.s  4
0x114ac  ldloc.2
0x114ad  ldarg.1
0x114ae  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_OrganizationId()
0x114b3  ldarg.1
0x114b4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x114b9  ldarg.1
0x114ba  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_CrmUserId()
0x114bf  ldstr    aSyncuserupdate_7// "SyncUserUpdateHandler.UpdateUser: Calli"...
0x114c4  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningUserEventSource::UserProvisioningInfo(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid trackingId, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId, valuetype [mscorlib]System.Guid crmUserId, string message)
0x114c9  ldarg.0
0x114ca  ldarg.1
0x114cb  ldloc.1
0x114cc  ldloc.s  0xD
  ... truncated ...
```
