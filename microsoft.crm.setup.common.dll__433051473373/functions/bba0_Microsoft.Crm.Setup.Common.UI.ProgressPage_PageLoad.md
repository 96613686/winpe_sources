# Microsoft.Crm.Setup.Common.UI.ProgressPage::PageLoad

- ea: `0xbba0`
- end: `0xbc26`
- name: `Microsoft.Crm.Setup.Common.UI.ProgressPage::PageLoad`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb850`
- `0xbba0`
- `0xfca0`
- `0xfcb0`
- `0xfcd0`
- `0x10ff0`
- `0x110f0`

## pseudocode

```c

```

## disassembly

```asm
0xbba0  ldarg.0
0xbba1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbba6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0xbbab  ldc.i4.0
0xbbac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xbbb1  ldarg.0
0xbbb2  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbbb7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0xbbbc  ldc.i4.0
0xbbbd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xbbc2  ldarg.0
0xbbc3  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbbc8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0xbbcd  ldc.i4.0
0xbbce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xbbd3  ldarg.0
0xbbd4  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbbd9  ldc.i4.0
0xbbda  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ControlBox(bool)
0xbbdf  ldarg.0
0xbbe0  call     instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::get_IsFirstPage()
0xbbe5  brfalse.s loc_BBF3
0xbbe7  ldarg.0
0xbbe8  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbbed  ldc.i4.1
0xbbee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_WindowState(valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState)
0xbbf3  ldarg.0
0xbbf4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xbbf9  ldarg.0
0xbbfa  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbbff  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Form::get_RightToLeftLayout()
0xbc04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::set_RightToLeftLayout(bool)
0xbc09  ldarg.0
0xbc0a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressBar
0xbc0f  ldarg.0
0xbc10  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc15  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Form::get_RightToLeftLayout()
0xbc1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::set_RightToLeftLayout(bool)
0xbc1f  ldarg.0
0xbc20  call     instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::HookProgressEvents()
0xbc25  ret
```
