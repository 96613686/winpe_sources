# Microsoft.Crm.Platform.SolutionAwareComponents.DeleteIdAction::Execute

- ea: `0x3f6b0`
- end: `0x3f7c3`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.DeleteIdAction::Execute`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x31470`
- `0x31490`
- `0x36040`
- `0x37da0`
- `0x3f6b0`
- `0x5d5d0`
- `0x66b00`

## string_xrefs

- `0x3f6f4`: `delete from [{0}] where [{1}] = {2}`
- `0x3f767`: `DeleteEntityId, Sql To Execute = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3f6b0  ldarg.0
0x3f6b1  call     instance class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionAction::get_Instance()
0x3f6b6  castclass Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x3f6bb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x3f6c0  stloc.0
0x3f6c1  ldloc.0
0x3f6c2  call     bool Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionUtility::HasIdsTable(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x3f6c7  brfalse  loc_3F7C2
0x3f6cc  ldnull
0x3f6cd  stloc.1
0x3f6ce  ldsfld   string [mscorlib]System.String::Empty
0x3f6d3  stloc.2
0x3f6d4  ldarg.1
0x3f6d5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x3f6da  stloc.1
0x3f6db  ldloc.1
0x3f6dc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x3f6e1  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x3f6e6  stloc.3
0x3f6e7  ldstr    aId_4// "@id"
0x3f6ec  stloc.s  4
0x3f6ee  ldloc.3
0x3f6ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f6f4  ldstr    aDeleteFrom0Whe// "delete from [{0}] where [{1}] = {2}"
0x3f6f9  ldc.i4.3
0x3f6fa  newarr   [mscorlib]System.Object
0x3f6ff  dup
0x3f700  ldc.i4.0
0x3f701  ldloc.0
0x3f702  call     string Microsoft.Crm.Platform.MultipleRowEntities.StateTransitionUtility::BuildIdsTableName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x3f707  stelem.ref
0x3f708  dup
0x3f709  ldc.i4.1
0x3f70a  ldloc.0
0x3f70b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x3f710  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x3f715  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x3f71a  stelem.ref
0x3f71b  dup
0x3f71c  ldc.i4.2
0x3f71d  ldloc.s  4
0x3f71f  stelem.ref
0x3f720  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3f725  dup
0x3f726  stloc.s  5
0x3f728  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3f72d  ldloc.s  5
0x3f72f  stloc.2
0x3f730  ldloc.3
0x3f731  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3f736  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3f73b  ldloc.s  4
0x3f73d  ldloc.0
0x3f73e  ldloc.0
0x3f73f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x3f744  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x3f749  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x3f74e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x3f753  ldc.i4.1
0x3f754  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object, bool)
0x3f759  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3f75e  pop
0x3f75f  ldarg.1
0x3f760  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3f765  ldc.i4.s 0x1D
0x3f767  ldstr    aDeleteentityid// "DeleteEntityId, Sql To Execute = {0}"
0x3f76c  ldc.i4.1
0x3f76d  newarr   [mscorlib]System.Object
0x3f772  dup
0x3f773  ldc.i4.0
0x3f774  ldloc.3
0x3f775  stelem.ref
0x3f776  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3f77b  ldloc.3
0x3f77c  ldarg.1
0x3f77d  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3f782  pop
0x3f783  leave.s  loc_3F78F
0x3f785  ldloc.3
0x3f786  brfalse.s loc_3F78E
0x3f788  ldloc.3
0x3f789  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f78e  endfinally
0x3f78f  leave.s  loc_3F7C2
0x3f791  stloc.s  6
0x3f793  ldloc.s  6
0x3f795  ldarg.1
0x3f796  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3f79b  ldc.i4.s 0x1D
0x3f79d  ldstr    aExceptionWhenE// "Exception when executing query: {0} Exc"...
0x3f7a2  ldc.i4.2
0x3f7a3  newarr   [mscorlib]System.Object
0x3f7a8  dup
0x3f7a9  ldc.i4.0
0x3f7aa  ldloc.2
0x3f7ab  stelem.ref
0x3f7ac  dup
0x3f7ad  ldc.i4.1
0x3f7ae  ldloc.s  6
0x3f7b0  stelem.ref
0x3f7b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3f7b6  rethrow
0x3f7b8  ldloc.1
0x3f7b9  brfalse.s loc_3F7C1
0x3f7bb  ldloc.1
0x3f7bc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x3f7c1  endfinally
0x3f7c2  ret
```
