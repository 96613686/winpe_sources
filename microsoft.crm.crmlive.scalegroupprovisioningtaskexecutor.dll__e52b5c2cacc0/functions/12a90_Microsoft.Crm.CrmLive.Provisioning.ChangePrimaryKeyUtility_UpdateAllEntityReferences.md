# Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::UpdateAllEntityReferences

- ea: `0x12a90`
- end: `0x12bd0`
- name: `Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::UpdateAllEntityReferences`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x126e0`

## callees

- `0x12a90`

## string_xrefs

- `0x12b62`: `update {0} set {1} = @new where {1} = @old`
- `0x12a9c`: `\n				select\n					case ar.IsStoredOnPrimaryTable\n					when 0 then er.ExtensionTableName\n					else er.BaseTableName\n					end ReferencingTable\n					, ar.PhysicalName referencingfield\n				from Relationship r\n				join EntityView eo on eo.EntityId = r.ReferencedEntityId\n				join EntityView er on er.EntityId = r.ReferencingEntityId\n				join AttributeView ar on ar.AttributeId = r.ReferencingAttributeId\n				join AttributeTypes at on ar.AttributeTypeId = at.AttributeTypeId\n				wher`

## pseudocode

```c

```

## disassembly

```asm
0x12a90  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::.ctor()
0x12a95  stloc.0
0x12a96  ldarg.0
0x12a97  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_connection
0x12a9c  ldstr    aSelectCaseArIs// "\r\n\t\t\t\tselect\r\n\t\t\t\t\tcase ar"...
0x12aa1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x12aa6  stloc.1
0x12aa7  ldloc.1
0x12aa8  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x12aad  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x12ab2  ldstr    aEntityname// "entityname"
0x12ab7  ldarg.0
0x12ab8  ldfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_entityName
0x12abd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12ac2  pop
0x12ac3  ldloc.1
0x12ac4  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x12ac9  stloc.2
0x12aca  br.s     loc_12AEB
0x12acc  ldloc.2
0x12acd  ldc.i4.0
0x12ace  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x12ad3  stloc.3
0x12ad4  ldloc.2
0x12ad5  ldc.i4.1
0x12ad6  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x12adb  stloc.s  4
0x12add  ldloc.0
0x12ade  ldloc.3
0x12adf  ldloc.s  4
0x12ae1  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::.ctor(var<u1>, !!T0)
0x12ae6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::Add(var<u1>)
0x12aeb  ldloc.2
0x12aec  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x12af1  brtrue.s loc_12ACC
0x12af3  leave.s  loc_12B09
0x12af5  ldloc.2
0x12af6  brfalse.s loc_12AFE
0x12af8  ldloc.2
0x12af9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12afe  endfinally
0x12aff  ldloc.1
0x12b00  brfalse.s loc_12B08
0x12b02  ldloc.1
0x12b03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12b08  endfinally
0x12b09  ldarg.0
0x12b0a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_connection
0x12b0f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x12b14  stloc.s  5
0x12b16  ldloc.s  5
0x12b18  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x12b1d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x12b22  dup
0x12b23  ldstr    aNew// "new"
0x12b28  ldarg.0
0x12b29  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_newId
0x12b2e  box      [mscorlib]System.Guid
0x12b33  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12b38  pop
0x12b39  ldstr    aOld_0// "old"
0x12b3e  ldarg.0
0x12b3f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_oldId
0x12b44  box      [mscorlib]System.Guid
0x12b49  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12b4e  pop
0x12b4f  ldloc.0
0x12b50  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x12b55  stloc.s  6
0x12b57  br.s     loc_12BAA
0x12b59  ldloca.s 6
0x12b5b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x12b60  stloc.s  7
0x12b62  ldstr    aUpdate0Set1New// "update {0} set {1} = @new where {1} = @"...
0x12b67  stloc.s  8
0x12b69  ldloca.s 7
0x12b6b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x12b70  stloc.s  9
0x12b72  ldloca.s 7
0x12b74  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x12b79  stloc.s  0xA
0x12b7b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12b80  ldloc.s  8
0x12b82  ldc.i4.2
0x12b83  newarr   [mscorlib]System.Object
0x12b88  dup
0x12b89  ldc.i4.0
0x12b8a  ldloc.s  9
0x12b8c  stelem.ref
0x12b8d  dup
0x12b8e  ldc.i4.1
0x12b8f  ldloc.s  0xA
0x12b91  stelem.ref
0x12b92  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12b97  stloc.s  8
0x12b99  ldloc.s  5
0x12b9b  ldloc.s  8
0x12b9d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x12ba2  ldloc.s  5
0x12ba4  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x12ba9  pop
0x12baa  ldloca.s 6
0x12bac  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::MoveNext()
0x12bb1  brtrue.s loc_12B59
0x12bb3  leave.s  loc_12BCF
0x12bb5  ldloca.s 6
0x12bb7  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>
0x12bbd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12bc2  endfinally
0x12bc3  ldloc.s  5
0x12bc5  brfalse.s loc_12BCE
0x12bc7  ldloc.s  5
0x12bc9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12bce  endfinally
0x12bcf  ret
```
