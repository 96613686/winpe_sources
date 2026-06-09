# Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutFolder

- ea: `0x270`
- end: `0x291`
- name: `Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutFolder`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x50`
- `0x1b0`
- `0x2a0`

## callees

- `0x350`
- `0x360`
- `0x400`

## pseudocode

```c

```

## disassembly

```asm
0x270  ldarg.0
0x271  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutRootFolder()
0x276  ldarg.0
0x277  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutRelativeFolder()
0x27c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x281  stloc.0
0x282  ldarg.0
0x283  ldloc.0
0x284  call     char[] [mscorlib]System.IO.Path::GetInvalidPathChars()
0x289  call     instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::ScrubString(string stringToScrub, char[] invalidChars)
0x28e  stloc.0
0x28f  ldloc.0
0x290  ret
```
