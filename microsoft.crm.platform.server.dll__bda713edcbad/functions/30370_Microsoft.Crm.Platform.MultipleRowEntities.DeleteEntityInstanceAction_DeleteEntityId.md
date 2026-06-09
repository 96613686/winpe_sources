# Microsoft.Crm.Platform.MultipleRowEntities.DeleteEntityInstanceAction::DeleteEntityId

- ea: `0x30370`
- end: `0x30481`
- name: `Microsoft.Crm.Platform.MultipleRowEntities.DeleteEntityInstanceAction::DeleteEntityId`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x30320`

## callees

- `0x30370`
- `0x31470`
- `0x31490`
- `0x5d5d0`
- `0x66b00`

## string_xrefs

- `0x303e9`: `delete from [{0}] where [{1}] = {2}`
- `0x30425`: `DeleteEntityId, Sql To Execute = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x30370  ldarg.1
0x30371  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x30376  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsShareableAcrossOrgs()
0x3037b  brtrue.s loc_3037E
0x3037d  ret
0x3037e  ldarg.1
0x3037f  call     bool Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionUtility::HasIdsTable(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x30384  brfalse  loc_30480
0x30389  ldnull
0x3038a  stloc.0
0x3038b  ldsfld   string [mscorlib]System.String::Empty
0x30390  stloc.1
0x30391  ldarg.2
0x30392  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x30397  stloc.0
0x30398  ldloc.0
0x30399  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x3039e  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x303a3  stloc.2
0x303a4  ldstr    aId_4// "@id"
0x303a9  stloc.3
0x303aa  ldarg.1
0x303ab  ldarg.1
0x303ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x303b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x303b6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x303bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x303c0  ldc.i4.1
0x303c1  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object, bool)
0x303c6  stloc.s  4
0x303c8  ldloc.2
0x303c9  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x303ce  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x303d3  ldloc.3
0x303d4  ldloc.s  4
0x303d6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x303db  pop
0x303dc  ldarg.1
0x303dd  call     string Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionUtility::BuildIdsTableName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x303e2  stloc.s  5
0x303e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x303e9  ldstr    aDeleteFrom0Whe// "delete from [{0}] where [{1}] = {2}"
0x303ee  ldc.i4.3
0x303ef  newarr   [mscorlib]System.Object
0x303f4  dup
0x303f5  ldc.i4.0
0x303f6  ldloc.s  5
0x303f8  stelem.ref
0x303f9  dup
0x303fa  ldc.i4.1
0x303fb  ldarg.1
0x303fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x30401  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x30406  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x3040b  stelem.ref
0x3040c  dup
0x3040d  ldc.i4.2
0x3040e  ldloc.3
0x3040f  stelem.ref
0x30410  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30415  stloc.1
0x30416  ldloc.2
0x30417  ldloc.1
0x30418  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3041d  ldarg.2
0x3041e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x30423  ldc.i4.s 0x1D
0x30425  ldstr    aDeleteentityid// "DeleteEntityId, Sql To Execute = {0}"
0x3042a  ldc.i4.1
0x3042b  newarr   [mscorlib]System.Object
0x30430  dup
0x30431  ldc.i4.0
0x30432  ldloc.2
0x30433  stelem.ref
0x30434  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x30439  ldloc.2
0x3043a  ldarg.2
0x3043b  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x30440  pop
0x30441  leave.s  loc_3044D
0x30443  ldloc.2
0x30444  brfalse.s loc_3044C
0x30446  ldloc.2
0x30447  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3044c  endfinally
0x3044d  leave.s  loc_30480
0x3044f  stloc.s  6
0x30451  ldloc.s  6
0x30453  ldarg.2
0x30454  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x30459  ldc.i4.s 0x1D
0x3045b  ldstr    aExceptionWhenE// "Exception when executing query: {0} Exc"...
0x30460  ldc.i4.2
0x30461  newarr   [mscorlib]System.Object
0x30466  dup
0x30467  ldc.i4.0
0x30468  ldloc.1
0x30469  stelem.ref
0x3046a  dup
0x3046b  ldc.i4.1
0x3046c  ldloc.s  6
0x3046e  stelem.ref
0x3046f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x30474  rethrow
0x30476  ldloc.0
0x30477  brfalse.s loc_3047F
0x30479  ldloc.0
0x3047a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x3047f  endfinally
0x30480  ret
```
