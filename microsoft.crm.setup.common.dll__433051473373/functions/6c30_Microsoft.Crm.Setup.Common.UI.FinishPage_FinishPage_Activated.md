# Microsoft.Crm.Setup.Common.UI.FinishPage::FinishPage_Activated

- ea: `0x6c30`
- end: `0x6f03`
- name: `Microsoft.Crm.Setup.Common.UI.FinishPage::FinishPage_Activated`
- size: `723`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x5640`
- `0x5660`
- `0x5680`
- `0x56a0`
- `0x5740`
- `0x5780`
- `0x5790`
- `0x6c30`
- `0xfbc0`
- `0xfc10`
- `0xfc20`
- `0xfca0`
- `0xfcb0`
- `0xfcc0`
- `0xfcd0`
- `0xfd40`
- `0x10ff0`
- `0x11210`

## pseudocode

```c

```

## disassembly

```asm
0x6c30  ldarg.0
0x6c31  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6c36  ldarg.0
0x6c37  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c3c  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x6c41  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x6c46  stloc.0
0x6c47  ldarg.0
0x6c48  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c4d  ldc.i4.0
0x6c4e  callvirt instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_RequiresClosingConfirmation(bool value)
0x6c53  ldarg.0
0x6c54  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c59  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Crm.Setup.Common.UI.Wizard::get_HeaderPanel()
0x6c5e  ldc.i4.0
0x6c5f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6c64  ldarg.0
0x6c65  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c6a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control Microsoft.Crm.Setup.Common.UI.Wizard::get_TopSeparator()
0x6c6f  ldc.i4.0
0x6c70  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6c75  ldarg.0
0x6c76  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c7b  ldarg.0
0x6c7c  call     instance bool Microsoft.Crm.Setup.Common.UI.FinishPage::get_InClientContext()
0x6c81  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ControlBox(bool)
0x6c86  ldarg.0
0x6c87  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c8c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x6c91  ldc.i4.0
0x6c92  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6c97  ldarg.0
0x6c98  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6c9d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x6ca2  ldc.i4.0
0x6ca3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6ca8  ldarg.0
0x6ca9  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6cae  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x6cb3  ldc.i4.0
0x6cb4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6cb9  ldarg.0
0x6cba  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6cbf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x6cc4  ldc.i4.1
0x6cc5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6cca  ldarg.0
0x6ccb  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6cd0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x6cd5  ldc.i4.1
0x6cd6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x6cdb  ldarg.0
0x6cdc  ldfld    string Microsoft.Crm.Setup.Common.UI.FinishPage::_applicationTitle
0x6ce1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6ce6  brtrue.s loc_6CF9
0x6ce8  ldarg.0
0x6ce9  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6cee  ldarg.0
0x6cef  ldfld    string Microsoft.Crm.Setup.Common.UI.FinishPage::_applicationTitle
0x6cf4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6cf9  ldarg.0
0x6cfa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x6cff  ldarg.0
0x6d00  callvirt instance string Microsoft.Crm.Setup.Common.UI.FinishPage::get_PageTitle()
0x6d05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6d0a  ldarg.0
0x6d0b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Diagnostics.ProcessStartInfo> Microsoft.Crm.Setup.Common.UI.FinishPage::get_LinkApplications()
0x6d10  brfalse.s loc_6D1F
0x6d12  ldarg.0
0x6d13  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Diagnostics.ProcessStartInfo> Microsoft.Crm.Setup.Common.UI.FinishPage::get_LinkApplications()
0x6d18  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Diagnostics.ProcessStartInfo>::get_Count()
0x6d1d  brtrue.s loc_6D62
0x6d1f  ldarg.0
0x6d20  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x6d25  ldarg.0
0x6d26  callvirt instance string Microsoft.Crm.Setup.Common.UI.FinishPage::get_Details()
0x6d2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6d30  ldarg.0
0x6d31  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x6d36  ldc.i4.1
0x6d37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6d3c  ldarg.0
0x6d3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x6d42  ldc.i4.1
0x6d43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x6d48  ldarg.0
0x6d49  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelPostInstallAction
0x6d4e  ldc.i4.0
0x6d4f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6d54  ldarg.0
0x6d55  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelPostInstallAction
0x6d5a  ldc.i4.0
0x6d5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x6d60  br.s     loc_6DAE
0x6d62  ldarg.0
0x6d63  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelPostInstallAction
0x6d68  ldarg.0
0x6d69  callvirt instance string Microsoft.Crm.Setup.Common.UI.FinishPage::get_Details()
0x6d6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6d73  ldarg.0
0x6d74  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelPostInstallAction
0x6d79  call     void Microsoft.Crm.Setup.Common.Utility.LinkLabelUtility::SetLinkArea(class [System.Windows.Forms]System.Windows.Forms.LinkLabel linkLabelControl)
0x6d7e  ldarg.0
0x6d7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x6d84  ldc.i4.0
0x6d85  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6d8a  ldarg.0
0x6d8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x6d90  ldc.i4.0
0x6d91  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x6d96  ldarg.0
0x6d97  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelPostInstallAction
0x6d9c  ldc.i4.1
0x6d9d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6da2  ldarg.0
0x6da3  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelPostInstallAction
0x6da8  ldc.i4.1
0x6da9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x6dae  ldloc.0
0x6daf  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_RebootRequired()
0x6db4  brfalse  loc_6E4A
0x6db9  ldarg.0
0x6dba  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelInstructions
0x6dbf  ldstr    aInfoRebootrequ// "Info.RebootRequired"
0x6dc4  ldc.i4.1
0x6dc5  newarr   [mscorlib]System.Object
0x6dca  dup
0x6dcb  ldc.i4.0
0x6dcc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x6dd1  stelem.ref
0x6dd2  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x6dd7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6ddc  ldarg.0
0x6ddd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelInstructions
0x6de2  ldc.i4.1
0x6de3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6de8  ldarg.0
0x6de9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelInstructions
0x6dee  ldc.i4.1
0x6def  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x6df4  ldarg.0
0x6df5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxRestart
0x6dfa  ldc.i4.1
0x6dfb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6e00  ldarg.0
0x6e01  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxRestart
0x6e06  ldloc.0
0x6e07  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_SuppressReboot()
0x6e0c  brtrue.s loc_6E36
0x6e0e  ldloc.0
0x6e0f  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_Setup()
0x6e14  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::get_ErrorEncountered()
0x6e19  brfalse.s loc_6E28
0x6e1b  ldloc.0
0x6e1c  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_Setup()
0x6e21  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::get_OverrideErrorReboot()
0x6e26  brfalse.s loc_6E36
0x6e28  ldc.i4.4
0x6e29  ldloc.0
0x6e2a  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x6e2f  ceq
0x6e31  ldc.i4.0
0x6e32  ceq
0x6e34  br.s     loc_6E37
0x6e36  ldc.i4.0
0x6e37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x6e3c  ldarg.0
0x6e3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxLaunchApp
0x6e42  ldc.i4.0
0x6e43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6e48  br.s     loc_6E8B
0x6e4a  ldarg.0
0x6e4b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelInstructions
0x6e50  ldc.i4.0
0x6e51  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6e56  ldarg.0
0x6e57  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelInstructions
0x6e5c  ldc.i4.0
0x6e5d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x6e62  ldarg.0
0x6e63  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxRestart
0x6e68  ldc.i4.0
0x6e69  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6e6e  ldarg.0
0x6e6f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxRestart
0x6e74  ldc.i4.0
0x6e75  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x6e7a  ldarg.0
0x6e7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxLaunchApp
0x6e80  ldarg.0
0x6e81  callvirt instance bool Microsoft.Crm.Setup.Common.UI.FinishPage::get_IsLaunchApplicationOptionVisible()
0x6e86  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x6e8b  ldarg.0
0x6e8c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxLaunchApp
0x6e91  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_Visible()
0x6e96  brfalse.s loc_6ED6
0x6e98  ldarg.0
0x6e99  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxLaunchApp
0x6e9e  ldarg.0
0x6e9f  callvirt instance bool Microsoft.Crm.Setup.Common.UI.FinishPage::get_IsLaunchApplicationOptionChecked()
0x6ea4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x6ea9  ldarg.0
0x6eaa  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxLaunchApp
0x6eaf  ldarg.0
0x6eb0  callvirt instance string Microsoft.Crm.Setup.Common.UI.FinishPage::get_CheckBoxTextForLaunchApplicationOption()
0x6eb5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x6eba  ldarg.0
0x6ebb  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6ec0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x6ec5  ldarg.0
0x6ec6  ldftn    instance void Microsoft.Crm.Setup.Common.UI.FinishPage::FinishButtonLaunchApp(object sender, class [mscorlib]System.EventArgs e)
0x6ecc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6ed1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6ed6  ldc.i4.1
0x6ed7  ldarg.0
0x6ed8  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6edd  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState [System.Windows.Forms]System.Windows.Forms.Form::get_WindowState()
0x6ee2  bne.un.s loc_6EFB
0x6ee4  ldarg.0
0x6ee5  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6eea  ldc.i4.0
0x6eeb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_WindowState(valuetype [System.Windows.Forms]System.Windows.Forms.FormWindowState)
0x6ef0  ldarg.0
0x6ef1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x6ef6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Update()
0x6efb  ldarg.0
0x6efc  ldc.i4.1
0x6efd  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x6f02  ret
```
