# Microsoft.Crm.Setup.Common.UI.Wizard::NavigateForward_0

- ea: `0x10530`
- end: `0x10573`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::NavigateForward_0`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x103b0`
- `0x10520`

## callees

- `0xfbe0`
- `0xfbf0`
- `0x10530`
- `0x105c0`
- `0x105f0`
- `0x10600`
- `0x108d0`

## pseudocode

```c

```

## disassembly

```asm
0x10530  ldarg.1
0x10531  ldnull
0x10532  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10537  brfalse.s loc_10551
0x10539  ldarg.0
0x1053a  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x1053f  ldarg.0
0x10540  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.Wizard::get_Pages()
0x10545  ldarg.1
0x10546  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageCollection::get_Item(class [mscorlib]System.Type type)
0x1054b  callvirt instance void Microsoft.Crm.Setup.Common.UI.IWizardPageModel::ActivatePage(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x10550  ret
0x10551  ldarg.0
0x10552  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10557  ldarg.0
0x10558  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x1055d  ldarg.0
0x1055e  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x10563  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x10568  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::GetNextPage(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x1056d  callvirt instance void Microsoft.Crm.Setup.Common.UI.IWizardPageModel::ActivatePage(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x10572  ret
```
