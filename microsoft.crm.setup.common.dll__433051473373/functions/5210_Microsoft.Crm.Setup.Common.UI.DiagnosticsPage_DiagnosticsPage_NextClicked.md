# Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_NextClicked

- ea: `0x5210`
- end: `0x526f`
- name: `Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::DiagnosticsPage_NextClicked`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4b30`
- `0x5210`
- `0x5270`
- `0xfbc0`
- `0x10ff0`

## pseudocode

```c

```

## disassembly

```asm
0x5210  ldc.i4.1
0x5211  stloc.0
0x5212  ldarg.0
0x5213  ldfld    class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwTool
0x5218  brfalse.s loc_523D
0x521a  ldarg.0
0x521b  ldfld    class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwTool
0x5220  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWToolResults [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool::get_Results()
0x5225  callvirt instance bool [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWToolResults::get_Success()
0x522a  stloc.0
0x522b  ldarg.0
0x522c  ldfld    class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwTool
0x5231  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool::Close()
0x5236  ldarg.0
0x5237  ldnull
0x5238  stfld    class Microsoft.Crm.Setup.Common.CommonEdwTool Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::_edwTool
0x523d  ldarg.0
0x523e  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x5243  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x5248  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x524d  ldc.i4.0
0x524e  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_RunEdwChecks(bool)
0x5253  ldloc.0
0x5254  brfalse.s loc_5267
0x5256  ldarg.0
0x5257  call     instance class [mscorlib]System.Exception Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::get_DiagnosticsException()
0x525c  brtrue.s loc_5267
0x525e  ldarg.0
0x525f  ldarg.1
0x5260  ldarg.2
0x5261  callvirt instance void Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::OnNextClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x5266  ret
0x5267  ldarg.2
0x5268  ldc.i4.1
0x5269  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x526e  ret
```
