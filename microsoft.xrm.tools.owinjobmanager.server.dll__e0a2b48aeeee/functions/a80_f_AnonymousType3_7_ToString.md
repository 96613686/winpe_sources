# <>f__AnonymousType3`7::ToString

- ea: `0xa80`
- end: `0xc43`
- name: `<>f__AnonymousType3`7::ToString`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xa80`

## pseudocode

```c

```

## disassembly

```asm
0xa80  ldnull
0xa81  ldstr    aId0Status1Dura_1// "{{ Id = {0}, Status = {1}, Duration = {"...
0xa86  ldc.i4.7
0xa87  newarr   [mscorlib]System.Object
0xa8c  dup
0xa8d  ldc.i4.0
0xa8e  ldarg.0
0xa8f  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Id>i__Field
0xa94  stloc.0
0xa95  ldloca.s 0
0xa97  ldloca.s 1
0xa99  initobj  var<u1>
0xa9f  ldloc.1
0xaa0  box      var<u1>
0xaa5  brtrue.s loc_ABB
0xaa7  ldobj    var<u1>
0xaac  stloc.1
0xaad  ldloca.s 1
0xaaf  ldloc.1
0xab0  box      var<u1>
0xab5  brtrue.s loc_ABB
0xab7  pop
0xab8  ldnull
0xab9  br.s     loc_AC6
0xabb  constrained. var<u1>
0xac1  callvirt instance string [mscorlib]System.Object::ToString()
0xac6  stelem.ref
0xac7  dup
0xac8  ldc.i4.1
0xac9  ldarg.0
0xaca  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Status>i__Field
0xacf  stloc.2
0xad0  ldloca.s 2
0xad2  ldloca.s 3
0xad4  initobj  var<u1>
0xada  ldloc.3
0xadb  box      var<u1>
0xae0  brtrue.s loc_AF6
0xae2  ldobj    var<u1>
0xae7  stloc.3
0xae8  ldloca.s 3
0xaea  ldloc.3
0xaeb  box      var<u1>
0xaf0  brtrue.s loc_AF6
0xaf2  pop
0xaf3  ldnull
0xaf4  br.s     loc_B01
0xaf6  constrained. var<u1>
0xafc  callvirt instance string [mscorlib]System.Object::ToString()
0xb01  stelem.ref
0xb02  dup
0xb03  ldc.i4.2
0xb04  ldarg.0
0xb05  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Duration>i__Field
0xb0a  stloc.s  4
0xb0c  ldloca.s 4
0xb0e  ldloca.s 5
0xb10  initobj  var<u1>
0xb16  ldloc.s  5
0xb18  box      var<u1>
0xb1d  brtrue.s loc_B35
0xb1f  ldobj    var<u1>
0xb24  stloc.s  5
0xb26  ldloca.s 5
0xb28  ldloc.s  5
0xb2a  box      var<u1>
0xb2f  brtrue.s loc_B35
0xb31  pop
0xb32  ldnull
0xb33  br.s     loc_B40
0xb35  constrained. var<u1>
0xb3b  callvirt instance string [mscorlib]System.Object::ToString()
0xb40  stelem.ref
0xb41  dup
0xb42  ldc.i4.3
0xb43  ldarg.0
0xb44  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<OutputCount>i__Field
0xb49  stloc.s  6
0xb4b  ldloca.s 6
0xb4d  ldloca.s 7
0xb4f  initobj  var<u1>
0xb55  ldloc.s  7
0xb57  box      var<u1>
0xb5c  brtrue.s loc_B74
0xb5e  ldobj    var<u1>
0xb63  stloc.s  7
0xb65  ldloca.s 7
0xb67  ldloc.s  7
0xb69  box      var<u1>
0xb6e  brtrue.s loc_B74
0xb70  pop
0xb71  ldnull
0xb72  br.s     loc_B7F
0xb74  constrained. var<u1>
0xb7a  callvirt instance string [mscorlib]System.Object::ToString()
0xb7f  stelem.ref
0xb80  dup
0xb81  ldc.i4.4
0xb82  ldarg.0
0xb83  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionType>i__Field
0xb88  stloc.s  8
0xb8a  ldloca.s 8
0xb8c  ldloca.s 9
0xb8e  initobj  var<u1>
0xb94  ldloc.s  9
0xb96  box      var<u1>
0xb9b  brtrue.s loc_BB3
0xb9d  ldobj    var<u1>
0xba2  stloc.s  9
0xba4  ldloca.s 9
0xba6  ldloc.s  9
0xba8  box      var<u1>
0xbad  brtrue.s loc_BB3
0xbaf  pop
0xbb0  ldnull
0xbb1  br.s     loc_BBE
0xbb3  constrained. var<u1>
0xbb9  callvirt instance string [mscorlib]System.Object::ToString()
0xbbe  stelem.ref
0xbbf  dup
0xbc0  ldc.i4.5
0xbc1  ldarg.0
0xbc2  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<ExceptionMessage>i__Field
0xbc7  stloc.s  0xA
0xbc9  ldloca.s 0xA
0xbcb  ldloca.s 0xB
0xbcd  initobj  var<u1>
0xbd3  ldloc.s  0xB
0xbd5  box      var<u1>
0xbda  brtrue.s loc_BF2
0xbdc  ldobj    var<u1>
0xbe1  stloc.s  0xB
0xbe3  ldloca.s 0xB
0xbe5  ldloc.s  0xB
0xbe7  box      var<u1>
0xbec  brtrue.s loc_BF2
0xbee  pop
0xbef  ldnull
0xbf0  br.s     loc_BFD
0xbf2  constrained. var<u1>
0xbf8  callvirt instance string [mscorlib]System.Object::ToString()
0xbfd  stelem.ref
0xbfe  dup
0xbff  ldc.i4.6
0xc00  ldarg.0
0xc01  ldfld    var<u1> class <>f__AnonymousType3`7<var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>>::<Error>i__Field
0xc06  stloc.s  0xC
0xc08  ldloca.s 0xC
0xc0a  ldloca.s 0xD
0xc0c  initobj  var<u1>
0xc12  ldloc.s  0xD
0xc14  box      var<u1>
0xc19  brtrue.s loc_C31
0xc1b  ldobj    var<u1>
0xc20  stloc.s  0xD
0xc22  ldloca.s 0xD
0xc24  ldloc.s  0xD
0xc26  box      var<u1>
0xc2b  brtrue.s loc_C31
0xc2d  pop
0xc2e  ldnull
0xc2f  br.s     loc_C3C
0xc31  constrained. var<u1>
0xc37  callvirt instance string [mscorlib]System.Object::ToString()
0xc3c  stelem.ref
0xc3d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc42  ret
```
