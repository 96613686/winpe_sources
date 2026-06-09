# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::OrgUninstall

- ea: `0x12960`
- end: `0x12a53`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::OrgUninstall`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12850`

## callees

- `0x12960`

## string_xrefs

- `0x129e9`: `Optin uninstall skipped due to error: {0}, stacktrace: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x12960  ldc.i4.0
0x12961  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::.ctor(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12966  ldarg.0
0x12967  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x1296c  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::WriteUninstallReleaseAndActionFiles(class [mscorlib]System.Version)
0x12971  stloc.0
0x12972  ldc.i4.6
0x12973  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::.ctor(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase)
0x12978  ldarg.0
0x12979  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x1297e  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.DBUpdateInstallInfo::WriteUninstallReleaseAndActionFiles(class [mscorlib]System.Version)
0x12983  stloc.1
0x12984  ldloc.0
0x12985  brfalse.s loc_1298D
0x12987  ldloc.1
0x12988  brtrue   loc_12A52
0x1298d  ldc.i4.0
0x1298e  ldarg.0
0x1298f  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x12994  ldc.i4.0
0x12995  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgUninstallReleaseFilePath(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase, class [mscorlib]System.Version, bool)
0x1299a  stloc.2
0x1299b  ldc.i4.6
0x1299c  ldarg.0
0x1299d  ldfld    class [mscorlib]System.Version Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::_version
0x129a2  ldc.i4.0
0x129a3  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetOrgUninstallReleaseFilePath(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.CrmDatabase, class [mscorlib]System.Version, bool)
0x129a8  stloc.3
0x129a9  ldarg.1
0x129aa  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x129af  stloc.s  4
0x129b1  br.s     loc_12A2F
0x129b3  ldloc.s  4
0x129b5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x129ba  unbox.any [mscorlib]System.Guid
0x129bf  stloc.s  5
0x129c1  ldloc.1
0x129c2  brtrue.s loc_12A1E
0x129c4  ldloc.s  5
0x129c6  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x129cb  ldloc.3
0x129cc  ldc.i4.1
0x129cd  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::UninstallUpdate(string, bool)
0x129d2  leave.s  loc_12A1E
0x129d4  stloc.s  6
0x129d6  ldloc.s  6
0x129d8  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x129dd  ldc.i4   0x8004023B
0x129e2  bne.un.s loc_12A1A
0x129e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x129e9  ldstr    aOptinUninstall// "Optin uninstall skipped due to error: {"...
0x129ee  ldc.i4.2
0x129ef  newarr   [mscorlib]System.Object
0x129f4  dup
0x129f5  ldc.i4.0
0x129f6  ldloc.s  6
0x129f8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x129fd  stelem.ref
0x129fe  dup
0x129ff  ldc.i4.1
0x12a00  ldloc.s  6
0x12a02  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x12a07  stelem.ref
0x12a08  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12a0d  ldc.i4.0
0x12a0e  newarr   [mscorlib]System.Object
0x12a13  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x12a18  br.s     loc_12A1C
0x12a1a  rethrow
0x12a1c  leave.s  loc_12A1E
0x12a1e  ldloc.0
0x12a1f  brtrue.s loc_12A2F
0x12a21  ldloc.s  5
0x12a23  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x12a28  ldloc.2
0x12a29  ldc.i4.1
0x12a2a  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::UninstallUpdate(string, bool)
0x12a2f  ldloc.s  4
0x12a31  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12a36  brtrue   loc_129B3
0x12a3b  leave.s  loc_12A52
0x12a3d  ldloc.s  4
0x12a3f  isinst   [mscorlib]System.IDisposable
0x12a44  stloc.s  7
0x12a46  ldloc.s  7
0x12a48  brfalse.s loc_12A51
0x12a4a  ldloc.s  7
0x12a4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12a51  endfinally
0x12a52  ret
```
