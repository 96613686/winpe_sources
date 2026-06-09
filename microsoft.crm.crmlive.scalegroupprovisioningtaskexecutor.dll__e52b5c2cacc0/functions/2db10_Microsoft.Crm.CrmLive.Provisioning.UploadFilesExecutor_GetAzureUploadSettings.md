# Microsoft.Crm.CrmLive.Provisioning.UploadFilesExecutor::GetAzureUploadSettings

- ea: `0x2db10`
- end: `0x2dc18`
- name: `Microsoft.Crm.CrmLive.Provisioning.UploadFilesExecutor::GetAzureUploadSettings`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d8d0`

## callees

- `0xdce0`
- `0x2db10`

## string_xrefs

- `0x2db42`: `AzureUploadBlockBlobThreadCount`
- `0x2db81`: `AzureUploadBlockBlobThreadCount`

## pseudocode

```c

```

## disassembly

```asm
0x2db10  newobj   instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureUploadSettings::.ctor()
0x2db15  dup
0x2db16  ldarg.0
0x2db17  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureInfo::get_AzureRestorePointId()
0x2db1c  call     class [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureAccountSettings Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::GetAzureAccountSettings(valuetype [mscorlib]System.Guid restorePointId)
0x2db21  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_AzureAccountSettings(class [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureAccountSettings)
0x2db26  dup
0x2db27  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2db2c  ldstr    aAzureuploadblo// "AzureUploadBlockBlobSizeInBytes"
0x2db31  callvirt T0x2B000075
0x2db36  conv.i8
0x2db37  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_BlockBlobSize(int64)
0x2db3c  dup
0x2db3d  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2db42  ldstr    aAzureuploadblo_0// "AzureUploadBlockBlobThreadCount"
0x2db47  callvirt T0x2B000075
0x2db4c  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_MaxDegreeOfParallelism(int32)
0x2db51  dup
0x2db52  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2db57  ldstr    aAzureuploadmax// "AzureUploadMaxExecutionTimeInMinutes"
0x2db5c  callvirt T0x2B000075
0x2db61  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureUploadSettings::set_MaxExecutionTimePerUpload(int32)
0x2db66  dup
0x2db67  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2db6c  ldstr    aAzureuploadmax_0// "AzureUploadMaxRetryCount"
0x2db71  callvirt T0x2B000075
0x2db76  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_MaxRetryCount(int32)
0x2db7b  dup
0x2db7c  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2db81  ldstr    aAzureuploadblo_0// "AzureUploadBlockBlobThreadCount"
0x2db86  callvirt T0x2B000075
0x2db8b  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureUploadSettings::set_ParallelOperationThreadCount(int32)
0x2db90  dup
0x2db91  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2db96  ldstr    aAzureuploadret// "AzureUploadRetryIntervalInSeconds"
0x2db9b  callvirt T0x2B000075
0x2dba0  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_RetryInterval(int32)
0x2dba5  dup
0x2dba6  ldarg.0
0x2dba7  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureInfo::get_HypernetEnabled()
0x2dbac  brtrue.s loc_2DBB5
0x2dbae  ldsfld   string [mscorlib]System.String::Empty
0x2dbb3  br.s     loc_2DBC5
0x2dbb5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x2dbba  ldstr    aAzurehypernete// "AzureHypernetEndpoint"
0x2dbbf  ldc.i4.0
0x2dbc0  callvirt T0x2B000011
0x2dbc5  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_HypernetEndpoint(string)
0x2dbca  dup
0x2dbcb  ldarg.0
0x2dbcc  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureInfo::get_HypernetEnabled()
0x2dbd1  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_HypernetEnabled(bool)
0x2dbd6  dup
0x2dbd7  ldarg.0
0x2dbd8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationBackupToAzureInfo::get_OrganizationId()
0x2dbdd  callvirt instance void [Microsoft.Crm.Azure]Microsoft.Crm.Azure.Models.AzureOperationSettingsBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x2dbe2  stloc.0
0x2dbe3  leave.s  loc_2DC16
0x2dbe5  stloc.1
0x2dbe6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2dbeb  ldstr    aErrorOccurredW_2// "Error occurred while getting Azure uplo"...
0x2dbf0  ldc.i4.1
0x2dbf1  newarr   [mscorlib]System.Object
0x2dbf6  dup
0x2dbf7  ldc.i4.0
0x2dbf8  ldloc.1
0x2dbf9  stelem.ref
0x2dbfa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2dbff  stloc.2
0x2dc00  ldloc.1
0x2dc01  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2dc06  ldc.i4.s 0x12
0x2dc08  ldloc.2
0x2dc09  ldc.i4.0
0x2dc0a  newarr   [mscorlib]System.Object
0x2dc0f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2dc14  rethrow
0x2dc16  ldloc.0
0x2dc17  ret
```
