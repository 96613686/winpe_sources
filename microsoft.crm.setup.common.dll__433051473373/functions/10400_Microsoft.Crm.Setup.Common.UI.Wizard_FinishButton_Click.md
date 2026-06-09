# Microsoft.Crm.Setup.Common.UI.Wizard::FinishButton_Click

- ea: `0x10400`
- end: `0x1042f`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::FinishButton_Click`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0xfbb0`
- `0xfbe0`
- `0xfd40`
- `0x10400`
- `0x105c0`
- `0x110a0`

## pseudocode

```c

```

## disassembly

```asm
0x10400  ldarg.0
0x10401  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10406  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x1040b  brtrue.s loc_1040E
0x1040d  ret
0x1040e  ldarg.0
0x1040f  ldc.i4.0
0x10410  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_RequiresClosingConfirmation(bool value)
0x10415  ldarg.0
0x10416  ldc.i4.1
0x10417  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_WizardClose(valuetype WizardCloseType value)
0x1041c  ldarg.0
0x1041d  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10422  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x10427  ldarg.1
0x10428  ldarg.2
0x10429  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPage::RaiseFinishClicked(object sender, class [mscorlib]System.EventArgs e)
0x1042e  ret
```
