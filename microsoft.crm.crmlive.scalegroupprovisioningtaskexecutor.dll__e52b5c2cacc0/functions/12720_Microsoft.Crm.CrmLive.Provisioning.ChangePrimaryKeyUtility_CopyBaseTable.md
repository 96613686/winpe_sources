# Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::CopyBaseTable

- ea: `0x12720`
- end: `0x1296b`
- name: `Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::CopyBaseTable`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x126e0`

## callees

- `0x12720`

## string_xrefs

- `0x12739`: `\n				declare @entityid uniqueidentifier\n\n				select @entityid = EntityId\n				from EntityView\n				where Name = @entityname\n				\n				select \n					e.BaseTableName,\n					e.ExtensionTableName,\n					a.PhysicalName\n				from EntityView e\n				join AttributeView a on a.EntityId = e.EntityId\n				where e.EntityId = @entityid\n				and a.IsPkAttribute = 1\n\n				select a.PhysicalName\n				from AttributeView a\n				join AttributeTypes at \n				on at.AttributeTypeId = a.Attribute`

## pseudocode

```c

```

## disassembly

```asm
0x12720  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x12725  stloc.0
0x12726  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1272b  stloc.1
0x1272c  ldarg.0
0x1272d  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_connection
0x12732  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x12737  stloc.2
0x12738  ldloc.2
0x12739  ldstr    aDeclareEntityi// "\r\n\t\t\t\tdeclare @entityid uniqueide"...
0x1273e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x12743  ldloc.2
0x12744  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x12749  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1274e  stloc.3
0x1274f  ldloc.3
0x12750  ldstr    aEntityname// "entityname"
0x12755  ldarg.0
0x12756  ldfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_entityName
0x1275b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12760  pop
0x12761  ldloc.2
0x12762  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x12767  stloc.s  4
0x12769  ldloc.s  4
0x1276b  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x12770  brtrue.s loc_1277D
0x12772  ldstr    aUnableToFindPr// "Unable to find primary key for entity"
0x12777  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1277c  throw
0x1277d  ldarg.0
0x1277e  ldloc.s  4
0x12780  ldc.i4.0
0x12781  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x12786  stfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_baseTable
0x1278b  ldarg.0
0x1278c  ldloc.s  4
0x1278e  ldc.i4.1
0x1278f  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x12794  brtrue.s loc_127A0
0x12796  ldloc.s  4
0x12798  ldc.i4.1
0x12799  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x1279e  br.s     loc_127A1
0x127a0  ldnull
0x127a1  stfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_extensionTable
0x127a6  ldarg.0
0x127a7  ldloc.s  4
0x127a9  ldc.i4.2
0x127aa  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x127af  stfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_primaryKey
0x127b4  ldloc.s  4
0x127b6  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x127bb  brfalse.s loc_127C8
0x127bd  ldstr    aUnableToDeterm// "Unable to determine primary key for ent"...
0x127c2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x127c7  throw
0x127c8  ldloc.s  4
0x127ca  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x127cf  pop
0x127d0  br.s     loc_127E0
0x127d2  ldloc.1
0x127d3  ldloc.s  4
0x127d5  ldc.i4.0
0x127d6  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x127db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x127e0  ldloc.s  4
0x127e2  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x127e7  brtrue.s loc_127D2
0x127e9  leave.s  loc_127F7
0x127eb  ldloc.s  4
0x127ed  brfalse.s loc_127F6
0x127ef  ldloc.s  4
0x127f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x127f6  endfinally
0x127f7  ldloc.0
0x127f8  ldstr    aInsert// "insert "
0x127fd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12802  pop
0x12803  ldloc.0
0x12804  ldarg.0
0x12805  ldfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_baseTable
0x1280a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1280f  pop
0x12810  ldloc.0
0x12811  ldstr    asc_405FC// "("
0x12816  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1281b  pop
0x1281c  ldloc.0
0x1281d  ldarg.0
0x1281e  ldfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_primaryKey
0x12823  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12828  pop
0x12829  ldloc.1
0x1282a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1282f  stloc.s  5
0x12831  br.s     loc_12851
0x12833  ldloca.s 5
0x12835  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1283a  stloc.s  6
0x1283c  ldloc.0
0x1283d  ldstr    asc_3F5CC// ", "
0x12842  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12847  pop
0x12848  ldloc.0
0x12849  ldloc.s  6
0x1284b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12850  pop
0x12851  ldloca.s 5
0x12853  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x12858  brtrue.s loc_12833
0x1285a  leave.s  loc_1286A
0x1285c  ldloca.s 5
0x1285e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x12864  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12869  endfinally
0x1286a  ldloc.0
0x1286b  ldstr    aSelectNew// ") select @new"
0x12870  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12875  pop
0x12876  ldloc.1
0x12877  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1287c  stloc.s  5
0x1287e  br.s     loc_128C0
0x12880  ldloca.s 5
0x12882  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x12887  stloc.s  7
0x12889  ldloc.0
0x1288a  ldstr    asc_3F5CC// ", "
0x1288f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12894  pop
0x12895  ldarg.0
0x12896  ldfld    class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_uniqueKeyFields
0x1289b  ldloc.s  7
0x1289d  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x128a2  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0x128a7  brfalse.s loc_128B7
0x128a9  ldloc.0
0x128aa  ldstr    aNewid// "newid()"
0x128af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x128b4  pop
0x128b5  br.s     loc_128C0
0x128b7  ldloc.0
0x128b8  ldloc.s  7
0x128ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x128bf  pop
0x128c0  ldloca.s 5
0x128c2  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x128c7  brtrue.s loc_12880
0x128c9  leave.s  loc_128D9
0x128cb  ldloca.s 5
0x128cd  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x128d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x128d8  endfinally
0x128d9  ldloc.0
0x128da  ldstr    aFrom// " from "
0x128df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x128e4  pop
0x128e5  ldloc.0
0x128e6  ldarg.0
0x128e7  ldfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_baseTable
0x128ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x128f1  pop
0x128f2  ldloc.0
0x128f3  ldstr    aWhere// " where "
0x128f8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x128fd  pop
0x128fe  ldloc.0
0x128ff  ldarg.0
0x12900  ldfld    string Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_primaryKey
0x12905  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1290a  pop
0x1290b  ldloc.0
0x1290c  ldstr    aOld// " = @old"
0x12911  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12916  pop
0x12917  ldloc.3
0x12918  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x1291d  ldloc.3
0x1291e  ldstr    aNew// "new"
0x12923  ldarg.0
0x12924  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_newId
0x12929  box      [mscorlib]System.Guid
0x1292e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12933  pop
0x12934  ldloc.3
0x12935  ldstr    aOld_0// "old"
0x1293a  ldarg.0
0x1293b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ChangePrimaryKeyUtility::_oldId
0x12940  box      [mscorlib]System.Guid
0x12945  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1294a  pop
0x1294b  ldloc.2
0x1294c  ldloc.0
0x1294d  callvirt instance string [mscorlib]System.Object::ToString()
0x12952  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x12957  ldloc.2
0x12958  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1295d  pop
0x1295e  leave.s  loc_1296A
0x12960  ldloc.2
0x12961  brfalse.s loc_12969
0x12963  ldloc.2
0x12964  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12969  endfinally
0x1296a  ret
```
