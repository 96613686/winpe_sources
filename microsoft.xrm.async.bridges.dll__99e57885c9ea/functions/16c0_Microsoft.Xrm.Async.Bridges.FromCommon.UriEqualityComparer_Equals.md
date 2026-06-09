# Microsoft.Xrm.Async.Bridges.FromCommon.UriEqualityComparer::Equals

- ea: `0x16c0`
- end: `0x16f0`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.UriEqualityComparer::Equals`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x16c0`

## pseudocode

```c

```

## disassembly

```asm
0x16c0  ldarg.1
0x16c1  ldnull
0x16c2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x16c7  brfalse.s loc_16D4
0x16c9  ldarg.2
0x16ca  ldnull
0x16cb  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x16d0  brfalse.s loc_16D4
0x16d2  ldc.i4.1
0x16d3  ret
0x16d4  ldarg.1
0x16d5  ldnull
0x16d6  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x16db  brtrue.s loc_16E6
0x16dd  ldarg.2
0x16de  ldnull
0x16df  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x16e4  brfalse.s loc_16E8
0x16e6  ldc.i4.0
0x16e7  ret
0x16e8  ldarg.1
0x16e9  ldarg.2
0x16ea  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x16ef  ret
```
