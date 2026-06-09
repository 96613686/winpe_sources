# Microsoft.Crm.Setup.Common.CA.CommonCustomActions::EnableDesktopExperience

- ea: `0x16ee0`
- end: `0x16ef1`
- name: `Microsoft.Crm.Setup.Common.CA.CommonCustomActions::EnableDesktopExperience`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x16f00`

## string_xrefs

- `0x16ee6`: `ClientDesktopExperienceInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x16ee0  ldarg.0
0x16ee1  ldstr    aDesktopexperie// "DesktopExperience"
0x16ee6  ldstr    aClientdesktope// "ClientDesktopExperienceInstalled"
0x16eeb  call     valuetype [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.ActionResult Microsoft.Crm.Setup.Common.CA.CommonCustomActions::EnableWindowsFeature(class [Microsoft.WindowsInstaller]Microsoft.WindowsInstaller.Session session, string feature, string disabledRegKeyName)
0x16ef0  ret
```
