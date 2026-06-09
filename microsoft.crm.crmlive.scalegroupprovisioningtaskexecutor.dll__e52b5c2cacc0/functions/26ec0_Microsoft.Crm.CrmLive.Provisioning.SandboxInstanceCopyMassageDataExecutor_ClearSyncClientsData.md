# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::ClearSyncClientsData

- ea: `0x26ec0`
- end: `0x26f86`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::ClearSyncClientsData`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x26b20`

## callees

- `0x26ec0`
- `0x28430`

## string_xrefs

- `0x26ee9`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SandboxInstanceCopyMassageDataExecutor.cs`
- `0x26f60`: `Exception ocurred during Sync tables cleanup: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x26ec0  ldarg.0
0x26ec1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26ec6  ldc.i4.1
0x26ec7  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(bool)
0x26ecc  stloc.0
0x26ecd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x26ed2  stloc.1
0x26ed3  ldloc.0
0x26ed4  ldstr    aSelectSubscrip// "SELECT SubscriptionId FROM Subscription"
0x26ed9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x26ede  ldloc.0
0x26edf  ldc.i4   0x127
0x26ee4  ldstr    aClearsyncclien// "ClearSyncClientsData"
0x26ee9  ldstr    aDDbsShDccm2110_41// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x26eee  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x26ef3  stloc.2
0x26ef4  br.s     loc_26F05
0x26ef6  ldloc.2
0x26ef7  ldc.i4.0
0x26ef8  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x26efd  stloc.3
0x26efe  ldloc.1
0x26eff  ldloc.3
0x26f00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x26f05  ldloc.2
0x26f06  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x26f0b  brtrue.s loc_26EF6
0x26f0d  leave.s  loc_26F19
0x26f0f  ldloc.2
0x26f10  brfalse.s loc_26F18
0x26f12  ldloc.2
0x26f13  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26f18  endfinally
0x26f19  ldloc.1
0x26f1a  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::PrepareDropSyncTablesStatements(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> subscriptionIds)
0x26f1f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x26f24  stloc.s  4
0x26f26  br.s     loc_26F40
0x26f28  ldloc.s  4
0x26f2a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x26f2f  stloc.s  5
0x26f31  ldloc.0
0x26f32  ldloc.s  5
0x26f34  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x26f39  ldloc.0
0x26f3a  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x26f3f  pop
0x26f40  ldloc.s  4
0x26f42  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26f47  brtrue.s loc_26F28
0x26f49  leave.s  loc_26F57
0x26f4b  ldloc.s  4
0x26f4d  brfalse.s loc_26F56
0x26f4f  ldloc.s  4
0x26f51  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26f56  endfinally
0x26f57  leave.s  loc_26F85
0x26f59  stloc.s  6
0x26f5b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26f60  ldstr    aExceptionOcurr// "Exception ocurred during Sync tables cl"...
0x26f65  ldc.i4.1
0x26f66  newarr   [mscorlib]System.Object
0x26f6b  dup
0x26f6c  ldc.i4.0
0x26f6d  ldloc.s  6
0x26f6f  stelem.ref
0x26f70  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26f75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x26f7a  throw
0x26f7b  ldloc.0
0x26f7c  brfalse.s loc_26F84
0x26f7e  ldloc.0
0x26f7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26f84  endfinally
0x26f85  ret
```
