# Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::VerifyIfOrganizationExists

- ea: `0x6100`
- end: `0x6177`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::VerifyIfOrganizationExists`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5af0`

## callees

- `0x6100`
- `0x64b0`
- `0x91b0`

## string_xrefs

- `0x612c`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\CreateOrganizationInConfigDbAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6100  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x6105  stloc.0
0x6106  ldloc.0
0x6107  ldstr    aOrganization// "Organization"
0x610c  ldarg.0
0x610d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6112  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6117  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x611c  box      [mscorlib]System.Guid
0x6121  ldnull
0x6122  ldc.i4   0xEC
0x6127  ldstr    aVerifyiforgani_0// "VerifyIfOrganizationExists"
0x612c  ldstr    aDDbsShDccm2110_4// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x6131  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x6136  stloc.1
0x6137  ldloc.1
0x6138  brtrue.s loc_613E
0x613a  ldc.i4.0
0x613b  stloc.3
0x613c  leave.s  loc_6175
0x613e  ldloc.1
0x613f  ldstr    aState// "State"
0x6144  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x6149  unbox.any [mscorlib]System.Int32
0x614e  stloc.2
0x614f  ldloc.2
0x6150  ldc.i4.2
0x6151  beq.s    loc_6167
0x6153  ldloc.2
0x6154  ldc.i4.3
0x6155  beq.s    loc_6167
0x6157  ldstr    aOrganizationSt// "Organization State is neither Pending n"...
0x615c  ldc.i4   0x8004B001
0x6161  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6166  throw
0x6167  ldc.i4.1
0x6168  stloc.3
0x6169  leave.s  loc_6175
0x616b  ldloc.0
0x616c  brfalse.s loc_6174
0x616e  ldloc.0
0x616f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6174  endfinally
0x6175  ldloc.3
0x6176  ret
```
