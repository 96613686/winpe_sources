# Microsoft.Crm.Application.Components.UI.CheckBox::.ctor

- ea: `0x154b0`
- end: `0x154d8`
- name: `Microsoft.Crm.Application.Components.UI.CheckBox::.ctor`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x11390`
- `0x158a0`
- `0x1d9e0`
- `0x281f0`
- `0x29330`

## callees

- `0x15610`
- `0x15630`
- `0x23840`

## pseudocode

```c

```

## disassembly

```asm
0x154b0  ldarg.0
0x154b1  ldstr    aMsCrmCheckbox// "ms-crm-CheckBox"
0x154b6  stfld    string Microsoft.Crm.Application.Components.UI.CheckBox::_className
0x154bb  ldarg.0
0x154bc  call     instance void Microsoft.Crm.Application.Components.UI.CrmFormUIControl::.ctor()
0x154c1  ldarg.0
0x154c2  ldstr    aMscrmBooleanat// "Mscrm.BooleanAttribute"
0x154c7  call     instance void Microsoft.Crm.Application.Components.UI.CheckBox::set_ClientSideAttributeClassName(string value)
0x154cc  ldarg.0
0x154cd  ldstr    aMscrmForminput_3// "Mscrm.FormInputControl.CheckBoxInputBeh"...
0x154d2  call     instance void Microsoft.Crm.Application.Components.UI.CheckBox::set_ClientSideFormInputBehaviorClassName(string value)
0x154d7  ret
```
