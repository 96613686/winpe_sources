# Microsoft.Crm.CrmLive.Provisioning.Organization::CalculateOrganizationUpgradeOrUpdateRequirement

- ea: `0x1ae10`
- end: `0x1ae9c`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::CalculateOrganizationUpgradeOrUpdateRequirement`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x25770`

## callees

- `0x1ae10`
- `0x1b0d0`

## string_xrefs

- `0x1ae43`: `OrganizationVersion {0} is less than db update version level {1}`
- `0x1ae68`: `OrganizationVersion {0} > current db update version level {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1ae10  ldc.i4.0
0x1ae11  stloc.0
0x1ae12  ldarg.0
0x1ae13  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x1ae18  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::GetVersion()
0x1ae1d  stloc.1
0x1ae1e  call     class [mscorlib]System.Version Microsoft.Crm.CrmLive.Provisioning.Organization::get_CurrentReleaseVersion()
0x1ae23  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1ae28  ldloc.1
0x1ae29  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1ae2e  ble.s    loc_1AE34
0x1ae30  ldc.i4.2
0x1ae31  stloc.0
0x1ae32  br.s     loc_1AE9A
0x1ae34  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::get_DBUpdateVersionThresholdForServer()
0x1ae39  stloc.2
0x1ae3a  ldloc.2
0x1ae3b  ldloc.1
0x1ae3c  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1ae41  brfalse.s loc_1AE5F
0x1ae43  ldstr    aOrganizationve// "OrganizationVersion {0} is less than db"...
0x1ae48  ldc.i4.2
0x1ae49  newarr   [mscorlib]System.Object
0x1ae4e  dup
0x1ae4f  ldc.i4.0
0x1ae50  ldloc.1
0x1ae51  stelem.ref
0x1ae52  dup
0x1ae53  ldc.i4.1
0x1ae54  ldloc.2
0x1ae55  stelem.ref
0x1ae56  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x1ae5b  ldc.i4.1
0x1ae5c  stloc.0
0x1ae5d  br.s     loc_1AE9A
0x1ae5f  ldloc.2
0x1ae60  ldloc.1
0x1ae61  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1ae66  brfalse.s loc_1AE84
0x1ae68  ldstr    aOrganizationve_0// "OrganizationVersion {0} > current db up"...
0x1ae6d  ldc.i4.2
0x1ae6e  newarr   [mscorlib]System.Object
0x1ae73  dup
0x1ae74  ldc.i4.0
0x1ae75  ldloc.1
0x1ae76  stelem.ref
0x1ae77  dup
0x1ae78  ldc.i4.1
0x1ae79  ldloc.2
0x1ae7a  stelem.ref
0x1ae7b  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x1ae80  ldc.i4.3
0x1ae81  stloc.0
0x1ae82  br.s     loc_1AE9A
0x1ae84  ldstr    aOrganizationve_1// "OrganizationVersion {0} matches the cur"...
0x1ae89  ldc.i4.1
0x1ae8a  newarr   [mscorlib]System.Object
0x1ae8f  dup
0x1ae90  ldc.i4.0
0x1ae91  ldloc.1
0x1ae92  stelem.ref
0x1ae93  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x1ae98  ldc.i4.0
0x1ae99  stloc.0
0x1ae9a  ldloc.0
0x1ae9b  ret
```
