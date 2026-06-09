# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::Install

- ea: `0x12510`
- end: `0x125cb`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::Install`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x13050`

## callees

- `0x12510`
- `0x125d0`
- `0x12690`
- `0x127f0`
- `0x12f80`

## string_xrefs

- `0x125ba`: `Database updates are not supported for this particular Component/Sku.  Only updating server version in ConfigDB`

## pseudocode

```c

```

## disassembly

```asm
0x12510  ldarg.0
0x12511  ldc.i4.0
0x12512  call     instance bool Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::IsDatabaseUpdateSupported(valuetype Microsoft.Crm.Setup.Common.Update.InstallerActionName actionName)
0x12517  brfalse  loc_125BA
0x1251c  ldarg.0
0x1251d  ldfld    int32 Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_componentCode
0x12522  stloc.0
0x12523  ldloc.0
0x12524  brfalse.s loc_12532
0x12526  ldloc.0
0x12527  ldc.i4.1
0x12528  beq      loc_125B3
0x1252d  ldloc.0
0x1252e  ldc.i4.6
0x1252f  beq.s    loc_125A1
0x12531  ret
0x12532  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x12537  stloc.1
0x12538  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1253d  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x12542  ldc.i4.2
0x12543  bne.un.s loc_12558
0x12545  ldc.i4.4
0x12546  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::.ctor(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x1254b  ldarg.0
0x1254c  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x12551  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::AddVersion(class [mscorlib]System.Version)
0x12556  br.s     loc_12577
0x12558  ldarg.0
0x12559  call     instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ConfigOnPremiseInstall()
0x1255e  ldarg.0
0x1255f  call     class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateUtility::GetEnabledOrganizationIds()
0x12564  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::OrgInstall(class [mscorlib]System.Collections.ArrayList orgIdArray)
0x12569  stloc.1
0x1256a  ldarg.0
0x1256b  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x12570  ldloc.1
0x12571  ldc.i4.1
0x12572  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateUtility::UpdateVersionForAllOrgs(class [mscorlib]System.Version, class [mscorlib]System.Collections.ArrayList, bool)
0x12577  ldc.i4.0
0x12578  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::.ctor(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x1257d  ldarg.0
0x1257e  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x12583  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::AddVersion(class [mscorlib]System.Version)
0x12588  ldsfld   bool [Microsoft.Crm]Microsoft.Crm.CrmVersions::OptInAvailableInBuild
0x1258d  brfalse.s loc_125CA
0x1258f  ldc.i4.6
0x12590  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::.ctor(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12595  ldarg.0
0x12596  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x1259b  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::AddVersion(class [mscorlib]System.Version)
0x125a0  ret
0x125a1  ldc.i4.3
0x125a2  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::.ctor(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x125a7  ldarg.0
0x125a8  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x125ad  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::AddVersion(class [mscorlib]System.Version)
0x125b2  ret
0x125b3  ldarg.0
0x125b4  call     instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ClientInstall()
0x125b9  ret
0x125ba  ldstr    aDatabaseUpdate_0// "Database updates are not supported for "...
0x125bf  ldc.i4.0
0x125c0  newarr   [mscorlib]System.Object
0x125c5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x125ca  ret
```
