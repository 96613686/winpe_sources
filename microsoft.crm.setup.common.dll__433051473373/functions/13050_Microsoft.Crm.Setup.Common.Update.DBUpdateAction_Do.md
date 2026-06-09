# Microsoft.Crm.Setup.Common.Update.DBUpdateAction::Do

- ea: `0x13050`
- end: `0x130e8`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateAction::Do`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x123f0`
- `0x12430`
- `0x12510`
- `0x13050`

## string_xrefs

- `0x130cc`: `InstallerException: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x13050  ldarg.1
0x13051  ldstr    aParameters// "parameters"
0x13056  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1305b  ldc.i4.0
0x1305c  stloc.0
0x1305d  ldarg.1
0x1305e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x13063  stloc.1
0x13064  ldloc.1
0x13065  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::get_BuildVersion()
0x1306a  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1306f  ldloc.1
0x13070  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.ComponentInfo [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::get_CompInfo()
0x13075  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.ComponentInfo::get_Code()
0x1307a  ldloc.1
0x1307b  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::get_AllowPatchRemoval()
0x13080  newobj   instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::.ctor(class [mscorlib]System.Version version, int32 compCode, bool allowPatchRemoval)
0x13085  stloc.2
0x13086  ldloc.2
0x13087  callvirt instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::Install()
0x1308c  ldarg.0
0x1308d  ldloc.2
0x1308e  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::get_UpdateErrors()
0x13093  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateActionWithErrors::SetErrors(class [mscorlib]System.Collections.ArrayList)
0x13098  ldarg.0
0x13099  ldfld    int32 Microsoft.Crm.Setup.Common.Update.DBUpdateAction::allocatedProgress
0x1309e  stloc.0
0x1309f  ldarg.0
0x130a0  ldfld    class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Setup.Common.Update.DBUpdateAction::progressEventSource
0x130a5  ldarg.0
0x130a6  ldarg.0
0x130a7  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_Description()
0x130ac  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription::get_ProgressMessage()
0x130b1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(string)
0x130b6  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x130bb  ldarg.0
0x130bc  ldarg.0
0x130bd  ldfld    int32 Microsoft.Crm.Setup.Common.Update.DBUpdateAction::progressStart
0x130c2  ldloc.0
0x130c3  add
0x130c4  stfld    int32 Microsoft.Crm.Setup.Common.Update.DBUpdateAction::progressStart
0x130c9  leave.s  loc_130E7
0x130cb  stloc.3
0x130cc  ldstr    aInstallerexcep// "InstallerException: {0}"
0x130d1  ldc.i4.1
0x130d2  newarr   [mscorlib]System.Object
0x130d7  dup
0x130d8  ldc.i4.0
0x130d9  ldloc.3
0x130da  callvirt instance string [mscorlib]System.Exception::get_Message()
0x130df  stelem.ref
0x130e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x130e5  rethrow
0x130e7  ret
```
