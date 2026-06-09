# Microsoft.Crm.Setup.Common.UI.MaintenancePage::AddRemoveRadioButton_CheckedChanged

- ea: `0x9c70`
- end: `0x9d27`
- name: `Microsoft.Crm.Setup.Common.UI.MaintenancePage::AddRemoveRadioButton_CheckedChanged`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x9c70`
- `0xfbc0`
- `0xfca0`
- `0xfcc0`
- `0x10250`
- `0x10ff0`

## pseudocode

```c

```

## disassembly

```asm
0x9c70  ldarg.0
0x9c71  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9c76  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x9c7b  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x9c80  ldarg.0
0x9c81  ldfld    valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType Microsoft.Crm.Setup.Common.UI.MaintenancePage::_operationForAddRemoveButton
0x9c86  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_InstallType(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType)
0x9c8b  ldarg.1
0x9c8c  castclass [System.Windows.Forms]System.Windows.Forms.RadioButton
0x9c91  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.RadioButton::get_Checked()
0x9c96  brfalse  loc_9D26
0x9c9b  ldarg.0
0x9c9c  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9ca1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9ca6  ldarg.0
0x9ca7  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MaintenancePage::addRemoveRadioButton
0x9cac  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_Visible()
0x9cb1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9cb6  ldarg.0
0x9cb7  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9cbc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9cc1  ldarg.0
0x9cc2  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MaintenancePage::addRemoveRadioButton
0x9cc7  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_Visible()
0x9ccc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9cd1  ldarg.0
0x9cd2  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9cd7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9cdc  ldc.i4.0
0x9cdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9ce2  ldarg.0
0x9ce3  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9ce8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9ced  ldc.i4.0
0x9cee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9cf3  ldarg.0
0x9cf4  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9cf9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9cfe  ldstr    aNextbuttontext// "NextButtonText"
0x9d03  ldc.i4.1
0x9d04  newarr   [mscorlib]System.Object
0x9d09  dup
0x9d0a  ldc.i4.0
0x9d0b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x9d10  stelem.ref
0x9d11  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x9d16  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x9d1b  ldarg.0
0x9d1c  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9d21  callvirt instance void Microsoft.Crm.Setup.Common.UI.Wizard::ArrangeNavigationButtons()
0x9d26  ret
```
