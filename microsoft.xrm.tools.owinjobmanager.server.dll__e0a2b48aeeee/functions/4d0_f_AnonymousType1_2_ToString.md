# <>f__AnonymousType1`2::ToString

- ea: `0x4d0`
- end: `0x558`
- name: `<>f__AnonymousType1`2::ToString`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x4d0`

## pseudocode

```c

```

## disassembly

```asm
0x4d0  ldnull
0x4d1  ldstr    aId0Status1// "{{ Id = {0}, Status = {1} }}"
0x4d6  ldc.i4.2
0x4d7  newarr   [mscorlib]System.Object
0x4dc  dup
0x4dd  ldc.i4.0
0x4de  ldarg.0
0x4df  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Id>i__Field
0x4e4  stloc.0
0x4e5  ldloca.s 0
0x4e7  ldloca.s 1
0x4e9  initobj  var<u1>
0x4ef  ldloc.1
0x4f0  box      var<u1>
0x4f5  brtrue.s loc_50B
0x4f7  ldobj    var<u1>
0x4fc  stloc.1
0x4fd  ldloca.s 1
0x4ff  ldloc.1
0x500  box      var<u1>
0x505  brtrue.s loc_50B
0x507  pop
0x508  ldnull
0x509  br.s     loc_516
0x50b  constrained. var<u1>
0x511  callvirt instance string [mscorlib]System.Object::ToString()
0x516  stelem.ref
0x517  dup
0x518  ldc.i4.1
0x519  ldarg.0
0x51a  ldfld    var<u1> class <>f__AnonymousType1`2<var<u1>, !!T0>::<Status>i__Field
0x51f  stloc.2
0x520  ldloca.s 2
0x522  ldloca.s 3
0x524  initobj  var<u1>
0x52a  ldloc.3
0x52b  box      var<u1>
0x530  brtrue.s loc_546
0x532  ldobj    var<u1>
0x537  stloc.3
0x538  ldloca.s 3
0x53a  ldloc.3
0x53b  box      var<u1>
0x540  brtrue.s loc_546
0x542  pop
0x543  ldnull
0x544  br.s     loc_551
0x546  constrained. var<u1>
0x54c  callvirt instance string [mscorlib]System.Object::ToString()
0x551  stelem.ref
0x552  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x557  ret
```
