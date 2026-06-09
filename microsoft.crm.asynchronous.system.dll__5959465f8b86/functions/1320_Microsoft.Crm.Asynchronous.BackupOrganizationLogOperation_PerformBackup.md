# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::PerformBackup

- ea: `0x1320`
- end: `0x139f`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::PerformBackup`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x12c0`

## callees

- `0x1320`
- `0x1440`

## string_xrefs

- `0x1335`: `Error creating backup for SQL Server {0}, Database {1} Path {2}: {3}`
- `0x136b`: `Error creating backup for SQL Server {0}, Database {1} Path {2}: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x1320  ldarg.1
0x1321  ldarg.2
0x1322  ldarg.3
0x1323  ldarg.s  4
0x1325  ldarg.s  5
0x1327  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility::ExecuteBackupSqlCommandByOrg(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility/DatabaseBackupType, string, string, string, string)
0x132c  stloc.0
0x132d  leave.s  loc_139D
0x132f  stloc.1
0x1330  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1335  ldstr    aErrorCreatingB_1// "Error creating backup for SQL Server {0"...
0x133a  ldc.i4.4
0x133b  newarr   [mscorlib]System.Object
0x1340  dup
0x1341  ldc.i4.0
0x1342  ldarg.3
0x1343  stelem.ref
0x1344  dup
0x1345  ldc.i4.1
0x1346  ldarg.s  4
0x1348  stelem.ref
0x1349  dup
0x134a  ldc.i4.2
0x134b  ldarg.2
0x134c  stelem.ref
0x134d  dup
0x134e  ldc.i4.3
0x134f  ldloc.1
0x1350  callvirt instance string [mscorlib]System.Object::ToString()
0x1355  stelem.ref
0x1356  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x135b  stloc.2
0x135c  ldarg.0
0x135d  ldloc.2
0x135e  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::LogError(string message)
0x1363  rethrow
0x1365  stloc.3
0x1366  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x136b  ldstr    aErrorCreatingB_1// "Error creating backup for SQL Server {0"...
0x1370  ldc.i4.4
0x1371  newarr   [mscorlib]System.Object
0x1376  dup
0x1377  ldc.i4.0
0x1378  ldarg.3
0x1379  stelem.ref
0x137a  dup
0x137b  ldc.i4.1
0x137c  ldarg.s  4
0x137e  stelem.ref
0x137f  dup
0x1380  ldc.i4.2
0x1381  ldarg.2
0x1382  stelem.ref
0x1383  dup
0x1384  ldc.i4.3
0x1385  ldloc.3
0x1386  callvirt instance string [mscorlib]System.Object::ToString()
0x138b  stelem.ref
0x138c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1391  stloc.s  4
0x1393  ldarg.0
0x1394  ldloc.s  4
0x1396  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::LogError(string message)
0x139b  rethrow
0x139d  ldloc.0
0x139e  ret
```
