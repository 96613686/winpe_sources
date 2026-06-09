# Microsoft.Crm.Controls.CommandBar::.ctor

- ea: `0xee80`
- end: `0xeedb`
- name: `Microsoft.Crm.Controls.CommandBar::.ctor`
- size: `91`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xc690`
- `0xf160`
- `0xf180`
- `0xf460`

## callees

- `0xed30`
- `0xfa80`
- `0xfbc0`
- `0xfbd0`
- `0x23ad0`

## pseudocode

```c

```

## disassembly

```asm
0xee80  ldarg.0
0xee81  ldsfld   string [mscorlib]System.String::Empty
0xee86  stfld    string Microsoft.Crm.Controls.CommandBar::_cssClass
0xee8b  ldarg.0
0xee8c  ldc.i4.1
0xee8d  stfld    valuetype Microsoft.Crm.Controls.CommandBarAlignment Microsoft.Crm.Controls.CommandBar::_commandBarAlignment
0xee92  ldarg.0
0xee93  ldsfld   string [mscorlib]System.String::Empty
0xee98  stfld    string Microsoft.Crm.Controls.CommandBar::_title
0xee9d  ldarg.0
0xee9e  ldc.i4.m1
0xee9f  stfld    valuetype Microsoft.Crm.Controls.CommandBarType Microsoft.Crm.Controls.CommandBar::_type
0xeea4  ldarg.0
0xeea5  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::.ctor()
0xeeaa  ldarg.0
0xeeab  call     instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_InternalControls()
0xeeb0  ldarg.0
0xeeb1  dup
0xeeb2  ldvirtftn instance void Microsoft.Crm.Controls.CommandBar::OnBeforeAddItem(class Microsoft.Crm.Controls.CommandBarControlCollection sender, class Microsoft.Crm.Controls.CommandBarControlCollectionEventArgs e)
0xeeb8  newobj   instance void Microsoft.Crm.Controls.CommandBarControlCollectionEventHandler::.ctor(object object, native int method)
0xeebd  callvirt instance void Microsoft.Crm.Controls.CommandBarControlCollection::AttachBeforeAddEvent(class Microsoft.Crm.Controls.CommandBarControlCollectionEventHandler onBeforeAddEvent)
0xeec2  ldarg.0
0xeec3  call     instance class Microsoft.Crm.Controls.CommandBarControlCollection Microsoft.Crm.Controls.CommandBar::get_InternalControls()
0xeec8  ldarg.0
0xeec9  dup
0xeeca  ldvirtftn instance void Microsoft.Crm.Controls.CommandBar::OnBeforeRemoveItem(class Microsoft.Crm.Controls.CommandBarControlCollection sender, class Microsoft.Crm.Controls.CommandBarControlCollectionEventArgs e)
0xeed0  newobj   instance void Microsoft.Crm.Controls.CommandBarControlCollectionEventHandler::.ctor(object object, native int method)
0xeed5  callvirt instance void Microsoft.Crm.Controls.CommandBarControlCollection::AttachBeforeRemoveEvent(class Microsoft.Crm.Controls.CommandBarControlCollectionEventHandler onBeforeRemoveEvent)
0xeeda  ret
```
