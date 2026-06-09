# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SetBootstrapRetryCount

- ea: `0xf010`
- end: `0xf0a0`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SetBootstrapRetryCount`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xe7b0`
- `0xe930`
- `0xf010`

## string_xrefs

- `0xf043`: `RollupPropertiesId`
- `0xf075`: `@rollupPropertiesId`
- `0xf01c`: `UPDATE {0} SET {1} = @retryCount WHERE {2} = @rollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xf010  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf015  stloc.0
0xf016  ldloc.0
0xf017  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf01c  ldstr    aUpdate0Set1Ret// "UPDATE {0} SET {1} = @retryCount WHERE "...
0xf021  ldc.i4.3
0xf022  newarr   [mscorlib]System.Object
0xf027  dup
0xf028  ldc.i4.0
0xf029  ldstr    aRollupproperti_2// "RollupProperties"
0xf02e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf033  stelem.ref
0xf034  dup
0xf035  ldc.i4.1
0xf036  ldstr    aBootstrapretry// "BootstrapRetryCount"
0xf03b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf040  stelem.ref
0xf041  dup
0xf042  ldc.i4.2
0xf043  ldstr    aRollupproperti// "RollupPropertiesId"
0xf048  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf04d  stelem.ref
0xf04e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf053  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf058  ldloc.0
0xf059  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf05e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf063  dup
0xf064  ldstr    aRetrycount// "@retryCount"
0xf069  ldarg.1
0xf06a  box      valuetype [mscorlib]System.Nullable`1<int32>
0xf06f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf074  pop
0xf075  ldstr    aRollupproperti_0// "@rollupPropertiesId"
0xf07a  ldarg.0
0xf07b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf080  box      [mscorlib]System.Guid
0xf085  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf08a  pop
0xf08b  ldarg.0
0xf08c  ldloc.0
0xf08d  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf092  pop
0xf093  leave.s  loc_F09F
0xf095  ldloc.0
0xf096  brfalse.s loc_F09E
0xf098  ldloc.0
0xf099  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf09e  endfinally
0xf09f  ret
```
