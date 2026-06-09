# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::DeleteJobsRelatedToNonExistingRollupFields

- ea: `0xd3b0`
- end: `0xd40f`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::DeleteJobsRelatedToNonExistingRollupFields`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0xc2b0`

## callees

- `0xc990`
- `0xd210`
- `0xd3b0`
- `0xe600`

## string_xrefs

- `0xd3bc`: `DELETE TOP({0}) RJ FROM RollupJobBase AS RJ\n	LEFT JOIN RollupPropertiesBase AS RP \n	ON RJ.RollupPropertiesId = RP.RollupPropertiesId\n	WHERE (RP.RollupPropertiesId IS NULL OR RP.StatusCode = 2)\n	SELECT @@ROWCOUNT`

## pseudocode

```c

```

## disassembly

```asm
0xd3b0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xd3b5  stloc.0
0xd3b6  ldloc.0
0xd3b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd3bc  ldstr    aDeleteTop0RjFr// "DELETE TOP({0}) RJ FROM RollupJobBase A"...
0xd3c1  ldc.i4.1
0xd3c2  newarr   [mscorlib]System.Object
0xd3c7  dup
0xd3c8  ldc.i4.0
0xd3c9  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupSelectBatchSize()
0xd3ce  box      [mscorlib]System.Int32
0xd3d3  stelem.ref
0xd3d4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd3d9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd3de  ldarg.0
0xd3df  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd3e4  ldloc.0
0xd3e5  callvirt instance object Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xd3ea  stloc.1
0xd3eb  ldloc.1
0xd3ec  brfalse.s loc_D3FF
0xd3ee  ldloc.1
0xd3ef  isinst   [mscorlib]System.Int32
0xd3f4  brfalse.s loc_D3FF
0xd3f6  ldloc.1
0xd3f7  unbox.any [mscorlib]System.Int32
0xd3fc  stloc.2
0xd3fd  leave.s  loc_D40D
0xd3ff  ldc.i4.0
0xd400  stloc.2
0xd401  leave.s  loc_D40D
0xd403  ldloc.0
0xd404  brfalse.s loc_D40C
0xd406  ldloc.0
0xd407  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd40c  endfinally
0xd40d  ldloc.2
0xd40e  ret
```
