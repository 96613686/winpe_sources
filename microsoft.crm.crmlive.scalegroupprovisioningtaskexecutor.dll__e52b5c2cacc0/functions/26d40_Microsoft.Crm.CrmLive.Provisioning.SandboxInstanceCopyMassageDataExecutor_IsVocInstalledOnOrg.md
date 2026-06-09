# Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::IsVocInstalledOnOrg

- ea: `0x26d40`
- end: `0x26d8c`
- name: `Microsoft.Crm.CrmLive.Provisioning.SandboxInstanceCopyMassageDataExecutor::IsVocInstalledOnOrg`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x26c70`

## callees

- `0x26d40`

## string_xrefs

- `0x26d5d`: `IsVocInstalledOnOrg`
- `0x26d62`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SandboxInstanceCopyMassageDataExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x26d40  ldarg.0
0x26d41  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26d46  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x26d4b  stloc.0
0x26d4c  ldloc.0
0x26d4d  ldstr    aSelectUniquena// "SELECT [UniqueName] FROM [dbo].[Solutio"...
0x26d52  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x26d57  ldloc.0
0x26d58  ldc.i4   0xCF
0x26d5d  ldstr    aIsvocinstalled// "IsVocInstalledOnOrg"
0x26d62  ldstr    aDDbsShDccm2110_41// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x26d67  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x26d6c  stloc.1
0x26d6d  ldloc.1
0x26d6e  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x26d73  stloc.2
0x26d74  leave.s  loc_26D8A
0x26d76  ldloc.1
0x26d77  brfalse.s loc_26D7F
0x26d79  ldloc.1
0x26d7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d7f  endfinally
0x26d80  ldloc.0
0x26d81  brfalse.s loc_26D89
0x26d83  ldloc.0
0x26d84  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26d89  endfinally
0x26d8a  ldloc.2
0x26d8b  ret
```
