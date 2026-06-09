# Microsoft.Crm.RibbonConstants::get_ImageAttributeNames

- ea: `0x22d70`
- end: `0x22e0f`
- name: `Microsoft.Crm.RibbonConstants::get_ImageAttributeNames`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x22d70`

## string_xrefs

- `0x22dd5`: `ImageSideArrow`
- `0x22de7`: `ToolTipDisabledCommandImage16by16`

## pseudocode

```c

```

## disassembly

```asm
0x22d70  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_imageAttributeNames
0x22d75  brtrue   loc_22E09
0x22d7a  ldc.i4.s 0xF
0x22d7c  newarr   [mscorlib]System.String
0x22d81  dup
0x22d82  ldc.i4.0
0x22d83  ldstr    aImage// "Image"
0x22d88  stelem.ref
0x22d89  dup
0x22d8a  ldc.i4.1
0x22d8b  ldstr    aImage16by16// "Image16by16"
0x22d90  stelem.ref
0x22d91  dup
0x22d92  ldc.i4.2
0x22d93  ldstr    aImage32by32// "Image32by32"
0x22d98  stelem.ref
0x22d99  dup
0x22d9a  ldc.i4.3
0x22d9b  ldstr    aImage32by32gro// "Image32by32GroupPopupDefault"
0x22da0  stelem.ref
0x22da1  dup
0x22da2  ldc.i4.4
0x22da3  ldstr    aImage32by32pop// "Image32by32Popup"
0x22da8  stelem.ref
0x22da9  dup
0x22daa  ldc.i4.5
0x22dab  ldstr    aImagearrow// "ImageArrow"
0x22db0  stelem.ref
0x22db1  dup
0x22db2  ldc.i4.6
0x22db3  ldstr    aImagearrowgrou// "ImageArrowGroupPopup"
0x22db8  stelem.ref
0x22db9  dup
0x22dba  ldc.i4.7
0x22dbb  ldstr    aImagedown// "ImageDown"
0x22dc0  stelem.ref
0x22dc1  dup
0x22dc2  ldc.i4.8
0x22dc3  ldstr    aImagedownarrow// "ImageDownArrow"
0x22dc8  stelem.ref
0x22dc9  dup
0x22dca  ldc.i4.s 9
0x22dcc  ldstr    aImagehover// "ImageHover"
0x22dd1  stelem.ref
0x22dd2  dup
0x22dd3  ldc.i4.s 0xA
0x22dd5  ldstr    aImagesidearrow// "ImageSideArrow"
0x22dda  stelem.ref
0x22ddb  dup
0x22ddc  ldc.i4.s 0xB
0x22dde  ldstr    aImageuparrow// "ImageUpArrow"
0x22de3  stelem.ref
0x22de4  dup
0x22de5  ldc.i4.s 0xC
0x22de7  ldstr    aTooltipdisable// "ToolTipDisabledCommandImage16by16"
0x22dec  stelem.ref
0x22ded  dup
0x22dee  ldc.i4.s 0xD
0x22df0  ldstr    aTooltipfooteri// "ToolTipFooterImage16by16"
0x22df5  stelem.ref
0x22df6  dup
0x22df7  ldc.i4.s 0xE
0x22df9  ldstr    aTooltipimage32// "ToolTipImage32by32"
0x22dfe  stelem.ref
0x22dff  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x22e04  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_imageAttributeNames
0x22e09  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_imageAttributeNames
0x22e0e  ret
```
