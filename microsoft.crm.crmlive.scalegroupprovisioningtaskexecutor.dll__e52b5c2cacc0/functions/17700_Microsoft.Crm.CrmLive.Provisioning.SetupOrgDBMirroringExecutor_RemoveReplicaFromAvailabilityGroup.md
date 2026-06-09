# Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RemoveReplicaFromAvailabilityGroup

- ea: `0x17700`
- end: `0x178d5`
- name: `Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RemoveReplicaFromAvailabilityGroup`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x174f0`
- `0x17ad0`

## callees

- `0x17700`
- `0x178e0`
- `0x17d90`
- `0x31920`

## string_xrefs

- `0x17723`: `RemoveReplicaFromAvailabilityGroup: Primary: {0} Replica: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x17700  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x17705  stloc.0
0x17706  ldloc.0
0x17707  ldarg.s  5
0x17709  stfld    string <>c__DisplayClass6_0::replica
0x1770e  ldarg.3
0x1770f  ldarg.s  4
0x17711  ldarg.s  6
0x17713  ldloc.0
0x17714  ldfld    string <>c__DisplayClass6_0::replica
0x17719  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::DoesDatabaseReplicaExist(string, string, string, string)
0x1771e  brfalse  loc_17829
0x17723  ldstr    aRemovereplicaf// "RemoveReplicaFromAvailabilityGroup: Pri"...
0x17728  ldc.i4.2
0x17729  newarr   [mscorlib]System.Object
0x1772e  dup
0x1772f  ldc.i4.0
0x17730  ldarg.s  4
0x17732  stelem.ref
0x17733  dup
0x17734  ldc.i4.1
0x17735  ldloc.0
0x17736  ldfld    string <>c__DisplayClass6_0::replica
0x1773b  stelem.ref
0x1773c  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17741  ldstr    aGettingDatabas// "getting database replica status for dat"...
0x17746  ldc.i4.1
0x17747  newarr   [mscorlib]System.Object
0x1774c  dup
0x1774d  ldc.i4.0
0x1774e  ldarg.s  6
0x17750  stelem.ref
0x17751  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17756  ldarg.3
0x17757  ldarg.s  6
0x17759  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::GetDatabaseReplicaStatus(string, string)
0x1775e  ldloc.0
0x1775f  ldftn    instance bool <>c__DisplayClass6_0::<RemoveReplicaFromAvailabilityGroup>b__0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus databaseStatus)
0x17765  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus, bool>::.ctor(object, native int)
0x1776a  call     T0x2B000085
0x1776f  stloc.1
0x17770  ldarg.s  7
0x17772  brtrue.s loc_17789
0x17774  ldloc.1
0x17775  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus::get_SynchronizationHealth()
0x1777a  ldstr    aNotHealthy// "NOT_HEALTHY"
0x1777f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17784  brfalse  loc_17809
0x17789  ldarg.s  7
0x1778b  brfalse.s loc_177AD
0x1778d  ldstr    aForceRemovalSe// "Force removal set to true, removing dat"...
0x17792  ldc.i4.2
0x17793  newarr   [mscorlib]System.Object
0x17798  dup
0x17799  ldc.i4.0
0x1779a  ldarg.s  6
0x1779c  stelem.ref
0x1779d  dup
0x1779e  ldc.i4.1
0x1779f  ldloc.0
0x177a0  ldfld    string <>c__DisplayClass6_0::replica
0x177a5  stelem.ref
0x177a6  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x177ab  br.s     loc_177CB
0x177ad  ldstr    aDatabase0IsNot// "database {0} is not healthy on replica "...
0x177b2  ldc.i4.2
0x177b3  newarr   [mscorlib]System.Object
0x177b8  dup
0x177b9  ldc.i4.0
0x177ba  ldarg.s  6
0x177bc  stelem.ref
0x177bd  dup
0x177be  ldc.i4.1
0x177bf  ldloc.0
0x177c0  ldfld    string <>c__DisplayClass6_0::replica
0x177c5  stelem.ref
0x177c6  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x177cb  ldstr    aRemovingDataba// "Removing database {0} on replica {1} "
0x177d0  ldc.i4.2
0x177d1  newarr   [mscorlib]System.Object
0x177d6  dup
0x177d7  ldc.i4.0
0x177d8  ldarg.s  6
0x177da  stelem.ref
0x177db  dup
0x177dc  ldc.i4.1
0x177dd  ldloc.0
0x177de  ldfld    string <>c__DisplayClass6_0::replica
0x177e3  stelem.ref
0x177e4  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x177e9  ldarg.s  6
0x177eb  ldloc.0
0x177ec  ldfld    string <>c__DisplayClass6_0::replica
0x177f1  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::RemoveDatabaseReplica(string, string)
0x177f6  ldarg.0
0x177f7  ldarg.3
0x177f8  ldarg.s  4
0x177fa  ldarg.s  6
0x177fc  ldloc.0
0x177fd  ldfld    string <>c__DisplayClass6_0::replica
0x17802  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::WaitOnDatabaseReplicaRemoval(string availabilityGroupName, string primaryReplica, string databaseName, string replica)
0x17807  br.s     loc_17829
0x17809  ldstr    aDatabase0IsHea// "Database {0} is healthy and exists on r"...
0x1780e  ldc.i4.2
0x1780f  newarr   [mscorlib]System.Object
0x17814  dup
0x17815  ldc.i4.0
0x17816  ldarg.s  6
0x17818  stelem.ref
0x17819  dup
0x1781a  ldc.i4.1
0x1781b  ldloc.0
0x1781c  ldfld    string <>c__DisplayClass6_0::replica
0x17821  stelem.ref
0x17822  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x17827  ldc.i4.0
0x17828  ret
0x17829  ldarg.s  8
0x1782b  brfalse  loc_178D3
0x17830  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x17835  ldarg.2
0x17836  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid)
0x1783b  stloc.2
0x1783c  ldloc.2
0x1783d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x17842  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17847  brfalse.s loc_1785A
0x17849  ldstr    aOrganizationDo// "Organization does not have connection s"...
0x1784e  dup
0x1784f  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x17854  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x17859  throw
0x1785a  ldarg.0
0x1785b  ldloc.2
0x1785c  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x17861  call     instance string Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::TryGetDataSource(string connectionString)
0x17866  stloc.3
0x17867  ldloc.3
0x17868  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1786d  brfalse.s loc_17880
0x1786f  ldstr    aOrganizationDo_0// "Organization does not have data source "...
0x17874  dup
0x17875  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1787a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1787f  throw
0x17880  ldarg.3
0x17881  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::GetReplicaStatus(string)
0x17886  stloc.s  4
0x17888  ldloc.0
0x17889  ldfld    string <>c__DisplayClass6_0::replica
0x1788e  ldarg.s  6
0x17890  ldloc.3
0x17891  ldarg.3
0x17892  ldloc.s  4
0x17894  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::SqlDropDatabaseReplica(string, string, string, string, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus)
0x17899  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x1789e  ldarg.1
0x1789f  ldstr    aQueueitem// "QueueItem"
0x178a4  ldstr    aDropdatabase// "DropDatabase"
0x178a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x178ae  ldstr    aDatabase0Dropp// "Database {0} dropped successfully from "...
0x178b3  ldc.i4.2
0x178b4  newarr   [mscorlib]System.Object
0x178b9  dup
0x178ba  ldc.i4.0
0x178bb  ldarg.s  6
0x178bd  stelem.ref
0x178be  dup
0x178bf  ldc.i4.1
0x178c0  ldloc.0
0x178c1  ldfld    string <>c__DisplayClass6_0::replica
0x178c6  stelem.ref
0x178c7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x178cc  ldc.i4.1
0x178cd  ldarg.2
0x178ce  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x178d3  ldc.i4.1
0x178d4  ret
```
