# <DequeueAll>d__2::MoveNext

- ea: `0x1bd0`
- end: `0x1c1f`
- name: `<DequeueAll>d__2::MoveNext`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1bd0`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  ldfld    int32 class <DequeueAll>d__2<var<u1>>::<>1__state
0x1bd6  stloc.0
0x1bd7  ldloc.0
0x1bd8  brfalse.s loc_1BE0
0x1bda  ldloc.0
0x1bdb  ldc.i4.1
0x1bdc  beq.s    loc_1BFE
0x1bde  ldc.i4.0
0x1bdf  ret
0x1be0  ldarg.0
0x1be1  ldc.i4.m1
0x1be2  stfld    int32 class <DequeueAll>d__2<var<u1>>::<>1__state
0x1be7  br.s     loc_1C05
0x1be9  ldarg.0
0x1bea  ldarg.0
0x1beb  ldfld    var<u1> class <DequeueAll>d__2<var<u1>>::<item>5__1
0x1bf0  stfld    var<u1> class <DequeueAll>d__2<var<u1>>::<>2__current
0x1bf5  ldarg.0
0x1bf6  ldc.i4.1
0x1bf7  stfld    int32 class <DequeueAll>d__2<var<u1>>::<>1__state
0x1bfc  ldc.i4.1
0x1bfd  ret
0x1bfe  ldarg.0
0x1bff  ldc.i4.m1
0x1c00  stfld    int32 class <DequeueAll>d__2<var<u1>>::<>1__state
0x1c05  ldarg.0
0x1c06  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class <DequeueAll>d__2<var<u1>>::<>4__this
0x1c0b  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>::items
0x1c10  ldarg.0
0x1c11  ldflda   var<u1> class <DequeueAll>d__2<var<u1>>::<item>5__1
0x1c16  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<var<u1>>::TryDequeue(var<u1>&)
0x1c1b  brtrue.s loc_1BE9
0x1c1d  ldc.i4.0
0x1c1e  ret
```
