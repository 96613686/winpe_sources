# LinkDescriptorComparer::Equals

- ea: `0x20ca0`
- end: `0x20ce8`
- name: `LinkDescriptorComparer::Equals`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3930`
- `0x3950`
- `0x3970`
- `0x20ca0`

## pseudocode

```c

```

## disassembly

```asm
0x20ca0  ldarg.1
0x20ca1  brtrue.s loc_20CA8
0x20ca3  ldarg.2
0x20ca4  brtrue.s loc_20CA8
0x20ca6  ldc.i4.1
0x20ca7  ret
0x20ca8  ldarg.1
0x20ca9  brfalse.s loc_20CE6
0x20cab  ldarg.2
0x20cac  brfalse.s loc_20CE6
0x20cae  ldarg.1
0x20caf  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x20cb4  ldarg.2
0x20cb5  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x20cba  call     bool [mscorlib]System.Object::Equals(object, object)
0x20cbf  brfalse.s loc_20CE6
0x20cc1  ldarg.1
0x20cc2  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x20cc7  ldarg.2
0x20cc8  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x20ccd  call     bool [mscorlib]System.Object::Equals(object, object)
0x20cd2  brfalse.s loc_20CE6
0x20cd4  ldarg.1
0x20cd5  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x20cda  ldarg.2
0x20cdb  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x20ce0  call     bool [mscorlib]System.Object::Equals(object, object)
0x20ce5  ret
0x20ce6  ldc.i4.0
0x20ce7  ret
```
