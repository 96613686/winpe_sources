# Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutFullPath

- ea: `0x2a0`
- end: `0x2ea`
- name: `Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutFullPath`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x50`
- `0x1b0`

## callees

- `0x270`
- `0x2a0`
- `0x380`
- `0x400`

## pseudocode

```c

```

## disassembly

```asm
0x2a0  ldarg.0
0x2a1  callvirt instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutName()
0x2a6  stloc.0
0x2a7  ldloc.0
0x2a8  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x2ad  stloc.1
0x2ae  ldloc.1
0x2af  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b4  brtrue.s loc_2C4
0x2b6  ldloc.1
0x2b7  ldstr    aLnk// ".lnk"
0x2bc  ldc.i4.5
0x2bd  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2c2  brtrue.s loc_2D0
0x2c4  ldloc.0
0x2c5  ldstr    aLnk// ".lnk"
0x2ca  call     string [mscorlib]System.String::Concat(string, string)
0x2cf  stloc.0
0x2d0  ldarg.0
0x2d1  ldloc.0
0x2d2  call     char[] [mscorlib]System.IO.Path::GetInvalidFileNameChars()
0x2d7  call     instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::ScrubString(string stringToScrub, char[] invalidChars)
0x2dc  stloc.0
0x2dd  ldarg.0
0x2de  call     instance string Microsoft.Crm.Setup.Common.ShortcutManagementAction::get_ShortcutFolder()
0x2e3  ldloc.0
0x2e4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2e9  ret
```
