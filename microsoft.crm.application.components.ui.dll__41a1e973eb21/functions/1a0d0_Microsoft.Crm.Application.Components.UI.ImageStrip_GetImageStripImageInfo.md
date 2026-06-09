# Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo

- ea: `0x1a0d0`
- end: `0x1a14c`
- name: `Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo`
- size: `124`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x97b0`
- `0xca40`
- `0x16260`
- `0x1a6d0`
- `0x24a50`
- `0x24eb0`
- `0x253d0`
- `0x284a0`
- `0x29330`
- `0x29980`

## callees

- `0x1a0b0`
- `0x1a0d0`
- `0x1a2f0`

## pseudocode

```c

```

## disassembly

```asm
0x1a0d0  call     bool Microsoft.Crm.Application.Components.UI.ImageStrip::get_ImageStripsEnabled()
0x1a0d5  brfalse.s loc_1A135
0x1a0d7  ldarg.1
0x1a0d8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x1a0dd  stloc.0
0x1a0de  ldarg.0
0x1a0df  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo> Microsoft.Crm.Application.Components.UI.ImageStrip::_imageDefinitions
0x1a0e4  ldloc.0
0x1a0e5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo>::ContainsKey(var<u1>)
0x1a0ea  brfalse.s loc_1A0F9
0x1a0ec  ldarg.0
0x1a0ed  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo> Microsoft.Crm.Application.Components.UI.ImageStrip::_imageDefinitions
0x1a0f2  ldloc.0
0x1a0f3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo>::get_Item(void)
0x1a0f8  ret
0x1a0f9  ldloc.0
0x1a0fa  ldstr    aImgs// "/_imgs"
0x1a0ff  ldc.i4.1
0x1a100  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1a105  stloc.1
0x1a106  ldloc.1
0x1a107  ldc.i4.0
0x1a108  ble.s    loc_1A135
0x1a10a  ldloc.0
0x1a10b  ldloc.1
0x1a10c  ldloc.0
0x1a10d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a112  ldloc.1
0x1a113  sub
0x1a114  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1a119  stloc.2
0x1a11a  ldarg.0
0x1a11b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo> Microsoft.Crm.Application.Components.UI.ImageStrip::_imageDefinitions
0x1a120  ldloc.2
0x1a121  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo>::ContainsKey(var<u1>)
0x1a126  brfalse.s loc_1A135
0x1a128  ldarg.0
0x1a129  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo> Microsoft.Crm.Application.Components.UI.ImageStrip::_imageDefinitions
0x1a12e  ldloc.2
0x1a12f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo>::get_Item(void)
0x1a134  ret
0x1a135  ldsfld   string [mscorlib]System.String::Empty
0x1a13a  ldarg.1
0x1a13b  callvirt instance string [mscorlib]System.Object::ToString()
0x1a140  ldsfld   string [mscorlib]System.String::Empty
0x1a145  ldc.i4.0
0x1a146  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::.ctor(string id, string url, string cssClass, bool isPartOfImageStrip)
0x1a14b  ret
```
