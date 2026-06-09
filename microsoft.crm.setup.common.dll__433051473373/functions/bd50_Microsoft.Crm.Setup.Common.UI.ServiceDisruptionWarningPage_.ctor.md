# Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::.ctor

- ea: `0xbd50`
- end: `0xbd8b`
- name: `Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::.ctor`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xbda0`
- `0xc060`
- `0xc530`
- `0x10ac0`
- `0x10f20`

## string_xrefs

- `0xbd67`: `setup process instance must be provided to the ServicesToStopPage constructor.`

## pseudocode

```c

```

## disassembly

```asm
0xbd50  ldarg.0
0xbd51  call     instance void Microsoft.Crm.Setup.Common.UI.SetupWizardPage::.ctor()
0xbd56  ldarg.0
0xbd57  call     instance void Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::InitializeComponent()
0xbd5c  ldarg.0
0xbd5d  ldc.i4.1
0xbd5e  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::set_HideSpacerPanel(bool value)
0xbd63  ldarg.1
0xbd64  ldnull
0xbd65  cgt.un
0xbd67  ldstr    aSetupProcessIn// "setup process instance must be provided"...
0xbd6c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xbd71  ldarg.0
0xbd72  ldarg.1
0xbd73  call     instance void Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::set_AssociatedSetup(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase value)
0xbd78  ldarg.0
0xbd79  ldarg.0
0xbd7a  ldftn    instance void Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::ServicesToStopPage_PageActivated(object sender, class [mscorlib]System.EventArgs e)
0xbd80  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xbd85  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_PageActivated(class [mscorlib]System.EventHandler value)
0xbd8a  ret
```
