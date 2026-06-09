# Microsoft.Crm.Tools.Admin.OrganizationController::IsOrganizationDatabaseAvailable

- ea: `0x7730`
- end: `0x77dc`
- name: `Microsoft.Crm.Tools.Admin.OrganizationController::IsOrganizationDatabaseAvailable`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7730`

## string_xrefs

- `0x7797`: `Cannot open connection on SQL Server. Connection string ({0})`
- `0x77bd`: `SQL Server does not exist or access denied. Connection string ({0})`

## pseudocode

```c

```

## disassembly

```asm
0x7730  ldnull
0x7731  stloc.0
0x7732  ldarg.1
0x7733  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::.ctor(string)
0x7738  stloc.1
0x7739  ldloc.1
0x773a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x773f  ldloc.1
0x7740  ldstr    aSelectTop1From_0// "SELECT TOP 1 * FROM OrganizationBase"
0x7745  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x774a  stloc.2
0x774b  ldloc.2
0x774c  ldc.i4   0x84
0x7751  ldstr    aIsorganization// "IsOrganizationDatabaseAvailable"
0x7756  ldstr    aDDbsShDccm2110_4// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x775b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x7760  pop
0x7761  leave.s  loc_7766
0x7763  stloc.0
0x7764  leave.s  loc_7766
0x7766  leave.s  loc_7772
0x7768  ldloc.2
0x7769  brfalse.s loc_7771
0x776b  ldloc.2
0x776c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7771  endfinally
0x7772  leave.s  loc_777E
0x7774  ldloc.1
0x7775  brfalse.s loc_777D
0x7777  ldloc.1
0x7778  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x777d  endfinally
0x777e  leave.s  loc_77B5
0x7780  stloc.3
0x7781  ldc.i4   0x80131904
0x7786  ldloc.3
0x7787  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x778c  bne.un.s loc_7792
0x778e  ldloc.3
0x778f  stloc.0
0x7790  br.s     loc_77B3
0x7792  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7797  ldstr    aCannotOpenConn// "Cannot open connection on SQL Server. C"...
0x779c  ldc.i4.1
0x779d  newarr   [mscorlib]System.Object
0x77a2  dup
0x77a3  ldc.i4.0
0x77a4  ldarg.1
0x77a5  stelem.ref
0x77a6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x77ab  ldloc.3
0x77ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x77b1  rethrow
0x77b3  leave.s  loc_77B5
0x77b5  ldloc.0
0x77b6  brfalse.s loc_77D7
0x77b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x77bd  ldstr    aSqlServerDoesN// "SQL Server does not exist or access den"...
0x77c2  ldc.i4.1
0x77c3  newarr   [mscorlib]System.Object
0x77c8  dup
0x77c9  ldc.i4.0
0x77ca  ldarg.1
0x77cb  stelem.ref
0x77cc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x77d1  ldloc.0
0x77d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x77d7  ldloc.0
0x77d8  ldnull
0x77d9  ceq
0x77db  ret
```
