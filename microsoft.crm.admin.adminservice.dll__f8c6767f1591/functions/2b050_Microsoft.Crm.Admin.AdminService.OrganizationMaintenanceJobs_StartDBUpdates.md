# Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::StartDBUpdates

- ea: `0x2b050`
- end: `0x2b1e7`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::StartDBUpdates`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ea10`
- `0x2b050`
- `0x2b1f0`
- `0x2dbf0`
- `0x2dc00`

## string_xrefs

- `0x2b0c9`: `UPDATE ScaleGroupOrganizationMaintenanceJobs SET NextRunTime = @nextRunTime WHERE OperationType = @operationType AND NextRunTime > @nextRunTime`
- `0x2b113`: `StartDBUpdates`

## pseudocode

```c

```

## disassembly

```asm
0x2b050  ldarg.1
0x2b051  ldstr    aScalegroupname// "scaleGroupName"
0x2b056  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2b05b  ldarg.2
0x2b05c  ldstr    aDatabasetype_0// "databaseType"
0x2b061  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2b066  ldarg.2
0x2b067  ldstr    aSgorgs// "SGORGS"
0x2b06c  ldc.i4.5
0x2b06d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2b072  brfalse  loc_2B174
0x2b077  ldarg.s  5
0x2b079  brtrue   loc_2B174
0x2b07e  ldarg.1
0x2b07f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RetrieveScaleGroupIdFromName(string scaleGroupName)
0x2b084  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x2b089  stloc.2
0x2b08a  ldloc.2
0x2b08b  ldc.i4.1
0x2b08c  callvirt instance class [System.Data]System.Data.IDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::NewConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x2b091  stloc.3
0x2b092  ldloc.3
0x2b093  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x2b098  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2b09d  stloc.s  4
0x2b09f  ldarg.0
0x2b0a0  ldloc.3
0x2b0a1  ldstr    aSelectCountFro_4// "SELECT count(*) FROM ScaleGroupOrganiza"...
0x2b0a6  ldloc.s  4
0x2b0a8  call     instance int32 Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::ExecuteAndGetCountForOrgDBUpdateCommand(class [System.Data]System.Data.IDbConnection connection, string sqlCommandText, valuetype [mscorlib]System.DateTime nextRunTime)
0x2b0ad  stloc.s  5
0x2b0af  ldarg.0
0x2b0b0  ldloc.3
0x2b0b1  ldstr    aSelectCountFro_5// "SELECT count(*) FROM ScaleGroupOrganiza"...
0x2b0b6  ldloc.s  4
0x2b0b8  call     instance int32 Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::ExecuteAndGetCountForOrgDBUpdateCommand(class [System.Data]System.Data.IDbConnection connection, string sqlCommandText, valuetype [mscorlib]System.DateTime nextRunTime)
0x2b0bd  stloc.s  6
0x2b0bf  ldloc.3
0x2b0c0  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x2b0c5  stloc.s  7
0x2b0c7  ldloc.s  7
0x2b0c9  ldstr    aUpdateScalegro_1// "UPDATE ScaleGroupOrganizationMaintenanc"...
0x2b0ce  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2b0d3  ldloc.s  7
0x2b0d5  ldc.i4.1
0x2b0d6  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x2b0db  ldloc.s  7
0x2b0dd  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2b0e2  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2b0e7  dup
0x2b0e8  ldstr    aNextruntime// "@nextRunTime"
0x2b0ed  ldloc.s  4
0x2b0ef  box      [mscorlib]System.DateTime
0x2b0f4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2b0f9  pop
0x2b0fa  ldstr    aOperationtype// "@operationType"
0x2b0ff  ldc.i4.s 0x2C
0x2b101  box      [mscorlib]System.Int32
0x2b106  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2b10b  pop
0x2b10c  ldloc.s  7
0x2b10e  ldc.i4   0x266
0x2b113  ldstr    aStartdbupdates// "StartDBUpdates"
0x2b118  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2b11d  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x2b122  pop
0x2b123  leave.s  loc_2B131
0x2b125  ldloc.s  7
0x2b127  brfalse.s loc_2B130
0x2b129  ldloc.s  7
0x2b12b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b130  endfinally
0x2b131  call     class Microsoft.Crm.Admin.AdminService.SGOrgMaintenanceEventSource Microsoft.Crm.Admin.AdminService.SGOrgMaintenanceEventSource::get_Instance()
0x2b136  ldarg.1
0x2b137  ldloc.s  4
0x2b139  ldloc.s  5
0x2b13b  ldloc.s  6
0x2b13d  ldarg.2
0x2b13e  ldarg.3
0x2b13f  dup
0x2b140  brtrue.s loc_2B148
0x2b142  pop
0x2b143  ldsfld   string [mscorlib]System.String::Empty
0x2b148  ldarg.s  4
0x2b14a  dup
0x2b14b  brtrue.s loc_2B153
0x2b14d  pop
0x2b14e  ldsfld   string [mscorlib]System.String::Empty
0x2b153  callvirt instance void Microsoft.Crm.Admin.AdminService.SGOrgMaintenanceEventSource::SGDBUpdatesScheduled(string scaleGroupName, valuetype [mscorlib]System.DateTime nextRunTime, int32 orgsAlreadyInQueue, int32 orgsAddedToQueue, string databaseType, string orgStateFilter, string orgMinRevisionFilter)
0x2b158  leave.s  loc_2B16E
0x2b15a  ldloc.3
0x2b15b  brfalse.s loc_2B163
0x2b15d  ldloc.3
0x2b15e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b163  endfinally
0x2b164  ldloc.2
0x2b165  brfalse.s loc_2B16D
0x2b167  ldloc.2
0x2b168  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b16d  endfinally
0x2b16e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2b173  ret
0x2b174  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::.ctor()
0x2b179  stloc.0
0x2b17a  ldloc.0
0x2b17b  ldarg.1
0x2b17c  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::set_ScaleGroupName(string)
0x2b181  ldloc.0
0x2b182  ldarg.2
0x2b183  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::set_DatabaseType(string)
0x2b188  ldloc.0
0x2b189  ldarg.3
0x2b18a  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::set_OrgStateFilter(string)
0x2b18f  ldloc.0
0x2b190  ldarg.s  4
0x2b192  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::set_OrgMinRevisionFilter(string)
0x2b197  ldloc.0
0x2b198  ldarg.s  5
0x2b19a  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::set_Uninstall(bool)
0x2b19f  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::.ctor()
0x2b1a4  stloc.1
0x2b1a5  ldloc.1
0x2b1a6  ldloc.0
0x2b1a7  call     string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::Serialize(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo)
0x2b1ac  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0x2b1b1  ldloc.1
0x2b1b2  ldc.i4.s 0x24
0x2b1b4  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemType(int32)
0x2b1b9  ldloc.1
0x2b1ba  ldarg.1
0x2b1bb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RetrieveScaleGroupIdFromName(string scaleGroupName)
0x2b1c0  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x2b1c5  ldloc.1
0x2b1c6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2b1cb  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_StartTime(valuetype [mscorlib]System.DateTime)
0x2b1d0  ldloc.1
0x2b1d1  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x2b1d6  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_EndTime(valuetype [mscorlib]System.DateTime)
0x2b1db  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::.ctor()
0x2b1e0  ldloc.1
0x2b1e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::CreateReady(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
0x2b1e6  ret
```
