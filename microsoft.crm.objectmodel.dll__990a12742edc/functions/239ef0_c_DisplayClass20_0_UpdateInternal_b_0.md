# <>c__DisplayClass20_0::<UpdateInternal>b__0

- ea: `0x239ef0`
- end: `0x23a76d`
- name: `<>c__DisplayClass20_0::<UpdateInternal>b__0`
- size: `2173`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0xde160`
- `0xe1960`
- `0xe1e70`
- `0x11fdb0`
- `0x1f4780`
- `0x239ef0`

## string_xrefs

- `0x23a266`: `azureactivedirectoryobjectid`
- `0x23a277`: `accessmode`
- `0x23a3dc`: `accessmode`
- `0x23a3f7`: `accessmode`
- `0x23a409`: `accessmode`
- `0x23a2dd`: `issyncwithdirectory`
- `0x23a222`: `activedirectoryguid`
- `0x239f50`: `usersAlreadyInConfigDB`
- `0x239f66`: `isStubUserRename`
- `0x23a233`: `isactivedirectoryuser`

## pseudocode

```c

```

## disassembly

```asm
0x239ef0  ldarg.0
0x239ef1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239ef6  ldstr    aSystemuser_2// "systemUser"
0x239efb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x239f00  ldarg.0
0x239f01  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x239f06  ldstr    aContext// "context"
0x239f0b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x239f10  ldarg.0
0x239f11  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239f16  ldstr    aSystemuserid// "systemuserid"
0x239f1b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x239f20  ldstr    aSystemuserid// "systemuserid"
0x239f25  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x239f2a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x239f2f  dup
0x239f30  ldstr    aSystemuserid_2// "SystemUserId"
0x239f35  ldarg.0
0x239f36  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239f3b  ldstr    aSystemuserid// "systemuserid"
0x239f40  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x239f45  callvirt instance string [mscorlib]System.Object::ToString()
0x239f4a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x239f4f  dup
0x239f50  ldstr    aUsersalreadyin// "usersAlreadyInConfigDB"
0x239f55  ldarg.0
0x239f56  ldflda   bool class <>c__DisplayClass20_0<var<u1>>::usersAlreadyInConfigDB
0x239f5b  call     instance string [mscorlib]System.Boolean::ToString()
0x239f60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x239f65  dup
0x239f66  ldstr    aIsstubuserrena// "isStubUserRename"
0x239f6b  ldarg.0
0x239f6c  ldflda   bool class <>c__DisplayClass20_0<var<u1>>::isStubUserRename
0x239f71  call     instance string [mscorlib]System.Boolean::ToString()
0x239f76  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x239f7b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x239f80  ldarg.0
0x239f81  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239f86  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x239f8b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Clone()
0x239f90  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x239f95  stloc.0
0x239f96  ldarg.0
0x239f97  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239f9c  ldstr    aBusinessunitid// "businessunitid"
0x239fa1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::ClearAttribute(string)
0x239fa6  ldarg.0
0x239fa7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239fac  ldstr    aParentsystemus// "parentsystemuserid"
0x239fb1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::ClearAttribute(string)
0x239fb6  ldarg.0
0x239fb7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239fbc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x239fc1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Count()
0x239fc6  ldc.i4.1
0x239fc7  ble      loc_23A729
0x239fcc  ldarg.0
0x239fcd  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x239fd2  ldarg.0
0x239fd3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239fd8  ldarg.0
0x239fd9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x239fde  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::CheckPrivilegeForIntegrationUserFlag(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x239fe3  ldarg.0
0x239fe4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x239fe9  ldstr    aSystemuserid// "systemuserid"
0x239fee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x239ff3  unbox.any [mscorlib]System.Guid
0x239ff8  stloc.1
0x239ff9  ldloc.1
0x239ffa  ldarg.0
0x239ffb  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a000  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x23a005  ldarg.0
0x23a006  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a00b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x23a010  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x23a015  stloc.2
0x23a016  ldarg.0
0x23a017  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a01c  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0x23a021  brtrue   loc_23A17A
0x23a026  ldarg.0
0x23a027  ldfld    bool class <>c__DisplayClass20_0<var<u1>>::isStubUserRename
0x23a02c  brtrue   loc_23A17A
0x23a031  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x23a036  ldarg.0
0x23a037  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a03c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x23a041  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x23a046  brfalse  loc_23A0E4
0x23a04b  ldarg.0
0x23a04c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a051  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x23a056  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Count()
0x23a05b  ldc.i4.2
0x23a05c  bne.un   loc_23A0E4
0x23a061  ldarg.0
0x23a062  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a067  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x23a06c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::get_CallerOrigin()
0x23a071  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ApplicationOrigin
0x23a076  brfalse.s loc_23A0E4
0x23a078  ldarg.0
0x23a079  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a07e  ldstr    aSystemuserid// "systemuserid"
0x23a083  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23a088  brtrue.s loc_23A0E4
0x23a08a  ldarg.0
0x23a08b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a090  ldstr    aInvitestatusco// "invitestatuscode"
0x23a095  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23a09a  brtrue.s loc_23A0E4
0x23a09c  ldarg.0
0x23a09d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a0a2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a0a7  stloc.s  0xE
0x23a0a9  ldarg.0
0x23a0aa  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a0af  ldarg.0
0x23a0b0  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a0b5  ldarg.0
0x23a0b6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a0bb  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::<>n__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a0c0  ldarg.0
0x23a0c1  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a0c6  ldloc.1
0x23a0c7  ldarg.0
0x23a0c8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a0cd  ldc.i4.0
0x23a0ce  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::FlushCaches(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x23a0d3  leave    loc_23A76C
0x23a0d8  ldloc.s  0xE
0x23a0da  brfalse.s loc_23A0E3
0x23a0dc  ldloc.s  0xE
0x23a0de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23a0e3  endfinally
0x23a0e4  ldarg.0
0x23a0e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a0ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x23a0ef  ldarg.0
0x23a0f0  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a0f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x23a0fa  ldc.i4.2
0x23a0fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x23a100  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x23a105  ldarg.0
0x23a106  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a10b  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a110  ldloc.2
0x23a111  ldc.i4.2
0x23a112  ldarg.0
0x23a113  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a118  call     void Microsoft.Crm.ObjectModel.BusinessManagementUtility::CheckAccess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights accessRights, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23a11d  ldarg.0
0x23a11e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a123  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x23a128  ldloc.1
0x23a129  ldarg.0
0x23a12a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a12f  call     valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary/SpecialUser [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::IsOrganizationSpecialUser(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23a134  brfalse.s loc_23A147
0x23a136  ldc.i4   0x80041D33
0x23a13b  ldc.i4.0
0x23a13c  newarr   [mscorlib]System.Object
0x23a141  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23a146  throw
0x23a147  ldarg.0
0x23a148  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a14d  ldarg.0
0x23a14e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a153  ldarg.0
0x23a154  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a159  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::CheckAssignTerritoryToUserPrivilege(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a15e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory::.ctor()
0x23a163  ldarg.0
0x23a164  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a169  ldarg.0
0x23a16a  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a16f  ldarg.0
0x23a170  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a175  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory::ValidateForUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a17a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x23a17f  ldarg.0
0x23a180  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a185  ldstr    aCalendarid// "calendarid"
0x23a18a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23a18f  bne.un.s loc_23A1A1
0x23a191  ldstr    aCalendaridCann// "calendarid cannot be cleared"
0x23a196  ldc.i4   0x80040203
0x23a19b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x23a1a0  throw
0x23a1a1  newobj   instance void Microsoft.Crm.ObjectModel.CalendarService::.ctor()
0x23a1a6  stloc.3
0x23a1a7  ldarg.0
0x23a1a8  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a1ad  ldstr    aCalendarid// "calendarid"
0x23a1b2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23a1b7  brtrue.s loc_23A1EC
0x23a1b9  ldarg.0
0x23a1ba  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a1bf  ldstr    aCalendarid// "calendarid"
0x23a1c4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23a1c9  brfalse.s loc_23A1EC
0x23a1cb  ldloc.3
0x23a1cc  ldarg.0
0x23a1cd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a1d2  ldstr    aCalendarid// "calendarid"
0x23a1d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23a1dc  unbox.any [mscorlib]System.Guid
0x23a1e1  ldarg.0
0x23a1e2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a1e7  callvirt instance void Microsoft.Crm.ObjectModel.CalendarService::ThrowExceptionIfCalendarTypeIsCustomerServiceOrHolidaySchedule(valuetype [mscorlib]System.Guid calendarId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23a1ec  ldarg.0
0x23a1ed  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a1f2  ldarg.0
0x23a1f3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a1f8  ldarg.0
0x23a1f9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a1fe  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::UpdateAccessMode(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a203  ldarg.0
0x23a204  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a209  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x23a20e  ldarg.0
0x23a20f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a214  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x23a219  stloc.s  4
0x23a21b  ldloc.s  4
0x23a21d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a222  ldstr    aActivedirector// "activedirectoryguid"
0x23a227  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a22c  ldloc.s  4
0x23a22e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a233  ldstr    aIsactivedirect// "isactivedirectoryuser"
0x23a238  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a23d  ldloc.s  4
0x23a23f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a244  ldstr    aWindowsliveid// "windowsliveid"
0x23a249  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a24e  ldloc.s  4
0x23a250  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a255  ldstr    aIsdisabled// "isdisabled"
0x23a25a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a25f  ldloc.s  4
0x23a261  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a266  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x23a26b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a270  ldloc.s  4
0x23a272  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a277  ldstr    aAccessmode// "accessmode"
0x23a27c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a281  ldloc.s  4
0x23a283  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a288  ldstr    aDomainname// "domainname"
0x23a28d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a292  ldloc.s  4
0x23a294  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a299  ldstr    aPositionid// "positionid"
0x23a29e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a2a3  ldloc.s  4
0x23a2a5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a2aa  ldstr    aParentsystemus// "parentsystemuserid"
0x23a2af  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a2b4  ldloc.s  4
0x23a2b6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a2bb  ldstr    aApplicationid// "applicationid"
0x23a2c0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a2c5  ldloc.s  4
0x23a2c7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a2cc  ldstr    aIslicensed_0// "islicensed"
0x23a2d1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a2d6  ldloc.s  4
0x23a2d8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a2dd  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x23a2e2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a2e7  ldarg.0
0x23a2e8  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a2ed  ldarg.0
0x23a2ee  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a2f3  call     instance bool class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::HasMobileOfflineProfileIdAttribute(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a2f8  brfalse.s loc_23A30B
0x23a2fa  ldloc.s  4
0x23a2fc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23a301  ldstr    aMobileofflinep// "mobileofflineprofileid"
0x23a306  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x23a30b  ldarg.0
0x23a30c  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a311  ldloc.2
0x23a312  ldloc.s  4
0x23a314  ldarg.0
0x23a315  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
0x23a31a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a31f  stloc.s  5
0x23a321  ldarg.0
0x23a322  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x23a327  ldarg.0
0x23a328  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass20_0<var<u1>>::systemUser
0x23a32d  ldloc.s  5
0x23a32f  ldarg.0
0x23a330  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass20_0<var<u1>>::context
  ... truncated ...
```
