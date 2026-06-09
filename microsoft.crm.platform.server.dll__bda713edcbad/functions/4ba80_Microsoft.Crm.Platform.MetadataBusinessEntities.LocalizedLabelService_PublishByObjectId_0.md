# Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::PublishByObjectId_0

- ea: `0x4ba80`
- end: `0x4bc23`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::PublishByObjectId_0`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x4ba60`

## callees

- `0x427e0`
- `0x42ed0`
- `0x45260`
- `0x4ba80`
- `0x4bd50`
- `0x4bd80`
- `0x4bdb0`
- `0x4c270`

## string_xrefs

- `0x4bb22`: `INSERT INTO #MetadataPublishCollect(ObjectId, ObjectTypeCode, ComponentState) values (@objectId, @objectTypeCode, @componentState)`
- `0x4bb90`: `@componentState`

## pseudocode

```c

```

## disassembly

```asm
0x4ba80  ldarg.1
0x4ba81  ldstr    aObjectids// "objectIds"
0x4ba86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4ba8b  ldarg.2
0x4ba8c  ldstr    aContext// "context"
0x4ba91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4ba96  ldarg.1
0x4ba97  ldlen
0x4ba98  brtrue.s loc_4BA9B
0x4ba9a  ret
0x4ba9b  ldc.i4.0
0x4ba9c  stloc.0
0x4ba9d  ldarg.2
0x4ba9e  call     bool Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataTimeStampUtility::CanPreCommitTransactionEventBeRegistered(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4baa3  brfalse.s loc_4BB19
0x4baa5  ldarg.1
0x4baa6  ldlen
0x4baa7  conv.i4
0x4baa8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>>::.ctor(int32)
0x4baad  stloc.1
0x4baae  ldarg.1
0x4baaf  stloc.s  4
0x4bab1  ldc.i4.0
0x4bab2  stloc.s  5
0x4bab4  br.s     loc_4BAD6
0x4bab6  ldloc.s  4
0x4bab8  ldloc.s  5
0x4baba  ldelem   [mscorlib]System.Guid
0x4babf  stloc.s  6
0x4bac1  ldloc.1
0x4bac2  ldloc.s  6
0x4bac4  ldc.i4.0
0x4bac5  ldc.i4.0
0x4bac6  newobj   instance void class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::.ctor(var<u1>, !!T0, var<u1>)
0x4bacb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>>::Add(var<u1>)
0x4bad0  ldloc.s  5
0x4bad2  ldc.i4.1
0x4bad3  add
0x4bad4  stloc.s  5
0x4bad6  ldloc.s  5
0x4bad8  ldloc.s  4
0x4bada  ldlen
0x4badb  conv.i4
0x4badc  blt.s    loc_4BAB6
0x4bade  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::.ctor()
0x4bae3  stloc.2
0x4bae4  ldloc.2
0x4bae5  ldloc.1
0x4bae6  ldstr    aMetadatapublis// "@metadataPublishCollectionTable"
0x4baeb  ldloca.s 3
0x4baed  call     class [System.Data]System.Data.SqlClient.SqlParameter Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::GetMetadataPublishCollectionTableParameter(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>> objectIdObjectTypeCodeComponentStateTupleList, string parameterName, [out] bool& insertMetadataTimeStamp)
0x4baf2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x4baf7  ldloc.2
0x4baf8  ldstr    aLabeltypecode_1// "@labelTypeCode"
0x4bafd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x4bb02  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x4bb07  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x4bb0c  ldarg.0
0x4bb0d  ldloc.2
0x4bb0e  ldarg.2
0x4bb0f  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::ExecutePublishLabelsStoredProc(class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> listSQLParamsForStoredProc, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bb14  br       loc_4BBDA
0x4bb19  ldarg.0
0x4bb1a  ldarg.2
0x4bb1b  call     instance bool Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::CreateMetadataPublishCollectTable(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bb20  stloc.0
0x4bb21  ldarg.2
0x4bb22  ldstr    aInsertIntoMeta// "INSERT INTO #MetadataPublishCollect(Obj"...
0x4bb27  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x4bb2c  stloc.s  7
0x4bb2e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, object>::.ctor()
0x4bb33  stloc.s  8
0x4bb35  ldarg.1
0x4bb36  stloc.s  4
0x4bb38  ldc.i4.0
0x4bb39  stloc.s  5
0x4bb3b  br.s     loc_4BBBA
0x4bb3d  ldloc.s  4
0x4bb3f  ldloc.s  5
0x4bb41  ldelem   [mscorlib]System.Guid
0x4bb46  stloc.s  9
0x4bb48  ldloc.s  8
0x4bb4a  ldloc.s  9
0x4bb4c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, object>::ContainsKey(var<u1>)
0x4bb51  brtrue.s loc_4BBB4
0x4bb53  ldloc.s  7
0x4bb55  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4bb5a  callvirt instance void [mscorlib]System.Collections.IList::Clear()
0x4bb5f  ldloc.s  7
0x4bb61  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4bb66  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4bb6b  dup
0x4bb6c  ldstr    aObjectid_4// "@objectId"
0x4bb71  ldloc.s  9
0x4bb73  box      [mscorlib]System.Guid
0x4bb78  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4bb7d  pop
0x4bb7e  dup
0x4bb7f  ldstr    aObjecttypecode_84// "@objectTypeCode"
0x4bb84  ldc.i4.0
0x4bb85  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataObjectTypeCode
0x4bb8a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4bb8f  pop
0x4bb90  ldstr    aComponentstate_5// "@componentState"
0x4bb95  ldc.i4.0
0x4bb96  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x4bb9b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4bba0  pop
0x4bba1  ldloc.s  7
0x4bba3  ldarg.2
0x4bba4  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bba9  pop
0x4bbaa  ldloc.s  8
0x4bbac  ldloc.s  9
0x4bbae  ldnull
0x4bbaf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, object>::Add(var<u1>, !!T0)
0x4bbb4  ldloc.s  5
0x4bbb6  ldc.i4.1
0x4bbb7  add
0x4bbb8  stloc.s  5
0x4bbba  ldloc.s  5
0x4bbbc  ldloc.s  4
0x4bbbe  ldlen
0x4bbbf  conv.i4
0x4bbc0  blt      loc_4BB3D
0x4bbc5  leave.s  loc_4BBD3
0x4bbc7  ldloc.s  7
0x4bbc9  brfalse.s loc_4BBD2
0x4bbcb  ldloc.s  7
0x4bbcd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bbd2  endfinally
0x4bbd3  ldarg.0
0x4bbd4  ldarg.2
0x4bbd5  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::PublishLabelByObjectId(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bbda  leave.s  loc_4BC22
0x4bbdc  stloc.s  0xA
0x4bbde  ldloc.s  0xA
0x4bbe0  ldarg.2
0x4bbe1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4bbe6  ldc.i4.s 0x19
0x4bbe8  ldstr    a0// "{0}"
0x4bbed  ldc.i4.1
0x4bbee  newarr   [mscorlib]System.Object
0x4bbf3  dup
0x4bbf4  ldc.i4.0
0x4bbf5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4bbfa  ldstr    aErrorWhilePubl_0// "Error while publishing label: {0}"
0x4bbff  ldc.i4.1
0x4bc00  newarr   [mscorlib]System.Object
0x4bc05  dup
0x4bc06  ldc.i4.0
0x4bc07  ldloc.s  0xA
0x4bc09  stelem.ref
0x4bc0a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4bc0f  stelem.ref
0x4bc10  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4bc15  rethrow
0x4bc17  ldloc.0
0x4bc18  brfalse.s loc_4BC21
0x4bc1a  ldarg.0
0x4bc1b  ldarg.2
0x4bc1c  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::DropMetadataPublishCollectTable(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4bc21  endfinally
0x4bc22  ret
```
