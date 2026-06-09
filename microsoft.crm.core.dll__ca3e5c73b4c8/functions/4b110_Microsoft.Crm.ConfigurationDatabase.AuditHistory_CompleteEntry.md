# Microsoft.Crm.ConfigurationDatabase.AuditHistory::CompleteEntry

- ea: `0x4b110`
- end: `0x4b1d2`
- name: `Microsoft.Crm.ConfigurationDatabase.AuditHistory::CompleteEntry`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd2f0`
- `0xd380`
- `0xd620`
- `0xdab0`
- `0x1fee0`
- `0x4a700`
- `0x4b110`

## string_xrefs

- `0x4b1b4`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\AuditHistory.cs`
- `0x4b162`: `exec p_CompleteAuditEntry @AuditEntryId,@Result,@Details`
- `0x4b1af`: `CompleteEntry`

## pseudocode

```c

```

## disassembly

```asm
0x4b110  ldarg.3
0x4b111  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4b116  brfalse.s loc_4B14F
0x4b118  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0x4b11d  stloc.0
0x4b11e  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4b123  dup
0x4b124  ldstr    aStackTraceInPl// "Stack trace in place of missing details"
0x4b129  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4b12e  pop
0x4b12f  dup
0x4b130  call     string [mscorlib]System.Environment::get_NewLine()
0x4b135  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4b13a  pop
0x4b13b  dup
0x4b13c  ldloc.0
0x4b13d  call     string Microsoft.Crm.CrmTrace::StackTraceToString(class [mscorlib]System.Diagnostics.StackTrace trace)
0x4b142  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4b147  pop
0x4b148  callvirt instance string [mscorlib]System.Object::ToString()
0x4b14d  starg.s  3
0x4b14f  ldarg.0
0x4b150  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.AuditHistory::_datacenterId
0x4b155  call     class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConfigDBConnection(valuetype [mscorlib]System.Guid datacenterId)
0x4b15a  stloc.1
0x4b15b  ldloc.1
0x4b15c  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x4b161  ldloc.1
0x4b162  ldstr    aExecPCompletea// "exec p_CompleteAuditEntry @AuditEntryId"...
0x4b167  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x4b16c  dup
0x4b16d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4b172  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4b177  dup
0x4b178  ldstr    aAuditentryid// "@AuditEntryId"
0x4b17d  ldarg.1
0x4b17e  box      [mscorlib]System.Guid
0x4b183  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4b188  pop
0x4b189  dup
0x4b18a  ldstr    aResult// "@Result"
0x4b18f  ldarg.2
0x4b190  brtrue.s loc_4B195
0x4b192  ldc.i4.2
0x4b193  br.s     loc_4B196
0x4b195  ldc.i4.1
0x4b196  box      [mscorlib]System.Int32
0x4b19b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4b1a0  pop
0x4b1a1  ldstr    aDetails// "@Details"
0x4b1a6  ldarg.3
0x4b1a7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4b1ac  pop
0x4b1ad  ldc.i4.s 0x70
0x4b1af  ldstr    aCompleteentry// "CompleteEntry"
0x4b1b4  ldstr    aDA1SSrcPlatfor_34// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4b1b9  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4b1be  pop
0x4b1bf  ldloc.1
0x4b1c0  callvirt instance void Microsoft.Crm.CrmDbConnection::Close()
0x4b1c5  leave.s  loc_4B1D1
0x4b1c7  ldloc.1
0x4b1c8  brfalse.s loc_4B1D0
0x4b1ca  ldloc.1
0x4b1cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b1d0  endfinally
0x4b1d1  ret
```
