# Microsoft.Crm.Asynchronous.OrgUpdateActions::GetScaleGroupDBConnectionString

- ea: `0xd1d0`
- end: `0xd1fb`
- name: `Microsoft.Crm.Asynchronous.OrgUpdateActions::GetScaleGroupDBConnectionString`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd100`

## callees

- `0xd1d0`

## pseudocode

```c

```

## disassembly

```asm
0xd1d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0xd1d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0xd1da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype [mscorlib]System.Guid)
0xd1df  stloc.0
0xd1e0  ldloc.0
0xd1e1  ldc.i4.1
0xd1e2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0xd1e7  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xd1ec  stloc.1
0xd1ed  leave.s  loc_D1F9
0xd1ef  ldloc.0
0xd1f0  brfalse.s loc_D1F8
0xd1f2  ldloc.0
0xd1f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd1f8  endfinally
0xd1f9  ldloc.1
0xd1fa  ret
```
