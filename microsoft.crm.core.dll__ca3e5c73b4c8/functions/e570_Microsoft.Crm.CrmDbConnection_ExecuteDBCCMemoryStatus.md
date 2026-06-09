# Microsoft.Crm.CrmDbConnection::ExecuteDBCCMemoryStatus

- ea: `0xe570`
- end: `0xe6af`
- name: `Microsoft.Crm.CrmDbConnection::ExecuteDBCCMemoryStatus`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0xe420`

## callees

- `0xd210`
- `0xd2f0`
- `0xd5f0`
- `0xdaf0`
- `0xe570`
- `0x54770`
- `0x54a10`
- `0x55d00`
- `0x55d20`

## string_xrefs

- `0xe5c6`: `D:\a\1\s\src\Platform\Core\DataServices\Connection\CrmDbConnection.cs`
- `0xe592`: `ConnectionOpened`

## pseudocode

```c

```

## disassembly

```asm
0xe570  ldarg.0
0xe571  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0xe576  callvirt instance string [System.Data]System.Data.IDbConnection::get_ConnectionString()
0xe57b  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(string connectionString)
0xe580  stloc.0
0xe581  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0xe586  stloc.1
0xe587  ldloc.0
0xe588  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0xe58d  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0xe592  ldstr    aConnectionopen// "ConnectionOpened"
0xe597  ldloc.0
0xe598  ldloc.1
0xe599  callvirt instance class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0xe59e  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::ConnectionEstablished(string eventName, class [System.Data]System.Data.IDbConnection connection, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0xe5a3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Text.StringBuilder>::.ctor()
0xe5a8  stloc.2
0xe5a9  ldloc.0
0xe5aa  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0xe5af  stloc.3
0xe5b0  ldloc.3
0xe5b1  ldstr    aDbccMemorystat// "DBCC MEMORYSTATUS"
0xe5b6  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xe5bb  ldloc.3
0xe5bc  ldc.i4   0x5BA
0xe5c1  ldstr    aExecutedbccmem// "ExecuteDBCCMemoryStatus"
0xe5c6  ldstr    aDA1SSrcPlatfor_3// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xe5cb  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xe5d0  stloc.s  4
0xe5d2  br       loc_E670
0xe5d7  ldnull
0xe5d8  stloc.s  5
0xe5da  ldc.i4.0
0xe5db  stloc.s  6
0xe5dd  br       loc_E662
0xe5e2  ldloc.s  4
0xe5e4  ldloc.s  6
0xe5e6  callvirt instance string [System.Data]System.Data.IDataRecord::GetName(int32)
0xe5eb  stloc.s  7
0xe5ed  ldloc.s  4
0xe5ef  ldloc.s  6
0xe5f1  callvirt instance object [System.Data]System.Data.IDataRecord::GetValue(int32)
0xe5f6  stloc.s  8
0xe5f8  ldloc.s  6
0xe5fa  brtrue.s loc_E62E
0xe5fc  ldloc.2
0xe5fd  ldloc.s  7
0xe5ff  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Text.StringBuilder>::ContainsKey(var<u1>)
0xe604  brtrue.s loc_E613
0xe606  ldloc.2
0xe607  ldloc.s  7
0xe609  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xe60e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Text.StringBuilder>::Add(var<u1>, !!T0)
0xe613  ldloc.2
0xe614  ldloc.s  7
0xe616  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Text.StringBuilder>::get_Item(void)
0xe61b  stloc.s  5
0xe61d  ldloc.s  5
0xe61f  ldstr    a0_0// "{0} = "
0xe624  ldloc.s  8
0xe626  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xe62b  pop
0xe62c  br.s     loc_E65C
0xe62e  ldloc.s  5
0xe630  ldstr    a01_0// "{0} {1}"
0xe635  ldloc.s  8
0xe637  ldloc.s  7
0xe639  ldstr    aValue// "Value"
0xe63e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe643  brtrue.s loc_E649
0xe645  ldloc.s  7
0xe647  br.s     loc_E64E
0xe649  ldsfld   string [mscorlib]System.String::Empty
0xe64e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0xe653  pop
0xe654  ldloc.s  5
0xe656  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xe65b  pop
0xe65c  ldloc.s  6
0xe65e  ldc.i4.1
0xe65f  add
0xe660  stloc.s  6
0xe662  ldloc.s  6
0xe664  ldloc.s  4
0xe666  callvirt instance int32 [System.Data]System.Data.IDataRecord::get_FieldCount()
0xe66b  blt      loc_E5E2
0xe670  ldloc.s  4
0xe672  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xe677  brtrue   loc_E5D7
0xe67c  ldloc.s  4
0xe67e  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0xe683  brtrue.s loc_E670
0xe685  leave.s  loc_E69D
0xe687  ldloc.s  4
0xe689  brfalse.s loc_E692
0xe68b  ldloc.s  4
0xe68d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe692  endfinally
0xe693  ldloc.3
0xe694  brfalse.s loc_E69C
0xe696  ldloc.3
0xe697  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe69c  endfinally
0xe69d  ldloc.2
0xe69e  stloc.s  9
0xe6a0  leave.s  loc_E6AC
0xe6a2  ldloc.0
0xe6a3  brfalse.s loc_E6AB
0xe6a5  ldloc.0
0xe6a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe6ab  endfinally
0xe6ac  ldloc.s  9
0xe6ae  ret
```
