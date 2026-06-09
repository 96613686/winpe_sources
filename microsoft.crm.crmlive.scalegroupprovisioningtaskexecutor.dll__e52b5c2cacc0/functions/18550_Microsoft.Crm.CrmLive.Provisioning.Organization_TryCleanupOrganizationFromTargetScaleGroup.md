# Microsoft.Crm.CrmLive.Provisioning.Organization::TryCleanupOrganizationFromTargetScaleGroup

- ea: `0x18550`
- end: `0x18726`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::TryCleanupOrganizationFromTargetScaleGroup`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x239f0`

## callees

- `0x137a0`
- `0x137b0`
- `0x18550`
- `0x1a190`
- `0x1c250`
- `0x1c3b0`

## string_xrefs

- `0x185f2`: `Failed to create DropXdbDatabase queueitem to delete Xdb organization database {0} , Scalegroup {1} , but ignored. Exception: {2}`
- `0x186f0`: `Failed to delete organization database, but ignored. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x18550  ldarg.0
0x18551  ldstr    aData_1// "data"
0x18556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1855b  ldarg.0
0x1855c  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_MoveSG()
0x18561  brfalse  loc_18725
0x18566  ldarg.0
0x18567  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x1856c  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::TryDeleteOrganizationMaintenanceJobs(valuetype [mscorlib]System.Guid organizationId)
0x18571  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x18576  ldarg.0
0x18577  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_UniqueName()
0x1857c  ldarg.0
0x1857d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x18582  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x18587  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::DeleteReports(string organizationUniqueName, string reportsUri)
0x1858c  ldarg.0
0x1858d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x18592  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::IsBackedByXdb(valuetype [mscorlib]System.Guid)
0x18597  brfalse  loc_18646
0x1859c  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::.ctor()
0x185a1  stloc.0
0x185a2  ldloc.0
0x185a3  ldc.i4.s 0x6D
0x185a5  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemType(int32)
0x185aa  ldloc.0
0x185ab  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseInfo::.ctor()
0x185b0  dup
0x185b1  ldc.i4.1
0x185b2  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.DropXdbDatabaseInfo::set_DropSoftDeletedDatabasesOnly(bool value)
0x185b7  call     T0x2B000089
0x185bc  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0x185c1  ldloc.0
0x185c2  ldarg.0
0x185c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x185c8  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x185cd  ldloc.0
0x185ce  ldarg.0
0x185cf  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x185d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x185d9  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x185de  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::NewRequest()
0x185e3  ldloc.0
0x185e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::CreateReady(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
0x185e9  pop
0x185ea  leave.s  loc_18645
0x185ec  stloc.1
0x185ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x185f2  ldstr    aFailedToCreate// "Failed to create DropXdbDatabase queuei"...
0x185f7  ldc.i4.3
0x185f8  newarr   [mscorlib]System.Object
0x185fd  dup
0x185fe  ldc.i4.0
0x185ff  ldarg.0
0x18600  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x18605  box      [mscorlib]System.Guid
0x1860a  stelem.ref
0x1860b  dup
0x1860c  ldc.i4.1
0x1860d  ldarg.0
0x1860e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x18613  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x18618  box      [mscorlib]System.Guid
0x1861d  stelem.ref
0x1861e  dup
0x1861f  ldc.i4.2
0x18620  ldloc.1
0x18621  stelem.ref
0x18622  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18627  stloc.2
0x18628  ldloc.2
0x18629  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1862e  ldloc.1
0x1862f  ldarg.0
0x18630  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x18635  ldc.i4.s 0xA
0x18637  ldloc.2
0x18638  ldc.i4.0
0x18639  newarr   [mscorlib]System.Object
0x1863e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18643  leave.s  loc_18645
0x18645  ret
0x18646  ldarg.0
0x18647  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1864c  brfalse  loc_18725
0x18651  ldarg.0
0x18652  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x18657  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x1865c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x18661  brtrue   loc_18725
0x18666  ldarg.0
0x18667  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1866c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x18671  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x18676  brtrue   loc_18725
0x1867b  ldarg.0
0x1867c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x18681  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x18686  ldarg.0
0x18687  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x1868c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x18691  call     void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::DropDatabase(string, string)
0x18696  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x1869b  ldarg.0
0x1869c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x186a1  ldstr    aOrganizationId// "Organization.Id"
0x186a6  ldstr    aDropdatabase// "DropDatabase"
0x186ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x186b0  ldstr    aDatabase0Dropp// "Database {0} dropped successfully from "...
0x186b5  ldc.i4.2
0x186b6  newarr   [mscorlib]System.Object
0x186bb  dup
0x186bc  ldc.i4.0
0x186bd  ldarg.0
0x186be  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x186c3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x186c8  stelem.ref
0x186c9  dup
0x186ca  ldc.i4.1
0x186cb  ldarg.0
0x186cc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x186d1  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_PrimaryServer()
0x186d6  stelem.ref
0x186d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x186dc  ldc.i4.1
0x186dd  ldarg.0
0x186de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x186e3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x186e8  leave.s  loc_18725
0x186ea  stloc.3
0x186eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x186f0  ldstr    aFailedToDelete// "Failed to delete organization database,"...
0x186f5  ldc.i4.1
0x186f6  newarr   [mscorlib]System.Object
0x186fb  dup
0x186fc  ldc.i4.0
0x186fd  ldloc.3
0x186fe  stelem.ref
0x186ff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18704  stloc.s  4
0x18706  ldloc.s  4
0x18708  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1870d  ldloc.3
0x1870e  ldarg.0
0x1870f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x18714  ldc.i4.s 0xA
0x18716  ldloc.s  4
0x18718  ldc.i4.0
0x18719  newarr   [mscorlib]System.Object
0x1871e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18723  leave.s  loc_18725
0x18725  ret
```
