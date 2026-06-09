# Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::StartDiagnostics

- ea: `0x4ff0`
- end: `0x5080`
- name: `Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::StartDiagnostics`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4ac0`
- `0x4af0`
- `0x4b00`
- `0x4ff0`
- `0x5080`
- `0x5090`
- `0xfbc0`
- `0x10ff0`

## pseudocode

```c

```

## disassembly

```asm
0x4ff0  ldarg.0
0x4ff1  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x4ff6  ldarg.0
0x4ff7  call     instance class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_EdwTool()
0x4ffc  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_Sniffer(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool)
0x5001  ldarg.0
0x5002  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x5007  ldnull
0x5008  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_SnifferToRun(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.BaseGroup)
0x500d  ldarg.0
0x500e  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x5013  ldc.i4.0
0x5014  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_RunOne(bool)
0x5019  ldarg.0
0x501a  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x501f  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_Sniffer()
0x5024  ldarg.0
0x5025  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x502a  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x502f  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool::set_Context(class [mscorlib]System.Collections.IDictionary)
0x5034  ldarg.0
0x5035  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x503a  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_Sniffer()
0x503f  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.RunModes [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool::get_Modes()
0x5044  ldarg.0
0x5045  callvirt instance string Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_EdwModes()
0x504a  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.StringPropertyBag::set_StringValue(string)
0x504f  ldarg.0
0x5050  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x5055  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_Sniffer()
0x505a  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWToolResults [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool::get_Results()
0x505f  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWToolResults::Clear()
0x5064  ldarg.0
0x5065  callvirt instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::BeforeStartDiagnostics()
0x506a  ldarg.0
0x506b  call     instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_ResultsPanel()
0x5070  ldarg.0
0x5071  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::SetupResults(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ISnifferPage)
0x5076  leave.s  loc_507F
0x5078  ldarg.0
0x5079  callvirt instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::AfterStartDiagnostics()
0x507e  endfinally
0x507f  ret
```
