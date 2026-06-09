# <>c__DisplayClass16_0::<CallStoredProcedure>b__0

- ea: `0x17170`
- end: `0x17290`
- name: `<>c__DisplayClass16_0::<CallStoredProcedure>b__0`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0xe600`
- `0x17170`

## string_xrefs

- `0x17170`: `storedProcedureName`

## pseudocode

```c

```

## disassembly

```asm
0x17170  ldstr    aStoredprocedur// "storedProcedureName"
0x17175  ldarg.0
0x17176  ldfld    string <>c__DisplayClass16_0::storedProcedureName
0x1717b  callvirt instance string [mscorlib]System.Object::ToString()
0x17180  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0x17185  ldstr    aRegardingid// "regardingId"
0x1718a  ldarg.0
0x1718b  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass16_0::regardingId
0x17190  constrained. [mscorlib]System.Guid
0x17196  callvirt instance string [mscorlib]System.Object::ToString()
0x1719b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0x171a0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x171a5  stloc.0
0x171a6  ldloc.0
0x171a7  ldc.i4.4
0x171a8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x171ad  ldloc.0
0x171ae  ldarg.0
0x171af  ldfld    string <>c__DisplayClass16_0::storedProcedureName
0x171b4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x171b9  ldloc.0
0x171ba  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x171bf  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x171c4  dup
0x171c5  ldstr    aId// "@id"
0x171ca  ldarg.0
0x171cb  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass16_0::regardingId
0x171d0  box      [mscorlib]System.Guid
0x171d5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x171da  pop
0x171db  dup
0x171dc  ldstr    aCalculatenow// "@calculateNow"
0x171e1  ldc.i4.0
0x171e2  box      [mscorlib]System.Int32
0x171e7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x171ec  pop
0x171ed  dup
0x171ee  ldstr    aState_0// "@state"
0x171f3  ldarg.0
0x171f4  ldfld    int32 <>c__DisplayClass16_0::errorState
0x171f9  box      [mscorlib]System.Int32
0x171fe  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x17203  pop
0x17204  ldstr    aNextitemid// "@nextItemId"
0x17209  ldc.i4.s 0xE
0x1720b  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0x17210  stloc.1
0x17211  ldloc.1
0x17212  ldc.i4.2
0x17213  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x17218  ldloc.1
0x17219  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x1721e  pop
0x1721f  ldarg.0
0x17220  ldfld    class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess <>c__DisplayClass16_0::<>4__this
0x17225  ldloc.0
0x17226  call     instance object Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0x1722b  pop
0x1722c  ldloc.1
0x1722d  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x17232  isinst   [mscorlib]System.DBNull
0x17237  brtrue.s loc_17246
0x17239  ldloc.1
0x1723a  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x1723f  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x17244  br.s     loc_1724F
0x17246  ldloca.s 3
0x17248  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1724e  ldloc.3
0x1724f  stloc.2
0x17250  ldstr    aNextitemid_0// "nextItemId"
0x17255  ldloca.s 2
0x17257  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1725c  brtrue.s loc_17265
0x1725e  ldsfld   string [mscorlib]System.String::Empty
0x17263  br.s     loc_1727B
0x17265  ldloca.s 2
0x17267  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1726c  stloc.s  4
0x1726e  ldloca.s 4
0x17270  constrained. [mscorlib]System.Guid
0x17276  callvirt instance string [mscorlib]System.Object::ToString()
0x1727b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0x17280  ldloc.2
0x17281  stloc.3
0x17282  leave.s  loc_1728E
0x17284  ldloc.0
0x17285  brfalse.s loc_1728D
0x17287  ldloc.0
0x17288  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1728d  endfinally
0x1728e  ldloc.3
0x1728f  ret
```
