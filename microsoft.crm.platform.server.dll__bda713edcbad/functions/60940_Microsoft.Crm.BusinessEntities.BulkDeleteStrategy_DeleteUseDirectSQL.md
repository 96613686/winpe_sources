# Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::DeleteUseDirectSQL

- ea: `0x60940`
- end: `0x60a97`
- name: `Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::DeleteUseDirectSQL`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x60560`

## callees

- `0x60790`
- `0x60820`
- `0x60860`
- `0x60890`
- `0x60910`
- `0x60940`
- `0x66ae0`
- `0x7f3a0`

## string_xrefs

- `0x6097d`: `DELETE FROM [{0}]`
- `0x60a6c`: `Delete`
- `0x60a53`: `DeleteUseDirectSQL`

## pseudocode

```c

```

## disassembly

```asm
0x60940  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x60945  stloc.0
0x60946  ldarg.2
0x60947  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_SecondaryTableAttributeCount()
0x6094c  ldc.i4.0
0x6094d  ble.s    loc_60957
0x6094f  ldarg.0
0x60950  ldloc.0
0x60951  ldarg.2
0x60952  call     instance void Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::AppendDeleteTableExtension(class [mscorlib]System.Text.StringBuilder sb, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x60957  ldarg.2
0x60958  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x6095d  brtrue.s loc_60977
0x6095f  ldarg.2
0x60960  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsDuplicateCheckSupported()
0x60965  brtrue.s loc_60977
0x60967  ldarg.2
0x60968  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsUserOwned()
0x6096d  brfalse.s loc_60977
0x6096f  ldarg.0
0x60970  ldloc.0
0x60971  ldarg.2
0x60972  call     instance void Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::AppendCleanupPOA(class [mscorlib]System.Text.StringBuilder sb, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x60977  ldloc.0
0x60978  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6097d  ldstr    aDeleteFrom0_0// "DELETE FROM [{0}]"
0x60982  ldc.i4.1
0x60983  newarr   [mscorlib]System.Object
0x60988  dup
0x60989  ldc.i4.0
0x6098a  ldarg.2
0x6098b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0x60990  stelem.ref
0x60991  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x60996  pop
0x60997  ldarg.2
0x60998  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x6099d  brtrue.s loc_609A7
0x6099f  ldarg.2
0x609a0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsDuplicateCheckSupported()
0x609a5  brfalse.s loc_609AF
0x609a7  ldarg.0
0x609a8  ldloc.0
0x609a9  ldarg.2
0x609aa  call     instance void Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::AppendSyncTracking(class [mscorlib]System.Text.StringBuilder sb, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x609af  ldloc.0
0x609b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x609b5  ldstr    aWhere0InSelect// " WHERE [{0}] IN  (SELECT id FROM {1}) ;"
0x609ba  ldc.i4.2
0x609bb  newarr   [mscorlib]System.Object
0x609c0  dup
0x609c1  ldc.i4.0
0x609c2  ldarg.2
0x609c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x609c8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x609cd  stelem.ref
0x609ce  dup
0x609cf  ldc.i4.1
0x609d0  ldstr    aCascadedeletio// "@cascadedeletionTable"
0x609d5  stelem.ref
0x609d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x609db  pop
0x609dc  ldarg.0
0x609dd  ldloc.0
0x609de  ldarg.2
0x609df  call     instance void Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::AppendSetIsDeletedForWorkflow(class [mscorlib]System.Text.StringBuilder sb, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata)
0x609e4  ldarg.0
0x609e5  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::_context
0x609ea  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x609ef  ldc.i4   0x12C
0x609f4  call     class [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier::SetNewTimeoutIfLonger(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, int32)
0x609f9  stloc.1
0x609fa  ldarg.0
0x609fb  ldarg.1
0x609fc  call     instance class [System.Data]System.Data.DataTable Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::PopulateTable(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> idList)
0x60a01  newobj   instance void [System.Data]System.Data.DataTableReader::.ctor(class [System.Data]System.Data.DataTable)
0x60a06  stloc.2
0x60a07  ldarg.0
0x60a08  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::_context
0x60a0d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x60a12  ldc.i4.1
0x60a13  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x60a18  stloc.3
0x60a19  ldloc.3
0x60a1a  ldloc.0
0x60a1b  callvirt instance string [mscorlib]System.Object::ToString()
0x60a20  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x60a25  ldloc.3
0x60a26  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x60a2b  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x60a30  ldstr    aCascadedeletio// "@cascadedeletionTable"
0x60a35  ldloc.2
0x60a36  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x60a3b  dup
0x60a3c  ldc.i4.s 0x1E
0x60a3e  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x60a43  ldstr    aEntityidcollec// "EntityIdCollection"
0x60a48  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_TypeName(string)
0x60a4d  ldloc.3
0x60a4e  ldc.i4   0xAC8
0x60a53  ldstr    aDeleteusedirec// "DeleteUseDirectSQL"
0x60a58  ldstr    aDA1SSrcManaged_13// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x60a5d  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x60a62  ldc.i4.0
0x60a63  ble.s    loc_60A76
0x60a65  ldarg.0
0x60a66  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.BulkDeleteStrategy::_context
0x60a6b  ldarg.2
0x60a6c  ldstr    aDelete// "Delete"
0x60a71  call     void Microsoft.Crm.BusinessEntities.ChangeTrackingHelper::TryAddEntityToChangedTypes(class Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, [opt] string messageName)
0x60a76  leave.s  loc_60A96
0x60a78  ldloc.3
0x60a79  brfalse.s loc_60A81
0x60a7b  ldloc.3
0x60a7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60a81  endfinally
0x60a82  ldloc.2
0x60a83  brfalse.s loc_60A8B
0x60a85  ldloc.2
0x60a86  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60a8b  endfinally
0x60a8c  ldloc.1
0x60a8d  brfalse.s loc_60A95
0x60a8f  ldloc.1
0x60a90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60a95  endfinally
0x60a96  ret
```
