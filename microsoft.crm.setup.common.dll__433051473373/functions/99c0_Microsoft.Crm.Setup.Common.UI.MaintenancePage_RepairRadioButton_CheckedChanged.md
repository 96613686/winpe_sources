# Microsoft.Crm.Setup.Common.UI.MaintenancePage::RepairRadioButton_CheckedChanged

- ea: `0x99c0`
- end: `0x9ad4`
- name: `Microsoft.Crm.Setup.Common.UI.MaintenancePage::RepairRadioButton_CheckedChanged`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x8740`
- `0x99c0`
- `0xfbc0`
- `0xfca0`
- `0xfcc0`
- `0x10250`
- `0x10ff0`

## string_xrefs

- `0x9a3d`: `RepairButtonText`

## pseudocode

```c

```

## disassembly

```asm
0x99c0  ldarg.0
0x99c1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x99c6  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x99cb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x99d0  ldc.i4.3
0x99d1  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_InstallType(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType)
0x99d6  ldarg.1
0x99d7  castclass [System.Windows.Forms]System.Windows.Forms.RadioButton
0x99dc  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.RadioButton::get_Checked()
0x99e1  brfalse  loc_9AD3
0x99e6  ldarg.0
0x99e7  callvirt instance bool Microsoft.Crm.Setup.Common.UI.MaintenancePage::get_UseFinishButtonForRepair()
0x99ec  brfalse.s loc_9A5C
0x99ee  ldarg.0
0x99ef  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x99f4  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x99f9  ldc.i4.0
0x99fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x99ff  ldarg.0
0x9a00  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a05  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9a0a  ldc.i4.0
0x9a0b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9a10  ldarg.0
0x9a11  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a16  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9a1b  ldc.i4.1
0x9a1c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9a21  ldarg.0
0x9a22  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a27  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9a2c  ldc.i4.1
0x9a2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9a32  ldarg.0
0x9a33  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a38  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9a3d  ldstr    aRepairbuttonte// "RepairButtonText"
0x9a42  ldc.i4.1
0x9a43  newarr   [mscorlib]System.Object
0x9a48  dup
0x9a49  ldc.i4.0
0x9a4a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x9a4f  stelem.ref
0x9a50  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x9a55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x9a5a  br.s     loc_9AC8
0x9a5c  ldarg.0
0x9a5d  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a62  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9a67  ldc.i4.1
0x9a68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9a6d  ldarg.0
0x9a6e  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a73  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9a78  ldc.i4.1
0x9a79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9a7e  ldarg.0
0x9a7f  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a84  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9a89  ldc.i4.0
0x9a8a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x9a8f  ldarg.0
0x9a90  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9a95  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x9a9a  ldc.i4.0
0x9a9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x9aa0  ldarg.0
0x9aa1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9aa6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x9aab  ldstr    aNextbuttontext// "NextButtonText"
0x9ab0  ldc.i4.1
0x9ab1  newarr   [mscorlib]System.Object
0x9ab6  dup
0x9ab7  ldc.i4.0
0x9ab8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x9abd  stelem.ref
0x9abe  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x9ac3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x9ac8  ldarg.0
0x9ac9  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x9ace  callvirt instance void Microsoft.Crm.Setup.Common.UI.Wizard::ArrangeNavigationButtons()
0x9ad3  ret
```
