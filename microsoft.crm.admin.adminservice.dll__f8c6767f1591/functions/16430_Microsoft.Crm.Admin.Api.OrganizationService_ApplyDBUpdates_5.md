# Microsoft.Crm.Admin.Api.OrganizationService::ApplyDBUpdates_5

- ea: `0x16430`
- end: `0x165df`
- name: `Microsoft.Crm.Admin.Api.OrganizationService::ApplyDBUpdates_5`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x16410`
- `0x16420`

## callees

- `0x16430`

## string_xrefs

- `0x165aa`: `D:\a\1\s\src\CrmLive\Admin\Organization\OrganizationService.cs`
- `0x164ec`: `ApplyDbUpdate-`
- `0x1651f`: `This code path should be reached only for install`
- `0x1654c`: `UPDATE ScaleGroupOrganizationMaintenanceJobs SET NextRunTime = @nextRunTime WHERE OrganizationId = @organizationId AND OperationType = @operationType`
- `0x165a5`: `ApplyDBUpdates`

## pseudocode

```c

```

## disassembly

```asm
0x16430  ldarg.1
0x16431  ldstr    aOrganizationid// "organizationId"
0x16436  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1643b  ldarg.2
0x1643c  ldarg.3
0x1643d  or
0x1643e  brfalse  loc_1651B
0x16443  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::.ctor()
0x16448  stloc.0
0x16449  ldloc.0
0x1644a  ldarg.1
0x1644b  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x16450  ldloc.0
0x16451  ldarg.3
0x16452  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::set_Uninstall(bool)
0x16457  ldarg.s  7
0x16459  brfalse.s loc_1647B
0x1645b  ldloc.0
0x1645c  ldarg.s  5
0x1645e  ldnull
0x1645f  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x16464  brtrue.s loc_1646F
0x16466  ldarg.s  5
0x16468  callvirt instance string [mscorlib]System.Object::ToString()
0x1646d  br.s     loc_16474
0x1646f  ldsfld   string [mscorlib]System.String::Empty
0x16474  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::set_UninstallVersion(string)
0x16479  br.s     loc_16483
0x1647b  ldloc.0
0x1647c  ldarg.s  4
0x1647e  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::set_UninstallRevision(int32)
0x16483  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::.ctor()
0x16488  stloc.1
0x16489  ldloc.1
0x1648a  ldloc.0
0x1648b  call     string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::Serialize(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo)
0x16490  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0x16495  ldloc.1
0x16496  ldc.i4.s 0x25
0x16498  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemType(int32)
0x1649d  ldloc.1
0x1649e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x164a3  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x164a8  ldloc.1
0x164a9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x164ae  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_EndTime(valuetype [mscorlib]System.DateTime)
0x164b3  ldloc.1
0x164b4  ldarg.1
0x164b5  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x164ba  ldarg.s  6
0x164bc  brfalse.s loc_164DA
0x164be  ldloc.1
0x164bf  ldarg.s  6
0x164c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x164c6  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ParentItemId(valuetype [mscorlib]System.Guid)
0x164cb  ldloc.1
0x164cc  ldarg.s  6
0x164ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ScaleGroupId()
0x164d3  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x164d8  br.s     loc_164EB
0x164da  ldloc.1
0x164db  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x164e0  ldarg.1
0x164e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x164e6  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x164eb  ldloc.1
0x164ec  ldstr    aApplydbupdate// "ApplyDbUpdate-"
0x164f1  ldloc.1
0x164f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ScaleGroupId()
0x164f7  stloc.2
0x164f8  ldloca.s 2
0x164fa  constrained. [mscorlib]System.Guid
0x16500  callvirt instance string [mscorlib]System.Object::ToString()
0x16505  call     string [mscorlib]System.String::Concat(string, string)
0x1650a  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ResourceName(string)
0x1650f  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::.ctor()
0x16514  ldloc.1
0x16515  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::CreateWaiting(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
0x1651a  ret
0x1651b  ldarg.3
0x1651c  ldc.i4.0
0x1651d  ceq
0x1651f  ldstr    aThisCodePathSh// "This code path should be reached only f"...
0x16524  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x16529  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x1652e  ldarg.1
0x1652f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x16534  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype [mscorlib]System.Guid)
0x16539  stloc.3
0x1653a  ldloc.3
0x1653b  ldc.i4.1
0x1653c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x16541  stloc.s  4
0x16543  ldloc.s  4
0x16545  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1654a  ldloc.s  4
0x1654c  ldstr    aUpdateScalegro// "UPDATE ScaleGroupOrganizationMaintenanc"...
0x16551  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x16556  stloc.s  5
0x16558  ldloc.s  5
0x1655a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1655f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x16564  dup
0x16565  ldstr    aNextruntime// "@nextRunTime"
0x1656a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1656f  box      [mscorlib]System.DateTime
0x16574  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x16579  pop
0x1657a  dup
0x1657b  ldstr    aOrganizationid_1// "@organizationId"
0x16580  ldarg.1
0x16581  box      [mscorlib]System.Guid
0x16586  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1658b  pop
0x1658c  ldstr    aOperationtype// "@operationType"
0x16591  ldc.i4.s 0x2C
0x16593  box      [mscorlib]System.Int32
0x16598  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1659d  pop
0x1659e  ldloc.s  5
0x165a0  ldc.i4   0x2EB
0x165a5  ldstr    aApplydbupdates// "ApplyDBUpdates"
0x165aa  ldstr    aDA1SSrcCrmlive_30// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x165af  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x165b4  pop
0x165b5  leave.s  loc_165D9
0x165b7  ldloc.s  5
0x165b9  brfalse.s loc_165C2
0x165bb  ldloc.s  5
0x165bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x165c2  endfinally
0x165c3  ldloc.s  4
0x165c5  brfalse.s loc_165CE
0x165c7  ldloc.s  4
0x165c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x165ce  endfinally
0x165cf  ldloc.3
0x165d0  brfalse.s loc_165D8
0x165d2  ldloc.3
0x165d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x165d8  endfinally
0x165d9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x165de  ret
```
