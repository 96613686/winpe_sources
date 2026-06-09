# Microsoft.Crm.Setup.Common.UI.FinishPage::PageLoad

- ea: `0x6ba0`
- end: `0x6c2d`
- name: `Microsoft.Crm.Setup.Common.UI.FinishPage::PageLoad`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5680`
- `0x6ba0`
- `0x10ff0`
- `0x110f0`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  ldarg.0
0x6ba1  call     instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::get_IsFirstPage()
0x6ba6  brfalse  loc_6C2C
0x6bab  ldarg.0
0x6bac  call     class [System.Windows.Forms]System.Windows.Forms.Screen [System.Windows.Forms]System.Windows.Forms.Screen::FromControl(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6bb1  stloc.0
0x6bb2  ldloc.0
0x6bb3  brfalse.s loc_6BBB
0x6bb5  call     class [System.Windows.Forms]System.Windows.Forms.Screen [System.Windows.Forms]System.Windows.Forms.Screen::get_PrimaryScreen()
0x6bba  stloc.0
0x6bbb  ldarg.0
0x6bbc  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6bc1  ldloc.0
0x6bc2  callvirt instance valuetype [System.Drawing]System.Drawing.Rectangle [System.Windows.Forms]System.Windows.Forms.Screen::get_WorkingArea()
0x6bc7  stloc.1
0x6bc8  ldloca.s 1
0x6bca  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Width()
0x6bcf  ldarg.0
0x6bd0  call     instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0x6bd5  sub
0x6bd6  ldc.i4.2
0x6bd7  div
0x6bd8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Left(int32)
0x6bdd  ldarg.0
0x6bde  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6be3  ldloc.0
0x6be4  callvirt instance valuetype [System.Drawing]System.Drawing.Rectangle [System.Windows.Forms]System.Windows.Forms.Screen::get_WorkingArea()
0x6be9  stloc.1
0x6bea  ldloca.s 1
0x6bec  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Height()
0x6bf1  ldarg.0
0x6bf2  call     instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x6bf7  sub
0x6bf8  ldc.i4.2
0x6bf9  div
0x6bfa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Top(int32)
0x6bff  ldarg.0
0x6c00  call     instance bool Microsoft.Crm.Setup.Common.UI.FinishPage::get_InClientContext()
0x6c05  brtrue.s loc_6C14
0x6c07  ldarg.0
0x6c08  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c0d  ldc.i4.1
0x6c0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_WindowState(valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState)
0x6c13  ret
0x6c14  ldarg.0
0x6c15  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c1a  ldc.i4.1
0x6c1b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_WindowState(valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState)
0x6c20  ldarg.0
0x6c21  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c26  ldc.i4.0
0x6c27  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_WindowState(valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState)
0x6c2c  ret
```
