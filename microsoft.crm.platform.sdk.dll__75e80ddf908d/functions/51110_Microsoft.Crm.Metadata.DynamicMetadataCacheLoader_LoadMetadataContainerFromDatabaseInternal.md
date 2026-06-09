# Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadMetadataContainerFromDatabaseInternal

- ea: `0x51110`
- end: `0x5134a`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadMetadataContainerFromDatabaseInternal`
- size: `570`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x51070`
- `0x510d0`
- `0x5d780`

## callees

- `0x50cf0`
- `0x51020`
- `0x51040`
- `0x51060`
- `0x51110`
- `0x52290`
- `0x523d0`
- `0x525d0`
- `0x796d0`
- `0xab470`

## string_xrefs

- `0x511ce`: `ASP_BEGIN_MDCACHE_LOADCACHE_LOAD_DATA_SET`
- `0x512da`: `Exception while loading Metadata Cache from Database with LoadMasks = {0} using {1} connection and {2} transaction. Exception: {3}`
- `0x51332`: `ASP_END_MDCACHE_LOADCACHE_LOAD_DATA_SET`

## pseudocode

```c

```

## disassembly

```asm
0x51110  ldarg.s  5
0x51112  ldstr    aBuildmetadatac// "buildMetadataContainerFromDatabase"
0x51117  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5111c  ldarga.s 6
0x5111e  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x51123  brfalse  loc_511B7
0x51128  ldarg.0
0x51129  ldstr    aXVersionnumber// " x.VersionNumber > CONVERT(timestamp, @"...
0x5112e  ldc.i4.1
0x5112f  newarr   [System.Data]System.Data.SqlClient.SqlParameter
0x51134  dup
0x51135  ldc.i4.0
0x51136  ldstr    aVersionnumber_0// "@VersionNumber"
0x5113b  ldarga.s 6
0x5113d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x51142  box      [mscorlib]System.Int64
0x51147  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x5114c  stelem.ref
0x5114d  newobj   instance void Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions::.ctor(string conditions, class [System.Data]System.Data.SqlClient.SqlParameter[] parameters)
0x51152  call     instance void Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::set_ExtraWhereConditionsToFilterOutData(class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions value)
0x51157  ldarg.0
0x51158  ldstr    aXMetadatasynct// " x.MetadataSyncTimestamp > CONVERT(time"...
0x5115d  ldc.i4.1
0x5115e  newarr   [System.Data]System.Data.SqlClient.SqlParameter
0x51163  dup
0x51164  ldc.i4.0
0x51165  ldstr    aVersionnumber_0// "@VersionNumber"
0x5116a  ldarga.s 6
0x5116c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x51171  box      [mscorlib]System.Int64
0x51176  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x5117b  stelem.ref
0x5117c  newobj   instance void Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions::.ctor(string conditions, class [System.Data]System.Data.SqlClient.SqlParameter[] parameters)
0x51181  call     instance void Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::set_ExtraWhereConditionsToFilterOutDataForOrgSettings(class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions value)
0x51186  ldarg.0
0x51187  ldstr    aXTimestampConv// " x.Timestamp > CONVERT(timestamp, @Time"...
0x5118c  ldc.i4.1
0x5118d  newarr   [System.Data]System.Data.SqlClient.SqlParameter
0x51192  dup
0x51193  ldc.i4.0
0x51194  ldstr    aTimestamp_2// "@Timestamp"
0x51199  ldarga.s 6
0x5119b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x511a0  box      [mscorlib]System.Int64
0x511a5  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x511aa  stelem.ref
0x511ab  newobj   instance void Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions::.ctor(string conditions, class [System.Data]System.Data.SqlClient.SqlParameter[] parameters)
0x511b0  call     instance void Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::set_WhereConditionsToFilterOutDeletedMetadata(class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions value)
0x511b5  br.s     loc_511BE
0x511b7  ldarg.0
0x511b8  ldnull
0x511b9  call     instance void Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::set_ExtraWhereConditionsToFilterOutData(class Microsoft.Crm.Metadata.TableFillPropertiesSelectWhereConditions value)
0x511be  ldstr    aLoadmetadataco_0// "LoadMetadataContainerFromDatabase"
0x511c3  ldarg.s  4
0x511c5  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x511ca  dup
0x511cb  starg.s  4
0x511cd  stloc.0
0x511ce  ldstr    aAspBeginMdcach_4// "ASP_BEGIN_MDCACHE_LOADCACHE_LOAD_DATA_S"...
0x511d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x511d8  ldarg.2
0x511d9  stloc.1
0x511da  ldnull
0x511db  stloc.2
0x511dc  ldarg.3
0x511dd  brfalse.s loc_511EE
0x511df  ldarg.3
0x511e0  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x511e5  brfalse.s loc_511EE
0x511e7  ldarg.3
0x511e8  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x511ed  stloc.2
0x511ee  ldc.i4.0
0x511ef  stloc.3
0x511f0  ldc.i4.0
0x511f1  stloc.s  4
0x511f3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInServerContext()
0x511f8  brtrue.s loc_51201
0x511fa  ldc.i4   0x100000
0x511ff  br.s     loc_51206
0x51201  ldc.i4   0x1000
0x51206  stloc.s  5
0x51208  ldarg.2
0x51209  brfalse.s loc_5124D
0x5120b  ldarg.3
0x5120c  brfalse.s loc_5124D
0x5120e  ldarg.3
0x5120f  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x51214  brfalse.s loc_5124D
0x51216  ldarg.3
0x51217  brfalse  loc_512B4
0x5121c  ldarg.3
0x5121d  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x51222  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbTransaction::get_Connection()
0x51227  brfalse  loc_512B4
0x5122c  ldarg.3
0x5122d  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x51232  callvirt instance valuetype [System.Data]System.Data.IsolationLevel [System.Data]System.Data.IDbTransaction::get_IsolationLevel()
0x51237  ldc.i4   0x100000
0x5123c  beq.s    loc_512B4
0x5123e  ldarg.3
0x5123f  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x51244  callvirt instance valuetype [System.Data]System.Data.IsolationLevel [System.Data]System.Data.IDbTransaction::get_IsolationLevel()
0x51249  ldloc.s  5
0x5124b  beq.s    loc_512B4
0x5124d  ldarg.0
0x5124e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x51253  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x51258  ldc.i4.0
0x51259  ldc.i4.0
0x5125a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x5125f  stloc.1
0x51260  ldloc.1
0x51261  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x51266  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::.ctor(string)
0x5126b  stloc.s  7
0x5126d  ldloc.s  7
0x5126f  ldc.i4.0
0x51270  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_MinPoolSize(int32)
0x51275  ldloc.s  7
0x51277  ldsfld   int32 Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::MetaDataCacheConnectionMaxPoolSize
0x5127c  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_MaxPoolSize(int32)
0x51281  ldloc.1
0x51282  ldloc.s  7
0x51284  callvirt instance string [System.Data]System.Data.Common.DbConnectionStringBuilder::get_ConnectionString()
0x51289  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::set_ConnectionString(string)
0x5128e  ldloc.1
0x5128f  ldsfld   int32 Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::MetaDataCacheConnectionMaxPoolSize
0x51294  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::set_SqlMaxPoolSize(int32)
0x51299  ldloc.1
0x5129a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x5129f  ldc.i4.1
0x512a0  stloc.3
0x512a1  call     bool Microsoft.Crm.Caching.CacheConfiguration::get_IsParallelLoadMetadataContainerEnabled()
0x512a6  brtrue.s loc_512B4
0x512a8  ldloc.1
0x512a9  ldloc.s  5
0x512ab  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::BeginTransaction(valuetype [System.Data]System.Data.IsolationLevel)
0x512b0  stloc.2
0x512b1  ldc.i4.1
0x512b2  stloc.s  4
0x512b4  ldloc.1
0x512b5  ldloc.2
0x512b6  ldsfld   int32 Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::MetaDataCacheConnectionMaxPoolSize
0x512bb  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess Microsoft.Crm.Metadata.Helpers::GetSqlDataAccesser(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, class [System.Data]System.Data.IDbTransaction transaction, [opt] int32 sqlMaxPoolSize)
0x512c0  stloc.s  6
0x512c2  ldarg.s  5
0x512c4  ldloc.s  6
0x512c6  callvirt instance class Microsoft.Crm.Metadata.IMetadataContainer BuildMetadataContainerFromDatabaseTemplate::Invoke(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser)
0x512cb  stloc.s  8
0x512cd  leave.s  loc_51347
0x512cf  stloc.s  9
0x512d1  ldloc.s  9
0x512d3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x512d8  ldc.i4.s 0x1D
0x512da  ldstr    aExceptionWhile_0// "Exception while loading Metadata Cache "...
0x512df  ldc.i4.4
0x512e0  newarr   [mscorlib]System.Object
0x512e5  dup
0x512e6  ldc.i4.0
0x512e7  ldarg.1
0x512e8  box      Microsoft.Crm.Metadata.LoadMasks
0x512ed  stelem.ref
0x512ee  dup
0x512ef  ldc.i4.1
0x512f0  ldloc.3
0x512f1  brtrue.s loc_512FA
0x512f3  ldstr    aExisting// "existing"
0x512f8  br.s     loc_512FF
0x512fa  ldstr    aNew// "new"
0x512ff  stelem.ref
0x51300  dup
0x51301  ldc.i4.2
0x51302  ldloc.s  4
0x51304  brtrue.s loc_5130D
0x51306  ldstr    aExisting// "existing"
0x5130b  br.s     loc_51312
0x5130d  ldstr    aNew// "new"
0x51312  stelem.ref
0x51313  dup
0x51314  ldc.i4.3
0x51315  ldloc.s  9
0x51317  stelem.ref
0x51318  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5131d  rethrow
0x5131f  ldloc.s  4
0x51321  brfalse.s loc_51329
0x51323  ldloc.2
0x51324  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51329  ldloc.3
0x5132a  brfalse.s loc_51332
0x5132c  ldloc.1
0x5132d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Dispose()
0x51332  ldstr    aAspEndMdcacheL_0// "ASP_END_MDCACHE_LOADCACHE_LOAD_DATA_SET"
0x51337  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x5133c  endfinally
0x5133d  ldloc.0
0x5133e  brfalse.s loc_51346
0x51340  ldloc.0
0x51341  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51346  endfinally
0x51347  ldloc.s  8
0x51349  ret
```
