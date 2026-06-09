# Microsoft.Crm.ScaleGroupApi.Controllers.OrganizationReportsController::Delete

- ea: `0x2ea0`
- end: `0x2ecf`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.OrganizationReportsController::Delete`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x2ea0`

## pseudocode

```c

```

## disassembly

```asm
0x2ea0  ldarg.1
0x2ea1  ldstr    aOrganizationid// "organizationId"
0x2ea6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2eab  ldc.i4.1
0x2eac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor(bool)
0x2eb1  stloc.0
0x2eb2  ldarg.1
0x2eb3  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x2eb8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetScaleGroupId()
0x2ebd  call     void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.Organization::DeleteOrganizationReports(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2ec2  leave.s  loc_2ECE
0x2ec4  ldloc.0
0x2ec5  brfalse.s loc_2ECD
0x2ec7  ldloc.0
0x2ec8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ecd  endfinally
0x2ece  ret
```
