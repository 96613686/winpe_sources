# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::IconPath

- ea: `0x1df00`
- end: `0x1df90`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::IconPath`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1ddc0`

## callees

- `0x142c0`
- `0x1df00`

## string_xrefs

- `0x1df42`: `remove`
- `0x1df0e`: `moveup`
- `0x1df1b`: `movedown`
- `0x1df7f`: `/_imgs/ico_16_remove.gif`

## pseudocode

```c

```

## disassembly

```asm
0x1df00  ldarg.1
0x1df01  ldstr    aAdd// "add"
0x1df06  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1df0b  brtrue.s loc_1DF50
0x1df0d  ldarg.1
0x1df0e  ldstr    aMoveup// "moveup"
0x1df13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1df18  brtrue.s loc_1DF50
0x1df1a  ldarg.1
0x1df1b  ldstr    aMovedown// "movedown"
0x1df20  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1df25  brtrue.s loc_1DF50
0x1df27  ldarg.1
0x1df28  ldstr    aSortasc_0// "sortasc"
0x1df2d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1df32  brtrue.s loc_1DF50
0x1df34  ldarg.1
0x1df35  ldstr    aSortdes// "sortdes"
0x1df3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1df3f  brtrue.s loc_1DF50
0x1df41  ldarg.1
0x1df42  ldstr    aRemove// "remove"
0x1df47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1df4c  brtrue.s loc_1DF6A
0x1df4e  br.s     loc_1DF8A
0x1df50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1df55  ldstr    aImgsPicklistCm// "/_imgs/picklist/cmd_{0}.png"
0x1df5a  ldc.i4.1
0x1df5b  newarr   [mscorlib]System.Object
0x1df60  dup
0x1df61  ldc.i4.0
0x1df62  ldarg.1
0x1df63  stelem.ref
0x1df64  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1df69  ret
0x1df6a  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1df6f  ldc.i4.1
0x1df70  newarr   [mscorlib]System.Char
0x1df75  dup
0x1df76  ldc.i4.0
0x1df77  ldc.i4.s 0x2F
0x1df79  stelem.i2
0x1df7a  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1df7f  ldstr    aImgsIco16Remov// "/_imgs/ico_16_remove.gif"
0x1df84  call     string [mscorlib]System.String::Concat(string, string)
0x1df89  ret
0x1df8a  ldstr    asc_3280A// ""
0x1df8f  ret
```
