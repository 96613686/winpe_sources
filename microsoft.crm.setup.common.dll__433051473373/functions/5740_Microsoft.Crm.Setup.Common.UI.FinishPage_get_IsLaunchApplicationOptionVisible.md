# Microsoft.Crm.Setup.Common.UI.FinishPage::get_IsLaunchApplicationOptionVisible

- ea: `0x5740`
- end: `0x5772`
- name: `Microsoft.Crm.Setup.Common.UI.FinishPage::get_IsLaunchApplicationOptionVisible`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6c30`

## callees

- `0x5740`
- `0xfbc0`
- `0x10ff0`

## string_xrefs

- `0x574b`: `InstallInfo.LaunchApplication`
- `0x5762`: `InstallInfo.LaunchApplicationPath`

## pseudocode

```c

```

## disassembly

```asm
0x5740  ldarg.0
0x5741  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x5746  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x574b  ldstr    aInstallinfoLau// "InstallInfo.LaunchApplication"
0x5750  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x5755  brfalse.s loc_5770
0x5757  ldarg.0
0x5758  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x575d  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x5762  ldstr    aInstallinfoLau_0// "InstallInfo.LaunchApplicationPath"
0x5767  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x576c  brfalse.s loc_5770
0x576e  ldc.i4.1
0x576f  ret
0x5770  ldc.i4.0
0x5771  ret
```
