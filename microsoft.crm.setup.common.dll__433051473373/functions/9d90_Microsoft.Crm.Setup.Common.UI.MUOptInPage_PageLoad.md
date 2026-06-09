# Microsoft.Crm.Setup.Common.UI.MUOptInPage::PageLoad

- ea: `0x9d90`
- end: `0x9dde`
- name: `Microsoft.Crm.Setup.Common.UI.MUOptInPage::PageLoad`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9d90`
- `0xfbc0`
- `0x10ff0`

## string_xrefs

- `0x9dac`: `InstallInfo.MUOptIn`

## pseudocode

```c

```

## disassembly

```asm
0x9d90  ldarg.0
0x9d91  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9d96  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x9d9b  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x9da0  stloc.0
0x9da1  ldarg.0
0x9da2  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9da7  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x9dac  ldstr    aInstallinfoMuo// "InstallInfo.MUOptIn"
0x9db1  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x9db6  brfalse.s loc_9DDD
0x9db8  ldarg.0
0x9db9  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0x9dbe  ldloc.0
0x9dbf  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_MUOptIn()
0x9dc4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x9dc9  ldarg.0
0x9dca  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseMicrosoftUpdate
0x9dcf  ldloc.0
0x9dd0  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_MUOptIn()
0x9dd5  ldc.i4.0
0x9dd6  ceq
0x9dd8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x9ddd  ret
```
