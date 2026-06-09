# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::ResetJobs

- ea: `0xd2e0`
- end: `0xd317`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::ResetJobs`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xc310`

## callees

- `0xd210`
- `0xd2e0`
- `0xd5a0`
- `0xe610`

## pseudocode

```c

```

## disassembly

```asm
0xd2e0  ldc.i4.s 0x64
0xd2e2  stloc.0
0xd2e3  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xd2e8  stloc.1
0xd2e9  ldarg.0
0xd2ea  ldloc.1
0xd2eb  ldc.i4.0
0xd2ec  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::SetupDbCommandForUpdate(class [System.Data]System.Data.IDbCommand crmDbCommand, bool outputData)
0xd2f1  ldarg.0
0xd2f2  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd2f7  ldloc.1
0xd2f8  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command)
0xd2fd  stloc.2
0xd2fe  ldloc.2
0xd2ff  ldc.i4.0
0xd300  ble.s    loc_D30A
0xd302  ldloc.0
0xd303  ldc.i4.1
0xd304  sub
0xd305  dup
0xd306  stloc.0
0xd307  ldc.i4.0
0xd308  bgt.s    loc_D2F1
0xd30a  leave.s  loc_D316
0xd30c  ldloc.1
0xd30d  brfalse.s loc_D315
0xd30f  ldloc.1
0xd310  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd315  endfinally
0xd316  ret
```
