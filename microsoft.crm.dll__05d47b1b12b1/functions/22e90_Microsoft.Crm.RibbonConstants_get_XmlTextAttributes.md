# Microsoft.Crm.RibbonConstants::get_XmlTextAttributes

- ea: `0x22e90`
- end: `0x22f11`
- name: `Microsoft.Crm.RibbonConstants::get_XmlTextAttributes`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x22e90`

## string_xrefs

- `0x22ef2`: `ToolTipDisabledCommandTitle`
- `0x22efb`: `ToolTipDisabledCommandDescription`

## pseudocode

```c

```

## disassembly

```asm
0x22e90  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_xmlTextAttributes
0x22e95  brtrue.s loc_22F0B
0x22e97  ldc.i4.s 0xC
0x22e99  newarr   [mscorlib]System.String
0x22e9e  dup
0x22e9f  ldc.i4.0
0x22ea0  ldstr    aDescription// "Description"
0x22ea5  stelem.ref
0x22ea6  dup
0x22ea7  ldc.i4.1
0x22ea8  ldstr    aTitle// "Title"
0x22ead  stelem.ref
0x22eae  dup
0x22eaf  ldc.i4.2
0x22eb0  ldstr    aImage16by16// "Image16by16"
0x22eb5  stelem.ref
0x22eb6  dup
0x22eb7  ldc.i4.3
0x22eb8  ldstr    aImage32by32// "Image32by32"
0x22ebd  stelem.ref
0x22ebe  dup
0x22ebf  ldc.i4.4
0x22ec0  ldstr    aAlt// "Alt"
0x22ec5  stelem.ref
0x22ec6  dup
0x22ec7  ldc.i4.5
0x22ec8  ldstr    aImagearrow// "ImageArrow"
0x22ecd  stelem.ref
0x22ece  dup
0x22ecf  ldc.i4.6
0x22ed0  ldstr    aLabeltext// "LabelText"
0x22ed5  stelem.ref
0x22ed6  dup
0x22ed7  ldc.i4.7
0x22ed8  ldstr    aTooltiptitle// "ToolTipTitle"
0x22edd  stelem.ref
0x22ede  dup
0x22edf  ldc.i4.8
0x22ee0  ldstr    aTooltipdescrip// "ToolTipDescription"
0x22ee5  stelem.ref
0x22ee6  dup
0x22ee7  ldc.i4.s 9
0x22ee9  ldstr    aTooltipimage32// "ToolTipImage32by32"
0x22eee  stelem.ref
0x22eef  dup
0x22ef0  ldc.i4.s 0xA
0x22ef2  ldstr    aTooltipdisable_0// "ToolTipDisabledCommandTitle"
0x22ef7  stelem.ref
0x22ef8  dup
0x22ef9  ldc.i4.s 0xB
0x22efb  ldstr    aTooltipdisable_1// "ToolTipDisabledCommandDescription"
0x22f00  stelem.ref
0x22f01  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x22f06  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_xmlTextAttributes
0x22f0b  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.RibbonConstants::_xmlTextAttributes
0x22f10  ret
```
