# Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::UpdateRollupStateOnRegardingObject

- ea: `0xe4a0`
- end: `0xe57c`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::UpdateRollupStateOnRegardingObject`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe090`

## callees

- `0xdc60`
- `0xdd20`
- `0xe4a0`
- `0xe770`
- `0x170f0`

## string_xrefs

- `0xe4cd`: `UPDATE \n	{0} \nSET \n	{1} = @errorCode \nWHERE \n	{2} = @regardingObjectId`

## pseudocode

```c

```

## disassembly

```asm
0xe4a0  ldarg.1
0xe4a1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupProperties()
0xe4a6  brtrue.s loc_E4AA
0xe4a8  ldc.i4.1
0xe4a9  ret
0xe4aa  newobj   instance void <>c__DisplayClass10_0::.ctor()
0xe4af  stloc.0
0xe4b0  ldloc.0
0xe4b1  ldarg.0
0xe4b2  stfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier <>c__DisplayClass10_0::<>4__this
0xe4b7  ldloc.0
0xe4b8  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xe4bd  stfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass10_0::crmDbCommand
0xe4c2  ldloc.0
0xe4c3  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass10_0::crmDbCommand
0xe4c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe4cd  ldstr    aUpdate0Set1Err// "UPDATE \r\n\t{0} \r\nSET \r\n\t{1} = @e"...
0xe4d2  ldc.i4.3
0xe4d3  newarr   [mscorlib]System.Object
0xe4d8  dup
0xe4d9  ldc.i4.0
0xe4da  ldarg.1
0xe4db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupProperties()
0xe4e0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData::get_RollupEntityBaseTableName()
0xe4e5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xe4ea  stelem.ref
0xe4eb  dup
0xe4ec  ldc.i4.1
0xe4ed  ldarg.1
0xe4ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupProperties()
0xe4f3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData::get_RollupEntityStateAttributePhysicalName()
0xe4f8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xe4fd  stelem.ref
0xe4fe  dup
0xe4ff  ldc.i4.2
0xe500  ldarg.1
0xe501  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupProperties()
0xe506  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData::get_RollupEntityPrimaryKeyPhysicalName()
0xe50b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xe510  stelem.ref
0xe511  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe516  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xe51b  ldloc.0
0xe51c  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass10_0::crmDbCommand
0xe521  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xe526  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xe52b  dup
0xe52c  ldstr    aErrorcode// "@errorCode"
0xe531  ldstr    a4_0// "4"
0xe536  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe53b  pop
0xe53c  ldstr    aRegardingobjec_2// "@regardingObjectId"
0xe541  ldarg.1
0xe542  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RegardingObjectId()
0xe547  box      [mscorlib]System.Guid
0xe54c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe551  pop
0xe552  ldloc.0
0xe553  ldftn    instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult <>c__DisplayClass10_0::<UpdateRollupStateOnRegardingObject>b__0()
0xe559  newobj   instance void class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult>::.ctor(object, native int)
0xe55e  call     valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.SqlErrorCodes::WrapSqlException(class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult> sqlFunc)
0xe563  stloc.1
0xe564  leave.s  loc_E57A
0xe566  ldloc.0
0xe567  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass10_0::crmDbCommand
0xe56c  brfalse.s loc_E579
0xe56e  ldloc.0
0xe56f  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass10_0::crmDbCommand
0xe574  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe579  endfinally
0xe57a  ldloc.1
0xe57b  ret
```
