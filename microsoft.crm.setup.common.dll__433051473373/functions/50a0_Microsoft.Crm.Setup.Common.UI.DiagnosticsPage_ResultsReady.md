# Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::ResultsReady

- ea: `0x50a0`
- end: `0x5135`
- name: `Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::ResultsReady`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x740`
- `0x4b00`
- `0x4b40`
- `0x50a0`
- `0xfca0`
- `0xfcb0`
- `0x10ff0`
- `0x110f0`

## pseudocode

```c

```

## disassembly

```asm
0x50a0  ldarg.0
0x50a1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x50a6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x50ab  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_InvokeRequired()
0x50b0  brfalse.s loc_50DB
0x50b2  ldarg.0
0x50b3  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x50b8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x50bd  ldarg.0
0x50be  dup
0x50bf  ldvirtftn instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::ResultsReady(class [mscorlib]System.Exception exception)
0x50c5  newobj   instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel/ResultsReadyCallback::.ctor(object, native int)
0x50ca  ldc.i4.1
0x50cb  newarr   [mscorlib]System.Object
0x50d0  dup
0x50d1  ldc.i4.0
0x50d2  ldarg.1
0x50d3  stelem.ref
0x50d4  callvirt instance object [System.Windows.Forms]System.Windows.Forms.Control::Invoke(class [mscorlib]System.Delegate, object[])
0x50d9  pop
0x50da  ret
0x50db  ldarg.0
0x50dc  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x50e1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x50e6  ldarg.0
0x50e7  call     instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::get_IsFirstPage()
0x50ec  ldc.i4.0
0x50ed  ceq
0x50ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x50f4  ldarg.0
0x50f5  ldarg.1
0x50f6  call     instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::set_DiagnosticsException(class [mscorlib]System.Exception value)
0x50fb  ldarg.1
0x50fc  brfalse.s loc_5119
0x50fe  ldarg.1
0x50ff  ldc.i4.s 0x10
0x5101  call     valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InputResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageReport::RequestInput(object, valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageType)
0x5106  pop
0x5107  ldarg.0
0x5108  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x510d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x5112  ldc.i4.0
0x5113  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x5118  ret
0x5119  ldarg.0
0x511a  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x511f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x5124  ldarg.0
0x5125  call     instance class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_EdwTool()
0x512a  callvirt instance bool Microsoft.Crm.Setup.Common.CommonEdwTool::get_AllowRun()
0x512f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x5134  ret
```
