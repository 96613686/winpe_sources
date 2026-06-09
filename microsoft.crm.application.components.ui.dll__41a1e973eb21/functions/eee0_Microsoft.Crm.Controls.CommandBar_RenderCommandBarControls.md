# Microsoft.Crm.Controls.CommandBar::RenderCommandBarControls

- ea: `0xeee0`
- end: `0xef75`
- name: `Microsoft.Crm.Controls.CommandBar::RenderCommandBarControls`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xf280`
- `0xf690`

## callees

- `0xecf0`
- `0xed80`
- `0xeee0`
- `0xefe0`
- `0x126c0`
- `0x126e0`
- `0x12700`
- `0x12710`
- `0x12770`

## pseudocode

```c

```

## disassembly

```asm
0xeee0  ldc.i4.0
0xeee1  stloc.0
0xeee2  ldc.i4.0
0xeee3  stloc.1
0xeee4  ldarg.0
0xeee5  call     instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xeeea  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xeeef  stloc.2
0xeef0  br.s     loc_EF55
0xeef2  ldloc.2
0xeef3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xeef8  castclass Microsoft.Crm.Controls.ICrmCommandBarControl
0xeefd  stloc.3
0xeefe  ldloc.3
0xeeff  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.ICrmCommandBarControl::get_Alignment()
0xef04  ldarg.2
0xef05  beq.s    loc_EF18
0xef07  ldloc.3
0xef08  callvirt instance valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.ICrmCommandBarControl::get_Alignment()
0xef0d  brtrue.s loc_EF55
0xef0f  ldarg.2
0xef10  ldarg.0
0xef11  call     instance valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.CommandBar::get_Alignment()
0xef16  bne.un.s loc_EF55
0xef18  ldloc.3
0xef19  callvirt instance bool Microsoft.Crm.Controls.ICrmCommandBarControl::get_Visible()
0xef1e  brfalse.s loc_EF4B
0xef20  ldloc.3
0xef21  callvirt instance bool Microsoft.Crm.Controls.ICrmCommandBarControl::get_StartGroup()
0xef26  ldloc.0
0xef27  or
0xef28  brfalse.s loc_EF37
0xef2a  ldloc.1
0xef2b  ldc.i4.0
0xef2c  ble.s    loc_EF37
0xef2e  ldc.i4.0
0xef2f  stloc.0
0xef30  ldarg.0
0xef31  ldarg.1
0xef32  callvirt instance void Microsoft.Crm.Controls.CommandBar::RenderSpacer(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xef37  ldloc.3
0xef38  ldarg.2
0xef39  callvirt instance void Microsoft.Crm.Controls.ICrmCommandBarControl::set_Alignment(valuetype Microsoft.Crm.Controls.CommandBarAlignment value)
0xef3e  ldloc.3
0xef3f  ldarg.1
0xef40  callvirt instance void Microsoft.Crm.Controls.ICrmCommandBarControl::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xef45  ldloc.1
0xef46  ldc.i4.1
0xef47  add
0xef48  stloc.1
0xef49  br.s     loc_EF55
0xef4b  ldloc.3
0xef4c  callvirt instance bool Microsoft.Crm.Controls.ICrmCommandBarControl::get_StartGroup()
0xef51  brfalse.s loc_EF55
0xef53  ldc.i4.1
0xef54  stloc.0
0xef55  ldloc.2
0xef56  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xef5b  brtrue.s loc_EEF2
0xef5d  leave.s  loc_EF73
0xef5f  ldloc.2
0xef60  isinst   [mscorlib]System.IDisposable
0xef65  stloc.s  4
0xef67  ldloc.s  4
0xef69  brfalse.s loc_EF72
0xef6b  ldloc.s  4
0xef6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xef72  endfinally
0xef73  ldloc.1
0xef74  ret
```
