# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdatesForSpecificRelease

- ea: `0x12a60`
- end: `0x12b2d`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdatesForSpecificRelease`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x12a60`

## string_xrefs

- `0x12acc`: `Database updates were successfully applied for orgId = {0}.`
- `0x12afd`: `Could not find release file {0}.  Database updates were not applied for orgId = {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x12a60  ldarg.0
0x12a61  ldstr    aOrgid// "orgId"
0x12a66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x12a6b  ldarg.1
0x12a6c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12a71  brtrue   loc_12AF8
0x12a76  ldarg.1
0x12a77  call     bool [mscorlib]System.IO.File::Exists(string)
0x12a7c  brfalse.s loc_12AF8
0x12a7e  ldarg.0
0x12a7f  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x12a84  stloc.0
0x12a85  ldarga.s 2
0x12a87  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>::get_HasValue()
0x12a8c  brfalse.s loc_12A9E
0x12a8e  ldarga.s 2
0x12a90  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>::get_HasValue()
0x12a95  brfalse.s loc_12A9E
0x12a97  ldloc.0
0x12a98  ldarg.2
0x12a99  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::set_OperationType(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>)
0x12a9e  ldloc.0
0x12a9f  ldarg.1
0x12aa0  ldc.i4.1
0x12aa1  ldarg.3
0x12aa2  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::InstallUpdate(string, bool, int32)
0x12aa7  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x12aac  stloc.1
0x12aad  ldloc.1
0x12aae  ldarg.0
0x12aaf  box      [mscorlib]System.Guid
0x12ab4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12ab9  pop
0x12aba  ldarg.1
0x12abb  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetVersionFromReleaseFile(string)
0x12ac0  ldloc.1
0x12ac1  ldc.i4.1
0x12ac2  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateUtility::UpdateVersionForAllOrgs(class [mscorlib]System.Version, class [mscorlib]System.Collections.ArrayList, bool)
0x12ac7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12acc  ldstr    aDatabaseUpdate_2// "Database updates were successfully appl"...
0x12ad1  ldc.i4.1
0x12ad2  newarr   [mscorlib]System.Object
0x12ad7  dup
0x12ad8  ldc.i4.0
0x12ad9  ldarga.s 0
0x12adb  constrained. [mscorlib]System.Guid
0x12ae1  callvirt instance string [mscorlib]System.Object::ToString()
0x12ae6  stelem.ref
0x12ae7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12aec  ldc.i4.0
0x12aed  newarr   [mscorlib]System.Object
0x12af2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x12af7  ret
0x12af8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12afd  ldstr    aCouldNotFindRe// "Could not find release file {0}.  Datab"...
0x12b02  ldc.i4.2
0x12b03  newarr   [mscorlib]System.Object
0x12b08  dup
0x12b09  ldc.i4.0
0x12b0a  ldarg.1
0x12b0b  stelem.ref
0x12b0c  dup
0x12b0d  ldc.i4.1
0x12b0e  ldarga.s 0
0x12b10  constrained. [mscorlib]System.Guid
0x12b16  callvirt instance string [mscorlib]System.Object::ToString()
0x12b1b  stelem.ref
0x12b1c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12b21  ldc.i4.0
0x12b22  newarr   [mscorlib]System.Object
0x12b27  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x12b2c  ret
```
