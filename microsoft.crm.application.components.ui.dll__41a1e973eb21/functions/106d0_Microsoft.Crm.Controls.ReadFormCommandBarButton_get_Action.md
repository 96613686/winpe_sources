# Microsoft.Crm.Controls.ReadFormCommandBarButton::get_Action

- ea: `0x106d0`
- end: `0x10703`
- name: `Microsoft.Crm.Controls.ReadFormCommandBarButton::get_Action`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x106b0`
- `0x106d0`
- `0x116f0`

## string_xrefs

- `0x106dd`: `Mscrm.ReadFormUtilities.execute({0},this)`

## pseudocode

```c

```

## disassembly

```asm
0x106d0  ldarg.0
0x106d1  call     instance int32 Microsoft.Crm.Controls.ReadFormCommandBarButton::get_ActionId()
0x106d6  brfalse.s loc_106FC
0x106d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x106dd  ldstr    aMscrmReadformu// "Mscrm.ReadFormUtilities.execute({0},thi"...
0x106e2  ldc.i4.1
0x106e3  newarr   [mscorlib]System.Object
0x106e8  dup
0x106e9  ldc.i4.0
0x106ea  ldarg.0
0x106eb  call     instance int32 Microsoft.Crm.Controls.ReadFormCommandBarButton::get_ActionId()
0x106f0  box      [mscorlib]System.Int32
0x106f5  stelem.ref
0x106f6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x106fb  ret
0x106fc  ldarg.0
0x106fd  call     instance string Microsoft.Crm.Controls.CommandBarControl::get_Action()
0x10702  ret
```
