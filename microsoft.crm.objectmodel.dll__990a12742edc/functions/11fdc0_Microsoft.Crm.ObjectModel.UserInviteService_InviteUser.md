# Microsoft.Crm.ObjectModel.UserInviteService::InviteUser

- ea: `0x11fdc0`
- end: `0x120491`
- name: `Microsoft.Crm.ObjectModel.UserInviteService::InviteUser`
- size: `1745`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0xd71d0`

## callees

- `0x11cd0`
- `0x11cf0`
- `0xd8c20`
- `0xdbe00`
- `0x11fdc0`
- `0x1204a0`
- `0x1204e0`
- `0x120500`
- `0x120520`
- `0x120580`
- `0x120950`
- `0x120970`
- `0x1cba90`

## string_xrefs

- `0x12042c`: `EmailService`
- `0x11fed3`: `accessmode`
- `0x11fdfd`: `Checking Invite Privileges`
- `0x11feed`: `Can only invite users with access mode of Full or Non-Interactive`
- `0x1200d3`: `Generating Invitation Token`
- `0x120231`: `Default template for InvitationEmail`
- `0x1202a9`: `Update system user record`

## pseudocode

```c

```

## disassembly

```asm
0x11fdc0  ldarg.2
0x11fdc1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11fdc6  ldc.i4.s 0xA
0x11fdc8  ldstr    aInviteuser// "InviteUser"
0x11fdcd  ldc.i4.0
0x11fdce  newarr   [mscorlib]System.Object
0x11fdd3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11fdd8  ldarg.0
0x11fdd9  ldarg.2
0x11fdda  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11fddf  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.UserInviteService::orgId
0x11fde4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x11fde9  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x11fdee  ldc.i4.2
0x11fdef  and
0x11fdf0  brfalse  loc_120480
0x11fdf5  ldarg.2
0x11fdf6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11fdfb  ldc.i4.s 0xA
0x11fdfd  ldstr    aCheckingInvite// "Checking Invite Privileges"
0x11fe02  ldc.i4.0
0x11fe03  newarr   [mscorlib]System.Object
0x11fe08  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11fe0d  ldarg.2
0x11fe0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x11fe13  ldarg.2
0x11fe14  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11fe19  ldstr    aPrvsendinvitef// "prvSendInviteForLive"
0x11fe1e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x11fe23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x11fe28  ldarg.2
0x11fe29  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x11fe2e  newobj   instance void Microsoft.Crm.ObjectModel.SystemUserService::.ctor()
0x11fe33  stloc.0
0x11fe34  ldarg.2
0x11fe35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11fe3a  ldc.i4.s 0xA
0x11fe3c  ldstr    aCheckingIfUser// "Checking if user is disabled"
0x11fe41  ldc.i4.0
0x11fe42  newarr   [mscorlib]System.Object
0x11fe47  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11fe4c  ldarg.1
0x11fe4d  ldstr    aSystemuser_0// "SystemUser"
0x11fe52  ldarg.2
0x11fe53  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11fe58  stloc.1
0x11fe59  ldstr    aSystemuser_0// "SystemUser"
0x11fe5e  ldarg.2
0x11fe5f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x11fe64  stloc.2
0x11fe65  ldloc.2
0x11fe66  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11fe6b  ldc.i4.1
0x11fe6c  newarr   [mscorlib]System.String
0x11fe71  dup
0x11fe72  ldc.i4.0
0x11fe73  ldstr    aIsdisabled// "isdisabled"
0x11fe78  stelem.ref
0x11fe79  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x11fe7e  ldloc.0
0x11fe7f  ldloc.1
0x11fe80  ldloc.2
0x11fe81  ldarg.2
0x11fe82  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x11fe87  stloc.3
0x11fe88  ldloc.3
0x11fe89  ldstr    aIsdisabled// "isdisabled"
0x11fe8e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x11fe93  brtrue.s loc_11FED0
0x11fe95  ldloc.3
0x11fe96  ldstr    aIsdisabled// "isdisabled"
0x11fe9b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11fea0  unbox.any [mscorlib]System.Boolean
0x11fea5  brfalse.s loc_11FED0
0x11fea7  ldarg.2
0x11fea8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11fead  ldc.i4.s 0xA
0x11feaf  ldstr    aDisabledUser// "Disabled User"
0x11feb4  ldc.i4.0
0x11feb5  newarr   [mscorlib]System.Object
0x11feba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11febf  ldc.i4   0x8004D212
0x11fec4  ldc.i4.0
0x11fec5  newarr   [mscorlib]System.Object
0x11feca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x11fecf  throw
0x11fed0  ldarg.0
0x11fed1  ldarg.1
0x11fed2  ldarg.2
0x11fed3  ldstr    aAccessmode// "accessmode"
0x11fed8  call     instance object Microsoft.Crm.ObjectModel.UserInviteService::RetrieveUserProperty(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string propertyName)
0x11fedd  unbox.any [mscorlib]System.Int32
0x11fee2  stloc.s  4
0x11fee4  ldloc.s  4
0x11fee6  brfalse.s loc_11FEFD
0x11fee8  ldloc.s  4
0x11feea  ldc.i4.4
0x11feeb  beq.s    loc_11FEFD
0x11feed  ldstr    aCanOnlyInviteU// "Can only invite users with access mode "...
0x11fef2  ldc.i4   0x80040216
0x11fef7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x11fefc  throw
0x11fefd  ldarg.0
0x11fefe  ldarg.1
0x11feff  ldarg.2
0x11ff00  ldstr    aWindowsliveid// "windowsliveid"
0x11ff05  call     instance object Microsoft.Crm.ObjectModel.UserInviteService::RetrieveUserProperty(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string propertyName)
0x11ff0a  castclass [mscorlib]System.String
0x11ff0f  stloc.s  5
0x11ff11  ldloc.s  5
0x11ff13  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11ff18  brtrue.s loc_11FF8E
0x11ff1a  ldstr    aSystemuser_0// "SystemUser"
0x11ff1f  ldarg.2
0x11ff20  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x11ff25  stloc.s  0x1D
0x11ff27  ldloc.s  0x1D
0x11ff29  ldstr    aWindowsliveid// "windowsliveid"
0x11ff2e  ldc.i4.0
0x11ff2f  ldloc.s  5
0x11ff31  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x11ff36  pop
0x11ff37  ldloc.0
0x11ff38  ldloc.s  0x1D
0x11ff3a  ldarg.2
0x11ff3b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x11ff40  stloc.s  0x1E
0x11ff42  ldloc.s  0x1E
0x11ff44  brfalse.s loc_11FF8E
0x11ff46  ldloc.s  0x1E
0x11ff48  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x11ff4d  ldc.i4.1
0x11ff4e  ble.s    loc_11FF8E
0x11ff50  ldarg.2
0x11ff51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11ff56  ldc.i4.s 0xA
0x11ff58  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11ff5d  ldstr    aDuplicateWlids// "Duplicate WLIDs found: {0}"
0x11ff62  ldc.i4.1
0x11ff63  newarr   [mscorlib]System.Object
0x11ff68  dup
0x11ff69  ldc.i4.0
0x11ff6a  ldloc.s  5
0x11ff6c  stelem.ref
0x11ff6d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11ff72  ldc.i4.0
0x11ff73  newarr   [mscorlib]System.Object
0x11ff78  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11ff7d  ldc.i4   0x8004D215
0x11ff82  ldc.i4.0
0x11ff83  newarr   [mscorlib]System.Object
0x11ff88  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x11ff8d  throw
0x11ff8e  ldarg.2
0x11ff8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11ff94  ldc.i4.s 0xA
0x11ff96  ldstr    aCheckingIfRole// "Checking if roles are assigned to the u"...
0x11ff9b  ldc.i4.0
0x11ff9c  newarr   [mscorlib]System.Object
0x11ffa1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11ffa6  ldstr    aRole// "Role"
0x11ffab  ldarg.2
0x11ffac  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x11ffb1  stloc.2
0x11ffb2  ldloc.2
0x11ffb3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11ffb8  ldc.i4.1
0x11ffb9  newarr   [mscorlib]System.String
0x11ffbe  dup
0x11ffbf  ldc.i4.0
0x11ffc0  ldstr    aRoleid// "roleid"
0x11ffc5  stelem.ref
0x11ffc6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x11ffcb  ldloc.2
0x11ffcc  ldstr    aSystemuserrole// "SystemUserRoles"
0x11ffd1  ldstr    aRoleid// "roleid"
0x11ffd6  ldstr    aRoleid// "roleid"
0x11ffdb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x11ffe0  ldstr    aSystemuser_0// "SystemUser"
0x11ffe5  ldstr    aSystemuserid// "systemuserid"
0x11ffea  ldstr    aSystemuserid// "systemuserid"
0x11ffef  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0x11fff4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x11fff9  ldstr    aSystemuserid// "systemuserid"
0x11fffe  ldc.i4.0
0x11ffff  ldarg.1
0x120000  box      [mscorlib]System.Guid
0x120005  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x12000a  pop
0x12000b  ldloc.0
0x12000c  ldloc.2
0x12000d  ldarg.2
0x12000e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x120013  stloc.s  6
0x120015  newobj   instance void Microsoft.Crm.ObjectModel.TeamService::.ctor()
0x12001a  stloc.s  7
0x12001c  ldstr    aRole// "Role"
0x120021  ldarg.2
0x120022  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x120027  stloc.s  8
0x120029  ldloc.s  8
0x12002b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x120030  ldc.i4.1
0x120031  newarr   [mscorlib]System.String
0x120036  dup
0x120037  ldc.i4.0
0x120038  ldstr    aRoleid// "roleid"
0x12003d  stelem.ref
0x12003e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x120043  ldloc.s  8
0x120045  ldstr    aTeamroles// "TeamRoles"
0x12004a  ldstr    aRoleid// "roleid"
0x12004f  ldstr    aRoleid// "roleid"
0x120054  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x120059  ldstr    aTeammembership// "TeamMembership"
0x12005e  ldstr    aTeamid_0// "teamid"
0x120063  ldstr    aTeamid_0// "teamid"
0x120068  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0x12006d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x120072  ldstr    aSystemuserid// "systemuserid"
0x120077  ldc.i4.0
0x120078  ldarg.1
0x120079  box      [mscorlib]System.Guid
0x12007e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x120083  pop
0x120084  ldloc.s  7
0x120086  ldloc.s  8
0x120088  ldarg.2
0x120089  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x12008e  stloc.s  9
0x120090  ldloc.s  6
0x120092  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x120097  brtrue.s loc_1200CB
0x120099  ldloc.s  9
0x12009b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1200a0  brtrue.s loc_1200CB
0x1200a2  ldarg.2
0x1200a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1200a8  ldc.i4.s 0xA
0x1200aa  ldstr    aRolesNotAssign// "Roles not assigned"
0x1200af  ldc.i4.0
0x1200b0  newarr   [mscorlib]System.Object
0x1200b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1200ba  ldc.i4   0x8004B012
0x1200bf  ldc.i4.0
0x1200c0  newarr   [mscorlib]System.Object
0x1200c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1200ca  throw
0x1200cb  ldarg.2
0x1200cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1200d1  ldc.i4.s 0xA
0x1200d3  ldstr    aGeneratingInvi// "Generating Invitation Token"
0x1200d8  ldc.i4.0
0x1200d9  newarr   [mscorlib]System.Object
0x1200de  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1200e3  ldarg.0
0x1200e4  ldarg.1
0x1200e5  ldarg.2
0x1200e6  call     instance void Microsoft.Crm.ObjectModel.UserInviteService::ValidateCanSendInvite(valuetype [mscorlib]System.Guid id, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1200eb  ldarg.0
0x1200ec  ldarg.2
0x1200ed  call     instance int32 Microsoft.Crm.ObjectModel.UserInviteService::RetrieveOrganizationLocaleId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1200f2  stloc.s  0xA
0x1200f4  ldarg.0
0x1200f5  ldarg.1
0x1200f6  ldloc.s  4
0x1200f8  ldarg.2
0x1200f9  call     instance class Microsoft.Crm.CrmLive.ClientInvitation.InvitationToken Microsoft.Crm.ObjectModel.UserInviteService::CreateInvite(valuetype [mscorlib]System.Guid userId, int32 accessMode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1200fe  stloc.s  0xB
0x120100  ldarg.0
0x120101  ldarg.1
0x120102  ldarg.2
0x120103  ldloca.s 0xC
0x120105  ldloca.s 0xD
0x120107  call     instance string Microsoft.Crm.ObjectModel.UserInviteService::RetrieveUserName(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& firstName, [out] string& lastName)
0x12010c  stloc.s  0xE
0x12010e  ldarg.0
0x12010f  ldarg.2
0x120110  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x120115  ldarg.2
0x120116  ldloca.s 0xF
0x120118  ldloca.s 0x10
0x12011a  call     instance string Microsoft.Crm.ObjectModel.UserInviteService::RetrieveUserName(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& firstName, [out] string& lastName)
0x12011f  stloc.s  0x11
0x120121  ldarg.0
0x120122  ldarg.1
0x120123  ldarg.2
0x120124  call     instance string Microsoft.Crm.ObjectModel.UserInviteService::RetrieveUserEmail(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x120129  stloc.s  0x12
0x12012b  ldloc.s  5
0x12012d  dup
0x12012e  brtrue.s loc_120133
0x120130  pop
0x120131  ldloc.s  0x12
0x120133  stloc.s  5
0x120135  ldloc.s  0xB
0x120137  callvirt instance string Microsoft.Crm.CrmLive.ClientInvitation.InvitationToken::get_Token()
0x12013c  call     class [System]System.Uri [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::GetShortAcceptInviteUrl(string)
0x120141  callvirt instance string [mscorlib]System.Object::ToString()
0x120146  stloc.s  0x13
  ... truncated ...
```
