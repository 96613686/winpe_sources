# Microsoft.Crm.Setup.Common.UI.ProgressPage::InitializeComponent

- ea: `0xb8f0`
- end: `0xba83`
- name: `Microsoft.Crm.Setup.Common.UI.ProgressPage::InitializeComponent`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb780`

## callees

- `0x10ac0`
- `0x10ca0`

## string_xrefs

- `0xb99e`: `componentProgressBar`
- `0xb9ba`: `componentProgressBar`
- `0xb9d7`: `componentProgressLabel`
- `0xb9f3`: `componentProgressLabel`

## pseudocode

```c

```

## disassembly

```asm
0xb8f0  ldtoken  Microsoft.Crm.Setup.Common.ProgressPage
0xb8f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb8fa  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(class [mscorlib]System.Type)
0xb8ff  ldarg.0
0xb900  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xb905  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressLabel
0xb90a  ldarg.0
0xb90b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::.ctor()
0xb910  stfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xb915  ldarg.0
0xb916  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::.ctor()
0xb91b  stfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressBar
0xb920  ldarg.0
0xb921  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xb926  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressLabel
0xb92b  ldarg.0
0xb92c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xb931  dup
0xb932  ldarg.0
0xb933  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressLabel
0xb938  ldstr    aOverallprogres// "overallProgressLabel"
0xb93d  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xb942  ldarg.0
0xb943  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressLabel
0xb948  ldc.i4.3
0xb949  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xb94e  ldarg.0
0xb94f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressLabel
0xb954  ldstr    aOverallprogres// "overallProgressLabel"
0xb959  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb95e  dup
0xb95f  ldarg.0
0xb960  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xb965  ldstr    aOverallprogres_0// "overallProgressBar"
0xb96a  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xb96f  ldarg.0
0xb970  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xb975  ldc.i4.3
0xb976  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xb97b  ldarg.0
0xb97c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xb981  ldstr    aOverallprogres_0// "overallProgressBar"
0xb986  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb98b  ldarg.0
0xb98c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xb991  ldc.i4.1
0xb992  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::set_Step(int32)
0xb997  dup
0xb998  ldarg.0
0xb999  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressBar
0xb99e  ldstr    aComponentprogr// "componentProgressBar"
0xb9a3  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xb9a8  ldarg.0
0xb9a9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressBar
0xb9ae  ldc.i4.3
0xb9af  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xb9b4  ldarg.0
0xb9b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressBar
0xb9ba  ldstr    aComponentprogr// "componentProgressBar"
0xb9bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb9c4  ldarg.0
0xb9c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressBar
0xb9ca  ldc.i4.1
0xb9cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::set_Step(int32)
0xb9d0  dup
0xb9d1  ldarg.0
0xb9d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressLabel
0xb9d7  ldstr    aComponentprogr_0// "componentProgressLabel"
0xb9dc  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xb9e1  ldarg.0
0xb9e2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressLabel
0xb9e7  ldc.i4.3
0xb9e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xb9ed  ldarg.0
0xb9ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressLabel
0xb9f3  ldstr    aComponentprogr_0// "componentProgressLabel"
0xb9f8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb9fd  ldarg.0
0xb9fe  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xba03  ldarg.0
0xba04  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressLabel
0xba09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xba0e  ldarg.0
0xba0f  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xba14  ldarg.0
0xba15  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xba1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xba1f  ldarg.0
0xba20  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xba25  ldarg.0
0xba26  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressBar
0xba2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xba30  ldarg.0
0xba31  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xba36  ldarg.0
0xba37  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ProgressPage::componentProgressLabel
0xba3c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xba41  ldarg.0
0xba42  ldstr    aProgresspage// "ProgressPage"
0xba47  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xba4c  ldarg.0
0xba4d  ldstr    aThis// "$this"
0xba52  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xba57  ldarg.0
0xba58  ldarg.0
0xba59  ldftn    instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::ProgressPage_CancelClicked(object sender, class [System]System.ComponentModel.CancelEventArgs e)
0xba5f  newobj   instance void [System]System.ComponentModel.CancelEventHandler::.ctor(object, native int)
0xba64  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_CancelClicked(class [System]System.ComponentModel.CancelEventHandler value)
0xba69  ldarg.0
0xba6a  ldarg.0
0xba6b  ldftn    instance void Microsoft.Crm.Setup.Common.UI.ProgressPage::ProgressPage_Activated(object sender, class [mscorlib]System.EventArgs e)
0xba71  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xba76  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_PageActivated(class [mscorlib]System.EventHandler value)
0xba7b  ldarg.0
0xba7c  ldc.i4.0
0xba7d  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0xba82  ret
```
