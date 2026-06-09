# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::RemovePersistMatchcodesAsyncJob

- ea: `0x1eed0`
- end: `0x1ef61`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::RemovePersistMatchcodesAsyncJob`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ee20`

## callees

- `0x1eed0`
- `0x1f0f0`

## string_xrefs

- `0x1eefa`: `UPDATE AsyncOperationBase SET RecurrencePattern = NULL, RecurrenceStartTime = NULL, PostponeUntil = NULL, StateCode = @stateCode, StatusCode = @statusCode WHERE RegardingObjectId=@regardingobjectid AND OperationType = @operationType AND RecurrencePattern IS NOT NULL AND RecurrenceStartTime IS NOT NULL`

## pseudocode

```c

```

## disassembly

```asm
0x1eed0  ldarg.1
0x1eed1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1eed6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eedb  ldarg.0
0x1eedc  ldc.i4.1
0x1eedd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1eee2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x1eee7  stloc.0
0x1eee8  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1eeed  stloc.1
0x1eeee  ldloc.1
0x1eeef  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1eef4  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1eef9  ldloc.1
0x1eefa  ldstr    aUpdateAsyncope_1// "UPDATE AsyncOperationBase SET Recurrenc"...
0x1eeff  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1ef04  dup
0x1ef05  ldstr    aRegardingobjec_4// "@regardingobjectid"
0x1ef0a  ldloc.0
0x1ef0b  box      [mscorlib]System.Guid
0x1ef10  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ef15  pop
0x1ef16  dup
0x1ef17  ldstr    aOperationtype_0// "@operationType"
0x1ef1c  ldc.i4.s 0xC
0x1ef1e  box      [mscorlib]System.Int32
0x1ef23  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ef28  pop
0x1ef29  dup
0x1ef2a  ldstr    aStatecode_0// "@stateCode"
0x1ef2f  ldc.i4.3
0x1ef30  box      [mscorlib]System.Int32
0x1ef35  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ef3a  pop
0x1ef3b  ldstr    aStatuscode_0// "@statusCode"
0x1ef40  ldc.i4.s 0x1E
0x1ef42  box      [mscorlib]System.Int32
0x1ef47  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1ef4c  pop
0x1ef4d  ldarg.2
0x1ef4e  ldloc.1
0x1ef4f  callvirt instance void Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess::ExecuteCommand(class [System.Data]System.Data.IDbCommand command)
0x1ef54  leave.s  loc_1EF60
0x1ef56  ldloc.1
0x1ef57  brfalse.s loc_1EF5F
0x1ef59  ldloc.1
0x1ef5a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ef5f  endfinally
0x1ef60  ret
```
