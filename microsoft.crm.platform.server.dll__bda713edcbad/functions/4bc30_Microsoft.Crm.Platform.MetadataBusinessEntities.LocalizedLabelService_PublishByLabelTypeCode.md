# Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::PublishByLabelTypeCode

- ea: `0x4bc30`
- end: `0x4bd41`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::PublishByLabelTypeCode`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x427e0`
- `0x42ed0`
- `0x45260`
- `0x4bc30`
- `0x4bd50`
- `0x4bd80`
- `0x4bdb0`
- `0x4c270`

## string_xrefs

- `0x4bccc`: `@componentState`
- `0x4bc87`: `INSERT INTO #MetadataPublishCollect(ObjectId, ObjectTypeCode, ComponentState)  (SELECT DISTINCT ObjectId , @objectTypeCode , @componentState from LocalizedLabelView where LabelTypeCode = @labelTypeCode)`

## pseudocode

```c

```

## disassembly

```asm
0x4bc30  ldarg.2
0x4bc31  ldstr    aContext// "context"
0x4bc36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4bc3b  ldc.i4.0
0x4bc3c  stloc.0
0x4bc3d  ldarg.2
0x4bc3e  call     bool Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataTimeStampUtility::CanPreCommitTransactionEventBeRegistered(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4bc43  brfalse.s loc_4BC7E
0x4bc45  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::.ctor()
0x4bc4a  stloc.1
0x4bc4b  ldloc.1
0x4bc4c  ldnull
0x4bc4d  ldstr    aMetadatapublis// "@metadataPublishCollectionTable"
0x4bc52  ldloca.s 2
0x4bc54  call     class [System.Data]System.Data.SqlClient.SqlParameter Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::GetMetadataPublishCollectionTableParameter(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>> objectIdObjectTypeCodeComponentStateTupleList, string parameterName, [out] bool& insertMetadataTimeStamp)
0x4bc59  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x4bc5e  ldloc.1
0x4bc5f  ldstr    aLabeltypecode_1// "@labelTypeCode"
0x4bc64  ldarg.1
0x4bc65  box      [mscorlib]System.Int32
0x4bc6a  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x4bc6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x4bc74  ldarg.0
0x4bc75  ldloc.1
0x4bc76  ldarg.2
0x4bc77  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::ExecutePublishLabelsStoredProc(class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> listSQLParamsForStoredProc, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bc7c  br.s     loc_4BCF8
0x4bc7e  ldarg.0
0x4bc7f  ldarg.2
0x4bc80  call     instance bool Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::CreateMetadataPublishCollectTable(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bc85  stloc.0
0x4bc86  ldarg.2
0x4bc87  ldstr    aInsertIntoMeta_0// "INSERT INTO #MetadataPublishCollect(Obj"...
0x4bc8c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x4bc91  stloc.3
0x4bc92  ldloc.3
0x4bc93  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4bc98  callvirt instance void [mscorlib]System.Collections.IList::Clear()
0x4bc9d  ldloc.3
0x4bc9e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4bca3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4bca8  dup
0x4bca9  ldstr    aLabeltypecode_1// "@labelTypeCode"
0x4bcae  ldarg.1
0x4bcaf  box      [mscorlib]System.Int32
0x4bcb4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4bcb9  pop
0x4bcba  dup
0x4bcbb  ldstr    aObjecttypecode_84// "@objectTypeCode"
0x4bcc0  ldc.i4.0
0x4bcc1  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataObjectTypeCode
0x4bcc6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4bccb  pop
0x4bccc  ldstr    aComponentstate_5// "@componentState"
0x4bcd1  ldc.i4.0
0x4bcd2  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x4bcd7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4bcdc  pop
0x4bcdd  ldloc.3
0x4bcde  ldarg.2
0x4bcdf  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bce4  pop
0x4bce5  leave.s  loc_4BCF1
0x4bce7  ldloc.3
0x4bce8  brfalse.s loc_4BCF0
0x4bcea  ldloc.3
0x4bceb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bcf0  endfinally
0x4bcf1  ldarg.0
0x4bcf2  ldarg.2
0x4bcf3  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::PublishLabelByObjectId(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bcf8  leave.s  loc_4BD40
0x4bcfa  stloc.s  4
0x4bcfc  ldloc.s  4
0x4bcfe  ldarg.2
0x4bcff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4bd04  ldc.i4.s 0x19
0x4bd06  ldstr    a0// "{0}"
0x4bd0b  ldc.i4.1
0x4bd0c  newarr   [mscorlib]System.Object
0x4bd11  dup
0x4bd12  ldc.i4.0
0x4bd13  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4bd18  ldstr    aErrorWhilePubl_0// "Error while publishing label: {0}"
0x4bd1d  ldc.i4.1
0x4bd1e  newarr   [mscorlib]System.Object
0x4bd23  dup
0x4bd24  ldc.i4.0
0x4bd25  ldloc.s  4
0x4bd27  stelem.ref
0x4bd28  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4bd2d  stelem.ref
0x4bd2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4bd33  rethrow
0x4bd35  ldloc.0
0x4bd36  brfalse.s loc_4BD3F
0x4bd38  ldarg.0
0x4bd39  ldarg.2
0x4bd3a  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::DropMetadataPublishCollectTable(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bd3f  endfinally
0x4bd40  ret
```
