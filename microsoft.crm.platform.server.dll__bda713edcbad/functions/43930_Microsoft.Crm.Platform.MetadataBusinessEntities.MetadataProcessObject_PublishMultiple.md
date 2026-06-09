# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::PublishMultiple

- ea: `0x43930`
- end: `0x43b68`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::PublishMultiple`
- size: `568`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x438d0`
- `0x43920`

## callees

- `0x42740`
- `0x427e0`
- `0x42d90`
- `0x42ed0`
- `0x43930`
- `0x43d60`
- `0x43e70`
- `0x43f20`
- `0x440a0`
- `0x44150`
- `0x45260`
- `0x458b0`
- `0x66ae0`

## string_xrefs

- `0x43a15`: `create table #MetadataPublishCollect(ObjectId uniqueidentifier PRIMARY KEY CLUSTERED, ObjectTypeCode int not null, ComponentState tinyint not null)`
- `0x43a3b`: `create statistics mpcstat on #MetadataPublishCollect(ObjectId)`
- `0x43b32`: `IF EXISTS (SELECT * FROM [tempdb].[sys].[tables] WHERE object_id = OBJECT_ID(N'[tempdb].[dbo].[#MetadataPublishCollect]')) DROP TABLE [dbo].[#MetadataPublishCollect]`

## pseudocode

```c

```

## disassembly

```asm
0x43930  ldc.i4.1
0x43931  stloc.0
0x43932  ldarg.1
0x43933  ldstr    aMonikers// "monikers"
0x43938  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4393d  ldarg.2
0x4393e  ldstr    aContext// "context"
0x43943  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x43948  ldarg.1
0x43949  ldlen
0x4394a  brtrue.s loc_4394D
0x4394c  ret
0x4394d  ldarg.2
0x4394e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x43953  stloc.1
0x43954  ldloc.1
0x43955  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::StartTransaction()
0x4395a  ldc.i4.0
0x4395b  stloc.2
0x4395c  ldc.i4.0
0x4395d  stloc.3
0x4395e  ldloc.1
0x4395f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x43964  stloc.s  4
0x43966  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x4396b  stloc.s  5
0x4396d  ldarg.1
0x4396e  stloc.s  8
0x43970  ldc.i4.0
0x43971  stloc.s  9
0x43973  br.s     loc_439BC
0x43975  ldloc.s  8
0x43977  ldloc.s  9
0x43979  ldelem.ref
0x4397a  stloc.s  0xA
0x4397c  ldloc.s  0xA
0x4397e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityMetadata()
0x43983  stloc.s  0xB
0x43985  ldloc.s  5
0x43987  ldloc.s  0xB
0x43989  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x4398e  brtrue.s loc_439A1
0x43990  ldloc.s  5
0x43992  ldloc.s  0xB
0x43994  ldarg.1
0x43995  ldlen
0x43996  conv.i4
0x43997  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor(int32)
0x4399c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0x439a1  ldloc.s  5
0x439a3  ldloc.s  0xB
0x439a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x439aa  ldloc.s  0xA
0x439ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x439b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x439b6  ldloc.s  9
0x439b8  ldc.i4.1
0x439b9  add
0x439ba  stloc.s  9
0x439bc  ldloc.s  9
0x439be  ldloc.s  8
0x439c0  ldlen
0x439c1  conv.i4
0x439c2  blt.s    loc_43975
0x439c4  ldloc.1
0x439c5  call     bool Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataTimeStampUtility::CanPreCommitTransactionEventBeRegistered(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x439ca  brfalse.s loc_43A14
0x439cc  ldloc.s  4
0x439ce  ldstr    aExecPPublishme// "exec p_PublishMetadataFromTable @publis"...
0x439d3  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x439d8  ldloc.s  4
0x439da  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x439df  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x439e4  dup
0x439e5  ldstr    aPublishdeep// "@publishDeep"
0x439ea  ldloc.0
0x439eb  box      [mscorlib]System.Boolean
0x439f0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x439f5  pop
0x439f6  ldarg.0
0x439f7  ldloc.s  5
0x439f9  ldloc.0
0x439fa  ldloc.1
0x439fb  call     instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>> Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveObjectsTypeAndId(class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> typesToIds, bool publishDeep, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x43a00  ldstr    aMetadatapublis// "@metadataPublishCollectionTable"
0x43a05  ldloca.s 3
0x43a07  call     class [System.Data]System.Data.SqlClient.SqlParameter Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::GetMetadataPublishCollectionTableParameter(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>> objectIdObjectTypeCodeComponentStateTupleList, string parameterName, [out] bool& insertMetadataTimeStamp)
0x43a0c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x43a11  pop
0x43a12  br.s     loc_43A91
0x43a14  ldloc.1
0x43a15  ldstr    aCreateTableMet// "create table #MetadataPublishCollect(Ob"...
0x43a1a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x43a1f  stloc.s  0xC
0x43a21  ldloc.s  0xC
0x43a23  ldloc.1
0x43a24  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x43a29  pop
0x43a2a  ldc.i4.1
0x43a2b  stloc.2
0x43a2c  leave.s  loc_43A3A
0x43a2e  ldloc.s  0xC
0x43a30  brfalse.s loc_43A39
0x43a32  ldloc.s  0xC
0x43a34  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43a39  endfinally
0x43a3a  ldloc.1
0x43a3b  ldstr    aCreateStatisti// "create statistics mpcstat on #MetadataP"...
0x43a40  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x43a45  stloc.s  0xD
0x43a47  ldloc.s  0xD
0x43a49  ldloc.1
0x43a4a  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x43a4f  pop
0x43a50  leave.s  loc_43A5E
0x43a52  ldloc.s  0xD
0x43a54  brfalse.s loc_43A5D
0x43a56  ldloc.s  0xD
0x43a58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43a5d  endfinally
0x43a5e  ldarg.0
0x43a5f  ldloc.s  5
0x43a61  ldloc.0
0x43a62  ldloc.1
0x43a63  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::AddObjectsByTypeAndId(class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> typesToIds, bool publishDeep, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x43a68  ldloc.s  4
0x43a6a  ldstr    aExecPPublishme_0// "exec p_PublishMetadata @publishDeep"
0x43a6f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x43a74  ldloc.s  4
0x43a76  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x43a7b  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x43a80  ldstr    aPublishdeep// "@publishDeep"
0x43a85  ldloc.0
0x43a86  box      [mscorlib]System.Boolean
0x43a8b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x43a90  pop
0x43a91  ldarg.0
0x43a92  ldloc.s  5
0x43a94  ldloc.0
0x43a95  ldloc.1
0x43a96  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::GetAuditChangeAttributesList(class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> typesToIds, bool publishDeep, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x43a9b  stloc.s  6
0x43a9d  ldc.i4.0
0x43a9e  stloc.s  7
0x43aa0  ldloc.s  4
0x43aa2  ldloc.1
0x43aa3  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x43aa8  stloc.s  0xE
0x43aaa  ldarg.0
0x43aab  ldloc.s  0xE
0x43aad  ldarg.2
0x43aae  ldloc.s  6
0x43ab0  call     instance bool Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::AddAllPublishedDependenciesAndProcessAuditChanges(class [System.Data]System.Data.IDataReader reader, class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> auditChangeAttributes)
0x43ab5  stloc.s  7
0x43ab7  leave.s  loc_43AC5
0x43ab9  ldloc.s  0xE
0x43abb  brfalse.s loc_43AC4
0x43abd  ldloc.s  0xE
0x43abf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43ac4  endfinally
0x43ac5  ldloc.s  7
0x43ac7  ldloc.3
0x43ac8  or
0x43ac9  brfalse.s loc_43AD1
0x43acb  ldloc.1
0x43acc  call     void Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataTimeStampUtility::TryRegisterEventForInsertMetadataTimestamp(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x43ad1  ldarg.0
0x43ad2  ldloc.s  6
0x43ad4  ldarg.2
0x43ad5  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::LogAuditChanges(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> auditChangeAttributes, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x43ada  ldarg.0
0x43adb  ldloc.1
0x43adc  call     instance void Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RegisterPostCommitTransactionEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x43ae1  leave.s  loc_43AEF
0x43ae3  ldloc.s  4
0x43ae5  brfalse.s loc_43AEE
0x43ae7  ldloc.s  4
0x43ae9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43aee  endfinally
0x43aef  leave.s  loc_43B2C
0x43af1  stloc.s  0xF
0x43af3  ldloc.s  0xF
0x43af5  ldloc.1
0x43af6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43afb  ldc.i4.s 0x19
0x43afd  ldstr    a0// "{0}"
0x43b02  ldc.i4.1
0x43b03  newarr   [mscorlib]System.Object
0x43b08  dup
0x43b09  ldc.i4.0
0x43b0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43b0f  ldstr    aErrorWhilePubl// "Error while publishing objects: {0}"
0x43b14  ldc.i4.1
0x43b15  newarr   [mscorlib]System.Object
0x43b1a  dup
0x43b1b  ldc.i4.0
0x43b1c  ldloc.s  0xF
0x43b1e  stelem.ref
0x43b1f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43b24  stelem.ref
0x43b25  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x43b2a  rethrow
0x43b2c  leave.s  loc_43B56
0x43b2e  ldloc.2
0x43b2f  brfalse.s loc_43B55
0x43b31  ldloc.1
0x43b32  ldstr    aIfExistsSelect_0// "IF EXISTS (SELECT * FROM [tempdb].[sys]"...
0x43b37  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x43b3c  stloc.s  0x10
0x43b3e  ldloc.s  0x10
0x43b40  ldloc.1
0x43b41  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x43b46  pop
0x43b47  leave.s  loc_43B55
0x43b49  ldloc.s  0x10
0x43b4b  brfalse.s loc_43B54
0x43b4d  ldloc.s  0x10
0x43b4f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43b54  endfinally
0x43b55  endfinally
0x43b56  ldloc.1
0x43b57  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CommitTransaction()
0x43b5c  leave.s  loc_43B67
0x43b5e  pop
0x43b5f  ldloc.1
0x43b60  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::RollbackTransaction()
0x43b65  rethrow
0x43b67  ret
```
