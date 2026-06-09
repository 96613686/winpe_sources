# Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RollbackFromFailure

- ea: `0x174f0`
- end: `0x176c3`
- name: `Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RollbackFromFailure`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x170b0`

## callees

- `0x174f0`
- `0x176d0`
- `0x17700`
- `0x17ca0`
- `0x318c0`

## string_xrefs

- `0x174fe`: `Attempting to rollback from mirroring failure`
- `0x17510`: `Skipping rollback, nothing to rollback.`
- `0x1759c`: `Both primary and sync replica exist in availability group {0}; skipping rollback as we have HA failover`
- `0x175b8`: `Error caught trying to get status during rollback. Assuming unhealthy and proceeding with rollback. Error {0}`
- `0x175d5`: `Error caught trying to get status during rollback. Assuming unhealthy and proceeding with rollback`
- `0x175e8`: `Attempting to rollback from mirroring failure. This will remove all the replicas from the AG and drop the primary replica from the AG`
- `0x17683`: `Rollback from mirroring failure complete`
- `0x17691`: `Error occured during rollback, error: {0}`
- `0x176b0`: `Error occured during rollback`

## pseudocode

```c

```

## disassembly

```asm
0x174f0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x174f5  stloc.0
0x174f6  ldloc.0
0x174f7  ldarg.s  4
0x174f9  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x174fe  ldstr    aAttemptingToRo// "Attempting to rollback from mirroring f"...
0x17503  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x17508  ldloc.0
0x17509  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x1750e  brtrue.s loc_1751B
0x17510  ldstr    aSkippingRollba// "Skipping rollback, nothing to rollback."
0x17515  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1751a  ret
0x1751b  nop
0x1751c  ldarg.3
0x1751d  ldloc.0
0x1751e  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x17523  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x17528  ldarg.s  5
0x1752a  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::IsDatabaseInAvailabilityGroup(string, string, string)
0x1752f  brfalse  loc_175B5
0x17534  ldarg.3
0x17535  ldloc.0
0x17536  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x1753b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_SyncReplica()
0x17540  ldarg.s  5
0x17542  call     bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::IsDatabaseInAvailabilityGroup(string, string, string)
0x17547  brfalse.s loc_175B5
0x17549  ldarg.3
0x1754a  ldarg.s  5
0x1754c  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.SqlUtility::GetDatabaseReplicaStatus(string, string)
0x17551  dup
0x17552  ldloc.0
0x17553  ldftn    instance bool <>c__DisplayClass4_0::<RollbackFromFailure>b__0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus databaseStatus)
0x17559  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus, bool>::.ctor(object, native int)
0x1755e  call     T0x2B000085
0x17563  stloc.1
0x17564  ldloc.0
0x17565  ldftn    instance bool <>c__DisplayClass4_0::<RollbackFromFailure>b__1(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus databaseStatus)
0x1756b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus, bool>::.ctor(object, native int)
0x17570  call     T0x2B000085
0x17575  stloc.2
0x17576  ldloc.1
0x17577  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus::get_SynchronizationHealth()
0x1757c  ldstr    aNotHealthy// "NOT_HEALTHY"
0x17581  ldc.i4.5
0x17582  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x17587  brtrue.s loc_175B5
0x17589  ldloc.2
0x1758a  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.DatabaseReplicaStatus::get_SynchronizationHealth()
0x1758f  ldstr    aNotHealthy// "NOT_HEALTHY"
0x17594  ldc.i4.5
0x17595  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1759a  brtrue.s loc_175B5
0x1759c  ldstr    aBothPrimaryAnd// "Both primary and sync replica exist in "...
0x175a1  ldc.i4.1
0x175a2  newarr   [mscorlib]System.Object
0x175a7  dup
0x175a8  ldc.i4.0
0x175a9  ldarg.3
0x175aa  stelem.ref
0x175ab  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x175b0  leave    loc_176C2
0x175b5  leave.s  loc_175E7
0x175b7  stloc.3
0x175b8  ldstr    aErrorCaughtTry// "Error caught trying to get status durin"...
0x175bd  ldc.i4.1
0x175be  newarr   [mscorlib]System.Object
0x175c3  dup
0x175c4  ldc.i4.0
0x175c5  ldloc.3
0x175c6  callvirt instance string [mscorlib]System.Object::ToString()
0x175cb  stelem.ref
0x175cc  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x175d1  ldloc.3
0x175d2  ldarg.2
0x175d3  ldc.i4.s 0xA
0x175d5  ldstr    aErrorCaughtTry_0// "Error caught trying to get status durin"...
0x175da  ldc.i4.0
0x175db  newarr   [mscorlib]System.Object
0x175e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x175e5  leave.s  loc_175E7
0x175e7  nop
0x175e8  ldstr    aAttemptingToRo_0// "Attempting to rollback from mirroring f"...
0x175ed  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x175f2  ldarg.0
0x175f3  ldarg.1
0x175f4  ldarg.2
0x175f5  ldarg.3
0x175f6  ldloc.0
0x175f7  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x175fc  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x17601  ldloc.0
0x17602  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x17607  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica2()
0x1760c  ldarg.s  5
0x1760e  ldc.i4.1
0x1760f  ldc.i4.0
0x17610  call     instance bool Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RemoveReplicaFromAvailabilityGroup(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primaryReplica, string replica, string databaseName, bool forceRemove, bool dropDatabase)
0x17615  pop
0x17616  ldarg.0
0x17617  ldarg.1
0x17618  ldarg.2
0x17619  ldarg.3
0x1761a  ldloc.0
0x1761b  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x17620  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x17625  ldloc.0
0x17626  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x1762b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_AsyncReplica1()
0x17630  ldarg.s  5
0x17632  ldc.i4.1
0x17633  ldc.i4.0
0x17634  call     instance bool Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RemoveReplicaFromAvailabilityGroup(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primaryReplica, string replica, string databaseName, bool forceRemove, bool dropDatabase)
0x17639  pop
0x1763a  ldarg.0
0x1763b  ldarg.1
0x1763c  ldarg.2
0x1763d  ldarg.3
0x1763e  ldloc.0
0x1763f  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x17644  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x17649  ldloc.0
0x1764a  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x1764f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_SyncReplica()
0x17654  ldarg.s  5
0x17656  ldc.i4.1
0x17657  ldc.i4.0
0x17658  call     instance bool Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RemoveReplicaFromAvailabilityGroup(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid organizationId, string availabilityGroupName, string primaryReplica, string replica, string databaseName, bool forceRemove, bool dropDatabase)
0x1765d  pop
0x1765e  ldarg.0
0x1765f  ldarg.3
0x17660  ldloc.0
0x17661  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x17666  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus::get_PrimaryReplica()
0x1766b  ldarg.s  5
0x1766d  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::RemovePrimaryFromAvailabilityGroup(string availabilityGroupName, string primaryReplica, string databaseName)
0x17672  ldarg.s  6
0x17674  brfalse.s loc_17683
0x17676  ldarg.0
0x17677  ldloc.0
0x17678  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus <>c__DisplayClass4_0::status
0x1767d  ldarg.2
0x1767e  call     instance void Microsoft.Crm.CrmLive.Provisioning.SetupOrgDBMirroringExecutor::UpdateCrmConfigurationForRollback(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ReplicaStatus replicaStatus, valuetype [mscorlib]System.Guid organizationId)
0x17683  ldstr    aRollbackFromMi// "Rollback from mirroring failure complet"...
0x17688  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1768d  leave.s  loc_176C2
0x1768f  stloc.s  4
0x17691  ldstr    aErrorOccuredDu// "Error occured during rollback, error: {"...
0x17696  ldc.i4.1
0x17697  newarr   [mscorlib]System.Object
0x1769c  dup
0x1769d  ldc.i4.0
0x1769e  ldloc.s  4
0x176a0  callvirt instance string [mscorlib]System.Object::ToString()
0x176a5  stelem.ref
0x176a6  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x176ab  ldloc.s  4
0x176ad  ldarg.2
0x176ae  ldc.i4.s 0xA
0x176b0  ldstr    aErrorOccuredDu_0// "Error occured during rollback"
0x176b5  ldc.i4.0
0x176b6  newarr   [mscorlib]System.Object
0x176bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x176c0  leave.s  loc_176C2
0x176c2  ret
```
