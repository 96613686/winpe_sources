# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::DeleteStagedComponents

- ea: `0x43c10`
- end: `0x43d5f`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::DeleteStagedComponents`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x42ed0`
- `0x43c10`
- `0x66ae0`

## string_xrefs

- `0x43c30`: `p_DeleteStagedMetadata`
- `0x43c41`: `@CountOfRecordsDeleted`
- `0x43ca3`: `Number of Records deleted: {0}; Number of Tables touched {1}`
- `0x43d01`: `Error while executing Stored Procedure to delete components in Staged state: {0}`
- `0x43d40`: `Error while executing/commiting Delete Of components in Staged state: {0}, Executing Rollback ...`

## pseudocode

```c

```

## disassembly

```asm
0x43c10  ldarg.1
0x43c11  ldstr    aContext// "context"
0x43c16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x43c1b  ldarg.1
0x43c1c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x43c21  stloc.0
0x43c22  ldloc.0
0x43c23  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::StartTransaction()
0x43c28  ldloc.0
0x43c29  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x43c2e  stloc.1
0x43c2f  ldloc.1
0x43c30  ldstr    aPDeletestagedm// "p_DeleteStagedMetadata"
0x43c35  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x43c3a  ldloc.1
0x43c3b  ldc.i4.4
0x43c3c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x43c41  ldstr    aCountofrecords// "@CountOfRecordsDeleted"
0x43c46  ldc.i4.8
0x43c47  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x43c4c  stloc.2
0x43c4d  ldloc.2
0x43c4e  ldc.i4.2
0x43c4f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x43c54  ldloc.1
0x43c55  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x43c5a  ldloc.2
0x43c5b  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x43c60  pop
0x43c61  ldstr    aCountoftables// "@CountOfTables"
0x43c66  ldc.i4.8
0x43c67  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x43c6c  stloc.3
0x43c6d  ldloc.3
0x43c6e  ldc.i4.2
0x43c6f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x43c74  ldloc.1
0x43c75  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x43c7a  ldloc.3
0x43c7b  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x43c80  pop
0x43c81  ldloc.1
0x43c82  ldloc.0
0x43c83  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x43c88  pop
0x43c89  ldloc.0
0x43c8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43c8f  ldc.i4.s 0x19
0x43c91  ldstr    a0// "{0}"
0x43c96  ldc.i4.1
0x43c97  newarr   [mscorlib]System.Object
0x43c9c  dup
0x43c9d  ldc.i4.0
0x43c9e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43ca3  ldstr    aNumberOfRecord// "Number of Records deleted: {0}; Number "...
0x43ca8  ldc.i4.2
0x43ca9  newarr   [mscorlib]System.Object
0x43cae  dup
0x43caf  ldc.i4.0
0x43cb0  ldloc.2
0x43cb1  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x43cb6  callvirt instance string [mscorlib]System.Object::ToString()
0x43cbb  stelem.ref
0x43cbc  dup
0x43cbd  ldc.i4.1
0x43cbe  ldloc.3
0x43cbf  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x43cc4  callvirt instance string [mscorlib]System.Object::ToString()
0x43cc9  stelem.ref
0x43cca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43ccf  stelem.ref
0x43cd0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x43cd5  leave.s  loc_43CE1
0x43cd7  ldloc.1
0x43cd8  brfalse.s loc_43CE0
0x43cda  ldloc.1
0x43cdb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43ce0  endfinally
0x43ce1  leave.s  loc_43D1E
0x43ce3  stloc.s  4
0x43ce5  ldloc.s  4
0x43ce7  ldloc.0
0x43ce8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43ced  ldc.i4.s 0x19
0x43cef  ldstr    a0// "{0}"
0x43cf4  ldc.i4.1
0x43cf5  newarr   [mscorlib]System.Object
0x43cfa  dup
0x43cfb  ldc.i4.0
0x43cfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43d01  ldstr    aErrorWhileExec// "Error while executing Stored Procedure "...
0x43d06  ldc.i4.1
0x43d07  newarr   [mscorlib]System.Object
0x43d0c  dup
0x43d0d  ldc.i4.0
0x43d0e  ldloc.s  4
0x43d10  stelem.ref
0x43d11  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43d16  stelem.ref
0x43d17  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x43d1c  rethrow
0x43d1e  ldloc.0
0x43d1f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CommitTransaction()
0x43d24  leave.s  loc_43D5E
0x43d26  ldloc.0
0x43d27  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43d2c  ldc.i4.s 0x19
0x43d2e  ldstr    a0// "{0}"
0x43d33  ldc.i4.1
0x43d34  newarr   [mscorlib]System.Object
0x43d39  dup
0x43d3a  ldc.i4.0
0x43d3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43d40  ldstr    aErrorWhileExec_0// "Error while executing/commiting Delete "...
0x43d45  ldc.i4.0
0x43d46  newarr   [mscorlib]System.Object
0x43d4b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43d50  stelem.ref
0x43d51  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x43d56  ldloc.0
0x43d57  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::RollbackTransaction()
0x43d5c  rethrow
0x43d5e  ret
```
