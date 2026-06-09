# Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::Execute

- ea: `0x16b0`
- end: `0x16f8`
- name: `Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::Execute`
- size: `72`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x800`
- `0xb00`
- `0xb80`
- `0xef0`
- `0x11f0`

## callees

- `0x2150`

## pseudocode

```c

```

## disassembly

```asm
0x16b0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x16b5  stloc.0
0x16b6  ldloc.0
0x16b7  ldarg.3
0x16b8  stfld    class [mscorlib]System.Action <>c__DisplayClass4_0::work
0x16bd  ldloc.0
0x16be  ldarg.0
0x16bf  stfld    class Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger <>c__DisplayClass4_0::<>4__this
0x16c4  ldloc.0
0x16c5  ldarg.1
0x16c6  stfld    string <>c__DisplayClass4_0::message
0x16cb  nop
0x16cc  ldloc.0
0x16cd  ldloc.0
0x16ce  ldftn    instance bool <>c__DisplayClass4_0::<Execute>b__0()
0x16d4  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x16d9  stfld    class [mscorlib]System.Func`1<bool> <>c__DisplayClass4_0::wrapper
0x16de  ldarg.0
0x16df  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::xrmLogger
0x16e4  ldarg.2
0x16e5  ldloc.0
0x16e6  ldftn    instance bool <>c__DisplayClass4_0::<Execute>b__1()
0x16ec  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x16f1  call     T0x2B000018
0x16f6  pop
0x16f7  ret
```
