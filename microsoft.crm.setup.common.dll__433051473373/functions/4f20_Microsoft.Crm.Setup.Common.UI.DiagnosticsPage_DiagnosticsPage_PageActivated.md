# Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_PageActivated

- ea: `0x4f20`
- end: `0x4fe1`
- name: `Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_PageActivated`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4ac0`
- `0x4ad0`
- `0x4ae0`
- `0x4ee0`
- `0x4f20`
- `0xfbc0`
- `0xfca0`
- `0xfcb0`
- `0x10ff0`
- `0x110f0`

## pseudocode

```c

```

## disassembly

```asm
0x4f20  ldarg.0
0x4f21  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x4f26  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x4f2b  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x4f30  stloc.0
0x4f31  ldarg.0
0x4f32  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x4f37  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_RunOneButton()
0x4f3c  ldc.i4.0
0x4f3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x4f42  ldarg.0
0x4f43  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x4f48  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_RunAllButton()
0x4f4d  ldc.i4.0
0x4f4e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x4f53  ldarg.0
0x4f54  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x4f59  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_SaveButton()
0x4f5e  ldc.i4.0
0x4f5f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x4f64  ldarg.0
0x4f65  ldloc.0
0x4f66  callvirt instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::ConfigureHelp(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo installInfo)
0x4f6b  ldloc.0
0x4f6c  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_RunEdwChecks()
0x4f71  brfalse.s loc_4FC7
0x4f73  ldarg.0
0x4f74  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x4f79  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x4f7e  ldc.i4.0
0x4f7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x4f84  ldarg.0
0x4f85  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x4f8a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x4f8f  ldc.i4.0
0x4f90  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x4f95  ldarg.0
0x4f96  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x4f9b  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x4fa0  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::LogData(class [mscorlib]System.Collections.IDictionary)
0x4fa5  ldarg.0
0x4fa6  ldarg.0
0x4fa7  ldftn    instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::StartDiagnostics()
0x4fad  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x4fb2  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x4fb7  call     instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::set_ValidatorThread(class [mscorlib]System.Threading.Thread value)
0x4fbc  ldarg.0
0x4fbd  call     instance class [mscorlib]System.Threading.Thread Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ValidatorThread()
0x4fc2  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x4fc7  ldarg.0
0x4fc8  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x4fcd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x4fd2  ldarg.0
0x4fd3  call     instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::get_IsFirstPage()
0x4fd8  ldc.i4.0
0x4fd9  ceq
0x4fdb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x4fe0  ret
```
