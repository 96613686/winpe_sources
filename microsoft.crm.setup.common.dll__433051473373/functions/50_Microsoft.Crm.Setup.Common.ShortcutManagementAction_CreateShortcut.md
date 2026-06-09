# Microsoft.Crm.Setup.Common.ShortcutManagementAction::CreateShortcut

- ea: `0x50`
- end: `0x149`
- name: `Microsoft.Crm.Setup.Common.ShortcutManagementAction::CreateShortcut`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x20`

## callees

- `0x50`
- `0x150`
- `0x270`
- `0x2a0`
- `0x2f0`
- `0x310`
- `0x370`
- `0x3a0`
- `0x3c0`
- `0x3d0`
- `0x3f0`

## string_xrefs

- `0xad`: `Shortcut {0} already exists, removing it`
- `0xca`: `Could not remove shortcut {0} due to reported error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x50  ldarg.0
0x51  call     instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutFolder()
0x56  stloc.0
0x57  ldarg.0
0x58  call     instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutFullPath()
0x5d  stloc.1
0x5e  ldarg.0
0x5f  call     instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_CurrentOperation()
0x64  ldc.i4.2
0x65  ceq
0x67  stloc.2
0x68  ldloc.2
0x69  brfalse.s loc_80
0x6b  ldarg.0
0x6c  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutRelativeFolderPreviousVersion()
0x71  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x76  brtrue.s loc_80
0x78  ldarg.0
0x79  ldloc.0
0x7a  ldloc.1
0x7b  callvirt instance void Microsoft.Crm.Setup.Common.ShortcutManagementAction::RemoveOldShortcut(string shortcutFolder, string shortcutFullPath)
0x80  ldloc.0
0x81  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x86  brtrue.s loc_A5
0x88  ldstr    aCreatingShortc// "Creating shortcut folder: "
0x8d  ldloc.0
0x8e  call     string [mscorlib]System.String::Concat(string, string)
0x93  ldc.i4.0
0x94  newarr   [mscorlib]System.Object
0x99  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x9e  ldloc.0
0x9f  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0xa4  pop
0xa5  ldloc.1
0xa6  call     bool [mscorlib]System.IO.File::Exists(string)
0xab  brfalse.s loc_E9
0xad  ldstr    aShortcut0Alrea// "Shortcut {0} already exists, removing i"...
0xb2  ldc.i4.1
0xb3  newarr   [mscorlib]System.Object
0xb8  dup
0xb9  ldc.i4.0
0xba  ldloc.1
0xbb  stelem.ref
0xbc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0xc1  ldloc.1
0xc2  call     void [mscorlib]System.IO.File::Delete(string)
0xc7  leave.s  loc_E9
0xc9  stloc.3
0xca  ldstr    aCouldNotRemove// "Could not remove shortcut {0} due to re"...
0xcf  ldc.i4.2
0xd0  newarr   [mscorlib]System.Object
0xd5  dup
0xd6  ldc.i4.0
0xd7  ldloc.1
0xd8  stelem.ref
0xd9  dup
0xda  ldc.i4.1
0xdb  ldloc.3
0xdc  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe1  stelem.ref
0xe2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0xe7  leave.s  loc_E9
0xe9  ldstr    aCreatingShortc_0// "Creating shortcut {0} for target {1}"
0xee  ldc.i4.2
0xef  newarr   [mscorlib]System.Object
0xf4  dup
0xf5  ldc.i4.0
0xf6  ldloc.1
0xf7  stelem.ref
0xf8  dup
0xf9  ldc.i4.1
0xfa  ldarg.0
0xfb  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_TargetPath()
0x100  stelem.ref
0x101  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x106  ldarg.0
0x107  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_TargetPath()
0x10c  ldarg.0
0x10d  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_Arguments()
0x112  ldloc.1
0x113  ldarg.0
0x114  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutDescription()
0x119  ldarg.0
0x11a  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_WorkingDirectory()
0x11f  ldarg.0
0x120  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_IconPath()
0x125  ldarg.0
0x126  callvirt instance int32 Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_IconIndex()
0x12b  call     void [Microsoft.Crm.Setup.Common.Interop]Microsoft.Crm.Setup.Common.Utility.ShellUtility::CreateShortcut(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string, string, string, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string, int32)
0x130  ldloc.2
0x131  brfalse.s loc_148
0x133  ldc.i4   0x8000000
0x138  ldc.i4.0
0x139  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x13e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x143  call     void [Microsoft.Crm.Setup.Common.Interop]Microsoft.Crm.Setup.Common.Utility.ShellUtility::SHChangeNotify(valuetype [Microsoft.Crm.Setup.Common.Interop]Microsoft.Crm.Setup.Common.Utility.ShellChangeNotifyEventID, valuetype [Microsoft.Crm.Setup.Common.Interop]Microsoft.Crm.Setup.Common.Utility.ShellChangeNotifyFlags, native int, native int)
0x148  ret
```
