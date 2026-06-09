# Microsoft.Crm.Metadata.MetadataSyncChangesHelper::GetFromDatabaseNewSyncTimeAndExpiredSyncTimeThreshold

- ea: `0x5e050`
- end: `0x5e19d`
- name: `Microsoft.Crm.Metadata.MetadataSyncChangesHelper::GetFromDatabaseNewSyncTimeAndExpiredSyncTimeThreshold`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5de70`

## callees

- `0x5dfc0`
- `0x5e050`

## string_xrefs

- `0x5e06c`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SDK\MetadataSyncChangesGenerator.cs`
- `0x5e0c6`: `metadatasynclasttimeofneverexpireddeletedobjects`
- `0x5e0ea`: `metadatasynclasttimeofneverexpireddeletedobjects`
- `0x5e15f`: `metadatasynclasttimeofneverexpireddeletedobjects`
- `0x5e16d`: `metadatasynclasttimeofneverexpireddeletedobjects`

## pseudocode

```c

```

## disassembly

```asm
0x5e050  ldarg.0
0x5e051  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5e056  ldstr    aDeclareNewsync// "declare @newSyncTime DateTime = GETUTCD"...
0x5e05b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x5e060  stloc.2
0x5e061  ldloc.2
0x5e062  ldc.i4   0xA0
0x5e067  ldstr    aGetfromdatabas// "GetFromDatabaseNewSyncTimeAndExpiredSyn"...
0x5e06c  ldstr    aDA1SSrcCoreObj_7// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x5e071  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5e076  stloc.3
0x5e077  ldloc.3
0x5e078  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x5e07d  pop
0x5e07e  ldloc.3
0x5e07f  ldstr    aNewsynctime// "NewSyncTime"
0x5e084  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5e089  unbox.any [mscorlib]System.DateTime
0x5e08e  stloc.0
0x5e08f  ldloc.3
0x5e090  ldstr    aExpiredsynctim// "ExpiredSyncTimeThreshold"
0x5e095  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x5e09a  unbox.any [mscorlib]System.DateTime
0x5e09f  stloc.1
0x5e0a0  leave.s  loc_5E0B6
0x5e0a2  ldloc.3
0x5e0a3  brfalse.s loc_5E0AB
0x5e0a5  ldloc.3
0x5e0a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e0ab  endfinally
0x5e0ac  ldloc.2
0x5e0ad  brfalse.s loc_5E0B5
0x5e0af  ldloc.2
0x5e0b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e0b5  endfinally
0x5e0b6  ldarg.0
0x5e0b7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5e0bc  ldstr    aOrganization// "Organization"
0x5e0c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x5e0c6  ldstr    aMetadatasyncla// "metadatasynclasttimeofneverexpireddelet"...
0x5e0cb  ldc.i4.1
0x5e0cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x5e0d1  brfalse  loc_5E195
0x5e0d6  ldstr    aOrganization// "Organization"
0x5e0db  ldarg.0
0x5e0dc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5e0e1  stloc.s  4
0x5e0e3  ldloc.s  4
0x5e0e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5e0ea  ldstr    aMetadatasyncla// "metadatasynclasttimeofneverexpireddelet"...
0x5e0ef  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5e0f4  ldloc.s  4
0x5e0f6  ldc.i4.1
0x5e0f7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0x5e0fc  ldloc.s  4
0x5e0fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x5e103  ldc.i4.0
0x5e104  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_Count(int32)
0x5e109  ldloc.s  4
0x5e10b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x5e110  ldc.i4.0
0x5e111  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_ReturnTotalRecordCount(bool)
0x5e116  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OrganizationService::.ctor()
0x5e11b  stloc.s  6
0x5e11d  ldarg.0
0x5e11e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5e123  stloc.s  8
0x5e125  ldloc.s  6
0x5e127  ldloc.s  4
0x5e129  ldarg.0
0x5e12a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5e12f  stloc.s  5
0x5e131  leave.s  loc_5E13F
0x5e133  ldloc.s  8
0x5e135  brfalse.s loc_5E13E
0x5e137  ldloc.s  8
0x5e139  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e13e  endfinally
0x5e13f  ldc.i4.1
0x5e140  ldloc.s  5
0x5e142  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5e147  ceq
0x5e149  ldstr    aTherreMustBeOn// "Therre must be one and only one Organiz"...
0x5e14e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5e153  ldloc.s  5
0x5e155  ldc.i4.0
0x5e156  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x5e15b  stloc.s  7
0x5e15d  ldloc.s  7
0x5e15f  ldstr    aMetadatasyncla// "metadatasynclasttimeofneverexpireddelet"...
0x5e164  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5e169  brtrue.s loc_5E195
0x5e16b  ldloc.s  7
0x5e16d  ldstr    aMetadatasyncla// "metadatasynclasttimeofneverexpireddelet"...
0x5e172  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x5e177  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x5e17c  stloc.s  9
0x5e17e  ldloc.1
0x5e17f  ldloc.s  9
0x5e181  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTimeWithMilliseconds()
0x5e186  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5e18b  brfalse.s loc_5E195
0x5e18d  ldloc.s  9
0x5e18f  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTimeWithMilliseconds()
0x5e194  stloc.1
0x5e195  ldloc.0
0x5e196  ldloc.1
0x5e197  newobj   instance void Microsoft.Crm.Metadata.MetadataSyncTimeAndExpiredThreshold::.ctor(valuetype [mscorlib]System.DateTime syncTime, valuetype [mscorlib]System.DateTime expiredSyncTimeThreshold)
0x5e19c  ret
```
