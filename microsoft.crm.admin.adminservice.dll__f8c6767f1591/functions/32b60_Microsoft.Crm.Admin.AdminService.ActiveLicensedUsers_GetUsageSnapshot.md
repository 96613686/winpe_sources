# Microsoft.Crm.Admin.AdminService.ActiveLicensedUsers::GetUsageSnapshot

- ea: `0x32b60`
- end: `0x32ef5`
- name: `Microsoft.Crm.Admin.AdminService.ActiveLicensedUsers::GetUsageSnapshot`
- size: `917`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x32b30`
- `0x32f00`

## callees

- `0x25a40`
- `0x27740`
- `0x285a0`
- `0x287b0`
- `0x32b60`
- `0x33010`
- `0x3f1c0`
- `0x3f1f0`
- `0x3f210`
- `0x3f230`
- `0x3f250`
- `0x3f270`
- `0x3f2a0`

## string_xrefs

- `0x32ba0`: `LastAccessTime`
- `0x32c40`: `LastAccessTime`
- `0x32c4e`: `LastAccessTime`
- `0x32ba8`: `LastAccessServer`
- `0x32c68`: `LastAccessServer`
- `0x32c76`: `LastAccessServer`
- `0x32d9c`: `Exception in counting the total number of users for all organizations. The error happened when trying to open Organization with Id=({0}). Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x32b60  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class OrganizationIdAndCrmUserIdPair, valuetype [mscorlib]System.Guid>::.ctor()
0x32b65  stloc.0
0x32b66  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Admin.AdminService.OrganizationUserInfo>::.ctor()
0x32b6b  stloc.1
0x32b6c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::.ctor()
0x32b71  stloc.2
0x32b72  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x32b77  stloc.s  4
0x32b79  ldloc.s  4
0x32b7b  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x32b80  ldc.i4.5
0x32b81  newarr   [mscorlib]System.String
0x32b86  dup
0x32b87  ldc.i4.0
0x32b88  ldstr    aCrmuserid// "CrmUserId"
0x32b8d  stelem.ref
0x32b8e  dup
0x32b8f  ldc.i4.1
0x32b90  ldstr    aOrganizationid_0// "OrganizationId"
0x32b95  stelem.ref
0x32b96  dup
0x32b97  ldc.i4.2
0x32b98  ldstr    aUserid// "UserId"
0x32b9d  stelem.ref
0x32b9e  dup
0x32b9f  ldc.i4.3
0x32ba0  ldstr    aLastaccesstime// "LastAccessTime"
0x32ba5  stelem.ref
0x32ba6  dup
0x32ba7  ldc.i4.4
0x32ba8  ldstr    aLastaccessserv// "LastAccessServer"
0x32bad  stelem.ref
0x32bae  ldnull
0x32baf  ldc.i4   0x432
0x32bb4  ldstr    aGetusagesnapsh// "GetUsageSnapshot"
0x32bb9  ldstr    aDA1SSrcCrmlive_59// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Licen"...
0x32bbe  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x32bc3  stloc.3
0x32bc4  leave.s  loc_32BD2
0x32bc6  ldloc.s  4
0x32bc8  brfalse.s loc_32BD1
0x32bca  ldloc.s  4
0x32bcc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32bd1  endfinally
0x32bd2  ldloc.3
0x32bd3  brfalse  loc_32CBA
0x32bd8  ldloc.3
0x32bd9  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x32bde  stloc.s  5
0x32be0  br       loc_32C9E
0x32be5  ldloca.s 5
0x32be7  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x32bec  stloc.s  7
0x32bee  ldloca.s 7
0x32bf0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x32bf5  stloc.s  6
0x32bf7  ldloc.s  6
0x32bf9  brfalse  loc_32C9E
0x32bfe  ldloc.s  6
0x32c00  ldstr    aCrmuserid// "CrmUserId"
0x32c05  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32c0a  unbox.any [mscorlib]System.Guid
0x32c0f  stloc.s  8
0x32c11  ldloc.s  6
0x32c13  ldstr    aOrganizationid_0// "OrganizationId"
0x32c18  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32c1d  unbox.any [mscorlib]System.Guid
0x32c22  stloc.s  9
0x32c24  ldloc.s  6
0x32c26  ldstr    aUserid// "UserId"
0x32c2b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32c30  unbox.any [mscorlib]System.Guid
0x32c35  stloc.s  0xA
0x32c37  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x32c3c  stloc.s  0xB
0x32c3e  ldloc.s  6
0x32c40  ldstr    aLastaccesstime// "LastAccessTime"
0x32c45  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32c4a  brfalse.s loc_32C5F
0x32c4c  ldloc.s  6
0x32c4e  ldstr    aLastaccesstime// "LastAccessTime"
0x32c53  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32c58  unbox.any [mscorlib]System.DateTime
0x32c5d  stloc.s  0xB
0x32c5f  ldsfld   string [mscorlib]System.String::Empty
0x32c64  stloc.s  0xC
0x32c66  ldloc.s  6
0x32c68  ldstr    aLastaccessserv// "LastAccessServer"
0x32c6d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32c72  brfalse.s loc_32C87
0x32c74  ldloc.s  6
0x32c76  ldstr    aLastaccessserv// "LastAccessServer"
0x32c7b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32c80  castclass [mscorlib]System.String
0x32c85  stloc.s  0xC
0x32c87  ldloc.2
0x32c88  ldloc.s  8
0x32c8a  ldloc.s  9
0x32c8c  ldloc.s  8
0x32c8e  ldloc.s  0xA
0x32c90  ldloc.s  0xB
0x32c92  ldloc.s  0xC
0x32c94  newobj   instance void UsersWithAccessInfo::.ctor(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmUserId, valuetype [mscorlib]System.Guid systemUserId, valuetype [mscorlib]System.DateTime lastAccessTime, string lastAccessServer)
0x32c99  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::set_Item(var<u1>, !!T0)
0x32c9e  ldloca.s 5
0x32ca0  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x32ca5  brtrue   loc_32BE5
0x32caa  leave.s  loc_32CBA
0x32cac  ldloca.s 5
0x32cae  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x32cb4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32cb9  endfinally
0x32cba  ldloc.2
0x32cbb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::get_Values()
0x32cc0  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::GetEnumerator()
0x32cc5  stloc.s  0xD
0x32cc7  br.s     loc_32D22
0x32cc9  ldloca.s 0xD
0x32ccb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::get_Current()
0x32cd0  stloc.s  0xE
0x32cd2  ldloc.s  0xE
0x32cd4  callvirt instance valuetype [mscorlib]System.DateTime UsersWithAccessInfo::get_LastAccessTime()
0x32cd9  stloc.s  0xF
0x32cdb  ldloca.s 0xF
0x32cdd  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x32ce2  ldarg.0
0x32ce3  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x32ce8  brfalse.s loc_32D22
0x32cea  ldloc.s  0xE
0x32cec  callvirt instance valuetype [mscorlib]System.DateTime UsersWithAccessInfo::get_LastAccessTime()
0x32cf1  stloc.s  0xF
0x32cf3  ldloca.s 0xF
0x32cf5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x32cfa  ldarg.1
0x32cfb  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x32d00  brfalse.s loc_32D22
0x32d02  ldloc.0
0x32d03  ldloc.s  0xE
0x32d05  callvirt instance valuetype [mscorlib]System.Guid UsersWithAccessInfo::get_OrganizationId()
0x32d0a  ldloc.s  0xE
0x32d0c  callvirt instance valuetype [mscorlib]System.Guid UsersWithAccessInfo::get_CrmUserId()
0x32d11  newobj   instance void OrganizationIdAndCrmUserIdPair::.ctor(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmUserId)
0x32d16  ldloc.s  0xE
0x32d18  callvirt instance valuetype [mscorlib]System.Guid UsersWithAccessInfo::get_UserId()
0x32d1d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class OrganizationIdAndCrmUserIdPair, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x32d22  ldloca.s 0xD
0x32d24  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::MoveNext()
0x32d29  brtrue.s loc_32CC9
0x32d2b  leave.s  loc_32D3B
0x32d2d  ldloca.s 0xD
0x32d2f  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>
0x32d35  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32d3a  endfinally
0x32d3b  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x32d40  ldc.i4.2
0x32d41  newarr   [mscorlib]System.String
0x32d46  dup
0x32d47  ldc.i4.0
0x32d48  ldstr    aState// "State"
0x32d4d  stelem.ref
0x32d4e  dup
0x32d4f  ldc.i4.1
0x32d50  ldstr    aId// "Id"
0x32d55  stelem.ref
0x32d56  callvirt instance class Microsoft.Crm.Admin.AdminService.OrganizationData[] Microsoft.Crm.Admin.AdminService.CrmOrganizationService::RetrieveMultiple(string[] columns)
0x32d5b  stloc.s  0x10
0x32d5d  ldc.i4.0
0x32d5e  stloc.s  0x11
0x32d60  br       loc_32EE8
0x32d65  ldloc.s  0x10
0x32d67  ldloc.s  0x11
0x32d69  ldelem.ref
0x32d6a  stloc.s  0x12
0x32d6c  ldc.i4.1
0x32d6d  ldloc.s  0x12
0x32d6f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Admin.AdminService.OrganizationData::get_State()
0x32d74  bne.un   loc_32EE2
0x32d79  ldloc.s  0x12
0x32d7b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x32d80  stloc.s  0x13
0x32d82  ldloc.s  0x13
0x32d84  ldc.i4.0
0x32d85  ldc.i4.0
0x32d86  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x32d8b  stloc.s  0x14
0x32d8d  ldloc.s  0x14
0x32d8f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x32d94  leave.s  loc_32DD1
0x32d96  stloc.s  0x15
0x32d98  ldloc.s  0x13
0x32d9a  ldc.i4.s 0x1D
0x32d9c  ldstr    aExceptionInCou// "Exception in counting the total number "...
0x32da1  ldc.i4.2
0x32da2  newarr   [mscorlib]System.Object
0x32da7  dup
0x32da8  ldc.i4.0
0x32da9  ldloc.s  0x13
0x32dab  box      [mscorlib]System.Guid
0x32db0  stelem.ref
0x32db1  dup
0x32db2  ldc.i4.1
0x32db3  ldloc.s  0x15
0x32db5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x32dba  stelem.ref
0x32dbb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x32dc0  ldc.i4   0x8004D24A
0x32dc5  ldc.i4.0
0x32dc6  newarr   [mscorlib]System.Object
0x32dcb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x32dd0  throw
0x32dd1  ldloc.s  0x14
0x32dd3  ldstr    aSelectSystemus// "SELECT SystemUserId, DomainName, FullNa"...
0x32dd8  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x32ddd  stloc.s  0x16
0x32ddf  ldloc.s  0x16
0x32de1  ldc.i4   0x482
0x32de6  ldstr    aGetusagesnapsh// "GetUsageSnapshot"
0x32deb  ldstr    aDA1SSrcCrmlive_59// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Licen"...
0x32df0  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x32df5  stloc.s  0x17
0x32df7  br       loc_32EA0
0x32dfc  ldloc.s  0x17
0x32dfe  ldstr    aSystemuserid// "SystemUserId"
0x32e03  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x32e08  unbox.any [mscorlib]System.Guid
0x32e0d  stloc.s  0x18
0x32e0f  ldloc.s  0x17
0x32e11  ldstr    aDomainname_0// "DomainName"
0x32e16  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x32e1b  castclass [mscorlib]System.String
0x32e20  stloc.s  0x19
0x32e22  ldloc.s  0x17
0x32e24  ldstr    aFullname// "FullName"
0x32e29  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x32e2e  castclass [mscorlib]System.String
0x32e33  stloc.s  0x1A
0x32e35  ldloc.s  0x17
0x32e37  ldstr    aCaltype// "CALType"
0x32e3c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x32e41  unbox.any [mscorlib]System.Int32
0x32e46  stloc.s  0x1B
0x32e48  ldloc.s  0x13
0x32e4a  ldloc.s  0x18
0x32e4c  newobj   instance void OrganizationIdAndCrmUserIdPair::.ctor(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmUserId)
0x32e51  stloc.s  0x1C
0x32e53  ldloc.0
0x32e54  ldloc.s  0x1C
0x32e56  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class OrganizationIdAndCrmUserIdPair, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x32e5b  brfalse.s loc_32EA0
0x32e5d  ldloc.0
0x32e5e  ldloc.s  0x1C
0x32e60  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class OrganizationIdAndCrmUserIdPair, valuetype [mscorlib]System.Guid>::get_Item(void)
0x32e65  stloc.s  0x1D
0x32e67  ldloc.2
0x32e68  ldloc.s  0x18
0x32e6a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::get_Item(void)
0x32e6f  callvirt instance valuetype [mscorlib]System.DateTime UsersWithAccessInfo::get_LastAccessTime()
0x32e74  stloc.s  0x1E
0x32e76  ldloc.2
0x32e77  ldloc.s  0x18
0x32e79  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class UsersWithAccessInfo>::get_Item(void)
0x32e7e  callvirt instance string UsersWithAccessInfo::get_LastAccessServer()
0x32e83  stloc.s  0x1F
0x32e85  ldloc.1
0x32e86  ldloc.s  0x1D
0x32e88  ldloc.s  0x1B
0x32e8a  ldloc.s  0x19
0x32e8c  ldloc.s  0x1A
0x32e8e  ldloc.s  0x1E
0x32e90  ldloc.s  0x1F
0x32e92  call     void Microsoft.Crm.Admin.AdminService.ActiveLicensedUsers::RefreshUserInfo(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Admin.AdminService.OrganizationUserInfo> hashConfigDbUserIdToCalType, valuetype [mscorlib]System.Guid configDbUserId, int32 newCalType, string domainName, string fullName, valuetype [mscorlib]System.DateTime lastAccessTime, string lastAccessServer)
0x32e97  ldloc.0
0x32e98  ldloc.s  0x1C
0x32e9a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class OrganizationIdAndCrmUserIdPair, valuetype [mscorlib]System.Guid>::Remove(var<u1>)
0x32e9f  pop
0x32ea0  ldloc.s  0x17
0x32ea2  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x32ea7  brtrue   loc_32DFC
0x32eac  ldloc.s  0x17
0x32eae  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0x32eb3  leave.s  loc_32ECD
0x32eb5  ldloc.s  0x17
0x32eb7  brfalse.s loc_32EC0
0x32eb9  ldloc.s  0x17
0x32ebb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32ec0  endfinally
0x32ec1  ldloc.s  0x16
0x32ec3  brfalse.s loc_32ECC
0x32ec5  ldloc.s  0x16
0x32ec7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32ecc  endfinally
0x32ecd  ldloc.s  0x14
0x32ecf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x32ed4  leave.s  loc_32EE2
0x32ed6  ldloc.s  0x14
0x32ed8  brfalse.s loc_32EE1
0x32eda  ldloc.s  0x14
0x32edc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32ee1  endfinally
0x32ee2  ldloc.s  0x11
  ... truncated ...
```
