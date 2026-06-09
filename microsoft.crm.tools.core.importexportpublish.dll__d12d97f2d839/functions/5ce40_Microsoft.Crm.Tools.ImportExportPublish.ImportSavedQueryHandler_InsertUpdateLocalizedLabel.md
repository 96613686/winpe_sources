# Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::InsertUpdateLocalizedLabel

- ea: `0x5ce40`
- end: `0x5d0a6`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::InsertUpdateLocalizedLabel`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5d4d0`

## callees

- `0x5cd10`
- `0x5cda0`
- `0x5ce40`

## string_xrefs

- `0x5cf8b`: `@OverwriteTime`
- `0x5cfa1`: `@ComponentStatePublished`
- `0x5d04a`: `@ComponentStatePublished`
- `0x5ce89`: `UPDATE LocalizedLabel\n					  SET Label = @LabelValue\n					  WHERE ObjectId = @ObjectIdValue\n						AND ObjectColumnName = @ObjectColumnNameValue\n						AND SolutionId = @SolutionIdValue\n						AND LanguageId = @LanguageIdValue`
- `0x5cef4`: `InsertUpdateLocalizedLabel`
- `0x5d089`: `InsertUpdateLocalizedLabel`
- `0x5cf25`: `INSERT into LocalizedLabel\n							(LocalizedLabelId, LocalizedLabelRowId, LanguageId, ObjectId,\n							 ObjectColumnName, Label, SolutionId, ComponentState, OverwriteTime, LabelTypeCode)\n						  SELECT\n							 LocalizedLabelId, @LocalizedLabelRowIdValue, LanguageId, ObjectId,\n							 ObjectColumnName, @LabelValue, @SolutionId, @ComponentStatePublished, @OverwriteTime, LabelTypeCode\n						  FROM LocalizedLabel where ObjectId = @ObjectIdValue\n							AND OverwriteTime = 0\n							AND`
- `0x5cfce`: `INSERT into LocalizedLabel\n							(LocalizedLabelId, LocalizedLabelRowId, LanguageId, ObjectId,\n							 ObjectColumnName, Label, SolutionId, ComponentState, OverwriteTime, LabelTypeCode)\n						VALUES\n							(@LocalizedLabelIdValue,  @LocalizedLabelRowIdValue, @LanguageIdValue, @ObjectIdValue,\n							 @ObjectColumnNameValue, @LabelValue, @SolutionId, @ComponentStatePublished, 0, @LabelTypeCode) `

## pseudocode

```c

```

## disassembly

```asm
0x5ce40  ldarg.0
0x5ce41  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5ce46  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x5ce4b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x5ce50  stloc.0
0x5ce51  ldloc.0
0x5ce52  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5ce57  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x5ce5c  stloc.1
0x5ce5d  ldloc.0
0x5ce5e  ldarg.0
0x5ce5f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5ce64  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5ce69  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_SqlTransaction()
0x5ce6e  callvirt instance void [System.Data]System.Data.IDbCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction)
0x5ce73  ldarg.0
0x5ce74  ldloc.0
0x5ce75  ldarg.3
0x5ce76  ldarg.s  4
0x5ce78  ldarg.1
0x5ce79  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5ce7e  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::RowExists(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid savedQueryId, int32 languageCode, string columnName, valuetype [mscorlib]System.Guid solutionId)
0x5ce83  brfalse  loc_5CF09
0x5ce88  ldloc.0
0x5ce89  ldstr    aUpdateLocalize// "UPDATE LocalizedLabel\r\n\t\t\t\t\t  SE"...
0x5ce8e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5ce93  ldloc.1
0x5ce94  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x5ce99  ldloc.1
0x5ce9a  ldstr    aLabelvalue// "@LabelValue"
0x5ce9f  ldarg.2
0x5cea0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cea5  pop
0x5cea6  ldloc.1
0x5cea7  ldstr    aObjectidvalue// "@ObjectIdValue"
0x5ceac  ldarg.3
0x5cead  box      [mscorlib]System.Guid
0x5ceb2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5ceb7  pop
0x5ceb8  ldloc.1
0x5ceb9  ldstr    aObjectcolumnna_0// "@ObjectColumnNameValue"
0x5cebe  ldarg.1
0x5cebf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cec4  pop
0x5cec5  ldloc.1
0x5cec6  ldstr    aLanguageidvalu// "@LanguageIdValue"
0x5cecb  ldarg.s  4
0x5cecd  box      [mscorlib]System.Int32
0x5ced2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5ced7  pop
0x5ced8  ldloc.1
0x5ced9  ldstr    aSolutionidvalu// "@SolutionIdValue"
0x5cede  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5cee3  box      [mscorlib]System.Guid
0x5cee8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5ceed  pop
0x5ceee  ldloc.0
0x5ceef  ldc.i4   0x1FB
0x5cef4  ldstr    aInsertupdatelo// "InsertUpdateLocalizedLabel"
0x5cef9  ldstr    aDA1SSrcCoreObj_2// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Im"...
0x5cefe  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5cf03  pop
0x5cf04  leave    loc_5D0A5
0x5cf09  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5cf0e  pop
0x5cf0f  ldarg.0
0x5cf10  ldloc.0
0x5cf11  ldarg.3
0x5cf12  ldarg.s  4
0x5cf14  ldarg.1
0x5cf15  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x5cf1a  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::RowExists(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid savedQueryId, int32 languageCode, string columnName, valuetype [mscorlib]System.DateTime overwriteTime)
0x5cf1f  brfalse  loc_5CFCD
0x5cf24  ldloc.0
0x5cf25  ldstr    aInsertIntoLoca// "INSERT into LocalizedLabel\r\n\t\t\t\t"...
0x5cf2a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5cf2f  ldloc.1
0x5cf30  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x5cf35  ldloc.1
0x5cf36  ldstr    aLocalizedlabel_2// "@LocalizedLabelRowIdValue"
0x5cf3b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x5cf40  box      [mscorlib]System.Guid
0x5cf45  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cf4a  pop
0x5cf4b  ldloc.1
0x5cf4c  ldstr    aLabelvalue// "@LabelValue"
0x5cf51  ldarg.2
0x5cf52  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cf57  pop
0x5cf58  ldloc.1
0x5cf59  ldstr    aObjectidvalue// "@ObjectIdValue"
0x5cf5e  ldarg.3
0x5cf5f  box      [mscorlib]System.Guid
0x5cf64  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cf69  pop
0x5cf6a  ldloc.1
0x5cf6b  ldstr    aObjectcolumnna_0// "@ObjectColumnNameValue"
0x5cf70  ldarg.1
0x5cf71  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cf76  pop
0x5cf77  ldloc.1
0x5cf78  ldstr    aLanguageidvalu// "@LanguageIdValue"
0x5cf7d  ldarg.s  4
0x5cf7f  box      [mscorlib]System.Int32
0x5cf84  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cf89  pop
0x5cf8a  ldloc.1
0x5cf8b  ldstr    aOverwritetime_0// "@OverwriteTime"
0x5cf90  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5cf95  box      [mscorlib]System.DateTime
0x5cf9a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cf9f  pop
0x5cfa0  ldloc.1
0x5cfa1  ldstr    aComponentstate_1// "@ComponentStatePublished"
0x5cfa6  ldc.i4.0
0x5cfa7  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x5cfac  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cfb1  pop
0x5cfb2  ldloc.1
0x5cfb3  ldstr    aSolutionid_2// "@SolutionId"
0x5cfb8  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5cfbd  box      [mscorlib]System.Guid
0x5cfc2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cfc7  pop
0x5cfc8  br       loc_5D083
0x5cfcd  ldloc.0
0x5cfce  ldstr    aInsertIntoLoca_0// "INSERT into LocalizedLabel\r\n\t\t\t\t"...
0x5cfd3  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5cfd8  ldloc.1
0x5cfd9  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x5cfde  ldloc.1
0x5cfdf  ldstr    aLocalizedlabel_3// "@LocalizedLabelIdValue"
0x5cfe4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x5cfe9  box      [mscorlib]System.Guid
0x5cfee  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cff3  pop
0x5cff4  ldloc.1
0x5cff5  ldstr    aLocalizedlabel_2// "@LocalizedLabelRowIdValue"
0x5cffa  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x5cfff  box      [mscorlib]System.Guid
0x5d004  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d009  pop
0x5d00a  ldloc.1
0x5d00b  ldstr    aLanguageidvalu// "@LanguageIdValue"
0x5d010  ldarg.s  4
0x5d012  box      [mscorlib]System.Int32
0x5d017  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d01c  pop
0x5d01d  ldloc.1
0x5d01e  ldstr    aObjectidvalue// "@ObjectIdValue"
0x5d023  ldarg.3
0x5d024  box      [mscorlib]System.Guid
0x5d029  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d02e  pop
0x5d02f  ldloc.1
0x5d030  ldstr    aObjectcolumnna_0// "@ObjectColumnNameValue"
0x5d035  ldarg.1
0x5d036  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d03b  pop
0x5d03c  ldloc.1
0x5d03d  ldstr    aLabelvalue// "@LabelValue"
0x5d042  ldarg.2
0x5d043  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d048  pop
0x5d049  ldloc.1
0x5d04a  ldstr    aComponentstate_1// "@ComponentStatePublished"
0x5d04f  ldc.i4.0
0x5d050  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x5d055  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d05a  pop
0x5d05b  ldloc.1
0x5d05c  ldstr    aSolutionid_2// "@SolutionId"
0x5d061  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x5d066  box      [mscorlib]System.Guid
0x5d06b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d070  pop
0x5d071  ldloc.1
0x5d072  ldstr    aLabeltypecode// "@LabelTypeCode"
0x5d077  ldc.i4.4
0x5d078  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode
0x5d07d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5d082  pop
0x5d083  ldloc.0
0x5d084  ldc.i4   0x22E
0x5d089  ldstr    aInsertupdatelo// "InsertUpdateLocalizedLabel"
0x5d08e  ldstr    aDA1SSrcCoreObj_2// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Im"...
0x5d093  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5d098  pop
0x5d099  leave.s  loc_5D0A5
0x5d09b  ldloc.0
0x5d09c  brfalse.s loc_5D0A4
0x5d09e  ldloc.0
0x5d09f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d0a4  endfinally
0x5d0a5  ret
```
