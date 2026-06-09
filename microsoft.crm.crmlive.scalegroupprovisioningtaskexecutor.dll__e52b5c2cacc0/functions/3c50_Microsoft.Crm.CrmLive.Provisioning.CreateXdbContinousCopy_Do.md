# Microsoft.Crm.CrmLive.Provisioning.CreateXdbContinousCopy::Do

- ea: `0x3c50`
- end: `0x3d86`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateXdbContinousCopy::Do`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x3c50`
- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0x9410`

## string_xrefs

- `0x3c75`: `ContinousCopy is not created for this organization because it is non-XDB or not enabled for disaster recovery.`
- `0x3cfb`: `_ContinuousCopy_`

## pseudocode

```c

```

## disassembly

```asm
0x3c50  ldarg.0
0x3c51  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x3c56  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x3c5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x3c60  stloc.0
0x3c61  ldarg.0
0x3c62  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x3c67  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x3c6c  brfalse.s loc_3C75
0x3c6e  call     bool [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::IsDisasterRecoveryForOrganizationsEnabled()
0x3c73  brtrue.s loc_3C80
0x3c75  ldstr    aContinouscopyI// "ContinousCopy is not created for this o"...
0x3c7a  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x3c7f  ret
0x3c80  ldarg.0
0x3c81  ldloc.0
0x3c82  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x3c87  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::GetSpartanAzureRegion()
0x3c8c  stloc.1
0x3c8d  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier::.ctor()
0x3c92  dup
0x3c93  ldloc.1
0x3c94  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_AzureRegion(string)
0x3c99  dup
0x3c9a  ldarg.0
0x3c9b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x3ca0  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x3ca5  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SqlServerName()
0x3caa  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_LogicalServer(string)
0x3caf  dup
0x3cb0  ldarg.0
0x3cb1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x3cb6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x3cbb  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0x3cc0  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_DatabaseName(string)
0x3cc5  dup
0x3cc6  ldarg.0
0x3cc7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x3ccc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x3cd1  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ConnectionString()
0x3cd6  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_ConnectionString(string)
0x3cdb  stloc.2
0x3cdc  ldloc.1
0x3cdd  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::GetSpartanAzurePairRegion(string)
0x3ce2  stloc.3
0x3ce3  ldc.i4.4
0x3ce4  newarr   [mscorlib]System.Object
0x3ce9  dup
0x3cea  ldc.i4.0
0x3ceb  ldloca.s 0
0x3ced  constrained. [mscorlib]System.Guid
0x3cf3  callvirt instance string [mscorlib]System.Object::ToString()
0x3cf8  stelem.ref
0x3cf9  dup
0x3cfa  ldc.i4.1
0x3cfb  ldstr    aContinuouscopy// "_ContinuousCopy_"
0x3d00  stelem.ref
0x3d01  dup
0x3d02  ldc.i4.2
0x3d03  ldloc.3
0x3d04  stelem.ref
0x3d05  dup
0x3d06  ldc.i4.3
0x3d07  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3d0c  box      [mscorlib]System.Guid
0x3d11  stelem.ref
0x3d12  call     string [mscorlib]System.String::Concat(object[])
0x3d17  stloc.s  4
0x3d19  ldarg.0
0x3d1a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x3d1f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x3d24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_ScaleGroupId()
0x3d29  stloc.s  5
0x3d2b  call     T0x2B000019
0x3d30  ldloc.s  4
0x3d32  ldloc.2
0x3d33  ldloc.3
0x3d34  ldloc.s  5
0x3d36  ldarg.0
0x3d37  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x3d3c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x3d41  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x3d46  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x3d4b  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::CreateDatabaseContinuousCopyAsync(string, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Threading.CancellationToken)
0x3d50  ldc.i4.0
0x3d51  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier>::ConfigureAwait(!!T0)
0x3d56  stloc.s  7
0x3d58  ldloca.s 7
0x3d5a  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier>::GetAwaiter()
0x3d5f  stloc.s  8
0x3d61  ldloca.s 8
0x3d63  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanSecondaryDatabaseIdentifier>::GetResult()
0x3d68  stloc.s  6
0x3d6a  ldloc.s  6
0x3d6c  brtrue.s loc_3D6F
0x3d6e  ret
0x3d6f  call     T0x2B00001A
0x3d74  ldloc.0
0x3d75  ldloc.s  6
0x3d77  ldc.i4.0
0x3d78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::CreateDatabaseEntry(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier, bool)
0x3d7d  pop
0x3d7e  ldarg.0
0x3d7f  ldloc.0
0x3d80  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x3d85  ret
```
