# <>c__DisplayClass63_0::<SetDisabledStatus>b__0

- ea: `0x23b220`
- end: `0x23b5b6`
- name: `<>c__DisplayClass63_0::<SetDisabledStatus>b__0`
- size: `918`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x11fdb0`
- `0x1206d0`
- `0x23b220`

## string_xrefs

- `0x23b29c`: `accessmode`
- `0x23b2fa`: `accessmode`
- `0x23b308`: `accessmode`
- `0x23b32b`: `accessmode`
- `0x23b339`: `accessmode`
- `0x23b53e`: `accessmode`
- `0x23b2ac`: `issyncwithdirectory`
- `0x23b294`: `activedirectoryguid`
- `0x23b2a4`: `isactivedirectoryuser`

## pseudocode

```c

```

## disassembly

```asm
0x23b220  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x23b225  stloc.0
0x23b226  ldloc.0
0x23b227  ldstr    aSystemuserid_2// "SystemUserId"
0x23b22c  ldarg.0
0x23b22d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b232  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x23b237  stloc.s  7
0x23b239  ldloca.s 7
0x23b23b  constrained. [mscorlib]System.Guid
0x23b241  callvirt instance string [mscorlib]System.Object::ToString()
0x23b246  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23b24b  ldloc.0
0x23b24c  ldstr    aSystemuserstat// "SystemUserState"
0x23b251  ldarg.0
0x23b252  ldflda   valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState class <>c__DisplayClass63_0<var<u1>>::state
0x23b257  constrained. [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState
0x23b25d  callvirt instance string [mscorlib]System.Object::ToString()
0x23b262  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23b267  ldarg.0
0x23b268  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b26d  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x23b272  ldarg.0
0x23b273  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b278  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x23b27d  stloc.1
0x23b27e  ldloc.1
0x23b27f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x23b284  ldc.i4.8
0x23b285  newarr   [mscorlib]System.String
0x23b28a  dup
0x23b28b  ldc.i4.0
0x23b28c  ldstr    aIsdisabled// "isdisabled"
0x23b291  stelem.ref
0x23b292  dup
0x23b293  ldc.i4.1
0x23b294  ldstr    aActivedirector// "activedirectoryguid"
0x23b299  stelem.ref
0x23b29a  dup
0x23b29b  ldc.i4.2
0x23b29c  ldstr    aAccessmode// "accessmode"
0x23b2a1  stelem.ref
0x23b2a2  dup
0x23b2a3  ldc.i4.3
0x23b2a4  ldstr    aIsactivedirect// "isactivedirectoryuser"
0x23b2a9  stelem.ref
0x23b2aa  dup
0x23b2ab  ldc.i4.4
0x23b2ac  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x23b2b1  stelem.ref
0x23b2b2  dup
0x23b2b3  ldc.i4.5
0x23b2b4  ldstr    aIslicensed_0// "islicensed"
0x23b2b9  stelem.ref
0x23b2ba  dup
0x23b2bb  ldc.i4.6
0x23b2bc  ldstr    aWindowsliveid// "windowsliveid"
0x23b2c1  stelem.ref
0x23b2c2  dup
0x23b2c3  ldc.i4.7
0x23b2c4  ldstr    aInvitestatusco// "invitestatuscode"
0x23b2c9  stelem.ref
0x23b2ca  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x23b2cf  ldarg.0
0x23b2d0  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b2d5  ldarg.0
0x23b2d6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b2db  ldloc.1
0x23b2dc  ldarg.0
0x23b2dd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b2e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b2e7  stloc.2
0x23b2e8  ldloc.2
0x23b2e9  ldstr    aIsdisabled// "isdisabled"
0x23b2ee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x23b2f3  unbox.any [mscorlib]System.Boolean
0x23b2f8  stloc.3
0x23b2f9  ldloc.2
0x23b2fa  ldstr    aAccessmode// "accessmode"
0x23b2ff  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x23b304  brtrue.s loc_23B32A
0x23b306  ldc.i4.3
0x23b307  ldloc.2
0x23b308  ldstr    aAccessmode// "accessmode"
0x23b30d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x23b312  unbox.any [mscorlib]System.Int32
0x23b317  bne.un.s loc_23B32A
0x23b319  ldc.i4   0x80041D41
0x23b31e  ldc.i4.0
0x23b31f  newarr   [mscorlib]System.Object
0x23b324  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23b329  throw
0x23b32a  ldloc.2
0x23b32b  ldstr    aAccessmode// "accessmode"
0x23b330  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x23b335  brtrue.s loc_23B35B
0x23b337  ldc.i4.5
0x23b338  ldloc.2
0x23b339  ldstr    aAccessmode// "accessmode"
0x23b33e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x23b343  unbox.any [mscorlib]System.Int32
0x23b348  bne.un.s loc_23B35B
0x23b34a  ldc.i4   0x80041D67
0x23b34f  ldc.i4.0
0x23b350  newarr   [mscorlib]System.Object
0x23b355  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23b35a  throw
0x23b35b  ldarg.0
0x23b35c  ldfld    valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState class <>c__DisplayClass63_0<var<u1>>::state
0x23b361  brfalse.s loc_23B366
0x23b363  ldc.i4.1
0x23b364  br.s     loc_23B367
0x23b366  ldc.i4.0
0x23b367  stloc.s  4
0x23b369  ldloc.3
0x23b36a  ldloc.s  4
0x23b36c  bne.un.s loc_23B387
0x23b36e  ldloc.0
0x23b36f  ldstr    aIsdisabled_1// "isDisabled"
0x23b374  ldloca.s 3
0x23b376  call     instance string [mscorlib]System.Boolean::ToString()
0x23b37b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23b380  ldloc.0
0x23b381  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x23b386  ret
0x23b387  ldarg.0
0x23b388  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b38d  ldloc.2
0x23b38e  ldarg.0
0x23b38f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b394  ldarg.0
0x23b395  ldfld    valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState class <>c__DisplayClass63_0<var<u1>>::state
0x23b39a  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::ValidateUserLicenseState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState)
0x23b39f  ldarg.0
0x23b3a0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b3a5  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUser::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23b3aa  stloc.s  5
0x23b3ac  ldloc.s  5
0x23b3ae  ldstr    aSystemuserid// "systemuserid"
0x23b3b3  ldarg.0
0x23b3b4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b3b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x23b3be  box      [mscorlib]System.Guid
0x23b3c3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x23b3c8  ldloc.s  5
0x23b3ca  ldstr    aIsdisabled// "isdisabled"
0x23b3cf  ldloc.s  4
0x23b3d1  box      [mscorlib]System.Boolean
0x23b3d6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x23b3db  ldloc.s  4
0x23b3dd  brfalse.s loc_23B403
0x23b3df  ldarg.0
0x23b3e0  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b3e5  ldarg.0
0x23b3e6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b3eb  call     instance bool class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::HasMobileOfflineProfileIdAttribute(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b3f0  brfalse.s loc_23B403
0x23b3f2  ldloc.s  5
0x23b3f4  ldstr    aMobileofflinep// "mobileofflineprofileid"
0x23b3f9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x23b3fe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x23b403  ldarg.0
0x23b404  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b409  ldarg.0
0x23b40a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b40f  ldloc.s  5
0x23b411  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::IsSetStatePipelineInvokedByUpdateSdk(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x23b416  brfalse.s loc_23B43F
0x23b418  ldarg.0
0x23b419  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b41e  ldloc.s  5
0x23b420  ldloc.s  5
0x23b422  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x23b427  ldarg.0
0x23b428  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b42d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b432  ldarg.0
0x23b433  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b438  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b43d  br.s     loc_23B452
0x23b43f  ldarg.0
0x23b440  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b445  ldloc.s  5
0x23b447  ldarg.0
0x23b448  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b44d  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::<>n__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b452  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory::.ctor()
0x23b457  ldloc.2
0x23b458  ldarg.0
0x23b459  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b45e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x23b463  ldarg.0
0x23b464  ldfld    valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState class <>c__DisplayClass63_0<var<u1>>::state
0x23b469  ldc.i4.0
0x23b46a  ceq
0x23b46c  ldarg.0
0x23b46d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b472  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory::SetExternalGroupMembership(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b477  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x23b47c  ldarg.0
0x23b47d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b482  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x23b487  ldarg.0
0x23b488  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b48d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x23b492  ldstr    aClearsystemuse// "ClearSystemUserPrincipalsWhenDisable"
0x23b497  ldc.i4.1
0x23b498  box      [mscorlib]System.Boolean
0x23b49d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x23b4a2  unbox.any [mscorlib]System.Boolean
0x23b4a7  stloc.s  6
0x23b4a9  ldloc.0
0x23b4aa  ldstr    aClearuserprinc// "clearUserPrincipals"
0x23b4af  ldloca.s 6
0x23b4b1  call     instance string [mscorlib]System.Boolean::ToString()
0x23b4b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23b4bb  ldc.i4.1
0x23b4bc  ldarg.0
0x23b4bd  ldfld    valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState class <>c__DisplayClass63_0<var<u1>>::state
0x23b4c2  bne.un.s loc_23B4E6
0x23b4c4  ldloc.s  6
0x23b4c6  brfalse.s loc_23B508
0x23b4c8  ldarg.0
0x23b4c9  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b4ce  ldarg.0
0x23b4cf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b4d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x23b4d9  ldarg.0
0x23b4da  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b4df  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::ClearSystemUserPrincipals(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b4e4  br.s     loc_23B508
0x23b4e6  ldloc.0
0x23b4e7  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x23b4ec  ldarg.0
0x23b4ed  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b4f2  ldarg.0
0x23b4f3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b4f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x23b4fd  ldarg.0
0x23b4fe  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b503  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::PopulateSystemUserPrincipals(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23b508  ldc.i4.2
0x23b509  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x23b50e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x23b513  bne.un   loc_23B598
0x23b518  ldarg.0
0x23b519  ldfld    valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SystemUserState class <>c__DisplayClass63_0<var<u1>>::state
0x23b51e  ldc.i4.1
0x23b51f  bne.un.s loc_23B598
0x23b521  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x23b526  ldarg.0
0x23b527  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b52c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x23b531  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x23b536  brtrue.s loc_23B598
0x23b538  newobj   instance void Microsoft.Crm.ObjectModel.UserInviteService::.ctor()
0x23b53d  ldloc.2
0x23b53e  ldstr    aAccessmode// "accessmode"
0x23b543  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x23b548  unbox.any [mscorlib]System.Int32
0x23b54d  ldc.i4.0
0x23b54e  ceq
0x23b550  stloc.s  8
0x23b552  ldloc.2
0x23b553  ldstr    aInvitestatusco// "invitestatuscode"
0x23b558  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x23b55d  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.UserInvitationStatus
0x23b562  ldsfld   string [mscorlib]System.String::Empty
0x23b567  stloc.s  9
0x23b569  ldc.i4.4
0x23b56a  bne.un.s loc_23B57E
0x23b56c  ldloc.2
0x23b56d  ldstr    aWindowsliveid// "windowsliveid"
0x23b572  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x23b577  castclass [mscorlib]System.String
0x23b57c  stloc.s  9
0x23b57e  ldarg.0
0x23b57f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b584  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x23b589  ldloc.s  8
0x23b58b  ldloc.s  9
0x23b58d  ldarg.0
0x23b58e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b593  callvirt instance void Microsoft.Crm.ObjectModel.UserInviteService::ResetUserInvite(valuetype [mscorlib]System.Guid userId, bool attemptDeprovision, string windowsLiveId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23b598  ldarg.0
0x23b599  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass63_0<var<u1>>::<>4__this
0x23b59e  ldarg.0
0x23b59f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class <>c__DisplayClass63_0<var<u1>>::moniker
0x23b5a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x23b5a9  ldarg.0
0x23b5aa  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass63_0<var<u1>>::context
0x23b5af  ldc.i4.1
0x23b5b0  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::FlushCaches(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x23b5b5  ret
```
