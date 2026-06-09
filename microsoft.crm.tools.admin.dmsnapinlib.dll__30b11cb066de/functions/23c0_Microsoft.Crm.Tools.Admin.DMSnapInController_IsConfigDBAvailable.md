# Microsoft.Crm.Tools.Admin.DMSnapInController::IsConfigDBAvailable

- ea: `0x23c0`
- end: `0x2475`
- name: `Microsoft.Crm.Tools.Admin.DMSnapInController::IsConfigDBAvailable`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x23c0`

## string_xrefs

- `0x23e6`: `IsConfigDBAvailable`
- `0x242f`: `Cannot open connection on SQL Server. Connection string ({0})`
- `0x2456`: `SQL Server does not exist or access denied. Connection string ({0})`

## pseudocode

```c

```

## disassembly

```asm
0x23c0  ldnull
0x23c1  stloc.0
0x23c2  ldnull
0x23c3  stloc.1
0x23c4  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConfigDBConnection()
0x23c9  stloc.2
0x23ca  ldloc.2
0x23cb  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x23d0  stloc.0
0x23d1  ldloc.2
0x23d2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x23d7  ldloc.2
0x23d8  ldstr    aSelectTop1From// "SELECT TOP 1 * FROM Deployment"
0x23dd  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x23e2  stloc.3
0x23e3  ldloc.3
0x23e4  ldc.i4.s 0x47
0x23e6  ldstr    aIsconfigdbavai// "IsConfigDBAvailable"
0x23eb  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x23f0  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x23f5  pop
0x23f6  leave.s  loc_23FB
0x23f8  stloc.1
0x23f9  leave.s  loc_23FB
0x23fb  leave.s  loc_2407
0x23fd  ldloc.3
0x23fe  brfalse.s loc_2406
0x2400  ldloc.3
0x2401  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2406  endfinally
0x2407  leave.s  loc_2413
0x2409  ldloc.2
0x240a  brfalse.s loc_2412
0x240c  ldloc.2
0x240d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2412  endfinally
0x2413  leave.s  loc_244E
0x2415  stloc.s  4
0x2417  ldc.i4   0x80131904
0x241c  ldloc.s  4
0x241e  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x2423  bne.un.s loc_242A
0x2425  ldloc.s  4
0x2427  stloc.1
0x2428  br.s     loc_244C
0x242a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x242f  ldstr    aCannotOpenConn// "Cannot open connection on SQL Server. C"...
0x2434  ldc.i4.1
0x2435  newarr   [mscorlib]System.Object
0x243a  dup
0x243b  ldc.i4.0
0x243c  ldloc.0
0x243d  stelem.ref
0x243e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2443  ldloc.s  4
0x2445  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x244a  rethrow
0x244c  leave.s  loc_244E
0x244e  ldloc.1
0x244f  brfalse.s loc_2470
0x2451  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2456  ldstr    aSqlServerDoesN// "SQL Server does not exist or access den"...
0x245b  ldc.i4.1
0x245c  newarr   [mscorlib]System.Object
0x2461  dup
0x2462  ldc.i4.0
0x2463  ldloc.0
0x2464  stelem.ref
0x2465  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x246a  ldloc.1
0x246b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x2470  ldloc.1
0x2471  ldnull
0x2472  ceq
0x2474  ret
```
