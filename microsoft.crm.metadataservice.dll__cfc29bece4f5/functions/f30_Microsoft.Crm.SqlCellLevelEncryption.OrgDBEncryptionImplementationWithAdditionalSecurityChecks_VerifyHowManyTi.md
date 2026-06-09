# Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::VerifyHowManyTimesChangeOperationHasBeenExecuted

- ea: `0xf30`
- end: `0xfdf`
- name: `Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::VerifyHowManyTimesChangeOperationHasBeenExecuted`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x260`

## callees

- `0xab0`
- `0xb40`
- `0xf30`

## string_xrefs

- `0xf9a`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SqlEncryption\OrgDBEncryptionImplementation.cs`
- `0xf44`: `\ndeclare @Now datetime = GETUTCDATE()\ndeclare @StartDateIntervalForCount datetime = DATEADD(minute, -@MinutesInterval, @Now)\ndeclare @StartDateIntervalForDelete datetime = DATEADD(year, -1, @Now)\n\ndeclare @Count integer\nselect @Count = count(*) from SqlEncryptionAudit where @StartDateIntervalForCount <= CreatedOn\n\nif (@Count < @ExecutionTimes)\nbegin\n	delete from SqlEncryptionAudit where CreatedOn < @StartDateIntervalForDelete\n	insert into SqlEncryptionAudit (CreatedOn, Crea`
- `0xf7e`: `@CreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0xf30  ldarg.0
0xf31  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::get_Context()
0xf36  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xf3b  stloc.0
0xf3c  ldarg.0
0xf3d  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::CreateCommand()
0xf42  stloc.1
0xf43  ldloc.1
0xf44  ldstr    aDeclareNowDate// "\r\ndeclare @Now datetime = GETUTCDATE("...
0xf49  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf4e  ldloc.1
0xf4f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf54  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf59  dup
0xf5a  ldstr    aMinutesinterva// "@MinutesInterval"
0xf5f  ldc.i4.s 0xF
0xf61  box      [mscorlib]System.Int32
0xf66  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf6b  pop
0xf6c  dup
0xf6d  ldstr    aExecutiontimes// "@ExecutionTimes"
0xf72  ldc.i4.3
0xf73  box      [mscorlib]System.Int32
0xf78  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf7d  pop
0xf7e  ldstr    aCreatedby// "@CreatedBy"
0xf83  ldloc.0
0xf84  box      [mscorlib]System.Guid
0xf89  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf8e  pop
0xf8f  ldloc.1
0xf90  ldc.i4   0x22D
0xf95  ldstr    aVerifyhowmanyt// "VerifyHowManyTimesChangeOperationHasBee"...
0xf9a  ldstr    aDA1SSrcCoreObj// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0xf9f  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xfa4  unbox.any [mscorlib]System.Int32
0xfa9  stloc.2
0xfaa  ldc.i4.3
0xfab  ldloc.2
0xfac  bgt.s    loc_FD2
0xfae  ldc.i4   0x80048529
0xfb3  ldc.i4.2
0xfb4  newarr   [mscorlib]System.Object
0xfb9  dup
0xfba  ldc.i4.0
0xfbb  ldc.i4.3
0xfbc  box      [mscorlib]System.Int32
0xfc1  stelem.ref
0xfc2  dup
0xfc3  ldc.i4.1
0xfc4  ldc.i4.s 0xF
0xfc6  box      [mscorlib]System.Int32
0xfcb  stelem.ref
0xfcc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xfd1  throw
0xfd2  leave.s  loc_FDE
0xfd4  ldloc.1
0xfd5  brfalse.s loc_FDD
0xfd7  ldloc.1
0xfd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfdd  endfinally
0xfde  ret
```
