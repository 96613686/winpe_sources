# Microsoft.Crm.Setup.Common.UI.ProgressPage::ProgressPage_Activated

- ea: `0xbc30`
- end: `0xbcbf`
- name: `Microsoft.Crm.Setup.Common.UI.ProgressPage::ProgressPage_Activated`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0xbc30`
- `0xfca0`
- `0xfcb0`
- `0xfcd0`
- `0x10ff0`

## string_xrefs

- `0xbca3`: `Starting thread routine provided to progress page by setup`

## pseudocode

```c

```

## disassembly

```asm
0xbc30  ldarg.0
0xbc31  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc36  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0xbc3b  ldc.i4.0
0xbc3c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xbc41  ldarg.0
0xbc42  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc47  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0xbc4c  ldc.i4.0
0xbc4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xbc52  ldarg.0
0xbc53  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc58  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0xbc5d  ldc.i4.0
0xbc5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xbc63  ldarg.0
0xbc64  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc69  ldc.i4.0
0xbc6a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ControlBox(bool)
0xbc6f  ldc.i4.1
0xbc70  ldarg.0
0xbc71  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc76  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState [System.Windows.Forms]System.Windows.Forms.Form::get_WindowState()
0xbc7b  bne.un.s loc_BC94
0xbc7d  ldarg.0
0xbc7e  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc83  ldc.i4.0
0xbc84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_WindowState(valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState)
0xbc89  ldarg.0
0xbc8a  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbc8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Update()
0xbc94  ldarg.0
0xbc95  ldc.i4.0
0xbc96  stfld    int32 Microsoft.Crm.Setup.Common.UI.ProgressPage::_completionNotificationReceived
0xbc9b  ldarg.0
0xbc9c  ldfld    class [mscorlib]System.Threading.Thread Microsoft.Crm.Setup.Common.UI.ProgressPage::_workerThread
0xbca1  brfalse.s loc_BCBE
0xbca3  ldstr    aStartingThread// "Starting thread routine provided to pro"...
0xbca8  ldc.i4.0
0xbca9  newarr   [mscorlib]System.Object
0xbcae  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xbcb3  ldarg.0
0xbcb4  ldfld    class [mscorlib]System.Threading.Thread Microsoft.Crm.Setup.Common.UI.ProgressPage::_workerThread
0xbcb9  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0xbcbe  ret
```
