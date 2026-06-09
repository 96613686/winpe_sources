# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveUserId

- ea: `0x20e60`
- end: `0x20ee1`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveUserId`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1de30`
- `0x1dfc0`

## callees

- `0x20e60`
- `0x20f10`

## string_xrefs

- `0x20ea4`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`
- `0x20e84`: `SELECT SystemUserId FROM SystemUserBase WHERE AccessMode = `

## pseudocode

```c

```

## disassembly

```asm
0x20e60  call     bool Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::get_CreateCrmUserTestMode()
0x20e65  brfalse.s loc_20E6D
0x20e67  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20e6c  ret
0x20e6d  ldarg.0
0x20e6e  ldc.i4.0
0x20e6f  ldc.i4.0
0x20e70  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x20e75  stloc.0
0x20e76  ldloc.0
0x20e77  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x20e7c  ldloc.0
0x20e7d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x20e82  stloc.1
0x20e83  ldloc.1
0x20e84  ldstr    aSelectSystemus_5// "SELECT SystemUserId FROM SystemUserBase"...
0x20e89  ldarg.1
0x20e8a  box      [mscorlib]System.Int32
0x20e8f  call     string [mscorlib]System.String::Concat(object, object)
0x20e94  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x20e99  ldloc.1
0x20e9a  ldc.i4   0xEA1
0x20e9f  ldstr    aRetrieveuserid// "RetrieveUserId"
0x20ea4  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x20ea9  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x20eae  stloc.2
0x20eaf  ldloc.2
0x20eb0  brfalse.s loc_20EBA
0x20eb2  ldloc.2
0x20eb3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x20eb8  bne.un.s loc_20EC2
0x20eba  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20ebf  stloc.3
0x20ec0  leave.s  loc_20EDF
0x20ec2  ldloc.2
0x20ec3  unbox.any [mscorlib]System.Guid
0x20ec8  stloc.3
0x20ec9  leave.s  loc_20EDF
0x20ecb  ldloc.1
0x20ecc  brfalse.s loc_20ED4
0x20ece  ldloc.1
0x20ecf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20ed4  endfinally
0x20ed5  ldloc.0
0x20ed6  brfalse.s loc_20EDE
0x20ed8  ldloc.0
0x20ed9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20ede  endfinally
0x20edf  ldloc.3
0x20ee0  ret
```
