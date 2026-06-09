# Microsoft.Crm.Application.Components.UI.PicklistEdit::IconPath

- ea: `0x1c230`
- end: `0x1c2c0`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::IconPath`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1c0f0`

## callees

- `0x142c0`
- `0x1c230`

## string_xrefs

- `0x1c272`: `remove`
- `0x1c23e`: `moveup`
- `0x1c24b`: `movedown`
- `0x1c2af`: `/_imgs/ico_16_remove.gif`

## pseudocode

```c

```

## disassembly

```asm
0x1c230  ldarg.1
0x1c231  ldstr    aAdd// "add"
0x1c236  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c23b  brtrue.s loc_1C280
0x1c23d  ldarg.1
0x1c23e  ldstr    aMoveup// "moveup"
0x1c243  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c248  brtrue.s loc_1C280
0x1c24a  ldarg.1
0x1c24b  ldstr    aMovedown// "movedown"
0x1c250  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c255  brtrue.s loc_1C280
0x1c257  ldarg.1
0x1c258  ldstr    aSortasc_0// "sortasc"
0x1c25d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c262  brtrue.s loc_1C280
0x1c264  ldarg.1
0x1c265  ldstr    aSortdes// "sortdes"
0x1c26a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c26f  brtrue.s loc_1C280
0x1c271  ldarg.1
0x1c272  ldstr    aRemove// "remove"
0x1c277  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c27c  brtrue.s loc_1C29A
0x1c27e  br.s     loc_1C2BA
0x1c280  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c285  ldstr    aImgsPicklistCm// "/_imgs/picklist/cmd_{0}.png"
0x1c28a  ldc.i4.1
0x1c28b  newarr   [mscorlib]System.Object
0x1c290  dup
0x1c291  ldc.i4.0
0x1c292  ldarg.1
0x1c293  stelem.ref
0x1c294  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c299  ret
0x1c29a  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1c29f  ldc.i4.1
0x1c2a0  newarr   [mscorlib]System.Char
0x1c2a5  dup
0x1c2a6  ldc.i4.0
0x1c2a7  ldc.i4.s 0x2F
0x1c2a9  stelem.i2
0x1c2aa  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1c2af  ldstr    aImgsIco16Remov// "/_imgs/ico_16_remove.gif"
0x1c2b4  call     string [mscorlib]System.String::Concat(string, string)
0x1c2b9  ret
0x1c2ba  ldstr    asc_3280A// ""
0x1c2bf  ret
```
