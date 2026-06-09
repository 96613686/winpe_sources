# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::UpdateVersionNumber

- ea: `0x1f020`
- end: `0x1f08f`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::UpdateVersionNumber`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e680`

## callees

- `0x1f020`
- `0x1f0f0`

## string_xrefs

- `0x1f035`: `IF EXISTS (SELECT 1 FROM {0} WHERE ObjectId = @objectId)\n											UPDATE {0} SET MatchCode = @matchcode WHERE ObjectId = @objectId\n										  ELSE\n											INSERT INTO {0} (ObjectId, MatchCode) VALUES(@objectId, @matchcode)`

## pseudocode

```c

```

## disassembly

```asm
0x1f020  ldarg.1
0x1f021  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f026  brfalse.s loc_1F029
0x1f028  ret
0x1f029  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1f02e  stloc.0
0x1f02f  ldloc.0
0x1f030  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f035  ldstr    aIfExistsSelect_2// "IF EXISTS (SELECT 1 FROM {0} WHERE Obje"...
0x1f03a  ldc.i4.1
0x1f03b  newarr   [mscorlib]System.Object
0x1f040  dup
0x1f041  ldc.i4.0
0x1f042  ldarg.0
0x1f043  stelem.ref
0x1f044  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f049  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1f04e  ldloc.0
0x1f04f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1f054  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1f059  dup
0x1f05a  ldstr    aObjectid_0// "@objectId"
0x1f05f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f064  box      [mscorlib]System.Guid
0x1f069  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f06e  pop
0x1f06f  ldstr    aMatchcode_0// "@matchcode"
0x1f074  ldarg.1
0x1f075  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f07a  pop
0x1f07b  ldarg.2
0x1f07c  ldloc.0
0x1f07d  callvirt instance void Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess::ExecuteCommand(class [System.Data]System.Data.IDbCommand command)
0x1f082  leave.s  loc_1F08E
0x1f084  ldloc.0
0x1f085  brfalse.s loc_1F08D
0x1f087  ldloc.0
0x1f088  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f08d  endfinally
0x1f08e  ret
```
