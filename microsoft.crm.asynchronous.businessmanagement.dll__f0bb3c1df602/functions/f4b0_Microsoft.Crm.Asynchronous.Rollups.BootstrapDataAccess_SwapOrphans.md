# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SwapOrphans

- ea: `0xf4b0`
- end: `0xf5b2`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SwapOrphans`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xe7b0`
- `0xe7d0`
- `0xe7f0`
- `0xe930`
- `0xf4b0`
- `0xf6d0`

## string_xrefs

- `0xf526`: `EXECUTE SP_RENAME '{0}', '{1}'`
- `0xf54c`: `EXECUTE SP_RENAME '{0}', '{1}'`
- `0xf57e`: `EXECUTE SP_RENAME '{0}', '{1}'`

## pseudocode

```c

```

## disassembly

```asm
0xf4b0  ldarg.0
0xf4b1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf4b6  stloc.2
0xf4b7  ldloca.s 2
0xf4b9  ldstr    aN// "N"
0xf4be  call     instance string [mscorlib]System.Guid::ToString(string)
0xf4c3  stloc.0
0xf4c4  ldarg.1
0xf4c5  ldc.i4.1
0xf4c6  bne.un.s loc_F501
0xf4c8  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf4cd  stloc.3
0xf4ce  ldloc.3
0xf4cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf4d4  ldstr    aIfExistsSelect// "if exists (select * from sys.objects wh"...
0xf4d9  ldc.i4.1
0xf4da  newarr   [mscorlib]System.Object
0xf4df  dup
0xf4e0  ldc.i4.0
0xf4e1  ldloc.0
0xf4e2  stelem.ref
0xf4e3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf4e8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf4ed  ldarg.0
0xf4ee  ldloc.3
0xf4ef  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf4f4  pop
0xf4f5  leave.s  loc_F501
0xf4f7  ldloc.3
0xf4f8  brfalse.s loc_F500
0xf4fa  ldloc.3
0xf4fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf500  endfinally
0xf501  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf506  stloc.1
0xf507  ldarg.1
0xf508  ldc.i4.1
0xf509  sub
0xf50a  switch   loc_F520, loc_F546, loc_F578
0xf51b  br       loc_F5A3
0xf520  ldloc.1
0xf521  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf526  ldstr    aExecuteSpRenam// "EXECUTE SP_RENAME '{0}', '{1}'"
0xf52b  ldc.i4.2
0xf52c  newarr   [mscorlib]System.Object
0xf531  dup
0xf532  ldc.i4.0
0xf533  ldarg.0
0xf534  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_OrphansTableName()
0xf539  stelem.ref
0xf53a  dup
0xf53b  ldc.i4.1
0xf53c  ldloc.0
0xf53d  stelem.ref
0xf53e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf543  pop
0xf544  br.s     loc_F5A3
0xf546  ldloc.1
0xf547  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf54c  ldstr    aExecuteSpRenam// "EXECUTE SP_RENAME '{0}', '{1}'"
0xf551  ldc.i4.2
0xf552  newarr   [mscorlib]System.Object
0xf557  dup
0xf558  ldc.i4.0
0xf559  ldarg.0
0xf55a  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_SourceTableName()
0xf55f  stelem.ref
0xf560  dup
0xf561  ldc.i4.1
0xf562  ldarg.0
0xf563  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf568  ldc.i4.5
0xf569  ldc.i4.1
0xf56a  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable, bool)
0xf56f  stelem.ref
0xf570  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf575  pop
0xf576  br.s     loc_F5A3
0xf578  ldloc.1
0xf579  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf57e  ldstr    aExecuteSpRenam// "EXECUTE SP_RENAME '{0}', '{1}'"
0xf583  ldc.i4.2
0xf584  newarr   [mscorlib]System.Object
0xf589  dup
0xf58a  ldc.i4.0
0xf58b  ldloc.0
0xf58c  stelem.ref
0xf58d  dup
0xf58e  ldc.i4.1
0xf58f  ldarg.0
0xf590  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf595  ldc.i4.2
0xf596  ldc.i4.1
0xf597  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable, bool)
0xf59c  stelem.ref
0xf59d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf5a2  pop
0xf5a3  ldloc.1
0xf5a4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf5a9  pop
0xf5aa  ldarg.0
0xf5ab  ldloc.1
0xf5ac  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript(class [mscorlib]System.Text.StringBuilder cleanupScript)
0xf5b1  ret
```
