# Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_BackClicked

- ea: `0x5160`
- end: `0x51f7`
- name: `Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_BackClicked`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4ad0`
- `0x4ae0`
- `0x5160`
- `0x5200`
- `0xfbc0`
- `0x10ff0`

## string_xrefs

- `0x5192`: `Aborting Validator thread`
- `0x51a8`: `Aborting Validator thread`
- `0x51b5`: `ThreadStateException exception thrown while aborting the validator thread {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5160  ldstr    aBackspaceClick// "Backspace clicked from Diagnostics Page"
0x5165  ldc.i4.0
0x5166  newarr   [mscorlib]System.Object
0x516b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x5170  ldarg.0
0x5171  ldfld    class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwTool
0x5176  brfalse.s loc_518A
0x5178  ldarg.0
0x5179  ldfld    class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwTool
0x517e  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool::Close()
0x5183  ldarg.0
0x5184  ldnull
0x5185  stfld    class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwTool
0x518a  ldarg.0
0x518b  call     instance class [mscorlib]System.Threading.Thread Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ValidatorThread()
0x5190  brfalse.s loc_51D8
0x5192  ldstr    aAbortingValida// "Aborting Validator thread"
0x5197  ldc.i4.0
0x5198  newarr   [mscorlib]System.Object
0x519d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x51a2  ldarg.0
0x51a3  call     instance class [mscorlib]System.Threading.Thread Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ValidatorThread()
0x51a8  ldstr    aAbortingValida// "Aborting Validator thread"
0x51ad  callvirt instance void [mscorlib]System.Threading.Thread::Abort(object)
0x51b2  leave.s  loc_51D8
0x51b4  stloc.0
0x51b5  ldstr    aThreadstateexc// "ThreadStateException exception thrown w"...
0x51ba  ldc.i4.1
0x51bb  newarr   [mscorlib]System.Object
0x51c0  dup
0x51c1  ldc.i4.0
0x51c2  ldloc.0
0x51c3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x51c8  stelem.ref
0x51c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x51ce  leave.s  loc_51D8
0x51d0  ldarg.0
0x51d1  ldnull
0x51d2  call     instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::set_ValidatorThread(class [mscorlib]System.Threading.Thread value)
0x51d7  endfinally
0x51d8  ldarg.0
0x51d9  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x51de  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x51e3  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x51e8  ldc.i4.1
0x51e9  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_RunEdwChecks(bool)
0x51ee  ldarg.0
0x51ef  ldarg.1
0x51f0  ldarg.2
0x51f1  callvirt instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::OnBackClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x51f6  ret
```
