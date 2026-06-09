# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveCrmUserId

- ea: `0x1de40`
- end: `0x1deb9`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveCrmUserId`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1de40`

## string_xrefs

- `0x1de7c`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x1de57`: `SELECT SystemUserId FROM SystemUserBase WHERE IsDisabled = 'false' and AzureActiveDirectoryObjectId = '`

## pseudocode

```c

```

## disassembly

```asm
0x1de40  ldarg.1
0x1de41  ldc.i4.0
0x1de42  ldc.i4.0
0x1de43  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1de48  stloc.0
0x1de49  ldloc.0
0x1de4a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1de4f  ldloc.0
0x1de50  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1de55  stloc.1
0x1de56  ldloc.1
0x1de57  ldstr    aSelectSystemus_2// "SELECT SystemUserId FROM SystemUserBase"...
0x1de5c  ldarg.2
0x1de5d  box      [mscorlib]System.Guid
0x1de62  ldstr    asc_3E000// "'"
0x1de67  call     string [mscorlib]System.String::Concat(object, object, object)
0x1de6c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1de71  ldloc.1
0x1de72  ldc.i4   0x5F8
0x1de77  ldstr    aRetrievecrmuse// "RetrieveCrmUserId"
0x1de7c  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1de81  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1de86  stloc.2
0x1de87  ldloc.2
0x1de88  brfalse.s loc_1DE92
0x1de8a  ldloc.2
0x1de8b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1de90  bne.un.s loc_1DE9A
0x1de92  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1de97  stloc.3
0x1de98  leave.s  loc_1DEB7
0x1de9a  ldloc.2
0x1de9b  unbox.any [mscorlib]System.Guid
0x1dea0  stloc.3
0x1dea1  leave.s  loc_1DEB7
0x1dea3  ldloc.1
0x1dea4  brfalse.s loc_1DEAC
0x1dea6  ldloc.1
0x1dea7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1deac  endfinally
0x1dead  ldloc.0
0x1deae  brfalse.s loc_1DEB6
0x1deb0  ldloc.0
0x1deb1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1deb6  endfinally
0x1deb7  ldloc.3
0x1deb8  ret
```
