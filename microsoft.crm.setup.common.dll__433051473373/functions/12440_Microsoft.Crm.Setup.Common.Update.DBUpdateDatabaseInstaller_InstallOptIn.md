# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::InstallOptIn

- ea: `0x12440`
- end: `0x124ca`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::InstallOptIn`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x127b0`

## callees

- `0x12440`

## string_xrefs

- `0x12460`: `Opt in update install was successful for orgId = {0}.`
- `0x12493`: `Database update install failed for orgId = {0}.  Continuing with other orgs.  Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x12440  ldc.i4.6
0x12441  call     string[] [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetReleaseFilePaths(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12446  ldc.i4.0
0x12447  ldelem.ref
0x12448  stloc.0
0x12449  ldarg.0
0x1244a  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x1244f  ldloc.0
0x12450  ldc.i4.1
0x12451  ldc.i4   0x409
0x12456  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::InstallUpdate(string, bool, int32)
0x1245b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12460  ldstr    aOptInUpdateIns// "Opt in update install was successful fo"...
0x12465  ldc.i4.1
0x12466  newarr   [mscorlib]System.Object
0x1246b  dup
0x1246c  ldc.i4.0
0x1246d  ldarga.s 0
0x1246f  constrained. [mscorlib]System.Guid
0x12475  callvirt instance string [mscorlib]System.Object::ToString()
0x1247a  stelem.ref
0x1247b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12480  ldc.i4.0
0x12481  newarr   [mscorlib]System.Object
0x12486  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1248b  leave.s  loc_124C9
0x1248d  stloc.1
0x1248e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12493  ldstr    aDatabaseUpdate// "Database update install failed for orgI"...
0x12498  ldc.i4.2
0x12499  newarr   [mscorlib]System.Object
0x1249e  dup
0x1249f  ldc.i4.0
0x124a0  ldarga.s 0
0x124a2  constrained. [mscorlib]System.Guid
0x124a8  callvirt instance string [mscorlib]System.Object::ToString()
0x124ad  stelem.ref
0x124ae  dup
0x124af  ldc.i4.1
0x124b0  ldloc.1
0x124b1  callvirt instance string [mscorlib]System.Object::ToString()
0x124b6  stelem.ref
0x124b7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x124bc  ldc.i4.0
0x124bd  newarr   [mscorlib]System.Object
0x124c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x124c7  rethrow
0x124c9  ret
```
