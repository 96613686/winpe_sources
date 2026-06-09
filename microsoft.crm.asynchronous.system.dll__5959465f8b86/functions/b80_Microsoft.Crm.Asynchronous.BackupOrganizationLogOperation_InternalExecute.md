# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::InternalExecute

- ea: `0xb80`
- end: `0x122e`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::InternalExecute`
- size: `1710`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb80`
- `0x1230`
- `0x12a0`
- `0x12c0`
- `0x13a0`
- `0x13f0`
- `0x1460`
- `0x14c0`
- `0x15c0`
- `0x15d0`
- `0x16e0`
- `0xd6a0`
- `0xd6b0`
- `0xd6f0`
- `0xd730`
- `0xd790`
- `0xd7f0`
- `0xd850`
- `0xd8b0`
- `0xd910`
- `0xd980`
- `0xd9e0`
- `0xda30`
- `0xda70`
- `0xdad0`
- `0xdb40`
- `0xdba0`
- `0xdc00`
- `0xdc60`
- `0xdcc0`
- `0xdd20`

## string_xrefs

- `0xea3`: `Error creating backup for Organization: {0}; SQL Server: {1}; Service Account: {2}, message: {3}`
- `0x10c3`: `_MANIFEST.XML`
- `0x1163`: `Error creating backup manifest for Organization: {0}; SQL Server: {1}; message: {2}`

## pseudocode

```c

```

## disassembly

```asm
0xb80  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0xb85  ldarg.1
0xb86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xb8b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid)
0xb90  stloc.0
0xb91  ldloc.0
0xb92  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseMirroringSetupInProgress()
0xb97  brfalse.s loc_BAF
0xb99  ldstr    aDatabaseMirror// "Database Mirroring Setup is In Progress"...
0xb9e  ldarg.1
0xb9f  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0xba4  call     string [mscorlib]System.String::Format(string, object)
0xba9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSkippedResult::.ctor(string)
0xbae  ret
0xbaf  ldloc.0
0xbb0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_IsBackedByXdb()
0xbb5  stloc.3
0xbb6  ldc.i4.1
0xbb7  stloc.s  4
0xbb9  ldloca.s 3
0xbbb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0xbc0  ldloc.s  4
0xbc2  beq.s    loc_BC7
0xbc4  ldc.i4.0
0xbc5  br.s     loc_BCE
0xbc7  ldloca.s 3
0xbc9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xbce  brfalse.s loc_BE6
0xbd0  ldstr    aDatabaseBackup// "Database backup is not supported becaus"...
0xbd5  ldarg.1
0xbd6  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0xbdb  call     string [mscorlib]System.String::Format(string, object)
0xbe0  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSkippedResult::.ctor(string)
0xbe5  ret
0xbe6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xbeb  stloc.1
0xbec  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0xbf1  stloc.2
0xbf2  ldloc.2
0xbf3  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xbf8  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xbfd  ldloc.1
0xbfe  ldarg.1
0xbff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc04  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::BackupJobStart(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.Guid organizationId)
0xc09  ldarg.1
0xc0a  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xc0f  ldc.i4.s 0x1A
0xc11  ceq
0xc13  ldstr    aOperationTypeM_0// "Operation type must be 'DatabaseLogBack"...
0xc18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xc1d  ldarg.1
0xc1e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc23  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc28  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc2d  ldstr    aOperationMustH// "Operation must have an Organization ID"
0xc32  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xc37  ldsfld   string [mscorlib]System.String::Empty
0xc3c  stloc.s  5
0xc3e  ldnull
0xc3f  stloc.s  6
0xc41  ldnull
0xc42  stloc.s  7
0xc44  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc49  stloc.s  9
0xc4b  ldarg.1
0xc4c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc51  call     bool Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::AllowCreateSystemRestorePoints(valuetype [mscorlib]System.Guid organizationId)
0xc56  stloc.s  0xA
0xc58  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xc5d  stloc.s  0xB
0xc5f  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xc64  ldloc.1
0xc65  ldarg.1
0xc66  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc6b  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CleanUpAndBackupStart(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.Guid organizationId)
0xc70  ldarg.1
0xc71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc76  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility::RetrieveSqlServerName(valuetype [mscorlib]System.Guid)
0xc7b  stloc.s  5
0xc7d  ldarg.0
0xc7e  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::InitializeSettings()
0xc83  ldarg.0
0xc84  ldarg.1
0xc85  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc8a  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::_orgId
0xc8f  ldarg.0
0xc90  ldarg.1
0xc91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xc96  call     instance string Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::GenerateBackupPath(valuetype [mscorlib]System.Guid orgId)
0xc9b  stloc.s  7
0xc9d  ldc.i4.0
0xc9e  stloc.s  0xE
0xca0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xca5  stloc.s  0x13
0xca7  ldloca.s 0x13
0xca9  ldarg.0
0xcaa  ldfld    int32 Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::_backupExpirationInDays
0xcaf  ldc.i4.m1
0xcb0  mul
0xcb1  conv.r8
0xcb2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xcb7  stloc.s  8
0xcb9  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xcbe  stloc.s  0xF
0xcc0  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xcc5  ldloc.1
0xcc6  ldarg.1
0xcc7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xccc  ldloc.s  7
0xcce  ldloc.s  5
0xcd0  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupStart(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.Guid organizationId, string backupPath, string sqlServerName)
0xcd5  ldloc.0
0xcd6  ldloc.s  5
0xcd8  call     string Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::IsDuplicateBackupInProgressForOrg(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData orgData, string serverName)
0xcdd  stloc.s  0x14
0xcdf  ldloc.s  0x14
0xce1  brfalse.s loc_D12
0xce3  ldloc.s  0xF
0xce5  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xcea  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xcef  ldloc.1
0xcf0  ldloc.s  0xF
0xcf2  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xcf7  ldarg.1
0xcf8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xcfd  ldloc.s  0x14
0xcff  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::FullBackupJobDuplicateFound(valuetype [mscorlib]System.Guid jobSessionId, int64 duration, valuetype [mscorlib]System.Guid organizationId, string message)
0xd04  ldarg.0
0xd05  ldarg.1
0xd06  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::CreateOperationSucceededResult(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0xd0b  stloc.s  0x15
0xd0d  leave    loc_122B
0xd12  leave.s  loc_D31
0xd14  stloc.s  0x16
0xd16  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xd1b  ldloc.1
0xd1c  ldloc.2
0xd1d  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xd22  ldarg.1
0xd23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd28  ldloc.s  0x16
0xd2a  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::BackupJobError(valuetype [mscorlib]System.Guid jobSessionId, int64 duration, valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Exception exception)
0xd2f  leave.s  loc_D31
0xd31  ldarg.0
0xd32  ldloc.s  0xE
0xd34  ldloc.s  7
0xd36  ldarg.1
0xd37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd3c  ldloc.s  5
0xd3e  call     instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::DelegateBackup(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility/DatabaseBackupType backupType, string backupPath, valuetype [mscorlib]System.Guid orgId, string sqlServerName)
0xd43  stloc.s  6
0xd45  ldloc.s  0xF
0xd47  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xd4c  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xd51  ldloc.1
0xd52  ldloc.s  0xF
0xd54  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xd59  ldarg.1
0xd5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd5f  ldloc.s  6
0xd61  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_BackupPathOnShare()
0xd66  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupFinish(valuetype [mscorlib]System.Guid jobSessionId, int64 duration, valuetype [mscorlib]System.Guid organizationId, string fullBackupPath)
0xd6b  ldstr    aRestorefromazu// "RestoreFromAzureStorage"
0xd70  ldarg.1
0xd71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd76  call     bool [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClientHelper::IsGeoFeatureEnabledForOrg(string, valuetype [mscorlib]System.Guid)
0xd7b  stloc.s  0x10
0xd7d  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xd82  stloc.s  0x11
0xd84  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xd89  ldloc.1
0xd8a  ldarg.1
0xd8b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd90  ldloc.s  8
0xd92  ldloc.s  7
0xd94  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CleanUpBackupsStart(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime expirationDate, string backupPath)
0xd99  ldloc.s  7
0xd9b  ldloc.s  8
0xd9d  ldc.i4.1
0xd9e  ldarg.1
0xd9f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xda4  ldloc.s  0x10
0xda6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility::CleanupBackupFiles(string, valuetype [mscorlib]System.DateTime, bool, valuetype [mscorlib]System.Guid, bool)
0xdab  stloc.s  0x12
0xdad  ldloc.s  0x11
0xdaf  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xdb4  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xdb9  ldloc.1
0xdba  ldloc.s  0x11
0xdbc  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xdc1  ldarg.1
0xdc2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xdc7  ldloc.s  0x12
0xdc9  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CleanUpBackupsFinish(valuetype [mscorlib]System.Guid jobSessionId, int64 duration, valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> deletedFiles)
0xdce  call     bool Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::IsSystemRestorePointsFeatureEnabled()
0xdd3  brfalse.s loc_E28
0xdd5  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xdda  stloc.s  0x17
0xddc  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xde1  ldloc.1
0xde2  ldarg.1
0xde3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xde8  ldloc.s  8
0xdea  ldloc.s  0x12
0xdec  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CleanUpRestorePointsStart(valuetype [mscorlib]System.Guid jobSessionId, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.DateTime expirationDate, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> deletedFiles)
0xdf1  ldarg.1
0xdf2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xdf7  ldloc.s  0x12
0xdf9  ldloc.s  8
0xdfb  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0xe00  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::CleanupRestorePoints(valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0xe05  stloc.s  0x18
0xe07  ldloc.s  0x17
0xe09  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xe0e  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xe13  ldloc.1
0xe14  ldloc.s  0x17
0xe16  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xe1b  ldarg.1
0xe1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xe21  ldloc.s  0x18
0xe23  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CleanUpRestorePointsFinish(valuetype [mscorlib]System.Guid jobSessionId, int64 duration, valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> deletedRestorePoints)
0xe28  ldarg.0
0xe29  ldarg.1
0xe2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xe2f  ldloc.s  0x12
0xe31  ldloc.s  6
0xe33  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::UpdateBackupHistory(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> deletedFiles, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData newBackup)
0xe38  leave    loc_EF9
0xe3d  stloc.s  0x19
0xe3f  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xe44  ldloc.1
0xe45  ldloc.s  0xB
0xe47  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xe4c  ldarg.1
0xe4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xe52  ldloc.s  0x19
0xe54  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::CleanUpAndBackupError(valuetype [mscorlib]System.Guid jobSessionId, int64 duration, valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Exception exception)
0xe59  call     class Microsoft.Crm.Asynchronous.FullBackupEventSource Microsoft.Crm.Asynchronous.FullBackupEventSource::get_Instance()
0xe5e  ldloc.1
0xe5f  ldloc.2
0xe60  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xe65  ldarg.1
0xe66  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xe6b  ldloc.s  0x19
0xe6d  callvirt instance void Microsoft.Crm.Asynchronous.FullBackupEventSource::BackupJobError(valuetype [mscorlib]System.Guid jobSessionId, int64 duration, valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Exception exception)
0xe72  ldnull
0xe73  stloc.s  0x1A
0xe75  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0xe7a  stloc.s  0x1C
0xe7c  ldloc.s  0x1C
0xe7e  brtrue.s loc_E87
0xe80  ldsfld   string [mscorlib]System.String::Empty
0xe85  br.s     loc_E8E
0xe87  ldloc.s  0x1C
0xe89  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0xe8e  stloc.s  0x1A
0xe90  leave.s  loc_E9E
0xe92  ldloc.s  0x1C
0xe94  brfalse.s loc_E9D
0xe96  ldloc.s  0x1C
0xe98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe9d  endfinally
0xe9e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xea3  ldstr    aErrorCreatingB// "Error creating backup for Organization:"...
0xea8  ldc.i4.4
0xea9  newarr   [mscorlib]System.Object
0xeae  dup
0xeaf  ldc.i4.0
0xeb0  ldarg.1
0xeb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xeb6  box      [mscorlib]System.Guid
0xebb  stelem.ref
0xebc  dup
0xebd  ldc.i4.1
0xebe  ldloc.s  5
0xec0  stelem.ref
0xec1  dup
0xec2  ldc.i4.2
0xec3  ldloc.s  0x1A
0xec5  stelem.ref
0xec6  dup
0xec7  ldc.i4.3
0xec8  ldloc.s  0x19
0xeca  stelem.ref
0xecb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xed0  stloc.s  0x1B
0xed2  ldarg.0
0xed3  ldc.i4   0x8000440E
0xed8  conv.u8
0xed9  ldloc.s  0x1B
0xedb  ldarg.1
0xedc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xee1  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::LogError(int64 errorId, string message, valuetype [mscorlib]System.Guid orgId)
0xee6  ldloc.s  0x19
0xee8  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0xeed  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRetryResult::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult)
0xef2  stloc.s  0x15
0xef4  leave    loc_122B
  ... truncated ...
```
