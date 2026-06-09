# Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotService::RegenerateReadSharingSnapshotData

- ea: `0x18afc0`
- end: `0x18b3ed`
- name: `Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotService::RegenerateReadSharingSnapshotData`
- size: `1069`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xf0a10`

## callees

- `0x6f530`
- `0x6f540`
- `0xce270`
- `0x18afc0`
- `0x18b400`

## string_xrefs

- `0x18b030`: `PrincipalObjectAccessReadSnapshot`
- `0x18b355`: `maxdepthforhierarchicalsecuritymodel`
- `0x18b05c`: `Regenerating principal object access read snapshot data for organization {0}.Entities count = {1}`
- `0x18b089`: `RegenerateReadSharingSnapshotData`
- `0x18b0f9`: `RegenerateReadSharingSnapshotData`
- `0x18b195`: `RegenerateReadSharingSnapshotData`
- `0x18b1b7`: `RegenerateReadSharingSnapshotData`
- `0x18b21a`: `RegenerateReadSharingSnapshotData`
- `0x18b2bc`: `RegenerateReadSharingSnapshotData`
- `0x18b303`: `RegenerateReadSharingSnapshotData`
- `0x18b385`: `RegenerateReadSharingSnapshotData`
- `0x18b3d7`: `RegenerateReadSharingSnapshotData`
- `0x18b0a3`: `Regenerating principal object access read snapshot data for organization {0}`
- `0x18b0e4`: `exec p_ReinitPrincipalObjectAccessReadSnapshots @minimumCount,@isHierarchicalSecurityModelEnabled`
- `0x18b0fe`: `Executing query : {0}{1}Parameters:{2}@minimumCount={3}{4}isHierarchicalSecurityModelEnabled={5}`
- `0x18b17a`: `@isHierarchicalSecurityModelEnabled`
- `0x18b19a`: `D:\a\1\s\src\Core\ObjectModel\Services\Sharing\PrincipalObjectAccessReadSnapshotService.cs`
- `0x18b1f8`: `Regenerated principal object access read snapshot data for organization {0}`
- `0x18b24e`: `RegenerateReadSharingSnapshotData:RegeneratePOAAdditonalColumnsSnapshotData`
- `0x18b281`: `RegenerateReadSharingSnapshotData:RegeneratePOAAdditonalColumnsSnapshotData`
- `0x18b286`: `Completed Execution : RegeneratePOAAdditonalColumnsSnapshotData`
- `0x18b2c1`: `Flushed POA read snapshot cache entry for organization: {0}`
- `0x18b38a`: `Updated the maxDepthForHSM for the Org: {0} with value: {1}`
- `0x18b3dc`: `MaxDepthForHSM : flushed Organization cache.`

## pseudocode

```c

```

## disassembly

```asm
0x18afc0  ldstr    aSharinglimitfo// "SharingLimitForPOASnapshotTable"
0x18afc5  ldc.i4.s 0xA
0x18afc7  box      [mscorlib]System.Int32
0x18afcc  call     object [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSetting(string, object)
0x18afd1  unbox.any [mscorlib]System.Int32
0x18afd6  stloc.0
0x18afd7  ldstr    aSharinglimitfo// "SharingLimitForPOASnapshotTable"
0x18afdc  ldloc.0
0x18afdd  box      [mscorlib]System.Int32
0x18afe2  ldarg.1
0x18afe3  call     object [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveSettingFromRegistryOrOrgDBOrgSettings(string, object, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18afe8  unbox.any [mscorlib]System.Int32
0x18afed  stloc.1
0x18afee  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::.ctor()
0x18aff3  ldstr    aEntity// "Entity"
0x18aff8  ldarg.1
0x18aff9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18affe  stloc.2
0x18afff  ldloc.2
0x18b000  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x18b005  ldarg.1
0x18b006  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b00b  ldstr    aEntity// "Entity"
0x18b010  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata::GetMetadataEntityByName(string)
0x18b015  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x18b01a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x18b01f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x18b024  ldloc.2
0x18b025  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x18b02a  ldstr    aName// "name"
0x18b02f  ldc.i4.0
0x18b030  ldstr    aPrincipalobjec// "PrincipalObjectAccessReadSnapshot"
0x18b035  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x18b03a  ldloc.2
0x18b03b  ldarg.1
0x18b03c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18b041  stloc.3
0x18b042  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x18b047  stloc.s  4
0x18b049  ldloc.s  4
0x18b04b  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x18b050  ldloc.3
0x18b051  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x18b056  ldc.i4.0
0x18b057  ble      loc_18B23C
0x18b05c  ldstr    aRegeneratingPr// "Regenerating principal object access re"...
0x18b061  ldarg.1
0x18b062  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b067  box      [mscorlib]System.Guid
0x18b06c  ldloc.3
0x18b06d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x18b072  box      [mscorlib]System.Int32
0x18b077  call     string [mscorlib]System.String::Format(string, object, object)
0x18b07c  stloc.s  6
0x18b07e  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b083  ldarg.1
0x18b084  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b089  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b08e  ldloc.s  6
0x18b090  ldc.i4.m1
0x18b091  ldsfld   string [mscorlib]System.String::Empty
0x18b096  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b09b  ldarg.1
0x18b09c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b0a1  ldc.i4.s 0x14
0x18b0a3  ldstr    aRegeneratingPr_0// "Regenerating principal object access re"...
0x18b0a8  ldc.i4.1
0x18b0a9  newarr   [mscorlib]System.Object
0x18b0ae  dup
0x18b0af  ldc.i4.0
0x18b0b0  ldarg.1
0x18b0b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b0b6  box      [mscorlib]System.Guid
0x18b0bb  stelem.ref
0x18b0bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18b0c1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x18b0c6  ldarg.1
0x18b0c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b0cc  ldarg.1
0x18b0cd  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x18b0d2  stloc.s  7
0x18b0d4  ldarg.1
0x18b0d5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x18b0da  ldc.i4.0
0x18b0db  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x18b0e0  stloc.s  8
0x18b0e2  ldloc.s  8
0x18b0e4  ldstr    aExecPReinitpri// "exec p_ReinitPrincipalObjectAccessReadS"...
0x18b0e9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x18b0ee  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b0f3  ldarg.1
0x18b0f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b0f9  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b0fe  ldstr    aExecutingQuery// "Executing query : {0}{1}Parameters:{2}@"...
0x18b103  ldc.i4.6
0x18b104  newarr   [mscorlib]System.Object
0x18b109  dup
0x18b10a  ldc.i4.0
0x18b10b  ldloc.s  8
0x18b10d  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b112  stelem.ref
0x18b113  dup
0x18b114  ldc.i4.1
0x18b115  call     string [mscorlib]System.Environment::get_NewLine()
0x18b11a  stelem.ref
0x18b11b  dup
0x18b11c  ldc.i4.2
0x18b11d  call     string [mscorlib]System.Environment::get_NewLine()
0x18b122  stelem.ref
0x18b123  dup
0x18b124  ldc.i4.3
0x18b125  ldloc.1
0x18b126  box      [mscorlib]System.Int32
0x18b12b  stelem.ref
0x18b12c  dup
0x18b12d  ldc.i4.4
0x18b12e  call     string [mscorlib]System.Environment::get_NewLine()
0x18b133  stelem.ref
0x18b134  dup
0x18b135  ldc.i4.5
0x18b136  ldloc.s  7
0x18b138  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsHierarchicalSecurityModelEnabled()
0x18b13d  box      [mscorlib]System.Boolean
0x18b142  stelem.ref
0x18b143  call     string [mscorlib]System.String::Format(string, object[])
0x18b148  ldc.i4.m1
0x18b149  ldloc.s  8
0x18b14b  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b150  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b155  ldloc.s  4
0x18b157  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x18b15c  ldloc.s  8
0x18b15e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x18b163  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x18b168  dup
0x18b169  ldstr    aMinimumcount// "@minimumCount"
0x18b16e  ldloc.1
0x18b16f  box      [mscorlib]System.Int32
0x18b174  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18b179  pop
0x18b17a  ldstr    aIshierarchical_0// "@isHierarchicalSecurityModelEnabled"
0x18b17f  ldloc.s  7
0x18b181  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsHierarchicalSecurityModelEnabled()
0x18b186  box      [mscorlib]System.Boolean
0x18b18b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18b190  pop
0x18b191  ldloc.s  8
0x18b193  ldc.i4.s 0x4A
0x18b195  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b19a  ldstr    aDA1SSrcCoreObj_50// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x18b19f  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x18b1a4  pop
0x18b1a5  ldloc.s  4
0x18b1a7  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x18b1ac  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b1b1  ldarg.1
0x18b1b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b1b7  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b1bc  ldstr    aQueryExecuted0// "Query executed : {0}"
0x18b1c1  ldloc.s  8
0x18b1c3  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b1c8  call     string [mscorlib]System.String::Format(string, object)
0x18b1cd  ldloc.s  4
0x18b1cf  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x18b1d4  stloc.s  9
0x18b1d6  ldloca.s 9
0x18b1d8  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x18b1dd  conv.i4
0x18b1de  ldloc.s  8
0x18b1e0  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b1e5  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b1ea  leave.s  loc_18B1F8
0x18b1ec  ldloc.s  8
0x18b1ee  brfalse.s loc_18B1F7
0x18b1f0  ldloc.s  8
0x18b1f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b1f7  endfinally
0x18b1f8  ldstr    aRegeneratedPri// "Regenerated principal object access rea"...
0x18b1fd  ldarg.1
0x18b1fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b203  box      [mscorlib]System.Guid
0x18b208  call     string [mscorlib]System.String::Format(string, object)
0x18b20d  stloc.s  6
0x18b20f  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b214  ldarg.1
0x18b215  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b21a  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b21f  ldloc.s  6
0x18b221  ldloc.s  4
0x18b223  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x18b228  stloc.s  9
0x18b22a  ldloca.s 9
0x18b22c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x18b231  conv.i4
0x18b232  ldsfld   string [mscorlib]System.String::Empty
0x18b237  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b23c  ldloc.s  4
0x18b23e  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x18b243  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b248  ldarg.1
0x18b249  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b24e  ldstr    aRegenerateread_0// "RegenerateReadSharingSnapshotData:Regen"...
0x18b253  ldstr    aStartingExecut// "Starting Execution : RegeneratePOAAddit"...
0x18b258  ldc.i4.m1
0x18b259  ldsfld   string [mscorlib]System.String::Empty
0x18b25e  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b263  ldarg.0
0x18b264  ldarg.1
0x18b265  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x18b26a  call     instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotService::RegeneratePOAAdditonalColumnsSnapshotData(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x18b26f  ldloc.s  4
0x18b271  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x18b276  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b27b  ldarg.1
0x18b27c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b281  ldstr    aRegenerateread_0// "RegenerateReadSharingSnapshotData:Regen"...
0x18b286  ldstr    aCompletedExecu// "Completed Execution : RegeneratePOAAddi"...
0x18b28b  ldloc.s  4
0x18b28d  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x18b292  stloc.s  9
0x18b294  ldloca.s 9
0x18b296  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x18b29b  conv.i4
0x18b29c  ldsfld   string [mscorlib]System.String::Empty
0x18b2a1  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b2a6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotCache::Instance()
0x18b2ab  ldarg.1
0x18b2ac  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PrincipalObjectAccessReadSnapshotDictionary>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b2b1  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b2b6  ldarg.1
0x18b2b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b2bc  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b2c1  ldstr    aFlushedPoaRead// "Flushed POA read snapshot cache entry f"...
0x18b2c6  ldarg.1
0x18b2c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b2cc  box      [mscorlib]System.Guid
0x18b2d1  call     string [mscorlib]System.String::Format(string, object)
0x18b2d6  ldc.i4.m1
0x18b2d7  ldsfld   string [mscorlib]System.String::Empty
0x18b2dc  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b2e1  ldc.i4.m1
0x18b2e2  stloc.s  5
0x18b2e4  ldarg.1
0x18b2e5  ldloca.s 5
0x18b2e7  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SettingsHelper::CheckIfSiteSettingForMaxDepthForHSMShouldOverrideOrgSetting(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32&)
0x18b2ec  brfalse  loc_18B3EC
0x18b2f1  ldloc.s  4
0x18b2f3  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x18b2f8  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b2fd  ldarg.1
0x18b2fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b303  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b308  ldstr    aUpdatingTheMax// "Updating the maxDepthForHSM for the Org"...
0x18b30d  ldarg.1
0x18b30e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b313  box      [mscorlib]System.Guid
0x18b318  ldloc.s  5
0x18b31a  box      [mscorlib]System.Int32
0x18b31f  call     string [mscorlib]System.String::Format(string, object, object)
0x18b324  ldc.i4.m1
0x18b325  ldsfld   string [mscorlib]System.String::Empty
0x18b32a  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b32f  ldstr    aOrganization// "Organization"
0x18b334  ldarg.1
0x18b335  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b33a  stloc.s  0xA
0x18b33c  ldloc.s  0xA
0x18b33e  ldstr    aOrganizationid_1// "organizationid"
0x18b343  ldarg.1
0x18b344  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b349  box      [mscorlib]System.Guid
0x18b34e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x18b353  ldloc.s  0xA
0x18b355  ldstr    aMaxdepthforhie// "maxdepthforhierarchicalsecuritymodel"
0x18b35a  ldloc.s  5
0x18b35c  box      [mscorlib]System.Int32
0x18b361  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x18b366  newobj   instance void Microsoft.Crm.ObjectModel.OrganizationService::.ctor()
0x18b36b  ldloc.s  0xA
0x18b36d  ldarg.1
0x18b36e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18b373  ldloc.s  4
0x18b375  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x18b37a  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b37f  ldarg.1
0x18b380  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b385  ldstr    aRegenerateread// "RegenerateReadSharingSnapshotData"
0x18b38a  ldstr    aUpdatedTheMaxd// "Updated the maxDepthForHSM for the Org:"...
0x18b38f  ldarg.1
0x18b390  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18b395  box      [mscorlib]System.Guid
0x18b39a  ldloc.s  5
0x18b39c  box      [mscorlib]System.Int32
0x18b3a1  call     string [mscorlib]System.String::Format(string, object, object)
0x18b3a6  ldloc.s  4
0x18b3a8  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x18b3ad  stloc.s  9
0x18b3af  ldloca.s 9
0x18b3b1  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x18b3b6  conv.i4
  ... truncated ...
```
