# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ProcessJobCompletion

- ea: `0xedf0`
- end: `0xeecf`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ProcessJobCompletion`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xe7b0`
- `0xe930`
- `0xedf0`
- `0xf710`

## string_xrefs

- `0xee57`: `RollupPropertiesId`
- `0xee8d`: `@rollupPropertiesId`
- `0xee09`: `UPDATE {0} SET {1} = 0, {2} = 0, {3} = @status, {4} = GETUTCDATE() WHERE {5} = @rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xedf0  ldarg.0
0xedf1  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::PerformObjectsCleanup()
0xedf6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xedfb  stloc.0
0xedfc  ldloc.0
0xedfd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xee02  pop
0xee03  ldloc.0
0xee04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xee09  ldstr    aUpdate0Set1020// "UPDATE {0} SET {1} = 0, {2} = 0, {3} = "...
0xee0e  ldc.i4.6
0xee0f  newarr   [mscorlib]System.Object
0xee14  dup
0xee15  ldc.i4.0
0xee16  ldstr    aRollupproperti_3// "RollupPropertiesBase"
0xee1b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xee20  stelem.ref
0xee21  dup
0xee22  ldc.i4.1
0xee23  ldstr    aBootstrapretry// "BootstrapRetryCount"
0xee28  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xee2d  stelem.ref
0xee2e  dup
0xee2f  ldc.i4.2
0xee30  ldstr    aBootstraptarge// "BootstrapTargetPointer"
0xee35  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xee3a  stelem.ref
0xee3b  dup
0xee3c  ldc.i4.3
0xee3d  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0xee42  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xee47  stelem.ref
0xee48  dup
0xee49  ldc.i4.4
0xee4a  ldstr    aLastcalculatio// "LastCalculationTime"
0xee4f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xee54  stelem.ref
0xee55  dup
0xee56  ldc.i4.5
0xee57  ldstr    aRollupproperti// "RollupPropertiesId"
0xee5c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xee61  stelem.ref
0xee62  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xee67  pop
0xee68  ldloc.0
0xee69  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xee6e  pop
0xee6f  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xee74  stloc.1
0xee75  ldloc.1
0xee76  ldloc.0
0xee77  callvirt instance string [mscorlib]System.Object::ToString()
0xee7c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xee81  ldloc.1
0xee82  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xee87  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xee8c  dup
0xee8d  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xee92  ldarg.0
0xee93  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xee98  box      [mscorlib]System.Guid
0xee9d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xeea2  pop
0xeea3  ldstr    aStatus_0// "@status"
0xeea8  ldc.i4.3
0xeea9  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BootstrapStatus
0xeeae  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xeeb3  pop
0xeeb4  ldarg.0
0xeeb5  ldloc.1
0xeeb6  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xeebb  pop
0xeebc  leave.s  loc_EEC8
0xeebe  ldloc.1
0xeebf  brfalse.s loc_EEC7
0xeec1  ldloc.1
0xeec2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeec7  endfinally
0xeec8  ldarg.1
0xeec9  callvirt instance void [mscorlib]System.Action::Invoke()
0xeece  ret
```
