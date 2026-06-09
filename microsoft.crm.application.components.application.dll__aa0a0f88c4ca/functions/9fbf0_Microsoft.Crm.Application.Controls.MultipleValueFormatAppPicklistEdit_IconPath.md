# Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::IconPath

- ea: `0x9fbf0`
- end: `0x9fd00`
- name: `Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::IconPath`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x9faf0`

## callees

- `0x9fbf0`
- `0xf0f70`

## string_xrefs

- `0x9fcef`: `/_imgs/ico_16_remove.gif`
- `0x9fcb2`: `remove`
- `0x9fc64`: `moveup`
- `0x9fc76`: `movedown`

## pseudocode

```c

```

## disassembly

```asm
0x9fbf0  ldarg.1
0x9fbf1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x9fbf6  stloc.0
0x9fbf7  ldloc.0
0x9fbf8  ldc.i4   0x3B391274
0x9fbfd  bgt.un.s loc_9FC1F
0x9fbff  ldloc.0
0x9fc00  ldc.i4   0xECE2837
0x9fc05  beq      loc_9FC93
0x9fc0a  ldloc.0
0x9fc0b  ldc.i4   0x2BB37AF9
0x9fc10  beq.s    loc_9FC63
0x9fc12  ldloc.0
0x9fc13  ldc.i4   0x3B391274
0x9fc18  beq.s    loc_9FC51
0x9fc1a  br       loc_9FCFA
0x9fc1f  ldloc.0
0x9fc20  ldc.i4   0xB8745040
0x9fc25  bgt.un.s loc_9FC3C
0x9fc27  ldloc.0
0x9fc28  ldc.i4   0x5BE7D591
0x9fc2d  beq.s    loc_9FCA2
0x9fc2f  ldloc.0
0x9fc30  ldc.i4   0xB8745040
0x9fc35  beq.s    loc_9FC75
0x9fc37  br       loc_9FCFA
0x9fc3c  ldloc.0
0x9fc3d  ldc.i4   0xDB9215FD
0x9fc42  beq.s    loc_9FCB1
0x9fc44  ldloc.0
0x9fc45  ldc.i4   0xF8145ACE
0x9fc4a  beq.s    loc_9FC84
0x9fc4c  br       loc_9FCFA
0x9fc51  ldarg.1
0x9fc52  ldstr    aAdd_0// "add"
0x9fc57  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fc5c  brtrue.s loc_9FCC0
0x9fc5e  br       loc_9FCFA
0x9fc63  ldarg.1
0x9fc64  ldstr    aMoveup// "moveup"
0x9fc69  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fc6e  brtrue.s loc_9FCC0
0x9fc70  br       loc_9FCFA
0x9fc75  ldarg.1
0x9fc76  ldstr    aMovedown// "movedown"
0x9fc7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fc80  brtrue.s loc_9FCC0
0x9fc82  br.s     loc_9FCFA
0x9fc84  ldarg.1
0x9fc85  ldstr    aSortasc// "sortasc"
0x9fc8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fc8f  brtrue.s loc_9FCC0
0x9fc91  br.s     loc_9FCFA
0x9fc93  ldarg.1
0x9fc94  ldstr    aSortdes// "sortdes"
0x9fc99  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fc9e  brtrue.s loc_9FCC0
0x9fca0  br.s     loc_9FCFA
0x9fca2  ldarg.1
0x9fca3  ldstr    aEdit// "edit"
0x9fca8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fcad  brtrue.s loc_9FCC0
0x9fcaf  br.s     loc_9FCFA
0x9fcb1  ldarg.1
0x9fcb2  ldstr    aRemove// "remove"
0x9fcb7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fcbc  brtrue.s loc_9FCDA
0x9fcbe  br.s     loc_9FCFA
0x9fcc0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fcc5  ldstr    aImgsPicklistCm_2// "/_imgs/picklist/cmd_{0}.png"
0x9fcca  ldc.i4.1
0x9fccb  newarr   [mscorlib]System.Object
0x9fcd0  dup
0x9fcd1  ldc.i4.0
0x9fcd2  ldarg.1
0x9fcd3  stelem.ref
0x9fcd4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9fcd9  ret
0x9fcda  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9fcdf  ldc.i4.1
0x9fce0  newarr   [mscorlib]System.Char
0x9fce5  dup
0x9fce6  ldc.i4.0
0x9fce7  ldc.i4.s 0x2F
0x9fce9  stelem.i2
0x9fcea  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9fcef  ldstr    aImgsIco16Remov_2// "/_imgs/ico_16_remove.gif"
0x9fcf4  call     string [mscorlib]System.String::Concat(string, string)
0x9fcf9  ret
0x9fcfa  ldstr    asc_F537C// ""
0x9fcff  ret
```
