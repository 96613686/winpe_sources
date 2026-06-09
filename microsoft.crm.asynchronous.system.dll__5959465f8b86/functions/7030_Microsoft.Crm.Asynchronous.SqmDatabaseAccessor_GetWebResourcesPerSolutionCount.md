# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetWebResourcesPerSolutionCount

- ea: `0x7030`
- end: `0x70d8`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetWebResourcesPerSolutionCount`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6d90`

## callees

- `0x7030`

## string_xrefs

- `0x705b`: `@ComponentType`
- `0x703d`: `SELECT COUNT(*) FROM WebResource as web INNER JOIN SolutionComponent as sol ON sol.ObjectId = web.WebResourceId where sol.ComponentType = @ComponentType AND sol.SolutionId = @SolutionId`

## pseudocode

```c

```

## disassembly

```asm
0x7030  ldc.i4.0
0x7031  stloc.0
0x7032  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7037  stloc.1
0x7038  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x703d  ldstr    aSelectCountFro_12// "SELECT COUNT(*) FROM WebResource as web"...
0x7042  ldc.i4.0
0x7043  newarr   [mscorlib]System.Object
0x7048  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x704d  stloc.2
0x704e  ldloc.1
0x704f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7054  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x7059  stloc.3
0x705a  ldloc.3
0x705b  ldstr    aComponenttype// "@ComponentType"
0x7060  ldc.i4.s 0x3D
0x7062  box      [mscorlib]System.Int32
0x7067  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x706c  pop
0x706d  ldloc.3
0x706e  ldstr    aSolutionid// "@SolutionId"
0x7073  ldc.i4.s 0xE
0x7075  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x707a  ldarg.1
0x707b  box      [mscorlib]System.Guid
0x7080  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7085  ldarg.2
0x7086  brtrue.s loc_70B6
0x7088  ldloc.2
0x7089  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x708e  ldstr    aAndWebWebresou// " AND web.WebResourceType = @WebResource"...
0x7093  ldc.i4.0
0x7094  newarr   [mscorlib]System.Object
0x7099  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x709e  call     string [mscorlib]System.String::Concat(string, string)
0x70a3  stloc.2
0x70a4  ldloc.3
0x70a5  ldstr    aWebresourcetyp// "@WebResourceType"
0x70aa  ldarg.3
0x70ab  box      [mscorlib]System.Int32
0x70b0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x70b5  pop
0x70b6  ldloc.1
0x70b7  ldloc.2
0x70b8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x70bd  ldarg.0
0x70be  ldloc.1
0x70bf  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x70c4  unbox.any [mscorlib]System.Int32
0x70c9  stloc.0
0x70ca  leave.s  loc_70D6
0x70cc  ldloc.1
0x70cd  brfalse.s loc_70D5
0x70cf  ldloc.1
0x70d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70d5  endfinally
0x70d6  ldloc.0
0x70d7  ret
```
