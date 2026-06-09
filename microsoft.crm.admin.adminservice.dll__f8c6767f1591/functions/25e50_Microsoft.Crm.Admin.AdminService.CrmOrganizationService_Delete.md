# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Delete

- ea: `0x25e50`
- end: `0x25fab`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Delete`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x17850`
- `0x25e50`
- `0x26580`
- `0x269f0`
- `0x276a0`
- `0x280e0`
- `0x28190`
- `0x28210`
- `0x282b0`
- `0x2a250`
- `0x2a260`
- `0x2a2e0`

## string_xrefs

- `0x25f03`: `Delete`
- `0x25f08`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x25f21`: `Deleted Organization, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x25e50  ldarg.1
0x25e51  ldc.i4.s 0x14
0x25e53  ldstr    aDeletingOrgani// "Deleting Organization, Id=({0})"
0x25e58  ldc.i4.1
0x25e59  newarr   [mscorlib]System.Object
0x25e5e  dup
0x25e5f  ldc.i4.0
0x25e60  ldarg.1
0x25e61  box      [mscorlib]System.Guid
0x25e66  stelem.ref
0x25e67  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25e6c  ldarg.1
0x25e6d  ldstr    aOrganizationId_1// "Organization identifier"
0x25e72  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x25e77  ldarg.0
0x25e78  ldarg.1
0x25e79  call     instance class Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid organizationId)
0x25e7e  pop
0x25e7f  ldc.i4.2
0x25e80  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x25e85  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x25e8a  ceq
0x25e8c  stloc.0
0x25e8d  ldarg.0
0x25e8e  ldarg.1
0x25e8f  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetState(valuetype [mscorlib]System.Guid organizationId)
0x25e94  stloc.1
0x25e95  ldc.i4.1
0x25e96  ldloc.1
0x25e97  bne.un.s loc_25EB0
0x25e99  ldstr    aOrganization// "Organization"
0x25e9e  ldarg.1
0x25e9f  box      [mscorlib]System.Guid
0x25ea4  ldloc.1
0x25ea5  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0x25eaa  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCannotDeleteObjectDueState(string objectType, object value, class [mscorlib]System.Enum state)
0x25eaf  throw
0x25eb0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x25eb5  stloc.2
0x25eb6  ldarg.1
0x25eb7  ldloc.2
0x25eb8  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationFeatures(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService cfg)
0x25ebd  ldarg.1
0x25ebe  ldloc.2
0x25ebf  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationUsers(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService cfg)
0x25ec4  call     class Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::NewService()
0x25ec9  stloc.3
0x25eca  ldloc.0
0x25ecb  brfalse.s loc_25EEB
0x25ecd  ldarg.1
0x25ece  ldloc.2
0x25ecf  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteEndUserNotifications(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService cfg)
0x25ed4  ldarg.1
0x25ed5  ldloc.2
0x25ed6  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationUpgradeSchedule(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService cfg)
0x25edb  ldloc.3
0x25edc  ldarg.1
0x25edd  ldarg.0
0x25ede  ldarg.1
0x25edf  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetDatacenterId(valuetype [mscorlib]System.Guid organizationId)
0x25ee4  callvirt instance void Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::DeleteJobs(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid datacenterId)
0x25ee9  br.s     loc_25EF2
0x25eeb  ldloc.3
0x25eec  ldarg.1
0x25eed  callvirt instance void Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::DeleteJobs(valuetype [mscorlib]System.Guid organizationId)
0x25ef2  ldloc.2
0x25ef3  ldstr    aOrganization// "Organization"
0x25ef8  ldarg.1
0x25ef9  box      [mscorlib]System.Guid
0x25efe  ldc.i4   0x137
0x25f03  ldstr    aDelete// "Delete"
0x25f08  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x25f0d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string, object, int32, string, string)
0x25f12  leave.s  loc_25F1E
0x25f14  ldloc.2
0x25f15  brfalse.s loc_25F1D
0x25f17  ldloc.2
0x25f18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25f1d  endfinally
0x25f1e  ldarg.1
0x25f1f  ldc.i4.s 0x14
0x25f21  ldstr    aDeletedOrganiz// "Deleted Organization, Id=({0})"
0x25f26  ldc.i4.1
0x25f27  newarr   [mscorlib]System.Object
0x25f2c  dup
0x25f2d  ldc.i4.0
0x25f2e  ldarg.1
0x25f2f  box      [mscorlib]System.Guid
0x25f34  stelem.ref
0x25f35  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25f3a  ldc.i4.s 0x20
0x25f3c  ldarga.s 1
0x25f3e  ldstr    aB// "B"
0x25f43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25f48  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x25f4d  ldarg.1
0x25f4e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x25f53  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25f58  ldarg.1
0x25f59  ldc.i4.s 0x14
0x25f5b  ldstr    aFiredNotificat// "Fired Notification: {0} For Organizatio"...
0x25f60  ldc.i4.2
0x25f61  newarr   [mscorlib]System.Object
0x25f66  dup
0x25f67  ldc.i4.0
0x25f68  ldc.i4.s 0x20
0x25f6a  box      [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0x25f6f  stelem.ref
0x25f70  dup
0x25f71  ldc.i4.1
0x25f72  ldarg.1
0x25f73  box      [mscorlib]System.Guid
0x25f78  stelem.ref
0x25f79  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25f7e  leave.s  loc_25FAA
0x25f80  stloc.s  4
0x25f82  ldarg.1
0x25f83  ldc.i4.s 0x14
0x25f85  ldstr    aExceptionDelet_7// "Exception deleting Organization, Id=({0"...
0x25f8a  ldc.i4.2
0x25f8b  newarr   [mscorlib]System.Object
0x25f90  dup
0x25f91  ldc.i4.0
0x25f92  ldarg.1
0x25f93  box      [mscorlib]System.Guid
0x25f98  stelem.ref
0x25f99  dup
0x25f9a  ldc.i4.1
0x25f9b  ldloc.s  4
0x25f9d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x25fa2  stelem.ref
0x25fa3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25fa8  rethrow
0x25faa  ret
```
