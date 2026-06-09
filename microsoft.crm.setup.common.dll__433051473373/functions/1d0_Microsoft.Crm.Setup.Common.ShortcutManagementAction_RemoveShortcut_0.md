# Microsoft.Crm.Setup.Common.ShortcutManagementAction::RemoveShortcut_0

- ea: `0x1d0`
- end: `0x270`
- name: `Microsoft.Crm.Setup.Common.ShortcutManagementAction::RemoveShortcut_0`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x150`
- `0x1b0`

## callees

- `0x1d0`

## string_xrefs

- `0x200`: `Could not remove shortcut {0} due to reported error: {1}`
- `0x250`: `Could not remove shortcut folder {0} due to reported error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1d0  ldarg.1
0x1d1  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1d6  brfalse  loc_26F
0x1db  ldarg.2
0x1dc  call     bool [mscorlib]System.IO.File::Exists(string)
0x1e1  brfalse.s loc_21F
0x1e3  ldstr    aRemovingShortc_0// "Removing shortcut {0}"
0x1e8  ldc.i4.1
0x1e9  newarr   [mscorlib]System.Object
0x1ee  dup
0x1ef  ldc.i4.0
0x1f0  ldarg.2
0x1f1  stelem.ref
0x1f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1f7  ldarg.2
0x1f8  call     void [mscorlib]System.IO.File::Delete(string)
0x1fd  leave.s  loc_233
0x1ff  stloc.1
0x200  ldstr    aCouldNotRemove// "Could not remove shortcut {0} due to re"...
0x205  ldc.i4.2
0x206  newarr   [mscorlib]System.Object
0x20b  dup
0x20c  ldc.i4.0
0x20d  ldarg.2
0x20e  stelem.ref
0x20f  dup
0x210  ldc.i4.1
0x211  ldloc.1
0x212  callvirt instance string [mscorlib]System.Exception::get_Message()
0x217  stelem.ref
0x218  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x21d  leave.s  loc_233
0x21f  ldstr    aShortcut0DoesN// "Shortcut {0} does not exist."
0x224  ldc.i4.1
0x225  newarr   [mscorlib]System.Object
0x22a  dup
0x22b  ldc.i4.0
0x22c  ldarg.2
0x22d  stelem.ref
0x22e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x233  ldarg.1
0x234  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x239  ldarg.1
0x23a  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x23f  stloc.0
0x240  ldlen
0x241  brtrue.s loc_26F
0x243  ldloc.0
0x244  ldlen
0x245  brtrue.s loc_26F
0x247  ldarg.1
0x248  call     void [mscorlib]System.IO.Directory::Delete(string)
0x24d  leave.s  loc_26F
0x24f  stloc.2
0x250  ldstr    aCouldNotRemove_0// "Could not remove shortcut folder {0} du"...
0x255  ldc.i4.2
0x256  newarr   [mscorlib]System.Object
0x25b  dup
0x25c  ldc.i4.0
0x25d  ldarg.1
0x25e  stelem.ref
0x25f  dup
0x260  ldc.i4.1
0x261  ldloc.2
0x262  callvirt instance string [mscorlib]System.Exception::get_Message()
0x267  stelem.ref
0x268  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x26d  leave.s  loc_26F
0x26f  ret
```
