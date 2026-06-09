# Microsoft.Crm.Setup.Common.UI.Wizard::ArrangeNavigationButtons

- ea: `0x10250`
- end: `0x1030a`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::ArrangeNavigationButtons`
- size: `186`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x99c0`
- `0x9ae0`
- `0x9c70`
- `0x10050`

## callees

- `0xfca0`
- `0xfcb0`
- `0xfcc0`
- `0xfcd0`
- `0x10250`

## pseudocode

```c

```

## disassembly

```asm
0x10250  ldarg.0
0x10251  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0x10256  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Right()
0x1025b  ldarg.0
0x1025c  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0x10261  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x10266  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::get_Right()
0x1026b  sub
0x1026c  stloc.0
0x1026d  ldarg.0
0x1026e  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x10273  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_Visible()
0x10278  brfalse.s loc_10294
0x1027a  ldloc.0
0x1027b  ldarg.0
0x1027c  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x10281  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0x10286  sub
0x10287  stloc.0
0x10288  ldarg.0
0x10289  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x1028e  ldloc.0
0x1028f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Left(int32)
0x10294  ldarg.0
0x10295  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x1029a  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_Visible()
0x1029f  brfalse.s loc_102BB
0x102a1  ldloc.0
0x102a2  ldarg.0
0x102a3  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x102a8  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0x102ad  sub
0x102ae  stloc.0
0x102af  ldarg.0
0x102b0  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0x102b5  ldloc.0
0x102b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Left(int32)
0x102bb  ldarg.0
0x102bc  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x102c1  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_Visible()
0x102c6  brfalse.s loc_102E2
0x102c8  ldloc.0
0x102c9  ldarg.0
0x102ca  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x102cf  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0x102d4  sub
0x102d5  stloc.0
0x102d6  ldarg.0
0x102d7  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x102dc  ldloc.0
0x102dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Left(int32)
0x102e2  ldarg.0
0x102e3  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x102e8  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_Visible()
0x102ed  brfalse.s loc_10309
0x102ef  ldloc.0
0x102f0  ldarg.0
0x102f1  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x102f6  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0x102fb  sub
0x102fc  stloc.0
0x102fd  ldarg.0
0x102fe  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x10303  ldloc.0
0x10304  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Left(int32)
0x10309  ret
```
