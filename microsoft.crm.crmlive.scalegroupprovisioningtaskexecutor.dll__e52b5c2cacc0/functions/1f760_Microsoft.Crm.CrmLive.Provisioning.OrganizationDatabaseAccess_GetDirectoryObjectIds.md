# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetDirectoryObjectIds

- ea: `0x1f760`
- end: `0x1f7e0`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetDirectoryObjectIds`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f760`

## string_xrefs

- `0x1f78e`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1f766`: `SELECT AzureActiveDirectoryObjectId FROM SystemUserBase WHERE AzureActiveDirectoryObjectId IS NOT NULL AND IsDisabled = 0`
- `0x1f789`: `GetDirectoryObjectIds`
- `0x1f79f`: `AzureActiveDirectoryObjectId`

## pseudocode

```c

```

## disassembly

```asm
0x1f760  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1f765  stloc.0
0x1f766  ldstr    aSelectAzureact// "SELECT AzureActiveDirectoryObjectId FRO"...
0x1f76b  stloc.1
0x1f76c  ldarg.1
0x1f76d  ldc.i4.0
0x1f76e  ldc.i4.0
0x1f76f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f774  stloc.2
0x1f775  ldloc.2
0x1f776  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1f77b  ldloc.2
0x1f77c  ldloc.1
0x1f77d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1f782  stloc.3
0x1f783  ldloc.3
0x1f784  ldc.i4   0xABF
0x1f789  ldstr    aGetdirectoryob// "GetDirectoryObjectIds"
0x1f78e  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1f793  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1f798  stloc.s  4
0x1f79a  br.s     loc_1F7B3
0x1f79c  ldloc.0
0x1f79d  ldloc.s  4
0x1f79f  ldstr    aAzureactivedir_0// "AzureActiveDirectoryObjectId"
0x1f7a4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1f7a9  unbox.any [mscorlib]System.Guid
0x1f7ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1f7b3  ldloc.s  4
0x1f7b5  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x1f7ba  brtrue.s loc_1F79C
0x1f7bc  leave.s  loc_1F7DE
0x1f7be  ldloc.s  4
0x1f7c0  brfalse.s loc_1F7C9
0x1f7c2  ldloc.s  4
0x1f7c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f7c9  endfinally
0x1f7ca  ldloc.3
0x1f7cb  brfalse.s loc_1F7D3
0x1f7cd  ldloc.3
0x1f7ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f7d3  endfinally
0x1f7d4  ldloc.2
0x1f7d5  brfalse.s loc_1F7DD
0x1f7d7  ldloc.2
0x1f7d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f7dd  endfinally
0x1f7de  ldloc.0
0x1f7df  ret
```
