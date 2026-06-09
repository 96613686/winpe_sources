# Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::CreateDeployment

- ea: `0x6070`
- end: `0x60f8`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::CreateDeployment`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5af0`

## callees

- `0x6070`
- `0x64b0`
- `0x91b0`

## string_xrefs

- `0x6095`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\CreateOrganizationInConfigDbAction.cs`
- `0x6090`: `CreateDeployment`
- `0x60bd`: `ConfigUtility.CreateDeployment for OrganizationId = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6070  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x6075  stloc.0
0x6076  ldloc.0
0x6077  ldstr    aDeployment// "Deployment"
0x607c  ldc.i4.1
0x607d  newarr   [mscorlib]System.String
0x6082  dup
0x6083  ldc.i4.0
0x6084  ldstr    aId// "Id"
0x6089  stelem.ref
0x608a  ldnull
0x608b  ldc.i4   0xDE
0x6090  ldstr    aCreatedeployme// "CreateDeployment"
0x6095  ldstr    aDDbsShDccm2110_4// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x609a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x609f  stloc.1
0x60a0  ldloc.1
0x60a1  brfalse.s loc_60AB
0x60a3  ldloc.1
0x60a4  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x60a9  brtrue.s loc_60EB
0x60ab  ldarg.0
0x60ac  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x60b1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x60b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x60bb  ldc.i4.s 0xA
0x60bd  ldstr    aConfigutilityC// "ConfigUtility.CreateDeployment for Orga"...
0x60c2  ldc.i4.1
0x60c3  newarr   [mscorlib]System.Object
0x60c8  dup
0x60c9  ldc.i4.0
0x60ca  ldarg.0
0x60cb  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x60d0  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x60d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x60da  box      [mscorlib]System.Guid
0x60df  stelem.ref
0x60e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x60e5  ldc.i4.1
0x60e6  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ConfigUtility::CreateDeployment(bool)
0x60eb  leave.s  loc_60F7
0x60ed  ldloc.0
0x60ee  brfalse.s loc_60F6
0x60f0  ldloc.0
0x60f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60f6  endfinally
0x60f7  ret
```
