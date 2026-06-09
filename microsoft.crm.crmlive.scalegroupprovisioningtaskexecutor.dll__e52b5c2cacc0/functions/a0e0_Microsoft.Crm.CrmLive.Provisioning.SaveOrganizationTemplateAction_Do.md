# Microsoft.Crm.CrmLive.Provisioning.SaveOrganizationTemplateAction::Do

- ea: `0xa0e0`
- end: `0xa228`
- name: `Microsoft.Crm.CrmLive.Provisioning.SaveOrganizationTemplateAction::Do`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0x91d0`
- `0x9410`
- `0x9430`
- `0xa0e0`

## string_xrefs

- `0xa1e3`: `Save template via Spartan service failed, template already exists on Spartan template servers.`

## pseudocode

```c

```

## disassembly

```asm
0xa0e0  ldarg.0
0xa0e1  ldarg.0
0xa0e2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa0e7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa0ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa0f1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0xa0f6  ldarg.0
0xa0f7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa0fc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa101  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SqlServerName()
0xa106  stloc.0
0xa107  ldarg.0
0xa108  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa10d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa112  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0xa117  stloc.1
0xa118  ldarg.0
0xa119  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa11e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa123  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0xa128  stloc.2
0xa129  ldarg.0
0xa12a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa12f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa134  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0xa139  stloc.3
0xa13a  ldarg.0
0xa13b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa140  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0xa145  brfalse  loc_A1FE
0xa14a  call     T0x2B000019
0xa14f  stloc.s  4
0xa151  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::GetSpartanAzureRegion()
0xa156  stloc.s  5
0xa158  ldarg.0
0xa159  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa15e  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_XdbTemplateIdentifier()
0xa163  stloc.s  6
0xa165  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier::.ctor()
0xa16a  dup
0xa16b  ldloc.s  5
0xa16d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_AzureRegion(string)
0xa172  dup
0xa173  ldloc.2
0xa174  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_ConnectionString(string)
0xa179  dup
0xa17a  ldloc.1
0xa17b  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_DatabaseName(string)
0xa180  dup
0xa181  ldloc.0
0xa182  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_LogicalServer(string)
0xa187  stloc.s  7
0xa189  ldloc.s  4
0xa18b  ldloc.s  7
0xa18d  ldloc.s  6
0xa18f  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0xa194  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::SaveTemplateDatabaseAsync(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier, string, valuetype [mscorlib]System.Threading.CancellationToken)
0xa199  ldc.i4.0
0xa19a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0xa19f  stloc.s  8
0xa1a1  ldloca.s 8
0xa1a3  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0xa1a8  stloc.s  9
0xa1aa  ldloca.s 9
0xa1ac  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0xa1b1  leave.s  loc_A211
0xa1b3  pop
0xa1b4  ldloc.s  4
0xa1b6  ldloc.s  5
0xa1b8  ldloc.s  6
0xa1ba  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0xa1bf  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::DoesTemplateDatabaseExistAsync(string, string, valuetype [mscorlib]System.Threading.CancellationToken)
0xa1c4  ldc.i4.0
0xa1c5  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0xa1ca  stloc.s  0xA
0xa1cc  ldloca.s 0xA
0xa1ce  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0xa1d3  stloc.s  0xB
0xa1d5  ldloca.s 0xB
0xa1d7  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0xa1dc  brfalse.s loc_A1FA
0xa1de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa1e3  ldstr    aSaveTemplateVi// "Save template via Spartan service faile"...
0xa1e8  ldc.i4.0
0xa1e9  newarr   [mscorlib]System.Object
0xa1ee  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa1f3  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0xa1f8  br.s     loc_A1FC
0xa1fa  rethrow
0xa1fc  leave.s  loc_A211
0xa1fe  ldloc.0
0xa1ff  ldloc.1
0xa200  ldloc.3
0xa201  ldarg.0
0xa202  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa207  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationTemplateName()
0xa20c  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility::ExecuteBackupTemplateCommand(string, string, string, string)
0xa211  ldarg.0
0xa212  ldarg.0
0xa213  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xa218  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xa21d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xa222  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0xa227  ret
```
