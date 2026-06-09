# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ClearSchemaForOrphans

- ea: `0xf3f0`
- end: `0xf4a6`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ClearSchemaForOrphans`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xe7b0`
- `0xe7d0`
- `0xe7e0`
- `0xf6d0`

## pseudocode

```c

```

## disassembly

```asm
0xf3f0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf3f5  stloc.0
0xf3f6  ldloc.0
0xf3f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf3fc  ldstr    aTruncateTable0// "TRUNCATE TABLE {0}"
0xf401  ldc.i4.1
0xf402  newarr   [mscorlib]System.Object
0xf407  dup
0xf408  ldc.i4.0
0xf409  ldarg.0
0xf40a  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_SourceTableName()
0xf40f  stelem.ref
0xf410  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf415  pop
0xf416  ldloc.0
0xf417  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf41c  pop
0xf41d  ldloc.0
0xf41e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf423  ldstr    aTruncateTable0// "TRUNCATE TABLE {0}"
0xf428  ldc.i4.1
0xf429  newarr   [mscorlib]System.Object
0xf42e  dup
0xf42f  ldc.i4.0
0xf430  ldarg.0
0xf431  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_MainTableName()
0xf436  stelem.ref
0xf437  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf43c  pop
0xf43d  ldloc.0
0xf43e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf443  pop
0xf444  ldloc.0
0xf445  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf44a  ldstr    aTruncateTable0// "TRUNCATE TABLE {0}"
0xf44f  ldc.i4.1
0xf450  newarr   [mscorlib]System.Object
0xf455  dup
0xf456  ldc.i4.0
0xf457  ldarg.0
0xf458  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf45d  ldc.i4.4
0xf45e  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable)
0xf463  stelem.ref
0xf464  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf469  pop
0xf46a  ldloc.0
0xf46b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf470  pop
0xf471  ldloc.0
0xf472  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf477  ldstr    aTruncateTable0// "TRUNCATE TABLE {0}"
0xf47c  ldc.i4.1
0xf47d  newarr   [mscorlib]System.Object
0xf482  dup
0xf483  ldc.i4.0
0xf484  ldarg.0
0xf485  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf48a  ldc.i4.5
0xf48b  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable)
0xf490  stelem.ref
0xf491  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf496  pop
0xf497  ldloc.0
0xf498  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf49d  pop
0xf49e  ldarg.0
0xf49f  ldloc.0
0xf4a0  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript(class [mscorlib]System.Text.StringBuilder cleanupScript)
0xf4a5  ret
```
