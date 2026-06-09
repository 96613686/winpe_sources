# <>c::<GetNameValues>b__2_0

- ea: `0x6770`
- end: `0x67da`
- name: `<>c::<GetNameValues>b__2_0`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x6770`

## string_xrefs

- `0x6797`: `Invalid Token`
- `0x67b2`: `Invalid Token`

## pseudocode

```c

```

## disassembly

```asm
0x6770  ldarg.2
0x6771  ldsfld   string [mscorlib]System.String::Empty
0x6776  call     bool [mscorlib]System.String::op_Equality(string, string)
0x677b  brfalse.s loc_677F
0x677d  ldarg.1
0x677e  ret
0x677f  ldarg.2
0x6780  ldc.i4.1
0x6781  newarr   [mscorlib]System.Char
0x6786  dup
0x6787  ldc.i4.0
0x6788  ldc.i4.s 0x3D
0x678a  stelem.i2
0x678b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x6790  stloc.0
0x6791  ldloc.0
0x6792  ldlen
0x6793  conv.i4
0x6794  ldc.i4.2
0x6795  beq.s    loc_67A7
0x6797  ldstr    aInvalidToken// "Invalid Token"
0x679c  ldc.i4   0x80044178
0x67a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x67a6  throw
0x67a7  ldarg.1
0x67a8  ldloc.0
0x67a9  ldc.i4.0
0x67aa  ldelem.ref
0x67ab  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x67b0  brfalse.s loc_67C2
0x67b2  ldstr    aInvalidToken// "Invalid Token"
0x67b7  ldc.i4   0x80044178
0x67bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x67c1  throw
0x67c2  ldarg.1
0x67c3  ldloc.0
0x67c4  ldc.i4.0
0x67c5  ldelem.ref
0x67c6  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x67cb  ldloc.0
0x67cc  ldc.i4.1
0x67cd  ldelem.ref
0x67ce  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x67d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x67d8  ldarg.1
0x67d9  ret
```
