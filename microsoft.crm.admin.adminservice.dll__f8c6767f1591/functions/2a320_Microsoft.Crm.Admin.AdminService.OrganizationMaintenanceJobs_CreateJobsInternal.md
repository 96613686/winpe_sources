# Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::CreateJobsInternal

- ea: `0x2a320`
- end: `0x2aa62`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::CreateJobsInternal`
- size: `1858`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a310`
- `0x2ac30`

## callees

- `0x27a80`
- `0x28380`
- `0x2a320`
- `0x2ab00`
- `0x2b6f0`
- `0x2b780`
- `0x2bbc0`
- `0x2bbe0`

## string_xrefs

- `0x2a324`: `NOT AN ERROR: Creating SG org maintenance jobs for org {0}. updateJobIfExists = {1}`
- `0x2a349`: `CreateOrganizationDbMaintenanceJobs`
- `0x2a3ce`: `DeletionServiceRecurrence`
- `0x2a3df`: `DeletionServiceRecurrence`
- `0x2a5fa`: `CheckForLanguagePackUpdatesRecurrence`
- `0x2a60b`: `CheckForLanguagePackUpdatesRecurrence`
- `0x2a8b7`: `OrgDBUpdateRecurrence`
- `0x2a8c8`: `OrgDBUpdateRecurrence`
- `0x2a91a`: `SolutionUpdateRecurrence`
- `0x2a92b`: `SolutionUpdateRecurrence`
- `0x2a97d`: `SnapshotIsolationUpdateRecurrence`
- `0x2a98e`: `SnapshotIsolationUpdateRecurrence`
- `0x2a9e0`: `ReadCommittedSnapshotIsolationUpdateRecurrence`
- `0x2a9f1`: `ReadCommittedSnapshotIsolationUpdateRecurrence`
- `0x2aa45`: `Exception in CreateOrganizationDbMaintenanceJobs {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2a320  ldnull
0x2a321  ldarg.1
0x2a322  ldc.i4.s 0x14
0x2a324  ldstr    aNotAnErrorCrea// "NOT AN ERROR: Creating SG org maintenan"...
0x2a329  ldarg.1
0x2a32a  box      [mscorlib]System.Guid
0x2a32f  ldarg.s  4
0x2a331  box      [mscorlib]System.Boolean
0x2a336  call     string [mscorlib]System.String::Format(string, object, object)
0x2a33b  ldc.i4.0
0x2a33c  newarr   [mscorlib]System.Object
0x2a341  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a346  ldarg.1
0x2a347  ldc.i4.s 0x14
0x2a349  ldstr    aCreateorganiza_2// "CreateOrganizationDbMaintenanceJobs"
0x2a34e  ldc.i4.0
0x2a34f  newarr   [mscorlib]System.Object
0x2a354  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a359  ldloca.s 0
0x2a35b  ldloca.s 1
0x2a35d  ldarg.2
0x2a35e  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::RetrieveMaintenanceWindowStartAndEndTime([out] valuetype [mscorlib]System.DateTime& maintenanceWindowStartTime, [out] valuetype [mscorlib]System.DateTime& maintenanceWindowEndTime, valuetype [mscorlib]System.Guid scaleGroupId)
0x2a363  ldarg.1
0x2a364  ldarg.2
0x2a365  ldarg.3
0x2a366  call     class [System.Data]System.Data.IDbConnection Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::RetrieveDatabaseConnection(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.Guid datacenterId)
0x2a36b  stloc.2
0x2a36c  ldloc.2
0x2a36d  callvirt instance void [System.Data]System.Data.IDbConnection::Open()
0x2a372  ldc.r8   1.0
0x2a37b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromDays(float64)
0x2a380  stloc.s  0xE
0x2a382  ldloca.s 0xE
0x2a384  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x2a389  conv.i4
0x2a38a  stloc.3
0x2a38b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2a390  stloc.s  0xF
0x2a392  ldloca.s 0xF
0x2a394  call     instance int32 [mscorlib]System.DateTime::get_Millisecond()
0x2a399  newobj   instance void [mscorlib]System.Random::.ctor(int32)
0x2a39e  ldloc.3
0x2a39f  callvirt instance int32 [mscorlib]System.Random::Next(int32)
0x2a3a4  stloc.s  4
0x2a3a6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2a3ab  stloc.s  0xF
0x2a3ad  ldloca.s 0xF
0x2a3af  ldloc.3
0x2a3b0  ldloc.s  4
0x2a3b2  add
0x2a3b3  conv.r8
0x2a3b4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x2a3b9  stloc.s  5
0x2a3bb  ldarg.2
0x2a3bc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a3c1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a3c6  brtrue.s loc_2A3DA
0x2a3c8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a3cd  ldarg.2
0x2a3ce  ldstr    aDeletionservic// "DeletionServiceRecurrence"
0x2a3d3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a3d8  br.s     loc_2A3E9
0x2a3da  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a3df  ldstr    aDeletionservic// "DeletionServiceRecurrence"
0x2a3e4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a3e9  stloc.s  6
0x2a3eb  ldarg.1
0x2a3ec  ldloc.0
0x2a3ed  ldloc.1
0x2a3ee  ldc.i4.s 0xE
0x2a3f0  ldloc.s  5
0x2a3f2  ldloc.s  6
0x2a3f4  brtrue.s loc_2A3FD
0x2a3f6  ldstr    aFreqMinutelyIn// "FREQ=MINUTELY;INTERVAL=1440;"
0x2a3fb  br.s     loc_2A404
0x2a3fd  ldloc.s  6
0x2a3ff  castclass [mscorlib]System.String
0x2a404  ldloc.2
0x2a405  ldarg.s  4
0x2a407  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a40c  ldarg.2
0x2a40d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a412  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a417  brtrue.s loc_2A42B
0x2a419  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a41e  ldarg.2
0x2a41f  ldstr    aIndexmanagemen// "IndexManagementRecurrence"
0x2a424  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a429  br.s     loc_2A43A
0x2a42b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a430  ldstr    aIndexmanagemen// "IndexManagementRecurrence"
0x2a435  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a43a  stloc.s  7
0x2a43c  ldarg.1
0x2a43d  ldloc.0
0x2a43e  ldloc.1
0x2a43f  ldc.i4.s 0xF
0x2a441  ldloca.s 5
0x2a443  ldc.r8   1.0
0x2a44c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x2a451  ldloc.s  7
0x2a453  brtrue.s loc_2A45C
0x2a455  ldstr    aFreqMinutelyIn// "FREQ=MINUTELY;INTERVAL=1440;"
0x2a45a  br.s     loc_2A463
0x2a45c  ldloc.s  7
0x2a45e  castclass [mscorlib]System.String
0x2a463  ldloc.2
0x2a464  ldarg.s  4
0x2a466  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a46b  ldarg.2
0x2a46c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a471  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a476  brtrue.s loc_2A48A
0x2a478  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a47d  ldarg.2
0x2a47e  ldstr    aReindexallrecu// "ReindexAllRecurrence"
0x2a483  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a488  br.s     loc_2A499
0x2a48a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a48f  ldstr    aReindexallrecu// "ReindexAllRecurrence"
0x2a494  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a499  stloc.s  8
0x2a49b  ldarg.1
0x2a49c  ldloc.0
0x2a49d  ldloc.1
0x2a49e  ldc.i4.s 0x1E
0x2a4a0  ldloca.s 5
0x2a4a2  ldc.r8   2.0
0x2a4ab  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x2a4b0  ldloc.s  8
0x2a4b2  brtrue.s loc_2A4BB
0x2a4b4  ldstr    aFreqMinutelyIn// "FREQ=MINUTELY;INTERVAL=1440;"
0x2a4b9  br.s     loc_2A4C2
0x2a4bb  ldloc.s  8
0x2a4bd  castclass [mscorlib]System.String
0x2a4c2  ldloc.2
0x2a4c3  ldarg.s  4
0x2a4c5  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a4ca  ldarg.2
0x2a4cb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a4d0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a4d5  brtrue.s loc_2A4E9
0x2a4d7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a4dc  ldarg.2
0x2a4dd  ldstr    aCheckfulltexti// "CheckFullTextIndexColumnStatusRecurrenc"...
0x2a4e2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a4e7  br.s     loc_2A4F8
0x2a4e9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a4ee  ldstr    aCheckfulltexti// "CheckFullTextIndexColumnStatusRecurrenc"...
0x2a4f3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a4f8  stloc.s  9
0x2a4fa  ldarg.1
0x2a4fb  ldloc.0
0x2a4fc  ldloc.1
0x2a4fd  ldc.i4.s 0x3D
0x2a4ff  ldloca.s 5
0x2a501  ldc.r8   3.0
0x2a50a  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x2a50f  ldloc.s  9
0x2a511  brtrue.s loc_2A51A
0x2a513  ldstr    aFreqMinutelyIn_0// "FREQ=MINUTELY;INTERVAL=360;"
0x2a518  br.s     loc_2A521
0x2a51a  ldloc.s  9
0x2a51c  castclass [mscorlib]System.String
0x2a521  ldloc.2
0x2a522  ldarg.s  4
0x2a524  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a529  ldarg.2
0x2a52a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a52f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a534  brtrue.s loc_2A548
0x2a536  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a53b  ldarg.2
0x2a53c  ldstr    aCleanupinactiv// "CleanupInactiveWorkflowAssembliesRecurr"...
0x2a541  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a546  br.s     loc_2A557
0x2a548  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a54d  ldstr    aCleanupinactiv// "CleanupInactiveWorkflowAssembliesRecurr"...
0x2a552  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a557  stloc.s  0xA
0x2a559  ldarg.1
0x2a55a  ldloc.0
0x2a55b  ldloc.1
0x2a55c  ldc.i4.s 0x20
0x2a55e  ldloca.s 5
0x2a560  ldc.r8   4.0
0x2a569  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x2a56e  ldloc.s  0xA
0x2a570  brtrue.s loc_2A579
0x2a572  ldstr    aFreqMinutelyIn// "FREQ=MINUTELY;INTERVAL=1440;"
0x2a577  br.s     loc_2A580
0x2a579  ldloc.s  0xA
0x2a57b  castclass [mscorlib]System.String
0x2a580  ldloc.2
0x2a581  ldarg.s  4
0x2a583  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a588  ldarg.2
0x2a589  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a58e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a593  brtrue.s loc_2A5A7
0x2a595  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a59a  ldarg.2
0x2a59b  ldstr    aAuditpartition// "AuditPartitionCreationRecurrence"
0x2a5a0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a5a5  br.s     loc_2A5B6
0x2a5a7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a5ac  ldstr    aAuditpartition// "AuditPartitionCreationRecurrence"
0x2a5b1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a5b6  stloc.s  0xB
0x2a5b8  ldarg.1
0x2a5b9  ldloc.0
0x2a5ba  ldloc.1
0x2a5bb  ldc.i4.s 0x29
0x2a5bd  ldloca.s 5
0x2a5bf  ldc.r8   6.0
0x2a5c8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x2a5cd  ldloc.s  0xB
0x2a5cf  brtrue.s loc_2A5D8
0x2a5d1  ldstr    aFreqMinutelyIn// "FREQ=MINUTELY;INTERVAL=1440;"
0x2a5d6  br.s     loc_2A5DF
0x2a5d8  ldloc.s  0xB
0x2a5da  castclass [mscorlib]System.String
0x2a5df  ldloc.2
0x2a5e0  ldarg.s  4
0x2a5e2  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a5e7  ldarg.2
0x2a5e8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a5ed  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a5f2  brtrue.s loc_2A606
0x2a5f4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a5f9  ldarg.2
0x2a5fa  ldstr    aCheckforlangua// "CheckForLanguagePackUpdatesRecurrence"
0x2a5ff  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a604  br.s     loc_2A615
0x2a606  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a60b  ldstr    aCheckforlangua// "CheckForLanguagePackUpdatesRecurrence"
0x2a610  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a615  stloc.s  0xC
0x2a617  ldarg.1
0x2a618  ldloc.0
0x2a619  ldloc.1
0x2a61a  ldc.i4.s 0x2A
0x2a61c  ldloca.s 5
0x2a61e  ldc.r8   8.0
0x2a627  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x2a62c  ldloc.s  0xC
0x2a62e  brtrue.s loc_2A637
0x2a630  ldstr    aFreqMinutelyIn_1// "FREQ=MINUTELY;INTERVAL=1440"
0x2a635  br.s     loc_2A63E
0x2a637  ldloc.s  0xC
0x2a639  castclass [mscorlib]System.String
0x2a63e  ldloc.2
0x2a63f  ldarg.s  4
0x2a641  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a646  ldarg.1
0x2a647  ldarg.2
0x2a648  ldloc.0
0x2a649  ldloc.1
0x2a64a  ldloc.2
0x2a64b  ldarg.s  4
0x2a64d  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::CreateRetrieveMultipleOptimizationSnapshotMaintenanceJobs(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.DateTime maintenanceWindowStartTime, valuetype [mscorlib]System.DateTime maintenanceWindowEndTime, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a652  ldarg.2
0x2a653  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a658  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a65d  brtrue.s loc_2A671
0x2a65f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a664  ldarg.2
0x2a665  ldstr    aOptinfcborgsyn// "OptInFcbOrgSyncRecurrence"
0x2a66a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(valuetype [mscorlib]System.Guid, string)
0x2a66f  br.s     loc_2A680
0x2a671  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2a676  ldstr    aOptinfcborgsyn// "OptInFcbOrgSyncRecurrence"
0x2a67b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x2a680  stloc.s  0xD
0x2a682  ldarg.1
0x2a683  ldloc.0
0x2a684  ldloc.1
0x2a685  ldc.i4.s 0x30
0x2a687  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x2a68c  stloc.s  0xF
0x2a68e  ldloca.s 0xF
0x2a690  ldc.i4.m1
0x2a691  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x2a696  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2a69b  ldloc.s  0xD
0x2a69d  brtrue.s loc_2A6A6
0x2a69f  ldstr    aFreqYearlyInte// "FREQ=YEARLY;INTERVAL=10;"
0x2a6a4  br.s     loc_2A6AD
0x2a6a6  ldloc.s  0xD
0x2a6a8  castclass [mscorlib]System.String
0x2a6ad  ldloc.2
0x2a6ae  ldarg.s  4
0x2a6b0  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::InsertJob(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime windowStartTime, valuetype [mscorlib]System.DateTime windowEndTime, int32 asyncOperationType, valuetype [mscorlib]System.DateTime nextRuntime, valuetype [mscorlib]System.DateTime recurrenceStartTime, string recurrencePattern, class [System.Data]System.Data.IDbConnection connection, [opt] bool updateJobIfExists)
0x2a6b5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2a6ba  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2a6bf  ldc.i4.2
0x2a6c0  bne.un   loc_2AA30
0x2a6c5  ldarg.1
0x2a6c6  call     bool Microsoft.Crm.Admin.AdminService.CrmOrganizationService::IsBackedByXdb(valuetype [mscorlib]System.Guid organizationId)
0x2a6cb  brtrue   loc_2A7D8
  ... truncated ...
```
