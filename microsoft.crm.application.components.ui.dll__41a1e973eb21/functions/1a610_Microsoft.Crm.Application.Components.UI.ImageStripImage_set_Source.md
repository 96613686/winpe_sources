# Microsoft.Crm.Application.Components.UI.ImageStripImage::set_Source

- ea: `0x1a610`
- end: `0x1a645`
- name: `Microsoft.Crm.Application.Components.UI.ImageStripImage::set_Source`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x101a0`
- `0x10f60`

## callees

- `0x1a610`
- `0x1a6d0`
- `0x24120`

## string_xrefs

- `0x1a633`: `Cannot set src since the expandos collection already contains a src. Please call ClearExpandos() if you are reusing the control.`

## pseudocode

```c

```

## disassembly

```asm
0x1a610  ldarg.0
0x1a611  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1a616  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a61b  brfalse.s loc_1A632
0x1a61d  ldarg.0
0x1a61e  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1a623  ldstr    aSrc_1// " src="
0x1a628  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1a62d  ldc.i4.0
0x1a62e  ceq
0x1a630  br.s     loc_1A633
0x1a632  ldc.i4.1
0x1a633  ldstr    aCannotSetSrcSi// "Cannot set src since the expandos colle"...
0x1a638  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x1a63d  ldarg.0
0x1a63e  ldarg.1
0x1a63f  call     instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::SetSrcAttribute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x1a644  ret
```
