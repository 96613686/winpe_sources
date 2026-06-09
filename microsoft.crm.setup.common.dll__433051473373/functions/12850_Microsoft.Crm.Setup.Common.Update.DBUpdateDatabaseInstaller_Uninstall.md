# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::Uninstall

- ea: `0x12850`
- end: `0x1290d`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::Uninstall`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x13100`

## callees

- `0x12850`
- `0x12910`
- `0x12960`
- `0x12f80`

## string_xrefs

- `0x128fc`: `Database updates are not supported for this particular Component/Sku.  Only updating server version in ConfigDB`

## pseudocode

```c

```

## disassembly

```asm
0x12850  ldarg.0
0x12851  ldc.i4.1
0x12852  call     instance bool Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::IsDatabaseUpdateSupported(valuetype Microsoft.Crm.Setup.Common.Update.InstallerActionName actionName)
0x12857  brfalse  loc_128FC
0x1285c  ldarg.0
0x1285d  ldfld    int32 Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_componentCode
0x12862  stloc.0
0x12863  ldloc.0
0x12864  brfalse.s loc_12872
0x12866  ldloc.0
0x12867  ldc.i4.1
0x12868  beq      loc_1290C
0x1286d  ldloc.0
0x1286e  ldc.i4.6
0x1286f  beq.s    loc_128EF
0x12871  ret
0x12872  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x12877  stloc.1
0x12878  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1287d  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x12882  ldc.i4.2
0x12883  bne.un.s loc_128AA
0x12885  ldarg.0
0x12886  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x1288b  ldc.i4.4
0x1288c  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::RemoveVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12891  ldarg.0
0x12892  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x12897  ldc.i4.0
0x12898  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::RemoveVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x1289d  ldarg.0
0x1289e  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x128a3  ldc.i4.6
0x128a4  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::RemoveVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x128a9  ret
0x128aa  ldarg.0
0x128ab  call     instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ConfigOnPremiseUninstall()
0x128b0  call     class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateUtility::GetEnabledOrganizationIds()
0x128b5  stloc.1
0x128b6  ldarg.0
0x128b7  ldloc.1
0x128b8  call     instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::OrgUninstall(class [mscorlib]System.Collections.ArrayList orgIdArray)
0x128bd  ldarg.0
0x128be  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x128c3  ldc.i4.0
0x128c4  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::RemoveVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x128c9  ldarg.0
0x128ca  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x128cf  ldc.i4.6
0x128d0  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::RemoveVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x128d5  ldarg.0
0x128d6  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x128db  ldc.i4.2
0x128dc  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::RemoveVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x128e1  ldc.i4.0
0x128e2  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::GetMaxDBUpdateVersion(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x128e7  ldloc.1
0x128e8  ldc.i4.0
0x128e9  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateUtility::UpdateVersionForAllOrgs(class [mscorlib]System.Version, class [mscorlib]System.Collections.ArrayList, bool)
0x128ee  ret
0x128ef  ldarg.0
0x128f0  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x128f5  ldc.i4.3
0x128f6  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::RemoveVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x128fb  ret
0x128fc  ldstr    aDatabaseUpdate_0// "Database updates are not supported for "...
0x12901  ldc.i4.0
0x12902  newarr   [mscorlib]System.Object
0x12907  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1290c  ret
```
