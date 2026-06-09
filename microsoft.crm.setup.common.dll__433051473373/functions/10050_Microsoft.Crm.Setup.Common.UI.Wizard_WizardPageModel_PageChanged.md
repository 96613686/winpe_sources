# Microsoft.Crm.Setup.Common.UI.Wizard::WizardPageModel_PageChanged

- ea: `0x10050`
- end: `0x1024a`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::WizardPageModel_PageChanged`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0xfc70`
- `0xfc90`
- `0xfca0`
- `0xfcb0`
- `0xfcc0`
- `0xfcd0`
- `0xfce0`
- `0x10050`
- `0x10250`
- `0x105d0`
- `0x10a20`
- `0x10a30`
- `0x10ec0`
- `0x10f10`
- `0x10f30`
- `0x10fb0`
- `0x10fd0`
- `0x11010`
- `0x11040`

## pseudocode

```c

```

## disassembly

```asm
0x10050  ldarg.0
0x10051  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x10056  ldarg.2
0x10057  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_LastPage()
0x1005c  brfalse.s loc_10087
0x1005e  ldarg.2
0x1005f  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_LastPage()
0x10064  ldc.i4.0
0x10065  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x1006a  ldarg.2
0x1006b  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_LastPage()
0x10070  ldarg.0
0x10071  newobj   instance void [mscorlib]System.EventArgs::.ctor()
0x10076  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPage::RaisePageDeactivated(object sender, class [mscorlib]System.EventArgs e)
0x1007b  ldarg.2
0x1007c  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_LastPage()
0x10081  ldc.i4.0
0x10082  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x10087  ldarg.2
0x10088  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x1008d  brfalse  loc_10242
0x10092  ldarg.0
0x10093  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x10098  ldc.i4.1
0x10099  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x1009e  ldarg.0
0x1009f  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x100a4  ldc.i4.1
0x100a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x100aa  ldarg.0
0x100ab  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x100b0  ldc.i4.0
0x100b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x100b6  ldarg.0
0x100b7  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x100bc  ldc.i4.1
0x100bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x100c2  ldarg.0
0x100c3  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x100c8  ldarg.2
0x100c9  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x100ce  ldarg.0
0x100cf  ldfld    class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::model
0x100d4  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::GetFirstPage()
0x100d9  ceq
0x100db  ldc.i4.0
0x100dc  ceq
0x100de  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x100e3  ldarg.0
0x100e4  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x100e9  ldc.i4.1
0x100ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x100ef  ldarg.0
0x100f0  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x100f5  ldc.i4.0
0x100f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x100fb  ldarg.0
0x100fc  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x10101  ldc.i4.1
0x10102  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x10107  ldarg.2
0x10108  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x1010d  ldc.i4.5
0x1010e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x10113  ldarg.2
0x10114  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x10119  ldarg.0
0x1011a  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::pagePanel
0x1011f  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_Size()
0x10124  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x10129  ldarg.0
0x1012a  call     instance class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Crm.Setup.Common.UI.Wizard::get_PagePanel()
0x1012f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x10134  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Clear()
0x10139  ldarg.2
0x1013a  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x1013f  callvirt instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::get_HideSpacerPanel()
0x10144  brtrue.s loc_10172
0x10146  ldarg.0
0x10147  call     instance class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Crm.Setup.Common.UI.Wizard::get_PagePanel()
0x1014c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x10151  ldarg.0
0x10152  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::spacerPanel
0x10157  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x1015c  ldarg.0
0x1015d  call     instance class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Crm.Setup.Common.UI.Wizard::get_PagePanel()
0x10162  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x10167  ldarg.0
0x10168  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::TopSpacerPanel
0x1016d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x10172  ldc.i4.0
0x10173  stloc.0
0x10174  br.s     loc_1019B
0x10176  ldarg.0
0x10177  call     instance class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Crm.Setup.Common.UI.Wizard::get_PagePanel()
0x1017c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x10181  ldarg.2
0x10182  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x10187  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection Microsoft.Crm.Setup.Common.UI.WizardPage::get_PageControls()
0x1018c  ldloc.0
0x1018d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::get_Item(int32)
0x10192  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x10197  ldloc.0
0x10198  ldc.i4.1
0x10199  add
0x1019a  stloc.0
0x1019b  ldloc.0
0x1019c  ldarg.2
0x1019d  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101a2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection Microsoft.Crm.Setup.Common.UI.WizardPage::get_PageControls()
0x101a7  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Layout.ArrangedElementCollection::get_Count()
0x101ac  blt.s    loc_10176
0x101ae  ldarg.2
0x101af  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101b4  ldc.i4.1
0x101b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x101ba  ldarg.2
0x101bb  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101c0  ldc.i4.1
0x101c1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x101c6  ldarg.2
0x101c7  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Select()
0x101d1  ldarg.2
0x101d2  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101d7  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x101dc  pop
0x101dd  ldarg.2
0x101de  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101e3  ldarg.2
0x101e4  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101e9  newobj   instance void [mscorlib]System.EventArgs::.ctor()
0x101ee  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPage::RaisePageLoad(object sender, class [mscorlib]System.EventArgs e)
0x101f3  ldarg.2
0x101f4  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x101f9  ldarg.0
0x101fa  newobj   instance void [mscorlib]System.EventArgs::.ctor()
0x101ff  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPage::RaisePageActivated(object sender, class [mscorlib]System.EventArgs e)
0x10204  ldarg.0
0x10205  ldarg.2
0x10206  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x1020b  callvirt instance string Microsoft.Crm.Setup.Common.UI.WizardPage::get_HeaderTitle()
0x10210  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_HeaderTitle(string value)
0x10215  ldarg.0
0x10216  ldarg.2
0x10217  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs::get_CurrentPage()
0x1021c  callvirt instance string Microsoft.Crm.Setup.Common.UI.WizardPage::get_HeaderDetails()
0x10221  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_HeaderDetails(string value)
0x10226  ldarg.0
0x10227  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.Wizard::headerTitleLabel
0x1022c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Refresh()
0x10231  ldarg.0
0x10232  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.Wizard::headerDetailsLabel
0x10237  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Refresh()
0x1023c  ldarg.0
0x1023d  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::ArrangeNavigationButtons()
0x10242  ldarg.0
0x10243  ldc.i4.1
0x10244  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x10249  ret
```
