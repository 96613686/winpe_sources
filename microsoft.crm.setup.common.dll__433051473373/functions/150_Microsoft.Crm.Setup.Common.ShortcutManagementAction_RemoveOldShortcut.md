# Microsoft.Crm.Setup.Common.ShortcutManagementAction::RemoveOldShortcut

- ea: `0x150`
- end: `0x1a5`
- name: `Microsoft.Crm.Setup.Common.ShortcutManagementAction::RemoveOldShortcut`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x50`

## callees

- `0x150`
- `0x1d0`
- `0x360`
- `0x370`
- `0x380`
- `0x390`

## pseudocode

```c

```

## disassembly

```asm
0x150  ldarg.1
0x151  ldarg.0
0x152  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutRelativeFolder()
0x157  ldarg.0
0x158  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutRelativeFolderPreviousVersion()
0x15d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x162  stloc.0
0x163  ldarg.2
0x164  ldarg.1
0x165  ldloc.0
0x166  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x16b  stloc.1
0x16c  ldarg.0
0x16d  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutName()
0x172  stloc.2
0x173  ldarg.0
0x174  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_OldShortcutName()
0x179  stloc.3
0x17a  ldloc.2
0x17b  ldloc.3
0x17c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x181  brfalse.s loc_18C
0x183  ldloc.1
0x184  ldloc.2
0x185  ldloc.3
0x186  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x18b  stloc.1
0x18c  ldstr    aRemovingShortc// "Removing shortcut from previous version"
0x191  ldc.i4.0
0x192  newarr   [mscorlib]System.Object
0x197  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x19c  ldarg.0
0x19d  ldloc.0
0x19e  ldloc.1
0x19f  call     instance void Microsoft.Crm.Setup.Common.ShortcutManagementAction::RemoveShortcut(string shortcutFolder, string shortcutFullPath)
0x1a4  ret
```
