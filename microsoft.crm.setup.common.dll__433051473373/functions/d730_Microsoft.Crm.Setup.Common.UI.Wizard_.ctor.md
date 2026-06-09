# Microsoft.Crm.Setup.Common.UI.Wizard::.ctor

- ea: `0xd730`
- end: `0xd797`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::.ctor`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc240`
- `0xd7a0`

## callees

- `0xd730`
- `0xd830`
- `0xfbb0`
- `0xfbe0`
- `0xfe20`
- `0x10590`
- `0x105b0`
- `0x10680`
- `0x108a0`
- `0x10a50`

## pseudocode

```c

```

## disassembly

```asm
0xd730  ldarg.0
0xd731  ldc.i4.1
0xd732  stfld    bool Microsoft.Crm.Setup.Common.UI.Wizard::_requiresClosingConfirmation
0xd737  ldarg.0
0xd738  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::.ctor()
0xd73d  ldarg.0
0xd73e  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::InitializeComponent()
0xd743  ldarg.0
0xd744  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::ResizeNavigationButtons()
0xd749  ldarg.0
0xd74a  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xd74f  stfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::data
0xd754  ldarg.0
0xd755  ldc.i4.1
0xd756  call     instance void Microsoft.Crm.Setup.Common.UI.Wizard::set_WizardClose(valuetype WizardCloseType value)
0xd75b  ldarg.0
0xd75c  ldarg.1
0xd75d  brtrue.s loc_D768
0xd75f  newobj   instance void Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::.ctor()
0xd764  stloc.0
0xd765  ldloc.0
0xd766  br.s     loc_D769
0xd768  ldarg.1
0xd769  stfld    class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::model
0xd76e  ldarg.0
0xd76f  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0xd774  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.IWizardPageModel::get_Pages()
0xd779  ldarg.0
0xd77a  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPageCollection::set_Wizard(class Microsoft.Crm.Setup.Common.UI.Wizard value)
0xd77f  ldarg.0
0xd780  call     instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0xd785  ldarg.0
0xd786  ldftn    instance void Microsoft.Crm.Setup.Common.UI.Wizard::WizardPageModel_PageChanged(object sender, class Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventArgs e)
0xd78c  newobj   instance void Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventHandler::.ctor(object object, native int method)
0xd791  callvirt instance void Microsoft.Crm.Setup.Common.UI.IWizardPageModel::add_PageChanged(class Microsoft.Crm.Setup.Common.UI.WizardPageChangedEventHandler value)
0xd796  ret
```
