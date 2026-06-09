# LinkDescriptorComparer::GetHashCode

- ea: `0x20cf0`
- end: `0x20d2f`
- name: `LinkDescriptorComparer::GetHashCode`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3930`
- `0x3950`
- `0x3970`
- `0x20cf0`

## pseudocode

```c

```

## disassembly

```asm
0x20cf0  ldarg.1
0x20cf1  brtrue.s loc_20CF5
0x20cf3  ldc.i4.0
0x20cf4  ret
0x20cf5  ldarg.1
0x20cf6  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x20cfb  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x20d00  ldarg.1
0x20d01  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x20d06  brtrue.s loc_20D0B
0x20d08  ldc.i4.0
0x20d09  br.s     loc_20D16
0x20d0b  ldarg.1
0x20d0c  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x20d11  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x20d16  xor
0x20d17  ldarg.1
0x20d18  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x20d1d  brtrue.s loc_20D22
0x20d1f  ldc.i4.0
0x20d20  br.s     loc_20D2D
0x20d22  ldarg.1
0x20d23  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x20d28  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x20d2d  xor
0x20d2e  ret
```
