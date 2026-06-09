# Microsoft.Crm.Setup.Common.UI.Wizard::BackButton_Click

- ea: `0x10310`
- end: `0x103ac`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::BackButton_Click`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0xfbe0`
- `0xfbf0`
- `0xfcb0`
- `0xfd00`
- `0x10310`
- `0x105c0`
- `0x105e0`
- `0x10600`
- `0x108d0`
- `0x11060`
- `0x11180`
- `0x111a0`

## pseudocode

```c

```

## disassembly

```asm
0x10310  ldarg.0
0x10311  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10316  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x1031b  brtrue.s loc_1031E
0x1031d  ret
0x1031e  nop
0x1031f  ldarg.0
0x10320  ldc.i4.1
0x10321  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_NavigatingBackward(bool value)
0x10326  ldarg.0
0x10327  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x1032c  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x10331  pop
0x10332  newobj   instance void Microsoft.Crm.Setup.Common.UI.NavigationEventArgs::.ctor()
0x10337  stloc.0
0x10338  ldarg.0
0x10339  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x1033e  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x10343  ldarg.1
0x10344  ldloc.0
0x10345  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPage::RaiseBackClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x1034a  ldloc.0
0x1034b  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0x10350  brfalse.s loc_10354
0x10352  leave.s  loc_103AB
0x10354  ldloc.0
0x10355  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Setup.Common.UI.NavigationEventArgs::get_PageType()
0x1035a  ldnull
0x1035b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10360  brfalse.s loc_10380
0x10362  ldarg.0
0x10363  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10368  ldarg.0
0x10369  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.Wizard::get_Pages()
0x1036e  ldloc.0
0x1036f  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Setup.Common.UI.NavigationEventArgs::get_PageType()
0x10374  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageCollection::get_Item(class [mscorlib]System.Type type)
0x10379  callvirt instance void Microsoft.Crm.Setup.Common.UI.IWizardPageModel::ActivatePage(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x1037e  leave.s  loc_103AB
0x10380  ldarg.0
0x10381  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10386  ldarg.0
0x10387  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x1038c  ldarg.0
0x1038d  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10392  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x10397  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::GetPrevPage(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x1039c  callvirt instance void Microsoft.Crm.Setup.Common.UI.IWizardPageModel::ActivatePage(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x103a1  leave.s  loc_103AB
0x103a3  ldarg.0
0x103a4  ldc.i4.0
0x103a5  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_NavigatingBackward(bool value)
0x103aa  endfinally
0x103ab  ret
```
