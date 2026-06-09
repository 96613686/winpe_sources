# <DequeueAll>d__2::System.Collections.Generic.IEnumerable<T>.GetEnumerator

- ea: `0x1c50`
- end: `0x1c87`
- name: `<DequeueAll>d__2::System.Collections.Generic.IEnumerable<T>.GetEnumerator`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1c50`

## pseudocode

```c

```

## disassembly

```asm
0x1c50  ldarg.0
0x1c51  ldfld    int32 class <DequeueAll>d__2<var<u1>>::<>1__state
0x1c56  ldc.i4.s 0xFE
0x1c58  bne.un.s loc_1C72
0x1c5a  ldarg.0
0x1c5b  ldfld    int32 class <DequeueAll>d__2<var<u1>>::<>l__initialThreadId
0x1c60  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x1c65  bne.un.s loc_1C72
0x1c67  ldarg.0
0x1c68  ldc.i4.0
0x1c69  stfld    int32 class <DequeueAll>d__2<var<u1>>::<>1__state
0x1c6e  ldarg.0
0x1c6f  stloc.0
0x1c70  br.s     loc_1C85
0x1c72  ldc.i4.0
0x1c73  newobj   instance void class <DequeueAll>d__2<var<u1>>::.ctor(int32)
0x1c78  stloc.0
0x1c79  ldloc.0
0x1c7a  ldarg.0
0x1c7b  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class <DequeueAll>d__2<var<u1>>::<>4__this
0x1c80  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class <DequeueAll>d__2<var<u1>>::<>4__this
0x1c85  ldloc.0
0x1c86  ret
```
