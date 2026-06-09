# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdatesForUninstall_0

- ea: `0x12c50`
- end: `0x12d77`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdatesForUninstall_0`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12c40`

## callees

- `0x12c50`
- `0x12d80`
- `0x12da0`
- `0x12e80`

## string_xrefs

- `0x12ccb`: `Cannot uninstall DBUpdates across a major version. Current Version={0}, Previous Version={1}`
- `0x12cfc`: `Cannot uninstall DBUpdates across a minor version. Current Version={0}, Previous Version={1}`

## pseudocode

```c

```

## disassembly

```asm
0x12c50  ldarg.1
0x12c51  ldnull
0x12c52  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x12c57  brfalse.s loc_12C75
0x12c59  ldc.i4.0
0x12c5a  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetVersionFromReleaseFile(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12c5f  starg.s  1
0x12c61  ldarg.1
0x12c62  ldnull
0x12c63  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x12c68  brfalse.s loc_12C75
0x12c6a  ldstr    aInvalidVersion// "Invalid version number found in the rel"...
0x12c6f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x12c74  throw
0x12c75  ldarg.0
0x12c76  ldstr    aOrgid// "orgId"
0x12c7b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x12c80  ldc.i4.0
0x12c81  ldarg.1
0x12c82  call     string Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::CreateAndGetOrgUninstallReleaseFilePath(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase database, class [mscorlib]System.Version version)
0x12c87  stloc.0
0x12c88  ldc.i4.6
0x12c89  ldarg.1
0x12c8a  call     string Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::CreateAndGetOrgUninstallReleaseFilePath(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase database, class [mscorlib]System.Version version)
0x12c8f  stloc.1
0x12c90  ldloc.0
0x12c91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12c96  brfalse.s loc_12CA3
0x12c98  ldloc.1
0x12c99  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12c9e  brtrue   loc_12D76
0x12ca3  ldarg.0
0x12ca4  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x12ca9  stloc.2
0x12caa  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x12caf  brtrue.s loc_12D1A
0x12cb1  ldloc.2
0x12cb2  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::GetVersion()
0x12cb7  stloc.3
0x12cb8  ldloc.3
0x12cb9  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x12cbe  ldarg.1
0x12cbf  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x12cc4  beq.s    loc_12CE9
0x12cc6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12ccb  ldstr    aCannotUninstal// "Cannot uninstall DBUpdates across a maj"...
0x12cd0  ldc.i4.2
0x12cd1  newarr   [mscorlib]System.Object
0x12cd6  dup
0x12cd7  ldc.i4.0
0x12cd8  ldloc.3
0x12cd9  stelem.ref
0x12cda  dup
0x12cdb  ldc.i4.1
0x12cdc  ldarg.1
0x12cdd  stelem.ref
0x12cde  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12ce3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x12ce8  throw
0x12ce9  ldloc.3
0x12cea  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x12cef  ldarg.1
0x12cf0  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x12cf5  beq.s    loc_12D1A
0x12cf7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12cfc  ldstr    aCannotUninstal_0// "Cannot uninstall DBUpdates across a min"...
0x12d01  ldc.i4.2
0x12d02  newarr   [mscorlib]System.Object
0x12d07  dup
0x12d08  ldc.i4.0
0x12d09  ldloc.3
0x12d0a  stelem.ref
0x12d0b  dup
0x12d0c  ldc.i4.1
0x12d0d  ldarg.1
0x12d0e  stelem.ref
0x12d0f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12d14  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x12d19  throw
0x12d1a  ldloc.1
0x12d1b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12d20  brtrue.s loc_12D2A
0x12d22  ldloc.2
0x12d23  ldloc.1
0x12d24  ldc.i4.1
0x12d25  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::UninstallUpdate(string, bool)
0x12d2a  ldloc.0
0x12d2b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12d30  brtrue.s loc_12D41
0x12d32  ldarg.0
0x12d33  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x12d38  stloc.2
0x12d39  ldloc.2
0x12d3a  ldloc.0
0x12d3b  ldc.i4.1
0x12d3c  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::UninstallUpdate(string, bool)
0x12d41  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x12d46  brtrue.s loc_12D76
0x12d48  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x12d4d  stloc.s  4
0x12d4f  ldloc.s  4
0x12d51  ldarg.0
0x12d52  box      [mscorlib]System.Guid
0x12d57  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12d5c  pop
0x12d5d  ldarg.1
0x12d5e  call     class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::DecrementRevision(class [mscorlib]System.Version version)
0x12d63  ldc.i4.0
0x12d64  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::GetLatestDBUpdateVersion(class [mscorlib]System.Version, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12d69  call     class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::IncrementRevision(class [mscorlib]System.Version version)
0x12d6e  ldloc.s  4
0x12d70  ldc.i4.0
0x12d71  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateUtility::UpdateVersionForAllOrgs(class [mscorlib]System.Version, class [mscorlib]System.Collections.ArrayList, bool)
0x12d76  ret
```
