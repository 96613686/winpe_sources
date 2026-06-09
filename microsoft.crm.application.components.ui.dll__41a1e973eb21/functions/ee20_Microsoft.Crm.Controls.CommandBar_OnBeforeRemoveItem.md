# Microsoft.Crm.Controls.CommandBar::OnBeforeRemoveItem

- ea: `0xee20`
- end: `0xee72`
- name: `Microsoft.Crm.Controls.CommandBar::OnBeforeRemoveItem`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0xec80`
- `0xed20`
- `0xed30`
- `0xee20`
- `0xfae0`
- `0xfc30`
- `0xfc60`
- `0xfc80`
- `0x126c0`
- `0x126d0`

## pseudocode

```c

```

## disassembly

```asm
0xee20  ldarg.2
0xee21  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Controls.CommandBarControlCollectionEventArgs::get_Control()
0xee26  stloc.0
0xee27  ldloc.0
0xee28  callvirt instance bool Microsoft.Crm.Controls.ICrmCommandBarControl::get_StartGroup()
0xee2d  brfalse.s loc_EE64
0xee2f  ldarg.0
0xee30  call     instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_InternalControls()
0xee35  ldloc.0
0xee36  callvirt instance int32 Microsoft.Crm.Controls.CommandBarControlCollection::IndexOf(class Microsoft.Crm.Controls.ICrmCommandBarControl value)
0xee3b  stloc.1
0xee3c  ldarg.0
0xee3d  callvirt instance int32 Microsoft.Crm.Controls.CommandBar::get_Count()
0xee42  ldloc.1
0xee43  ldc.i4.1
0xee44  add
0xee45  ble.s    loc_EE5D
0xee47  ldarg.0
0xee48  call     instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_InternalControls()
0xee4d  ldloc.1
0xee4e  ldc.i4.1
0xee4f  add
0xee50  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Controls.CommandBarControlCollection::get_Item(int32 index)
0xee55  ldc.i4.1
0xee56  callvirt instance void Microsoft.Crm.Controls.ICrmCommandBarControl::set_StartGroup(bool value)
0xee5b  br.s     loc_EE64
0xee5d  ldarg.0
0xee5e  ldc.i4.1
0xee5f  call     instance void Microsoft.Crm.Controls.CommandBar::set_BeginGroup(bool value)
0xee64  ldarg.0
0xee65  call     instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_InternalControls()
0xee6a  ldloc.0
0xee6b  callvirt instance class Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Controls.CommandBarControlCollection::Remove(class Microsoft.Crm.Controls.ICrmCommandBarControl value)
0xee70  pop
0xee71  ret
```
