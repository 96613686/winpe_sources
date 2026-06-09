# Microsoft.Crm.Setup.Common.UI.Wizard::NextButton_Click

- ea: `0x103b0`
- end: `0x103f8`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::NextButton_Click`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0xfbe0`
- `0xfca0`
- `0x103b0`
- `0x10530`
- `0x105c0`
- `0x11080`
- `0x11180`
- `0x111a0`

## pseudocode

```c

```

## disassembly

```asm
0x103b0  ldarg.0
0x103b1  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x103b6  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x103bb  brtrue.s loc_103BE
0x103bd  ret
0x103be  ldarg.0
0x103bf  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x103c4  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x103c9  pop
0x103ca  newobj   instance void Microsoft.Crm.Setup.Common.UI.NavigationEventArgs::.ctor()
0x103cf  stloc.0
0x103d0  ldarg.0
0x103d1  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x103d6  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_CurrentPage()
0x103db  ldarg.1
0x103dc  ldloc.0
0x103dd  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPage::RaiseNextClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x103e2  ldloc.0
0x103e3  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0x103e8  brfalse.s loc_103EB
0x103ea  ret
0x103eb  ldarg.0
0x103ec  ldloc.0
0x103ed  callvirt instance class [mscorlib]System.Type Microsoft.Crm.Setup.Common.UI.NavigationEventArgs::get_PageType()
0x103f2  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::NavigateForward(class [mscorlib]System.Type nextPageType)
0x103f7  ret
```
