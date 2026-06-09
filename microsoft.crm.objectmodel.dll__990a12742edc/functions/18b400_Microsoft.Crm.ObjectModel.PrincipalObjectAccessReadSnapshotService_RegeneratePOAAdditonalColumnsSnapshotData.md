# Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotService::RegeneratePOAAdditonalColumnsSnapshotData

- ea: `0x18b400`
- end: `0x18be3c`
- name: `Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotService::RegeneratePOAAdditonalColumnsSnapshotData`
- size: `2620`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18afc0`

## callees

- `0x6f530`
- `0x6f540`
- `0x6f590`
- `0x8c750`
- `0x8c7a0`
- `0x18b400`

## string_xrefs

- `0x18b7a0`: `PrincipalObjectAccessReadSnapshot`
- `0x18b472`: `D:\a\1\s\src\Core\ObjectModel\Services\Sharing\PrincipalObjectAccessReadSnapshotService.cs`
- `0x18b4fe`: `D:\a\1\s\src\Core\ObjectModel\Services\Sharing\PrincipalObjectAccessReadSnapshotService.cs`
- `0x18b903`: `D:\a\1\s\src\Core\ObjectModel\Services\Sharing\PrincipalObjectAccessReadSnapshotService.cs`
- `0x18b45c`: `IF (OBJECT_ID('p_ObjectTypeCodeReadSharesOwneridOwningBUdistribution') IS NULL) \n												  SELECT 0 AS SPExists\n												ELSE \n												  SELECT 1 AS SPExists`
- `0x18b4b3`: `SELECT rcs.Count AS 'RecordCount', \n											  poarsSummary.ObjectTypeCode, poarsSummary.Max_OTCReadShareByUID, poarsSummary.Avg_OTCReadShareByUID, \n											  poarsSummary.STDEV_OTCReadShareByUID, poarsSummary.Count_OTCReadShareByUID \n											  FROM RecordCountSnapshot rcs, \n												  (SELECT ObjectTypeCode, \n												  MAX(poars.[Count]) AS Max_OTCReadShareByUID, \n												  AVG(poars.[Count]) AS Avg_OTCReadShareByUID, \n												  STDEV(poars.[Count]) AS STDEV`
- `0x18b4d4`: `Stored procedure p_ObjectTypeCodeReadSharesOwneridOwningBUdistribution does not exists.Executing Query : {0}`
- `0x18b597`: `Max_OTCReadShareByUID`
- `0x18b5a5`: `Max_OTCReadShareByUID`
- `0x18b5c2`: `Max_OTCReadShareByUID`
- `0x18b99c`: `Max_OTCReadShareByUID`
- `0x18b9aa`: `Max_OTCReadShareByUID`
- `0x18b9c7`: `Max_OTCReadShareByUID`
- `0x18b5de`: `Avg_OTCReadShareByUID`
- `0x18b5ec`: `Avg_OTCReadShareByUID`
- `0x18b609`: `Avg_OTCReadShareByUID`
- `0x18b9e3`: `Avg_OTCReadShareByUID`
- `0x18b9f1`: `Avg_OTCReadShareByUID`
- `0x18ba0e`: `Avg_OTCReadShareByUID`
- `0x18b625`: `STDEV_OTCReadShareByUID`
- `0x18b633`: `STDEV_OTCReadShareByUID`
- `0x18b650`: `STDEV_OTCReadShareByUID`
- `0x18ba2a`: `STDEV_OTCReadShareByUID`
- `0x18ba38`: `STDEV_OTCReadShareByUID`
- `0x18ba55`: `STDEV_OTCReadShareByUID`
- `0x18b682`: `Count_OTCReadShareByUID`
- `0x18b690`: `Count_OTCReadShareByUID`
- `0x18b6ad`: `Count_OTCReadShareByUID`
- `0x18ba87`: `Count_OTCReadShareByUID`
- `0x18ba95`: `Count_OTCReadShareByUID`
- `0x18bab2`: `Count_OTCReadShareByUID`
- `0x18b775`: `p_ObjectTypeCodeReadSharesOwneridOwningBUdistribution`
- `0x18b787`: `Stored procedure p_ObjectTypeCodeReadSharesOwneridOwningBUdistribution exists.Executing query: `
- `0x18b7d3`: `POARSupdatePOAReadSnapshotTable`
- `0x18b81b`: `@updatePOAReadSnapshotTable`
- `0x18be1f`: ` Error while Regenerating principal object access read snapshot additional Telemetry data for organization Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x18b400  ldc.i4.m1
0x18b401  stloc.0
0x18b402  ldc.i4.m1
0x18b403  conv.i8
0x18b404  stloc.1
0x18b405  ldc.r8   -1.0
0x18b40e  stloc.2
0x18b40f  ldc.r8   -1.0
0x18b418  stloc.3
0x18b419  ldc.r8   -1.0
0x18b422  stloc.s  4
0x18b424  ldc.i4.m1
0x18b425  conv.i8
0x18b426  stloc.s  5
0x18b428  ldc.i4.m1
0x18b429  conv.i8
0x18b42a  stloc.s  6
0x18b42c  ldc.i4.m1
0x18b42d  conv.i8
0x18b42e  stloc.s  7
0x18b430  ldc.i4.m1
0x18b431  conv.i8
0x18b432  stloc.s  8
0x18b434  ldc.i4.m1
0x18b435  conv.i8
0x18b436  stloc.s  9
0x18b438  ldc.i4.m1
0x18b439  conv.i8
0x18b43a  stloc.s  0xA
0x18b43c  ldc.i4.m1
0x18b43d  conv.i8
0x18b43e  stloc.s  0xB
0x18b440  ldc.i4.m1
0x18b441  conv.i8
0x18b442  stloc.s  0xC
0x18b444  ldc.i4.m1
0x18b445  conv.i8
0x18b446  stloc.s  0xD
0x18b448  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x18b44d  stloc.s  0xE
0x18b44f  ldarg.1
0x18b450  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x18b455  stloc.s  0xF
0x18b457  ldc.i4.0
0x18b458  stloc.s  0x10
0x18b45a  ldloc.s  0xF
0x18b45c  ldstr    aIfObjectIdPObj// "IF (OBJECT_ID('p_ObjectTypeCodeReadShar"...
0x18b461  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x18b466  ldloc.s  0xF
0x18b468  ldc.i4   0x9C
0x18b46d  ldstr    aRegeneratepoaa// "RegeneratePOAAdditonalColumnsSnapshotDa"...
0x18b472  ldstr    aDA1SSrcCoreObj_50// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x18b477  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x18b47c  stloc.s  0x11
0x18b47e  br.s     loc_18B493
0x18b480  ldloc.s  0x11
0x18b482  ldstr    aSpexists// "SPExists"
0x18b487  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b48c  unbox.any [mscorlib]System.Int32
0x18b491  stloc.s  0x10
0x18b493  ldloc.s  0x11
0x18b495  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x18b49a  brtrue.s loc_18B480
0x18b49c  leave.s  loc_18B4AA
0x18b49e  ldloc.s  0x11
0x18b4a0  brfalse.s loc_18B4A9
0x18b4a2  ldloc.s  0x11
0x18b4a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b4a9  endfinally
0x18b4aa  ldloc.s  0x10
0x18b4ac  brtrue   loc_18B773
0x18b4b1  ldloc.s  0xF
0x18b4b3  ldstr    aSelectRcsCount// "SELECT rcs.Count AS 'RecordCount', \r\n"...
0x18b4b8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x18b4bd  ldloc.s  0xE
0x18b4bf  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x18b4c4  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b4c9  ldarg.1
0x18b4ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x18b4cf  ldstr    aRegeneratepoaa// "RegeneratePOAAdditonalColumnsSnapshotDa"...
0x18b4d4  ldstr    aStoredProcedur// "Stored procedure p_ObjectTypeCodeReadSh"...
0x18b4d9  ldloc.s  0xF
0x18b4db  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b4e0  call     string [mscorlib]System.String::Format(string, object)
0x18b4e5  ldc.i4.m1
0x18b4e6  ldloc.s  0xF
0x18b4e8  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b4ed  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b4f2  ldloc.s  0xF
0x18b4f4  ldc.i4   0xB7
0x18b4f9  ldstr    aRegeneratepoaa// "RegeneratePOAAdditonalColumnsSnapshotDa"...
0x18b4fe  ldstr    aDA1SSrcCoreObj_50// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x18b503  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x18b508  stloc.s  0x12
0x18b50a  br       loc_18B70F
0x18b50f  ldloc.s  0x12
0x18b511  ldstr    aRecordcount// "RecordCount"
0x18b516  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b51b  brfalse.s loc_18B552
0x18b51d  ldloc.s  0x12
0x18b51f  ldstr    aRecordcount// "RecordCount"
0x18b524  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b529  callvirt instance string [mscorlib]System.Object::ToString()
0x18b52e  ldsfld   string [mscorlib]System.String::Empty
0x18b533  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18b538  brtrue.s loc_18B552
0x18b53a  ldloc.s  0x12
0x18b53c  ldstr    aRecordcount// "RecordCount"
0x18b541  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b546  callvirt instance string [mscorlib]System.Object::ToString()
0x18b54b  call     int64 [mscorlib]System.Convert::ToInt64(string)
0x18b550  br.s     loc_18B554
0x18b552  ldc.i4.m1
0x18b553  conv.i8
0x18b554  stloc.1
0x18b555  ldloc.s  0x12
0x18b557  ldstr    aObjecttypecode_2// "ObjectTypeCode"
0x18b55c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b561  brfalse.s loc_18B593
0x18b563  ldloc.s  0x12
0x18b565  ldstr    aObjecttypecode_2// "ObjectTypeCode"
0x18b56a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b56f  callvirt instance string [mscorlib]System.Object::ToString()
0x18b574  ldsfld   string [mscorlib]System.String::Empty
0x18b579  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18b57e  brtrue.s loc_18B593
0x18b580  ldloc.s  0x12
0x18b582  ldstr    aObjecttypecode_2// "ObjectTypeCode"
0x18b587  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b58c  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x18b591  br.s     loc_18B594
0x18b593  ldc.i4.m1
0x18b594  stloc.0
0x18b595  ldloc.s  0x12
0x18b597  ldstr    aMaxOtcreadshar// "Max_OTCReadShareByUID"
0x18b59c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b5a1  brfalse.s loc_18B5D8
0x18b5a3  ldloc.s  0x12
0x18b5a5  ldstr    aMaxOtcreadshar// "Max_OTCReadShareByUID"
0x18b5aa  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b5af  callvirt instance string [mscorlib]System.Object::ToString()
0x18b5b4  ldsfld   string [mscorlib]System.String::Empty
0x18b5b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18b5be  brtrue.s loc_18B5D8
0x18b5c0  ldloc.s  0x12
0x18b5c2  ldstr    aMaxOtcreadshar// "Max_OTCReadShareByUID"
0x18b5c7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b5cc  callvirt instance string [mscorlib]System.Object::ToString()
0x18b5d1  call     int64 [mscorlib]System.Convert::ToInt64(string)
0x18b5d6  br.s     loc_18B5DA
0x18b5d8  ldc.i4.m1
0x18b5d9  conv.i8
0x18b5da  stloc.s  5
0x18b5dc  ldloc.s  0x12
0x18b5de  ldstr    aAvgOtcreadshar// "Avg_OTCReadShareByUID"
0x18b5e3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b5e8  brfalse.s loc_18B61F
0x18b5ea  ldloc.s  0x12
0x18b5ec  ldstr    aAvgOtcreadshar// "Avg_OTCReadShareByUID"
0x18b5f1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b5f6  callvirt instance string [mscorlib]System.Object::ToString()
0x18b5fb  ldsfld   string [mscorlib]System.String::Empty
0x18b600  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18b605  brtrue.s loc_18B61F
0x18b607  ldloc.s  0x12
0x18b609  ldstr    aAvgOtcreadshar// "Avg_OTCReadShareByUID"
0x18b60e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b613  callvirt instance string [mscorlib]System.Object::ToString()
0x18b618  call     int64 [mscorlib]System.Convert::ToInt64(string)
0x18b61d  br.s     loc_18B621
0x18b61f  ldc.i4.m1
0x18b620  conv.i8
0x18b621  stloc.s  6
0x18b623  ldloc.s  0x12
0x18b625  ldstr    aStdevOtcreadsh// "STDEV_OTCReadShareByUID"
0x18b62a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b62f  brfalse.s loc_18B675
0x18b631  ldloc.s  0x12
0x18b633  ldstr    aStdevOtcreadsh// "STDEV_OTCReadShareByUID"
0x18b638  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b63d  callvirt instance string [mscorlib]System.Object::ToString()
0x18b642  ldsfld   string [mscorlib]System.String::Empty
0x18b647  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18b64c  brtrue.s loc_18B675
0x18b64e  ldloc.s  0x12
0x18b650  ldstr    aStdevOtcreadsh// "STDEV_OTCReadShareByUID"
0x18b655  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b65a  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Convert::ToDecimal(object)
0x18b65f  ldc.i4.2
0x18b660  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Math::Round(valuetype [mscorlib]System.Decimal, int32)
0x18b665  stloc.s  0x14
0x18b667  ldloca.s 0x14
0x18b669  call     instance string [mscorlib]System.Decimal::ToString()
0x18b66e  call     float64 [mscorlib]System.Convert::ToDouble(string)
0x18b673  br.s     loc_18B67E
0x18b675  ldc.r8   -1.0
0x18b67e  stloc.s  4
0x18b680  ldloc.s  0x12
0x18b682  ldstr    aCountOtcreadsh// "Count_OTCReadShareByUID"
0x18b687  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b68c  brfalse.s loc_18B6C3
0x18b68e  ldloc.s  0x12
0x18b690  ldstr    aCountOtcreadsh// "Count_OTCReadShareByUID"
0x18b695  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b69a  callvirt instance string [mscorlib]System.Object::ToString()
0x18b69f  ldsfld   string [mscorlib]System.String::Empty
0x18b6a4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18b6a9  brtrue.s loc_18B6C3
0x18b6ab  ldloc.s  0x12
0x18b6ad  ldstr    aCountOtcreadsh// "Count_OTCReadShareByUID"
0x18b6b2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x18b6b7  callvirt instance string [mscorlib]System.Object::ToString()
0x18b6bc  call     int64 [mscorlib]System.Convert::ToInt64(string)
0x18b6c1  br.s     loc_18B6C5
0x18b6c3  ldc.i4.m1
0x18b6c4  conv.i8
0x18b6c5  stloc.s  7
0x18b6c7  ldarg.1
0x18b6c8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b6cd  ldloc.0
0x18b6ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x18b6d3  stloc.s  0x13
0x18b6d5  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessEventSource::get_Instance()
0x18b6da  ldarg.1
0x18b6db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x18b6e0  ldloc.1
0x18b6e1  ldloc.0
0x18b6e2  ldloc.s  0x13
0x18b6e4  brfalse.s loc_18B6EF
0x18b6e6  ldloc.s  0x13
0x18b6e8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x18b6ed  br.s     loc_18B6F4
0x18b6ef  ldsfld   string [mscorlib]System.String::Empty
0x18b6f4  ldloc.s  5
0x18b6f6  ldloc.s  6
0x18b6f8  ldloc.s  4
0x18b6fa  ldloc.s  7
0x18b6fc  ldloc.s  8
0x18b6fe  ldloc.s  9
0x18b700  ldloc.3
0x18b701  ldloc.s  0xA
0x18b703  ldloc.s  0xB
0x18b705  ldloc.s  0xC
0x18b707  ldloc.2
0x18b708  ldloc.s  0xD
0x18b70a  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessEventSource::LogPrincipalObjectAccessDistribution(valuetype [mscorlib]System.Guid organizationId, int64 recordCount, int32 objectTypeCode, string entityName, int64 maxOTCReadShareByUID, int64 avgOTCReadShareByUID, float64 stdevOTCReadShareByUID, int64 countOTCReadShareByUID, int64 maxOTCForOwnerIDByUID, int64 avgOTCForOwnerIDByUID, float64 stdevOTCForOwnerIDByUID, int64 countOTCForOwnerIDByUID, int64 maxOTCForOwningBUByUID, int64 avgOTCForOwningBUByUID, float64 stdevOTCForOwningBUByUID, int64 countOTCForOwningBUByUID)
0x18b70f  ldloc.s  0x12
0x18b711  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x18b716  brtrue   loc_18B50F
0x18b71b  leave.s  loc_18B729
0x18b71d  ldloc.s  0x12
0x18b71f  brfalse.s loc_18B728
0x18b721  ldloc.s  0x12
0x18b723  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18b728  endfinally
0x18b729  ldloc.s  0xE
0x18b72b  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x18b730  call     class Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::get_Instance()
0x18b735  ldarg.1
0x18b736  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x18b73b  ldstr    aRegeneratepoaa// "RegeneratePOAAdditonalColumnsSnapshotDa"...
0x18b740  ldstr    aQueryExecuted0// "Query executed : {0}"
0x18b745  ldloc.s  0xF
0x18b747  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b74c  call     string [mscorlib]System.String::Format(string, object)
0x18b751  ldloc.s  0xE
0x18b753  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x18b758  stloc.s  0x15
0x18b75a  ldloca.s 0x15
0x18b75c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x18b761  conv.i4
0x18b762  ldloc.s  0xF
0x18b764  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b769  callvirt instance void Microsoft.Crm.ObjectModel.PrincipalObjectAccessReadSnapshotEventSource::PoarsInformation(valuetype [mscorlib]System.Guid organizationId, string moduleName, string message, int32 executionTimeInSec, string sqlText)
0x18b76e  br       loc_18BDD5
0x18b773  ldloc.s  0xF
0x18b775  ldstr    aPObjecttypecod// "p_ObjectTypeCodeReadSharesOwneridOwning"...
0x18b77a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x18b77f  ldloc.s  0xF
0x18b781  ldc.i4.4
0x18b782  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x18b787  ldstr    aStoredProcedur_0// "Stored procedure p_ObjectTypeCodeReadSh"...
0x18b78c  ldloc.s  0xF
0x18b78e  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x18b793  call     string [mscorlib]System.String::Concat(string, string)
0x18b798  stloc.s  0x16
0x18b79a  ldarg.1
0x18b79b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b7a0  ldstr    aPrincipalobjec// "PrincipalObjectAccessReadSnapshot"
0x18b7a5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x18b7aa  ldstr    aCountpercentof// "countpercentoftotalrows"
0x18b7af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x18b7b4  brfalse  loc_18B8D1
0x18b7b9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x18b7be  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x18b7c3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_UseAdditionalPOAData()
0x18b7c8  ldarg.1
0x18b7c9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b7ce  brfalse  loc_18B8D1
0x18b7d3  ldstr    aPoarsupdatepoa// "POARSupdatePOAReadSnapshotTable"
  ... truncated ...
```
