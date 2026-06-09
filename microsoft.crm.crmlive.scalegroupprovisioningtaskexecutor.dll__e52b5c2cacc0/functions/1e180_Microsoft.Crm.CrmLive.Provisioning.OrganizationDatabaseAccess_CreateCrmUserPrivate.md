# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateCrmUserPrivate

- ea: `0x1e180`
- end: `0x1e37a`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateCrmUserPrivate`
- size: `506`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1e0e0`
- `0x1e140`
- `0x1e170`

## callees

- `0x1bda0`
- `0x1bdc0`
- `0x1e180`
- `0x1e760`
- `0x1e830`
- `0x1f8b0`
- `0x20b40`

## string_xrefs

- `0x1e230`: `accessmode`
- `0x1e24e`: `accessmode`
- `0x1e1f6`: `issyncwithdirectory`
- `0x1e2a4`: `Starting creating user for organization:{0}, directoryobjectid:{1}`
- `0x1e301`: `Completed creating user for organization:{0}, directoryobjectid:{1}`
- `0x1e346`: `skipped user for organization:{0}, directoryobjectid:{1}. UPN:{2} was already in the database`

## pseudocode

```c

```

## disassembly

```asm
0x1e180  ldarg.1
0x1e181  ldstr    aOrganizationid// "organizationId"
0x1e186  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1e18b  ldarg.2
0x1e18c  ldstr    aNewuser// "NewUser"
0x1e191  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1e196  ldarg.1
0x1e197  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetBusinessUnit(valuetype [mscorlib]System.Guid organizationId)
0x1e19c  ldc.i4.s 0x64
0x1e19e  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PerfCollector::WriteToProvisioningLog(valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CodeMarkers)
0x1e1a3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1e1a8  stloc.2
0x1e1a9  br.s     loc_1E1D7
0x1e1ab  ldloc.2
0x1e1ac  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1e1b1  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1e1b6  stloc.3
0x1e1b7  ldarg.2
0x1e1b8  ldstr    aBusinessunitid// "businessunitid"
0x1e1bd  ldloc.3
0x1e1be  ldstr    aBusinessunitid// "businessunitid"
0x1e1c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e1c8  unbox.any [mscorlib]System.Guid
0x1e1cd  box      [mscorlib]System.Guid
0x1e1d2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e1d7  ldloc.2
0x1e1d8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1e1dd  brtrue.s loc_1E1AB
0x1e1df  leave.s  loc_1E1F5
0x1e1e1  ldloc.2
0x1e1e2  isinst   [mscorlib]System.IDisposable
0x1e1e7  stloc.s  4
0x1e1e9  ldloc.s  4
0x1e1eb  brfalse.s loc_1E1F4
0x1e1ed  ldloc.s  4
0x1e1ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e1f4  endfinally
0x1e1f5  ldarg.2
0x1e1f6  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x1e1fb  ldarg.s  4
0x1e1fd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e202  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e207  box      [mscorlib]System.Boolean
0x1e20c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e211  ldarg.2
0x1e212  ldstr    aIslicensed// "islicensed"
0x1e217  ldc.i4.1
0x1e218  box      [mscorlib]System.Boolean
0x1e21d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e222  ldarg.2
0x1e223  ldstr    aCaltype// "caltype"
0x1e228  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1e22d  brtrue.s loc_1E23C
0x1e22f  ldarg.2
0x1e230  ldstr    aAccessmode// "accessmode"
0x1e235  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1e23a  brfalse.s loc_1E25E
0x1e23c  ldarg.2
0x1e23d  ldstr    aCaltype// "caltype"
0x1e242  ldc.i4.0
0x1e243  box      [mscorlib]System.Int32
0x1e248  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e24d  ldarg.2
0x1e24e  ldstr    aAccessmode// "accessmode"
0x1e253  ldc.i4.0
0x1e254  box      [mscorlib]System.Int32
0x1e259  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e25e  ldc.i4.s 0x65
0x1e260  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PerfCollector::WriteToProvisioningLog(valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CodeMarkers)
0x1e265  ldarg.2
0x1e266  ldstr    aDomainname_0// "domainname"
0x1e26b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1e270  castclass [mscorlib]System.String
0x1e275  stloc.0
0x1e276  ldarg.0
0x1e277  ldarg.1
0x1e278  ldloc.0
0x1e279  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveSystemUserIdByEmail(valuetype [mscorlib]System.Guid organizationId, string email)
0x1e27e  stloc.1
0x1e27f  ldloc.1
0x1e280  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e285  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e28a  brfalse  loc_1E331
0x1e28f  ldarg.1
0x1e290  ldc.i4.s 0x48
0x1e292  ldstr    a0// "{0}"
0x1e297  ldc.i4.1
0x1e298  newarr   [mscorlib]System.Object
0x1e29d  dup
0x1e29e  ldc.i4.0
0x1e29f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e2a4  ldstr    aStartingCreati// "Starting creating user for organization"...
0x1e2a9  ldc.i4.2
0x1e2aa  newarr   [mscorlib]System.Object
0x1e2af  dup
0x1e2b0  ldc.i4.0
0x1e2b1  ldarg.1
0x1e2b2  box      [mscorlib]System.Guid
0x1e2b7  stelem.ref
0x1e2b8  dup
0x1e2b9  ldc.i4.1
0x1e2ba  ldarg.s  4
0x1e2bc  box      [mscorlib]System.Guid
0x1e2c1  stelem.ref
0x1e2c2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e2c7  stelem.ref
0x1e2c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e2cd  ldarg.1
0x1e2ce  ldarg.3
0x1e2cf  ldarg.2
0x1e2d0  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::CreateUserRequest(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity newUser)
0x1e2d5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::MakeSdkCall(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpCreateUserBehavior behavior, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest sdkRequest)
0x1e2da  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse
0x1e2df  ldc.i4.s 0x66
0x1e2e1  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PerfCollector::WriteToProvisioningLog(valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CodeMarkers)
0x1e2e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse::get_id()
0x1e2eb  stloc.1
0x1e2ec  ldarg.1
0x1e2ed  ldc.i4.s 0x48
0x1e2ef  ldstr    a0// "{0}"
0x1e2f4  ldc.i4.1
0x1e2f5  newarr   [mscorlib]System.Object
0x1e2fa  dup
0x1e2fb  ldc.i4.0
0x1e2fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e301  ldstr    aCompletedCreat// "Completed creating user for organizatio"...
0x1e306  ldc.i4.2
0x1e307  newarr   [mscorlib]System.Object
0x1e30c  dup
0x1e30d  ldc.i4.0
0x1e30e  ldarg.1
0x1e30f  box      [mscorlib]System.Guid
0x1e314  stelem.ref
0x1e315  dup
0x1e316  ldc.i4.1
0x1e317  ldarg.s  4
0x1e319  box      [mscorlib]System.Guid
0x1e31e  stelem.ref
0x1e31f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e324  stelem.ref
0x1e325  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e32a  ldloc.1
0x1e32b  call     class Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult::FromCreatedUser(valuetype [mscorlib]System.Guid systemUserId)
0x1e330  ret
0x1e331  ldarg.1
0x1e332  ldc.i4.s 0x48
0x1e334  ldstr    a0// "{0}"
0x1e339  ldc.i4.1
0x1e33a  newarr   [mscorlib]System.Object
0x1e33f  dup
0x1e340  ldc.i4.0
0x1e341  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e346  ldstr    aSkippedUserFor// "skipped user for organization:{0}, dire"...
0x1e34b  ldc.i4.3
0x1e34c  newarr   [mscorlib]System.Object
0x1e351  dup
0x1e352  ldc.i4.0
0x1e353  ldarg.1
0x1e354  box      [mscorlib]System.Guid
0x1e359  stelem.ref
0x1e35a  dup
0x1e35b  ldc.i4.1
0x1e35c  ldarg.s  4
0x1e35e  box      [mscorlib]System.Guid
0x1e363  stelem.ref
0x1e364  dup
0x1e365  ldc.i4.2
0x1e366  ldloc.0
0x1e367  stelem.ref
0x1e368  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e36d  stelem.ref
0x1e36e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e373  ldloc.1
0x1e374  call     class Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult Microsoft.Crm.CrmLive.Provisioning.SyncUserCreationResult::FromUserAlreadyInOrgDb(valuetype [mscorlib]System.Guid systemUserId)
0x1e379  ret
```
