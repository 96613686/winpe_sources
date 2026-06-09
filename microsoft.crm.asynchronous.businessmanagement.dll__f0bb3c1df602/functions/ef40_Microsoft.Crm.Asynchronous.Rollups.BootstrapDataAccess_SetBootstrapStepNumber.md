# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SetBootstrapStepNumber

- ea: `0xef40`
- end: `0xf007`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SetBootstrapStepNumber`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xe7b0`
- `0xe930`
- `0xeaf0`
- `0xef40`

## string_xrefs

- `0xefaa`: `RollupPropertiesId`
- `0xefdc`: `@rollupPropertiesId`
- `0xef83`: `UPDATE {0} SET {1} = @stepNumber WHERE {2} = @rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xef40  ldarga.s 1
0xef42  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xef47  brfalse.s loc_EF77
0xef49  ldarga.s 1
0xef4b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xef50  ldc.i4.1
0xef51  beq.s    loc_EF77
0xef53  ldarg.0
0xef54  ldarg.0
0xef55  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xef5a  call     instance class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::GetBootstrapInformation(valuetype [mscorlib]System.Guid rollupPropertiesId)
0xef5f  callvirt instance var<u1> class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::get_Item5()
0xef64  ldc.i4.1
0xef65  beq.s    loc_EF77
0xef67  ldstr    aTheCurrentJobI// "The current job is no longer in progres"...
0xef6c  ldc.i4   0x80044162
0xef71  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xef76  throw
0xef77  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xef7c  stloc.0
0xef7d  ldloc.0
0xef7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef83  ldstr    aUpdate0Set1Ste// "UPDATE {0} SET {1} = @stepNumber WHERE "...
0xef88  ldc.i4.3
0xef89  newarr   [mscorlib]System.Object
0xef8e  dup
0xef8f  ldc.i4.0
0xef90  ldstr    aRollupproperti_3// "RollupPropertiesBase"
0xef95  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xef9a  stelem.ref
0xef9b  dup
0xef9c  ldc.i4.1
0xef9d  ldstr    aBootstrapstepn// "BootstrapStepNumber"
0xefa2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xefa7  stelem.ref
0xefa8  dup
0xefa9  ldc.i4.2
0xefaa  ldstr    aRollupproperti// "RollupPropertiesId"
0xefaf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xefb4  stelem.ref
0xefb5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xefba  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xefbf  ldloc.0
0xefc0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xefc5  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xefca  dup
0xefcb  ldstr    aStepnumber// "@stepNumber"
0xefd0  ldarg.1
0xefd1  box      valuetype [mscorlib]System.Nullable`1<int32>
0xefd6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xefdb  pop
0xefdc  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xefe1  ldarg.0
0xefe2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xefe7  box      [mscorlib]System.Guid
0xefec  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xeff1  pop
0xeff2  ldarg.0
0xeff3  ldloc.0
0xeff4  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xeff9  pop
0xeffa  leave.s  loc_F006
0xeffc  ldloc.0
0xeffd  brfalse.s loc_F005
0xefff  ldloc.0
0xf000  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf005  endfinally
0xf006  ret
```
