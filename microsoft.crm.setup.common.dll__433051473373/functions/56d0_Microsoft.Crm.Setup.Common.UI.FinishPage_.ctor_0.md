# Microsoft.Crm.Setup.Common.UI.FinishPage::.ctor_0

- ea: `0x56d0`
- end: `0x570f`
- name: `Microsoft.Crm.Setup.Common.UI.FinishPage::.ctor_0`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x56b0`

## callees

- `0x57c0`
- `0xc530`
- `0x10f20`
- `0x11210`

## pseudocode

```c

```

## disassembly

```asm
0x56d0  ldarg.0
0x56d1  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Diagnostics.ProcessStartInfo>::.ctor()
0x56d6  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Diagnostics.ProcessStartInfo> Microsoft.Crm.Setup.Common.UI.FinishPage::_linkApplications
0x56db  ldarg.0
0x56dc  call     instance void Microsoft.Crm.Setup.Common.UI.SetupWizardPage::.ctor()
0x56e1  ldarg.0
0x56e2  ldarg.1
0x56e3  stfld    string Microsoft.Crm.Setup.Common.UI.FinishPage::_applicationTitle
0x56e8  ldarg.0
0x56e9  ldarg.2
0x56ea  stfld    string Microsoft.Crm.Setup.Common.UI.FinishPage::_pageTitle
0x56ef  ldarg.0
0x56f0  ldarg.3
0x56f1  stfld    string Microsoft.Crm.Setup.Common.UI.FinishPage::_details
0x56f6  ldarg.0
0x56f7  call     instance void Microsoft.Crm.Setup.Common.UI.FinishPage::InitializeComponent()
0x56fc  ldarg.0
0x56fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelLogFile
0x5702  call     void Microsoft.Crm.Setup.Common.Utility.LinkLabelUtility::SetLinkArea(class [System.Windows.Forms]System.Windows.Forms.LinkLabel linkLabelControl)
0x5707  ldarg.0
0x5708  ldc.i4.1
0x5709  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::set_HideSpacerPanel(bool value)
0x570e  ret
```
