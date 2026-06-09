# Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLCommandWithExtendedTimeout

- ea: `0x4420`
- end: `0x4534`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLCommandWithExtendedTimeout`
- size: `276`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x17eb0`
- `0x18490`
- `0x1c180`
- `0x1c5c0`

## callees

- `0x4420`

## string_xrefs

- `0x44f4`: `d:\dbs\sh\dccm2\1101_190851\cmd\32\src\Core\ObjectModel\Async\Handlers\DataManagement\ImportDataAccess.cs`
- `0x445e`: `Exception while trying to open database connection for organization {0}`
- `0x44ef`: `ExecuteSQLCommandWithExtendedTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x4420  ldarg.0
0x4421  ldarg.0
0x4422  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x4427  ldc.i4   0x12C
0x442c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection(valuetype [mscorlib]System.Guid, int32)
0x4431  stloc.0
0x4432  ldloc.0
0x4433  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x4438  leave.s  loc_447B
0x443a  stloc.1
0x443b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4440  ldstr    aConnectionstri// "ConnectionString: {0}, "
0x4445  ldc.i4.1
0x4446  newarr   [mscorlib]System.Object
0x444b  dup
0x444c  ldc.i4.0
0x444d  ldloc.0
0x444e  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x4453  stelem.ref
0x4454  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4459  stloc.2
0x445a  ldarg.0
0x445b  ldloc.1
0x445c  ldnull
0x445d  ldloc.2
0x445e  ldstr    aExceptionWhile// "Exception while trying to open database"...
0x4463  call     string [mscorlib]System.String::Concat(string, string)
0x4468  ldarg.0
0x4469  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x446e  ldarg.0
0x446f  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x4474  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x4479  rethrow
0x447b  ldloc.0
0x447c  ldarg.1
0x447d  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x4482  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x4487  stloc.3
0x4488  ldloc.3
0x4489  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x448e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4493  stloc.s  4
0x4495  ldarg.1
0x4496  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x449b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x44a0  stloc.s  5
0x44a2  br.s     loc_44C8
0x44a4  ldloc.s  5
0x44a6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x44ab  castclass [System.Data]System.Data.SqlClient.SqlParameter
0x44b0  stloc.s  6
0x44b2  ldloc.s  4
0x44b4  ldloc.s  6
0x44b6  callvirt instance string [System.Data]System.Data.Common.DbParameter::get_ParameterName()
0x44bb  ldloc.s  6
0x44bd  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x44c2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x44c7  pop
0x44c8  ldloc.s  5
0x44ca  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x44cf  brtrue.s loc_44A4
0x44d1  leave.s  loc_44E8
0x44d3  ldloc.s  5
0x44d5  isinst   [mscorlib]System.IDisposable
0x44da  stloc.s  7
0x44dc  ldloc.s  7
0x44de  brfalse.s loc_44E7
0x44e0  ldloc.s  7
0x44e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x44e7  endfinally
0x44e8  nop
0x44e9  ldloc.3
0x44ea  ldc.i4   0x1A2
0x44ef  ldstr    aExecutesqlcomm// "ExecuteSQLCommandWithExtendedTimeout"
0x44f4  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x44f9  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x44fe  pop
0x44ff  leave.s  loc_4533
0x4501  stloc.s  8
0x4503  ldarg.0
0x4504  ldloc.s  8
0x4506  ldloc.3
0x4507  ldstr    aExceptionWhile_0// "Exception while executing database quer"...
0x450c  ldarg.0
0x450d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x4512  ldarg.0
0x4513  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x4518  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x451d  rethrow
0x451f  ldloc.3
0x4520  brfalse.s loc_4528
0x4522  ldloc.3
0x4523  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4528  endfinally
0x4529  ldloc.0
0x452a  brfalse.s loc_4532
0x452c  ldloc.0
0x452d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4532  endfinally
0x4533  ret
```
