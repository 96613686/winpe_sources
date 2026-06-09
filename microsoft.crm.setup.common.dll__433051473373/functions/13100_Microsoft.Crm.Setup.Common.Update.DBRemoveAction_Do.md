# Microsoft.Crm.Setup.Common.Update.DBRemoveAction::Do

- ea: `0x13100`
- end: `0x13164`
- name: `Microsoft.Crm.Setup.Common.Update.DBRemoveAction::Do`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x123f0`
- `0x12850`
- `0x13100`

## string_xrefs

- `0x13148`: `InstallerException: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x13100  ldarg.1
0x13101  ldstr    aParameters// "parameters"
0x13106  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1310b  ldarg.1
0x1310c  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x13111  stloc.0
0x13112  ldloc.0
0x13113  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::get_PatchId()
0x13118  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1311d  brtrue.s loc_13145
0x1311f  ldloc.0
0x13120  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::get_BuildVersion()
0x13125  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1312a  ldloc.0
0x1312b  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.ComponentInfo [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::get_CompInfo()
0x13130  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.ComponentInfo::get_Code()
0x13135  ldloc.0
0x13136  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Update.UpdateInstallInfo::get_AllowPatchRemoval()
0x1313b  newobj   instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::.ctor(class [mscorlib]System.Version version, int32 compCode, bool allowPatchRemoval)
0x13140  callvirt instance void Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::Uninstall()
0x13145  leave.s  loc_13163
0x13147  stloc.1
0x13148  ldstr    aInstallerexcep// "InstallerException: {0}"
0x1314d  ldc.i4.1
0x1314e  newarr   [mscorlib]System.Object
0x13153  dup
0x13154  ldc.i4.0
0x13155  ldloc.1
0x13156  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1315b  stelem.ref
0x1315c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13161  rethrow
0x13163  ret
```
