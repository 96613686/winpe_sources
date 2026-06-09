# Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUserRecordsInConfigDb

- ea: `0x35a20`
- end: `0x35b27`
- name: `Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUserRecordsInConfigDb`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x35540`

## callees

- `0x35a20`
- `0x35b30`
- `0x35bb0`
- `0x35c00`
- `0x35c60`
- `0x35cb0`
- `0x35d20`
- `0x35d80`
- `0x35f10`

## string_xrefs

- `0x35a35`: `No action - User auth records already exist in ConfigDB. CrmUserId: {0}, directoryObjectId: {1}`
- `0x35a78`: `No action - User auth records already exist in ConfigDB. CrmUserId: {0}, directoryObjectId: {1}`
- `0x35ae6`: `User auth records created in ConfigDB. CrmUserId: {0}, directoryObjectId: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x35a20  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x35a25  stloc.0
0x35a26  ldarg.1
0x35a27  ldarg.0
0x35a28  ldloc.0
0x35a29  ldarg.s  4
0x35a2b  call     bool Microsoft.Crm.Admin.AdminService.UserService::DoesSystemUserOrganizationRecordExist(valuetype [mscorlib]System.Guid crmUserId, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService dbService, valuetype [mscorlib]System.Guid directoryObjectId)
0x35a30  brfalse.s loc_35A5C
0x35a32  ldarg.0
0x35a33  ldc.i4.s 0x48
0x35a35  ldstr    aNoActionUserAu// "No action - User auth records already e"...
0x35a3a  ldarg.1
0x35a3b  box      [mscorlib]System.Guid
0x35a40  ldarg.s  4
0x35a42  box      [mscorlib]System.Guid
0x35a47  call     string [mscorlib]System.String::Format(string, object, object)
0x35a4c  ldc.i4.0
0x35a4d  newarr   [mscorlib]System.Object
0x35a52  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35a57  leave    loc_35B26
0x35a5c  ldarg.2
0x35a5d  call     string Microsoft.Crm.Admin.AdminService.UserService::AuthInfoToLockName(string authInfo)
0x35a62  ldc.i4.2
0x35a63  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLockWithClientSideWait(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x35a68  stloc.1
0x35a69  ldarg.1
0x35a6a  ldarg.0
0x35a6b  ldloc.0
0x35a6c  ldarg.s  4
0x35a6e  call     bool Microsoft.Crm.Admin.AdminService.UserService::DoesSystemUserOrganizationRecordExist(valuetype [mscorlib]System.Guid crmUserId, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService dbService, valuetype [mscorlib]System.Guid directoryObjectId)
0x35a73  brfalse.s loc_35A9F
0x35a75  ldarg.0
0x35a76  ldc.i4.s 0x48
0x35a78  ldstr    aNoActionUserAu// "No action - User auth records already e"...
0x35a7d  ldarg.1
0x35a7e  box      [mscorlib]System.Guid
0x35a83  ldarg.s  4
0x35a85  box      [mscorlib]System.Guid
0x35a8a  call     string [mscorlib]System.String::Format(string, object, object)
0x35a8f  ldc.i4.0
0x35a90  newarr   [mscorlib]System.Object
0x35a95  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35a9a  leave    loc_35B26
0x35a9f  ldarg.2
0x35aa0  ldloc.0
0x35aa1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UserService::TryGetSystemUserIdFromAuthInfo(string authInfo, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x35aa6  stloc.2
0x35aa7  ldloc.2
0x35aa8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35aad  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x35ab2  brfalse.s loc_35AC4
0x35ab4  ldarg.0
0x35ab5  ldloc.0
0x35ab6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUser(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService config)
0x35abb  stloc.2
0x35abc  ldarg.2
0x35abd  ldloc.2
0x35abe  ldloc.0
0x35abf  call     void Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUserAuthentication(string authInfo, valuetype [mscorlib]System.Guid systemUserId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService config)
0x35ac4  ldarg.0
0x35ac5  ldarg.s  4
0x35ac7  ldarg.s  5
0x35ac9  call     void Microsoft.Crm.Admin.AdminService.UserService::UpdateDirectoryObjectId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid directoryObjectId, valuetype Microsoft.Crm.Admin.AdminService.UserServiceIsToBeAppliedUpdateMode isToBeAppliedUpdateMode)
0x35ace  ldarg.0
0x35acf  ldarg.s  4
0x35ad1  ldloc.2
0x35ad2  ldloc.0
0x35ad3  call     void Microsoft.Crm.Admin.AdminService.UserService::DeleteOrphanSystemUserOrganizations(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid directoryObjectId, valuetype [mscorlib]System.Guid systemUserId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService config)
0x35ad8  ldarg.0
0x35ad9  ldarg.1
0x35ada  ldarg.s  4
0x35adc  ldloc.2
0x35add  ldloc.0
0x35ade  call     void Microsoft.Crm.Admin.AdminService.UserService::CreateSystemUserOrganizations(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmId, valuetype [mscorlib]System.Guid directoryObjectId, valuetype [mscorlib]System.Guid systemUserId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService config)
0x35ae3  ldarg.0
0x35ae4  ldc.i4.s 0x48
0x35ae6  ldstr    aUserAuthRecord// "User auth records created in ConfigDB. "...
0x35aeb  ldarg.1
0x35aec  box      [mscorlib]System.Guid
0x35af1  ldarg.s  4
0x35af3  box      [mscorlib]System.Guid
0x35af8  call     string [mscorlib]System.String::Format(string, object, object)
0x35afd  ldc.i4.0
0x35afe  newarr   [mscorlib]System.Object
0x35b03  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35b08  leave.s  loc_35B1E
0x35b0a  ldloc.1
0x35b0b  brfalse.s loc_35B13
0x35b0d  ldloc.1
0x35b0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35b13  endfinally
0x35b14  ldloc.0
0x35b15  brfalse.s loc_35B1D
0x35b17  ldloc.0
0x35b18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35b1d  endfinally
0x35b1e  ldarg.2
0x35b1f  ldarg.0
0x35b20  ldarg.3
0x35b21  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::FlushLocatorCacheForUserMembershipChange(string, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x35b26  ret
```
