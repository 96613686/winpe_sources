# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ProcessCancelJob

- ea: `0xf0a0`
- end: `0xf171`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ProcessCancelJob`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xe7b0`
- `0xe930`
- `0xe940`
- `0xf0a0`

## string_xrefs

- `0xf106`: `RollupPropertiesId`
- `0xf135`: `@rollupPropertiesId`
- `0xf0c5`: `UPDATE {0} SET {1} = 0, {2} = NULL, {3} = @status WHERE {4} = @rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xf0a0  ldarg.0
0xf0a1  ldarg.0
0xf0a2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf0a7  ldc.i4.1
0xf0a8  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetRollupBootstrapTableName(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapTable)
0xf0ad  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupObjects(string tempTableName)
0xf0b2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf0b7  stloc.0
0xf0b8  ldloc.0
0xf0b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf0be  pop
0xf0bf  ldloc.0
0xf0c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf0c5  ldstr    aUpdate0Set102N// "UPDATE {0} SET {1} = 0, {2} = NULL, {3}"...
0xf0ca  ldc.i4.5
0xf0cb  newarr   [mscorlib]System.Object
0xf0d0  dup
0xf0d1  ldc.i4.0
0xf0d2  ldstr    aRollupproperti_3// "RollupPropertiesBase"
0xf0d7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf0dc  stelem.ref
0xf0dd  dup
0xf0de  ldc.i4.1
0xf0df  ldstr    aBootstrapretry// "BootstrapRetryCount"
0xf0e4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf0e9  stelem.ref
0xf0ea  dup
0xf0eb  ldc.i4.2
0xf0ec  ldstr    aBootstrapstepn// "BootstrapStepNumber"
0xf0f1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf0f6  stelem.ref
0xf0f7  dup
0xf0f8  ldc.i4.3
0xf0f9  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0xf0fe  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf103  stelem.ref
0xf104  dup
0xf105  ldc.i4.4
0xf106  ldstr    aRollupproperti// "RollupPropertiesId"
0xf10b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf110  stelem.ref
0xf111  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf116  pop
0xf117  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf11c  stloc.1
0xf11d  ldloc.1
0xf11e  ldloc.0
0xf11f  callvirt instance string [mscorlib]System.Object::ToString()
0xf124  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf129  ldloc.1
0xf12a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf12f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf134  dup
0xf135  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xf13a  ldarg.0
0xf13b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf140  box      [mscorlib]System.Guid
0xf145  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf14a  pop
0xf14b  ldstr    aStatus_0// "@status"
0xf150  ldc.i4.0
0xf151  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BootstrapStatus
0xf156  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf15b  pop
0xf15c  ldarg.0
0xf15d  ldloc.1
0xf15e  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf163  pop
0xf164  leave.s  loc_F170
0xf166  ldloc.1
0xf167  brfalse.s loc_F16F
0xf169  ldloc.1
0xf16a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf16f  endfinally
0xf170  ret
```
