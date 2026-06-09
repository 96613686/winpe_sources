# Microsoft.Crm.CrmLive.Provisioning.CalculateOrgMaxStorageSizeOperationExecutor::UpdateOrganizationDetail

- ea: `0x221c0`
- end: `0x22205`
- name: `Microsoft.Crm.CrmLive.Provisioning.CalculateOrgMaxStorageSizeOperationExecutor::UpdateOrganizationDetail`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x22050`

## callees

- `0x221c0`

## string_xrefs

- `0x221e8`: `UpdateOrganizationDetail`
- `0x221ed`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\CalculateOrgMaxStorageSizeOperation.cs`

## pseudocode

```c

```

## disassembly

```asm
0x221c0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x221c5  stloc.0
0x221c6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x221cb  stloc.1
0x221cc  ldloc.1
0x221cd  ldarg.1
0x221ce  ldarg.2
0x221cf  box      [mscorlib]System.Int32
0x221d4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x221d9  ldloc.0
0x221da  ldstr    aOrganization// "Organization"
0x221df  ldarg.0
0x221e0  box      [mscorlib]System.Guid
0x221e5  ldloc.1
0x221e6  ldc.i4.s 0x73
0x221e8  ldstr    aUpdateorganiza_1// "UpdateOrganizationDetail"
0x221ed  ldstr    aDDbsShDccm2110_34// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x221f2  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x221f7  pop
0x221f8  leave.s  loc_22204
0x221fa  ldloc.0
0x221fb  brfalse.s loc_22203
0x221fd  ldloc.0
0x221fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22203  endfinally
0x22204  ret
```
