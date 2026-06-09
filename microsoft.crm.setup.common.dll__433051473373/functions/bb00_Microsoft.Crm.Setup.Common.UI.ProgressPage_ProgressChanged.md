# Microsoft.Crm.Setup.Common.UI.ProgressPage::ProgressChanged

- ea: `0xbb00`
- end: `0xbb9f`
- name: `Microsoft.Crm.Setup.Common.UI.ProgressPage::ProgressChanged`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb830`
- `0xbb00`
- `0xfd20`
- `0x10520`
- `0x10ff0`
- `0x11110`

## pseudocode

```c

```

## disassembly

```asm
0xbb00  ldarg.1
0xbb01  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::get_Done()
0xbb06  brfalse.s loc_BB67
0xbb08  ldarg.2
0xbb09  ldsfld   string [mscorlib]System.String::Empty
0xbb0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xbb13  ldarg.3
0xbb14  ldarg.3
0xbb15  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ProgressBar::get_Maximum()
0xbb1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::set_Value(int32)
0xbb1f  ldarg.3
0xbb20  ldarg.0
0xbb21  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar Microsoft.Crm.Setup.Common.UI.ProgressPage::overallProgressBar
0xbb26  bne.un.s loc_BB66
0xbb28  ldarg.0
0xbb29  call     instance bool Microsoft.Crm.Setup.Common.UI.ProgressPage::get_WorkerThreadIsComplete()
0xbb2e  brfalse.s loc_BB66
0xbb30  ldarg.0
0xbb31  ldflda   int32 Microsoft.Crm.Setup.Common.UI.ProgressPage::_completionNotificationReceived
0xbb36  ldarg.0
0xbb37  ldfld    int32 Microsoft.Crm.Setup.Common.UI.ProgressPage::_completionNotificationReceived
0xbb3c  ldc.i4.1
0xbb3d  add
0xbb3e  ldc.i4.0
0xbb3f  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xbb44  brtrue.s loc_BB66
0xbb46  ldarg.0
0xbb47  call     instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::get_IsLastPage()
0xbb4c  brfalse.s loc_BB5B
0xbb4e  ldarg.0
0xbb4f  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbb54  ldc.i4.0
0xbb55  callvirt instance void Microsoft.Crm.Setup.Common.UI.Wizard::Close(bool requiresClosingConfirmation)
0xbb5a  ret
0xbb5b  ldarg.0
0xbb5c  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbb61  callvirt instance void Microsoft.Crm.Setup.Common.UI.Wizard::NavigateForward()
0xbb66  ret
0xbb67  ldarg.1
0xbb68  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::get_Text()
0xbb6d  brfalse.s loc_BB7B
0xbb6f  ldarg.2
0xbb70  ldarg.1
0xbb71  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::get_Text()
0xbb76  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xbb7b  ldarg.1
0xbb7c  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::get_Value()
0xbb81  ldc.i4.0
0xbb82  blt.s    loc_BB9E
0xbb84  ldarg.1
0xbb85  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::get_Value()
0xbb8a  ldarg.3
0xbb8b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ProgressBar::get_Maximum()
0xbb90  bgt.s    loc_BB9E
0xbb92  ldarg.3
0xbb93  ldarg.1
0xbb94  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::get_Value()
0xbb99  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::set_Value(int32)
0xbb9e  ret
```
