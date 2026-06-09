# Microsoft.Crm.Setup.Common.UI.MaintenancePage::MaintenancePage_PageActivated

- ea: `0x9980`
- end: `0x99c0`
- name: `Microsoft.Crm.Setup.Common.UI.MaintenancePage::MaintenancePage_PageActivated`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9d50`
- `0xfbc0`
- `0xfcb0`
- `0xfcd0`
- `0x10ff0`

## pseudocode

```c

```

## disassembly

```asm
0x9980  ldarg.0
0x9981  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9986  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x998b  ldc.i4.0
0x998c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9991  ldarg.0
0x9992  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9997  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x999c  ldc.i4.1
0x999d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x99a2  ldarg.0
0x99a3  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x99a8  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x99ad  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x99b2  stloc.0
0x99b3  ldarg.0
0x99b4  ldloc.0
0x99b5  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x99ba  call     instance void Microsoft.Crm.Setup.Common.UI.MaintenancePage::set_PreviousInstallType(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType value)
0x99bf  ret
```
