# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdates

- ea: `0x12b30`
- end: `0x12c38`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdates`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x127b0`
- `0x12b30`

## string_xrefs

- `0x12bf8`: `Database updates were successfully applied for orgId = {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x12b30  ldarg.0
0x12b31  ldstr    aOrgid// "orgId"
0x12b36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x12b3b  ldc.i4.0
0x12b3c  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetVersionFromReleaseFile(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12b41  stloc.0
0x12b42  ldloc.0
0x12b43  call     class [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantHelper [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantCache::GetInstance(class [mscorlib]System.Version)
0x12b48  stloc.1
0x12b49  ldarg.0
0x12b4a  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x12b4f  stloc.2
0x12b50  ldarga.s 1
0x12b52  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>::get_HasValue()
0x12b57  brfalse.s loc_12B69
0x12b59  ldarga.s 1
0x12b5b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>::get_HasValue()
0x12b60  brfalse.s loc_12B69
0x12b62  ldloc.2
0x12b63  ldarg.1
0x12b64  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::set_OperationType(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>)
0x12b69  ldloc.2
0x12b6a  ldloc.1
0x12b6b  callvirt instance class [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantHelper::get_DatabaseInstallerData()
0x12b70  callvirt instance class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ReleaseInfo [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData::get_ReleaseInfo()
0x12b75  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::set_DBReleaseInfo(class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ReleaseInfo)
0x12b7a  ldloc.1
0x12b7b  callvirt instance class [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantHelper::get_DatabaseInstallerData()
0x12b80  callvirt instance class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ActionCollection [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData::get_ActionCollection()
0x12b85  brfalse.s loc_12B98
0x12b87  ldloc.2
0x12b88  ldloc.1
0x12b89  callvirt instance class [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantHelper::get_DatabaseInstallerData()
0x12b8e  callvirt instance class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ActionCollection [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData::get_ActionCollection()
0x12b93  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::set_DBActionCollection(class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ActionCollection)
0x12b98  ldarg.3
0x12b99  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12b9e  brfalse.s loc_12BA8
0x12ba0  ldloc.1
0x12ba1  callvirt instance string [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantHelper::get_ReleaseFilePath()
0x12ba6  br.s     loc_12BA9
0x12ba8  ldarg.3
0x12ba9  starg.s  3
0x12bab  ldloc.2
0x12bac  ldarg.3
0x12bad  ldc.i4.1
0x12bae  ldarg.2
0x12baf  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::InstallUpdate(string, bool, int32)
0x12bb4  ldloc.1
0x12bb5  callvirt instance class [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantHelper::get_DatabaseInstallerData()
0x12bba  callvirt instance class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ActionCollection [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData::get_ActionCollection()
0x12bbf  brtrue.s loc_12BD2
0x12bc1  ldloc.1
0x12bc2  callvirt instance class [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DBUpdateMultiTenantHelper::get_DatabaseInstallerData()
0x12bc7  ldloc.2
0x12bc8  callvirt instance class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ActionCollection [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::get_DBActionCollection()
0x12bcd  callvirt instance void [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.MultiTenantDatabaseInstallerData::set_ActionCollection(class [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ActionCollection)
0x12bd2  ldarg.0
0x12bd3  call     void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::InstallOptinUpdatesIfApplicable(valuetype [mscorlib]System.Guid orgId)
0x12bd8  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x12bdd  stloc.3
0x12bde  ldloc.3
0x12bdf  ldarg.0
0x12be0  box      [mscorlib]System.Guid
0x12be5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12bea  pop
0x12beb  ldloc.0
0x12bec  ldloc.3
0x12bed  ldc.i4.1
0x12bee  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateUtility::UpdateVersionForAllOrgs(class [mscorlib]System.Version, class [mscorlib]System.Collections.ArrayList, bool)
0x12bf3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12bf8  ldstr    aDatabaseUpdate_2// "Database updates were successfully appl"...
0x12bfd  ldc.i4.1
0x12bfe  newarr   [mscorlib]System.Object
0x12c03  dup
0x12c04  ldc.i4.0
0x12c05  ldarga.s 0
0x12c07  constrained. [mscorlib]System.Guid
0x12c0d  callvirt instance string [mscorlib]System.Object::ToString()
0x12c12  stelem.ref
0x12c13  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12c18  ldc.i4.0
0x12c19  newarr   [mscorlib]System.Object
0x12c1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x12c23  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x12c28  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x12c2d  ldc.i4.2
0x12c2e  bne.un.s loc_12C36
0x12c30  ldarg.0
0x12c31  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateUtility::ScheduleIndexManagementJob(valuetype [mscorlib]System.Guid)
0x12c36  ldloc.0
0x12c37  ret
```
