# Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::CreateRestorePointLocations

- ea: `0x3b740`
- end: `0x3b99a`
- name: `Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::CreateRestorePointLocations`
- size: `602`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3b740`
- `0x3c4f0`

## string_xrefs

- `0x3b747`: `Creating a new restore point location: RestorePointId = {0}, OrganizationId = {1}, FileType = {2}, Backup File = {3}, Transaction Log File = {4}, Manifest File = {5}`
- `0x3b870`: `Backup file not accessible: `
- `0x3b8a3`: `FileCreatedOn`
- `0x3b929`: `CreateRestorePointLocations`
- `0x3b95b`: `RestorePoint Location entity created`

## pseudocode

```c

```

## disassembly

```asm
0x3b740  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b745  ldc.i4.s 0x1D
0x3b747  ldstr    aCreatingANewRe_0// "Creating a new restore point location: "...
0x3b74c  ldc.i4.6
0x3b74d  newarr   [mscorlib]System.Object
0x3b752  dup
0x3b753  ldc.i4.0
0x3b754  ldarg.0
0x3b755  box      [mscorlib]System.Guid
0x3b75a  stelem.ref
0x3b75b  dup
0x3b75c  ldc.i4.1
0x3b75d  ldarg.1
0x3b75e  box      [mscorlib]System.Guid
0x3b763  stelem.ref
0x3b764  dup
0x3b765  ldc.i4.2
0x3b766  ldarg.3
0x3b767  box      [Microsoft.Crm.Core]Microsoft.Crm.RestorePointFileType
0x3b76c  stelem.ref
0x3b76d  dup
0x3b76e  ldc.i4.3
0x3b76f  ldarg.2
0x3b770  brtrue.s loc_3B779
0x3b772  ldstr    aNull// "null"
0x3b777  br.s     loc_3B77F
0x3b779  ldarg.2
0x3b77a  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_BackupPathOnShare()
0x3b77f  stelem.ref
0x3b780  dup
0x3b781  ldc.i4.4
0x3b782  ldarg.2
0x3b783  brtrue.s loc_3B78C
0x3b785  ldstr    aNull// "null"
0x3b78a  br.s     loc_3B792
0x3b78c  ldarg.2
0x3b78d  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_LogPathOnShare()
0x3b792  stelem.ref
0x3b793  dup
0x3b794  ldc.i4.5
0x3b795  ldarg.2
0x3b796  brtrue.s loc_3B79F
0x3b798  ldstr    aNull// "null"
0x3b79d  br.s     loc_3B7A5
0x3b79f  ldarg.2
0x3b7a0  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_ManifestPathOnShare()
0x3b7a5  stelem.ref
0x3b7a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b7ab  ldarg.0
0x3b7ac  ldstr    aRestorepointid// "restorePointId"
0x3b7b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3b7b6  ldarg.1
0x3b7b7  ldstr    aOrganizationid// "organizationId"
0x3b7bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3b7c1  ldarg.2
0x3b7c2  ldstr    aBackupdata// "backupData"
0x3b7c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3b7cc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3b7d1  stloc.0
0x3b7d2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3b7d7  stloc.1
0x3b7d8  ldnull
0x3b7d9  stloc.2
0x3b7da  ldarg.3
0x3b7db  switch   loc_3B7EE, loc_3B7F7, loc_3B800
0x3b7ec  br.s     loc_3B809
0x3b7ee  ldarg.2
0x3b7ef  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_BackupPathOnShare()
0x3b7f4  stloc.2
0x3b7f5  br.s     loc_3B843
0x3b7f7  ldarg.2
0x3b7f8  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_LogPathOnShare()
0x3b7fd  stloc.2
0x3b7fe  br.s     loc_3B843
0x3b800  ldarg.2
0x3b801  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData::get_ManifestPathOnShare()
0x3b806  stloc.2
0x3b807  br.s     loc_3B843
0x3b809  ldstr    aNotASupportedF// "Not a supported fileType for operation:"...
0x3b80e  ldarga.s 3
0x3b810  constrained. [Microsoft.Crm.Core]Microsoft.Crm.RestorePointFileType
0x3b816  callvirt instance string [mscorlib]System.Object::ToString()
0x3b81b  call     string [mscorlib]System.String::Concat(string, string)
0x3b820  stloc.3
0x3b821  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b826  ldc.i4.s 0x1D
0x3b828  ldstr    a0// "{0}"
0x3b82d  ldc.i4.1
0x3b82e  newarr   [mscorlib]System.Object
0x3b833  dup
0x3b834  ldc.i4.0
0x3b835  ldloc.3
0x3b836  stelem.ref
0x3b837  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b83c  ldloc.3
0x3b83d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0x3b842  throw
0x3b843  ldloc.2
0x3b844  call     bool [mscorlib]System.IO.File::Exists(string)
0x3b849  brtrue.s loc_3B881
0x3b84b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b850  ldc.i4.s 0x1D
0x3b852  ldstr    a0// "{0}"
0x3b857  ldc.i4.1
0x3b858  newarr   [mscorlib]System.Object
0x3b85d  dup
0x3b85e  ldc.i4.0
0x3b85f  ldstr    aFileDoesNotExi// "File does not exist: "
0x3b864  ldloc.2
0x3b865  call     string [mscorlib]System.String::Concat(string, string)
0x3b86a  stelem.ref
0x3b86b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b870  ldstr    aBackupFileNotA// "Backup file not accessible: "
0x3b875  ldloc.2
0x3b876  call     string [mscorlib]System.String::Concat(string, string)
0x3b87b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3b880  throw
0x3b881  ldstr    aId// "Id"
0x3b886  ldloc.0
0x3b887  box      [mscorlib]System.Guid
0x3b88c  ldloc.1
0x3b88d  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b892  ldstr    aFiletype// "FileType"
0x3b897  ldarg.3
0x3b898  box      [Microsoft.Crm.Core]Microsoft.Crm.RestorePointFileType
0x3b89d  ldloc.1
0x3b89e  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b8a3  ldstr    aFilecreatedon// "FileCreatedOn"
0x3b8a8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3b8ad  box      [mscorlib]System.DateTime
0x3b8b2  ldloc.1
0x3b8b3  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b8b8  ldstr    aChecksum// "Checksum"
0x3b8bd  ldc.i4.0
0x3b8be  newarr   [mscorlib]System.Byte
0x3b8c3  ldloc.1
0x3b8c4  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b8c9  ldstr    aAzuremd5checks// "AzureMD5Checksum"
0x3b8ce  ldsfld   string [mscorlib]System.String::Empty
0x3b8d3  ldloc.1
0x3b8d4  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b8d9  ldstr    aLocation// "Location"
0x3b8de  ldloc.2
0x3b8df  ldloc.1
0x3b8e0  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b8e5  ldstr    aRestorepointid_0// "RestorePointId"
0x3b8ea  ldarg.0
0x3b8eb  box      [mscorlib]System.Guid
0x3b8f0  ldloc.1
0x3b8f1  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b8f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x3b8fb  stloc.s  4
0x3b8fd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b902  ldc.i4.s 0x1D
0x3b904  ldstr    a0// "{0}"
0x3b909  ldc.i4.1
0x3b90a  newarr   [mscorlib]System.Object
0x3b90f  dup
0x3b910  ldc.i4.0
0x3b911  ldstr    aCreatingRestor_0// "Creating RestorePoint Location"
0x3b916  stelem.ref
0x3b917  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b91c  ldloc.s  4
0x3b91e  ldstr    aRestorepointlo// "RestorePointLocation"
0x3b923  ldloc.1
0x3b924  ldc.i4   0xCA
0x3b929  ldstr    aCreaterestorep_0// "CreateRestorePointLocations"
0x3b92e  ldstr    aDA1SSrcCrmlive_66// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Resto"...
0x3b933  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3b938  pop
0x3b939  leave.s  loc_3B947
0x3b93b  ldloc.s  4
0x3b93d  brfalse.s loc_3B946
0x3b93f  ldloc.s  4
0x3b941  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b946  endfinally
0x3b947  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b94c  ldc.i4.s 0x1D
0x3b94e  ldstr    a0// "{0}"
0x3b953  ldc.i4.1
0x3b954  newarr   [mscorlib]System.Object
0x3b959  dup
0x3b95a  ldc.i4.0
0x3b95b  ldstr    aRestorepointLo// "RestorePoint Location entity created"
0x3b960  stelem.ref
0x3b961  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b966  leave.s  loc_3B999
0x3b968  stloc.s  5
0x3b96a  ldloc.s  5
0x3b96c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b971  ldc.i4.s 0x1D
0x3b973  ldstr    aExceptionThrow_1// "Exception thrown while creating Restore"...
0x3b978  ldc.i4.2
0x3b979  newarr   [mscorlib]System.Object
0x3b97e  dup
0x3b97f  ldc.i4.0
0x3b980  ldloc.s  5
0x3b982  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3b987  stelem.ref
0x3b988  dup
0x3b989  ldc.i4.1
0x3b98a  ldloc.s  5
0x3b98c  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x3b991  stelem.ref
0x3b992  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b997  rethrow
0x3b999  ret
```
