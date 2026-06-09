# Microsoft.Crm.Setup.Common.UI.WizardPage::get_IsFirstPage

- ea: `0x110f0`
- end: `0x11104`
- name: `Microsoft.Crm.Setup.Common.UI.WizardPage::get_IsFirstPage`
- size: `20`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4f20`
- `0x50a0`
- `0x6ba0`
- `0xbba0`

## callees

- `0xfbe0`
- `0x105d0`
- `0x10ff0`

## pseudocode

```c

```

## disassembly

```asm
0x110f0  ldarg.0
0x110f1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x110f6  callvirt instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x110fb  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::GetFirstPage()
0x11100  ldarg.0
0x11101  ceq
0x11103  ret
```
