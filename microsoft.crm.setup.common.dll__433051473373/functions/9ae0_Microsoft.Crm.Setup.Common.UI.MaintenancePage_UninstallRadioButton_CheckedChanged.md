# Microsoft.Crm.Setup.Common.UI.MaintenancePage::UninstallRadioButton_CheckedChanged

- ea: `0x9ae0`
- end: `0x9c6d`
- name: `Microsoft.Crm.Setup.Common.UI.MaintenancePage::UninstallRadioButton_CheckedChanged`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x8730`
- `0x9ae0`
- `0xfbc0`
- `0xfca0`
- `0xfcc0`
- `0x10250`
- `0x10ff0`

## string_xrefs

- `0x9b5d`: `UninstallButtonText`
- `0x9bcb`: `UninstallButtonText`
- `0x9c44`: `UninstallButtonText`

## pseudocode

```c

```

## disassembly

```asm
0x9ae0  ldarg.0
0x9ae1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9ae6  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x9aeb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x9af0  ldc.i4.4
0x9af1  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_InstallType(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType)
0x9af6  ldarg.1
0x9af7  castclass [System.Windows.Forms]System.Windows.Forms.RadioButton
0x9afc  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.RadioButton::get_Checked()
0x9b01  brfalse  loc_9BF5
0x9b06  ldarg.0
0x9b07  callvirt instance bool Microsoft.Crm.Setup.Common.UI.MaintenancePage::get_UseFinishButtonForUninstall()
0x9b0c  brfalse.s loc_9B7C
0x9b0e  ldarg.0
0x9b0f  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9b14  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9b19  ldc.i4.0
0x9b1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9b1f  ldarg.0
0x9b20  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9b25  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9b2a  ldc.i4.0
0x9b2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9b30  ldarg.0
0x9b31  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9b36  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9b3b  ldc.i4.1
0x9b3c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9b41  ldarg.0
0x9b42  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9b47  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9b4c  ldc.i4.1
0x9b4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9b52  ldarg.0
0x9b53  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9b58  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9b5d  ldstr    aUninstallbutto// "UninstallButtonText"
0x9b62  ldc.i4.1
0x9b63  newarr   [mscorlib]System.Object
0x9b68  dup
0x9b69  ldc.i4.0
0x9b6a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x9b6f  stelem.ref
0x9b70  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x9b75  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x9b7a  br.s     loc_9BE8
0x9b7c  ldarg.0
0x9b7d  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9b82  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9b87  ldc.i4.1
0x9b88  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9b8d  ldarg.0
0x9b8e  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9b93  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9b98  ldc.i4.1
0x9b99  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9b9e  ldarg.0
0x9b9f  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9ba4  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9ba9  ldc.i4.0
0x9baa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9baf  ldarg.0
0x9bb0  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9bb5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9bba  ldc.i4.0
0x9bbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9bc0  ldarg.0
0x9bc1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9bc6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9bcb  ldstr    aUninstallbutto// "UninstallButtonText"
0x9bd0  ldc.i4.1
0x9bd1  newarr   [mscorlib]System.Object
0x9bd6  dup
0x9bd7  ldc.i4.0
0x9bd8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x9bdd  stelem.ref
0x9bde  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x9be3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x9be8  ldarg.0
0x9be9  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9bee  callvirt instance void Microsoft.Crm.Setup.Common.UI.Wizard::ArrangeNavigationButtons()
0x9bf3  br.s     loc_9C61
0x9bf5  ldarg.0
0x9bf6  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9bfb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9c00  ldc.i4.1
0x9c01  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9c06  ldarg.0
0x9c07  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9c0c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9c11  ldc.i4.1
0x9c12  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9c17  ldarg.0
0x9c18  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9c1d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9c22  ldc.i4.0
0x9c23  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9c28  ldarg.0
0x9c29  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9c2e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9c33  ldc.i4.0
0x9c34  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9c39  ldarg.0
0x9c3a  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9c3f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9c44  ldstr    aUninstallbutto// "UninstallButtonText"
0x9c49  ldc.i4.1
0x9c4a  newarr   [mscorlib]System.Object
0x9c4f  dup
0x9c50  ldc.i4.0
0x9c51  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x9c56  stelem.ref
0x9c57  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x9c5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x9c61  ldarg.0
0x9c62  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9c67  callvirt instance void Microsoft.Crm.Setup.Common.UI.Wizard::ArrangeNavigationButtons()
0x9c6c  ret
```
