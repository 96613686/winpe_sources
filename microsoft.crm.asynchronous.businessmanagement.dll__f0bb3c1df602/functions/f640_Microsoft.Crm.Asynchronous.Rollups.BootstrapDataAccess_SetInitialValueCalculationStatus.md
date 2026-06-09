# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SetInitialValueCalculationStatus

- ea: `0xf640`
- end: `0xf6d0`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SetInitialValueCalculationStatus`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0xc1b0`

## callees

- `0xe7b0`
- `0xe930`
- `0xf640`

## string_xrefs

- `0xf673`: `RollupPropertiesId`
- `0xf6a5`: `@rollupPropertiesId`
- `0xf64c`: `UPDATE {0} SET {1} = @initialValueCalculationStatus WHERE {2} = @rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xf640  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf645  stloc.0
0xf646  ldloc.0
0xf647  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf64c  ldstr    aUpdate0Set1Ini// "UPDATE {0} SET {1} = @initialValueCalcu"...
0xf651  ldc.i4.3
0xf652  newarr   [mscorlib]System.Object
0xf657  dup
0xf658  ldc.i4.0
0xf659  ldstr    aRollupproperti_3// "RollupPropertiesBase"
0xf65e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf663  stelem.ref
0xf664  dup
0xf665  ldc.i4.1
0xf666  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0xf66b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf670  stelem.ref
0xf671  dup
0xf672  ldc.i4.2
0xf673  ldstr    aRollupproperti// "RollupPropertiesId"
0xf678  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf67d  stelem.ref
0xf67e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf683  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf688  ldloc.0
0xf689  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf68e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf693  dup
0xf694  ldstr    aInitialvalueca_0// "@initialValueCalculationStatus"
0xf699  ldarg.1
0xf69a  box      valuetype [mscorlib]System.Nullable`1<int32>
0xf69f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf6a4  pop
0xf6a5  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xf6aa  ldarg.0
0xf6ab  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf6b0  box      [mscorlib]System.Guid
0xf6b5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf6ba  pop
0xf6bb  ldarg.0
0xf6bc  ldloc.0
0xf6bd  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf6c2  pop
0xf6c3  leave.s  loc_F6CF
0xf6c5  ldloc.0
0xf6c6  brfalse.s loc_F6CE
0xf6c8  ldloc.0
0xf6c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf6ce  endfinally
0xf6cf  ret
```
