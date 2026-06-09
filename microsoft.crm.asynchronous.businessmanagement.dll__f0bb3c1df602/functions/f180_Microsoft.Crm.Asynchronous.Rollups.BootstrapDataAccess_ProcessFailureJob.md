# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ProcessFailureJob

- ea: `0xf180`
- end: `0xf25e`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ProcessFailureJob`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xe7b0`
- `0xe930`
- `0xf180`
- `0xf710`

## string_xrefs

- `0xf1da`: `RollupPropertiesId`
- `0xf210`: `@rollupPropertiesId`
- `0xf199`: `UPDATE {0} SET {1} = @status, {2} = @statusCode, {3} = @initialValueCalculationStatus WHERE {4} = @rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xf180  ldarg.0
0xf181  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::PerformObjectsCleanup()
0xf186  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf18b  stloc.0
0xf18c  ldloc.0
0xf18d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf192  pop
0xf193  ldloc.0
0xf194  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf199  ldstr    aUpdate0Set1Sta// "UPDATE {0} SET {1} = @status, {2} = @st"...
0xf19e  ldc.i4.5
0xf19f  newarr   [mscorlib]System.Object
0xf1a4  dup
0xf1a5  ldc.i4.0
0xf1a6  ldstr    aRollupproperti_3// "RollupPropertiesBase"
0xf1ab  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf1b0  stelem.ref
0xf1b1  dup
0xf1b2  ldc.i4.1
0xf1b3  ldstr    aStatecode// "statecode"
0xf1b8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf1bd  stelem.ref
0xf1be  dup
0xf1bf  ldc.i4.2
0xf1c0  ldstr    aStatuscode// "statuscode"
0xf1c5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf1ca  stelem.ref
0xf1cb  dup
0xf1cc  ldc.i4.3
0xf1cd  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0xf1d2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf1d7  stelem.ref
0xf1d8  dup
0xf1d9  ldc.i4.4
0xf1da  ldstr    aRollupproperti// "RollupPropertiesId"
0xf1df  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf1e4  stelem.ref
0xf1e5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf1ea  pop
0xf1eb  ldloc.0
0xf1ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xf1f1  pop
0xf1f2  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf1f7  stloc.1
0xf1f8  ldloc.1
0xf1f9  ldloc.0
0xf1fa  callvirt instance string [mscorlib]System.Object::ToString()
0xf1ff  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf204  ldloc.1
0xf205  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf20a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf20f  dup
0xf210  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xf215  ldarg.0
0xf216  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf21b  box      [mscorlib]System.Guid
0xf220  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf225  pop
0xf226  dup
0xf227  ldstr    aStatus_0// "@status"
0xf22c  ldc.i4.1
0xf22d  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RollupStateCode
0xf232  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf237  pop
0xf238  ldstr    aInitialvalueca_0// "@initialValueCalculationStatus"
0xf23d  ldc.i4.4
0xf23e  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BootstrapStatus
0xf243  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf248  pop
0xf249  ldarg.0
0xf24a  ldloc.1
0xf24b  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf250  pop
0xf251  leave.s  loc_F25D
0xf253  ldloc.1
0xf254  brfalse.s loc_F25C
0xf256  ldloc.1
0xf257  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf25c  endfinally
0xf25d  ret
```
