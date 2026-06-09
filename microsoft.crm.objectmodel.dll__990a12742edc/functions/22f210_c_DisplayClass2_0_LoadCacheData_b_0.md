# <>c__DisplayClass2_0::<LoadCacheData>b__0

- ea: `0x22f210`
- end: `0x22f951`
- name: `<>c__DisplayClass2_0::<LoadCacheData>b__0`
- size: `1857`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation`

## callees

- `0x4dcb0`
- `0x4dcc0`
- `0x4dd40`
- `0x529f0`
- `0x52b30`
- `0x52ba0`
- `0x52c60`
- `0x52c90`
- `0x52cb0`
- `0x52df0`
- `0x52eb0`
- `0x52ff0`
- `0xcf240`
- `0xd0a30`
- `0xd8c70`
- `0x1bbaf0`
- `0x22f210`

## string_xrefs

- `0x22f32e`: `azureactivedirectoryobjectid`
- `0x22f40a`: `accessmode`
- `0x22f417`: `accessmode`
- `0x22f2ea`: `activedirectoryguid`
- `0x22f254`: `LoadUserDataCache`
- `0x22f56f`: `LoadUserTeamsDataCache`
- `0x22f92d`: `PrivilegesCount`

## pseudocode

```c

```

## disassembly

```asm
0x22f210  ldstr    aSystemuserid_2// "SystemUserId"
0x22f215  ldarg.0
0x22f216  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f21b  constrained. [mscorlib]System.Guid
0x22f221  callvirt instance string [mscorlib]System.Object::ToString()
0x22f226  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x22f22b  ldarg.0
0x22f22c  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f231  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22f236  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x22f23b  brfalse.s loc_22F248
0x22f23d  ldstr    aUseridIsEmptyG// "UserId is empty guid! "
0x22f242  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(string)
0x22f247  throw
0x22f248  ldarg.0
0x22f249  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f24e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22f253  pop
0x22f254  ldstr    aLoaduserdataca// "LoadUserDataCache"
0x22f259  ldc.i4.1
0x22f25a  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, bool)
0x22f25f  stloc.0
0x22f260  ldnull
0x22f261  stloc.1
0x22f262  ldnull
0x22f263  stloc.2
0x22f264  ldnull
0x22f265  stloc.3
0x22f266  ldnull
0x22f267  stloc.s  4
0x22f269  ldnull
0x22f26a  stloc.s  5
0x22f26c  ldnull
0x22f26d  stloc.s  6
0x22f26f  ldnull
0x22f270  stloc.s  7
0x22f272  ldnull
0x22f273  stloc.s  8
0x22f275  ldnull
0x22f276  stloc.s  9
0x22f278  ldnull
0x22f279  stloc.s  0xA
0x22f27b  ldc.i4.0
0x22f27c  stloc.s  0xB
0x22f27e  ldc.i4.0
0x22f27f  stloc.s  0xC
0x22f281  ldc.i4.0
0x22f282  stloc.s  0xD
0x22f284  ldc.i4.0
0x22f285  stloc.s  0xE
0x22f287  ldc.i4.0
0x22f288  stloc.s  0xF
0x22f28a  ldc.i4.0
0x22f28b  stloc.s  0x10
0x22f28d  ldc.i4.0
0x22f28e  stloc.s  0x11
0x22f290  ldc.i4.0
0x22f291  stloc.s  0x12
0x22f293  ldc.i4.0
0x22f294  stloc.s  0x13
0x22f296  ldc.i4.0
0x22f297  stloc.s  0x14
0x22f299  ldc.i4.0
0x22f29a  stloc.s  0x15
0x22f29c  ldnull
0x22f29d  stloc.s  0x16
0x22f29f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x22f2a4  stloc.s  0x1E
0x22f2a6  newobj   instance void Microsoft.Crm.ObjectModel.ProvisionSystemUserService::.ctor()
0x22f2ab  stloc.s  0x1F
0x22f2ad  ldarg.0
0x22f2ae  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f2b3  ldstr    aSystemuser_0// "SystemUser"
0x22f2b8  ldarg.0
0x22f2b9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f2be  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22f2c3  stloc.s  0x20
0x22f2c5  ldstr    aSystemuser_0// "SystemUser"
0x22f2ca  ldarg.0
0x22f2cb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f2d0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x22f2d5  stloc.s  0x21
0x22f2d7  ldloc.s  0x21
0x22f2d9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22f2de  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllSystemPhysicalPersistentColumns()
0x22f2e3  ldloc.s  0x21
0x22f2e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22f2ea  ldstr    aActivedirector// "activedirectoryguid"
0x22f2ef  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x22f2f4  ldloc.s  0x21
0x22f2f6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22f2fb  ldstr    aBusinessunitid_4// "businessunitidname"
0x22f300  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x22f305  ldloc.s  0x21
0x22f307  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22f30c  ldstr    aCaltype// "caltype"
0x22f311  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x22f316  ldloc.s  0x21
0x22f318  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22f31d  ldstr    aUserlicensetyp// "userlicensetype"
0x22f322  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x22f327  ldloc.s  0x21
0x22f329  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x22f32e  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x22f333  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x22f338  ldloc.s  0x21
0x22f33a  ldc.i4.0
0x22f33b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_RetrieveBehaviorForSecuredAttributes(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior)
0x22f340  ldloc.s  0x1F
0x22f342  ldloc.s  0x20
0x22f344  ldloc.s  0x21
0x22f346  ldarg.0
0x22f347  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f34c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22f351  stloc.1
0x22f352  ldloc.1
0x22f353  ldstr    aApplicationid// "applicationid"
0x22f358  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x22f35d  ldc.i4.0
0x22f35e  ceq
0x22f360  stloc.s  0xF
0x22f362  ldarg.0
0x22f363  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f368  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x22f36d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_EntitiesByName()
0x22f372  ldstr    aSystemuser_0// "SystemUser"
0x22f377  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x22f37c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x22f381  ldstr    aIdentityid// "identityid"
0x22f386  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x22f38b  brtrue.s loc_22F390
0x22f38d  ldc.i4.0
0x22f38e  br.s     loc_22F3A0
0x22f390  ldloc.1
0x22f391  ldstr    aIdentityid// "identityid"
0x22f396  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x22f39b  unbox.any [mscorlib]System.Int32
0x22f3a0  stloc.s  0x17
0x22f3a2  ldarg.0
0x22f3a3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f3a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x22f3ad  ldarg.0
0x22f3ae  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f3b3  ldarg.0
0x22f3b4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f3b9  call     valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary/SpecialUser [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::IsOrganizationSpecialUser(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22f3be  stloc.s  0x22
0x22f3c0  ldloc.s  0x22
0x22f3c2  ldc.i4.0
0x22f3c3  cgt.un
0x22f3c5  stloc.s  0xE
0x22f3c7  ldstr    aIssystemuser// "IsSystemUser"
0x22f3cc  ldloca.s 0xE
0x22f3ce  call     instance string [mscorlib]System.Boolean::ToString()
0x22f3d3  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x22f3d8  ldstr    aIsapplicationu// "IsApplicationUser"
0x22f3dd  ldloca.s 0xF
0x22f3df  call     instance string [mscorlib]System.Boolean::ToString()
0x22f3e4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x22f3e9  ldloc.s  0xE
0x22f3eb  brtrue   loc_22F49F
0x22f3f0  ldarg.0
0x22f3f1  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f3f6  ldloc.s  0x1F
0x22f3f8  ldarg.0
0x22f3f9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f3fe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Caching.UserDataCacheLoader::RetrieveUserSettings(valuetype [mscorlib]System.Guid& key, class Microsoft.Crm.ObjectModel.ProvisionSystemUserService userService, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x22f403  stloc.2
0x22f404  newobj   instance void Microsoft.Crm.ObjectModel.ProvisionPrivilegeService::.ctor()
0x22f409  ldloc.1
0x22f40a  ldstr    aAccessmode// "accessmode"
0x22f40f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x22f414  brfalse.s loc_22F42D
0x22f416  ldloc.1
0x22f417  ldstr    aAccessmode// "accessmode"
0x22f41c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x22f421  unbox.any [mscorlib]System.Int32
0x22f426  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x22f42b  br.s     loc_22F437
0x22f42d  ldloca.s 0x26
0x22f42f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x22f435  ldloc.s  0x26
0x22f437  stloc.s  0x25
0x22f439  dup
0x22f43a  ldarg.0
0x22f43b  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f440  ldloc.s  0x25
0x22f442  ldarg.0
0x22f443  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f448  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOn>::RetrieveUserPrivileges(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<int32>, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22f44d  stloc.3
0x22f44e  ldarg.0
0x22f44f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f454  ldloc.s  0x25
0x22f456  ldarg.0
0x22f457  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f45c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOn>::RetrievePrivilegeMaxDepthFromTeamRoles(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<int32>, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22f461  stloc.s  4
0x22f463  newobj   instance void Microsoft.Crm.ObjectModel.ProvisionPrincipalAttributeAccessMapService::.ctor()
0x22f468  ldc.i4.8
0x22f469  ldarg.0
0x22f46a  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f46f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32, valuetype [mscorlib]System.Guid)
0x22f474  ldarg.0
0x22f475  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f47a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilegeCollection class Microsoft.Crm.ObjectModel.PrincipalAttributeAccessMapServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOn>::RetrievePrincipalAttributePrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22f47f  stloc.s  5
0x22f481  ldarg.0
0x22f482  ldfld    class Microsoft.Crm.Caching.UserDataCacheLoader <>c__DisplayClass2_0::<>4__this
0x22f487  ldarg.0
0x22f488  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f48d  ldarg.0
0x22f48e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f493  call     instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<int32, valuetype [mscorlib]System.Guid[]> Microsoft.Crm.Caching.UserDataCacheLoader::RetrieveUserBusinessUnitsWithReadPrivilege(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x22f498  stloc.s  7
0x22f49a  br       loc_22F537
0x22f49f  ldarg.0
0x22f4a0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f4a5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22f4aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Privileges()
0x22f4af  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::.ctor()
0x22f4b4  stloc.s  0x27
0x22f4b6  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Keys()
0x22f4bb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x22f4c0  stloc.s  0x28
0x22f4c2  br.s     loc_22F4F3
0x22f4c4  ldloc.s  0x28
0x22f4c6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x22f4cb  unbox.any [mscorlib]System.Guid
0x22f4d0  stloc.s  0x29
0x22f4d2  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::.ctor()
0x22f4d7  stloc.s  0x2A
0x22f4d9  ldloc.s  0x2A
0x22f4db  ldloc.s  0x29
0x22f4dd  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::set_PrivilegeId(valuetype [mscorlib]System.Guid)
0x22f4e2  ldloc.s  0x2A
0x22f4e4  ldc.i4.3
0x22f4e5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::set_Depth(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth)
0x22f4ea  ldloc.s  0x27
0x22f4ec  ldloc.s  0x2A
0x22f4ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::Add(var<u1>)
0x22f4f3  ldloc.s  0x28
0x22f4f5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22f4fa  brtrue.s loc_22F4C4
0x22f4fc  leave.s  loc_22F513
0x22f4fe  ldloc.s  0x28
0x22f500  isinst   [mscorlib]System.IDisposable
0x22f505  stloc.s  0x2B
0x22f507  ldloc.s  0x2B
0x22f509  brfalse.s loc_22F512
0x22f50b  ldloc.s  0x2B
0x22f50d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22f512  endfinally
0x22f513  ldloc.s  0x27
0x22f515  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::ToArray()
0x22f51a  stloc.3
0x22f51b  ldc.i4.0
0x22f51c  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege
0x22f521  stloc.s  4
0x22f523  ldarg.0
0x22f524  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f529  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilegeCollection Microsoft.Crm.Caching.UserDataCacheLoader::RetrieveSpecialUserAttributePrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x22f52e  stloc.s  5
0x22f530  ldloc.s  0x22
0x22f532  ldc.i4.1
0x22f533  ceq
0x22f535  stloc.s  0xE
0x22f537  ldarg.0
0x22f538  ldfld    class Microsoft.Crm.Caching.UserDataCacheLoader <>c__DisplayClass2_0::<>4__this
0x22f53d  ldarg.0
0x22f53e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::key
0x22f543  ldarg.0
0x22f544  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f549  call     instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.Caching.UserDataCacheLoader::RetrieveUserOwnerTeams(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x22f54e  stloc.s  8
0x22f550  ldstr    aUserteamcount// "UserTeamCount"
0x22f555  ldloc.s  8
0x22f557  ldlen
0x22f558  conv.i4
0x22f559  stloc.s  0x2C
0x22f55b  ldloca.s 0x2C
0x22f55d  call     instance string [mscorlib]System.Int32::ToString()
0x22f562  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x22f567  ldloc.s  8
0x22f569  ldlen
0x22f56a  conv.i4
0x22f56b  ldc.i4.1
0x22f56c  ble.s    loc_22F59C
0x22f56e  ldloc.0
0x22f56f  ldstr    aLoaduserteamsd// "LoadUserTeamsDataCache"
0x22f574  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x22f579  stloc.s  0x2D
0x22f57b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache::Instance()
0x22f580  ldloc.s  8
0x22f582  ldarg.0
0x22f583  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass2_0::context
0x22f588  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ITeam>::LookupEntries(var<u1>, void)
0x22f58d  pop
0x22f58e  leave.s  loc_22F59C
0x22f590  ldloc.s  0x2D
  ... truncated ...
```
