# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::.ctor

- ea: `0x2e550`
- end: `0x2e5ca`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::.ctor`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18060`
- `0x2c200`

## string_xrefs

- `0x2e561`: `{0} on properties of complextype is not supported`
- `0x2e57b`: `{0} on properties of complextype is not supported`
- `0x2e595`: `{0} on properties of complextype is not supported`
- `0x2e5af`: `{0} on properties of complextype is not supported`

## pseudocode

```c

```

## disassembly

```asm
0x2e550  ldarg.0
0x2e551  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [System]System.Net.HttpStatusCode, string>>::.ctor()
0x2e556  dup
0x2e557  ldstr    aEntitysetKeyPr// "~/entityset/key/property/property"
0x2e55c  ldc.i4   0x1F5
0x2e561  ldstr    a0OnPropertiesO// "{0} on properties of complextype is not"...
0x2e566  call     T0x2B00010D
0x2e56b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [System]System.Net.HttpStatusCode, string>>::Add(var<u1>, !!T0)
0x2e570  dup
0x2e571  ldstr    aEntitysetKeyCa// "~/entityset/key/cast/property/property"
0x2e576  ldc.i4   0x1F5
0x2e57b  ldstr    a0OnPropertiesO// "{0} on properties of complextype is not"...
0x2e580  call     T0x2B00010D
0x2e585  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [System]System.Net.HttpStatusCode, string>>::Add(var<u1>, !!T0)
0x2e58a  dup
0x2e58b  ldstr    aSingletonPrope// "~/singleton/property/property"
0x2e590  ldc.i4   0x1F5
0x2e595  ldstr    a0OnPropertiesO// "{0} on properties of complextype is not"...
0x2e59a  call     T0x2B00010D
0x2e59f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [System]System.Net.HttpStatusCode, string>>::Add(var<u1>, !!T0)
0x2e5a4  dup
0x2e5a5  ldstr    aSingletonCastP// "~/singleton/cast/property/property"
0x2e5aa  ldc.i4   0x1F5
0x2e5af  ldstr    a0OnPropertiesO// "{0} on properties of complextype is not"...
0x2e5b4  call     T0x2B00010D
0x2e5b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [System]System.Net.HttpStatusCode, string>>::Add(var<u1>, !!T0)
0x2e5be  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [System]System.Net.HttpStatusCode, string>> Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::_unsupportedPathTemplateMap
0x2e5c3  ldarg.0
0x2e5c4  call     instance void [mscorlib]System.Object::.ctor()
0x2e5c9  ret
```
