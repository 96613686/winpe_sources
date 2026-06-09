# Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::.ctor

- ea: `0x4a10`
- end: `0x4ab7`
- name: `Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::.ctor`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4ac0`
- `0x4ae0`
- `0x4b70`
- `0xc530`
- `0x10ac0`
- `0x10b80`
- `0x10be0`
- `0x111c0`

## pseudocode

```c

```

## disassembly

```asm
0x4a10  ldarg.0
0x4a11  call     instance void Microsoft.Crm.Setup.Common.UI.SetupWizardPage::.ctor()
0x4a16  ldarg.0
0x4a17  ldarg.1
0x4a18  stfld    class Microsoft.Crm.Setup.Common.IDiagnosticToolProvider Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwProvider
0x4a1d  ldarg.0
0x4a1e  call     instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::InitializeComponent()
0x4a23  ldarg.0
0x4a24  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4a29  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_RunOneButton()
0x4a2e  ldc.i4.0
0x4a2f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x4a34  ldarg.0
0x4a35  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4a3a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_RunAllButton()
0x4a3f  ldc.i4.0
0x4a40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x4a45  ldarg.0
0x4a46  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4a4b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_SaveButton()
0x4a50  ldc.i4.0
0x4a51  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x4a56  ldarg.0
0x4a57  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4a5c  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::ResizeDetailAndHelpButtons()
0x4a61  ldarg.0
0x4a62  ldnull
0x4a63  call     instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::set_ValidatorThread(class [mscorlib]System.Threading.Thread value)
0x4a68  ldarg.0
0x4a69  ldarg.0
0x4a6a  ldftn    instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_PageActivated(object sender, class [mscorlib]System.EventArgs e)
0x4a70  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4a75  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_PageActivated(class [mscorlib]System.EventHandler value)
0x4a7a  ldarg.0
0x4a7b  ldarg.0
0x4a7c  ldftn    instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_BackClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x4a82  newobj   instance void Microsoft.Crm.Setup.Common.UI.NavigationEventHandler::.ctor(object object, native int method)
0x4a87  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_BackClicked(class Microsoft.Crm.Setup.Common.UI.NavigationEventHandler value)
0x4a8c  ldarg.0
0x4a8d  ldarg.0
0x4a8e  ldftn    instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_NextClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x4a94  newobj   instance void Microsoft.Crm.Setup.Common.UI.NavigationEventHandler::.ctor(object object, native int method)
0x4a99  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_NextClicked(class Microsoft.Crm.Setup.Common.UI.NavigationEventHandler value)
0x4a9e  ldarg.0
0x4a9f  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x4aa4  ldarg.0
0x4aa5  dup
0x4aa6  ldvirtftn instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::ResultsReady(class [mscorlib]System.Exception exception)
0x4aac  newobj   instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel/ResultsReadyCallback::.ctor(object, native int)
0x4ab1  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_ResultsReady(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel/ResultsReadyCallback)
0x4ab6  ret
```
