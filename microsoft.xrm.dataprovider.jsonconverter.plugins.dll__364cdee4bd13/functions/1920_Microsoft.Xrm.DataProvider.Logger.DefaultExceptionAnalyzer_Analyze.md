# Microsoft.Xrm.DataProvider.Logger.DefaultExceptionAnalyzer::Analyze

- ea: `0x1920`
- end: `0x19e5`
- name: `Microsoft.Xrm.DataProvider.Logger.DefaultExceptionAnalyzer::Analyze`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1b60`

## callees

- `0x18a0`
- `0x18d0`
- `0x1920`
- `0x22f0`

## pseudocode

```c

```

## disassembly

```asm
0x1920  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x1925  stloc.0
0x1926  nop
0x1927  ldloc.0
0x1928  newobj   instance void Microsoft.Xrm.DataProvider.Logger.AnalysisResult::.ctor()
0x192d  dup
0x192e  ldc.i4.4
0x192f  callvirt instance void Microsoft.Xrm.DataProvider.Logger.AnalysisResult::set_LogLevel(valuetype [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LogLevel value)
0x1934  nop
0x1935  stfld    class Microsoft.Xrm.DataProvider.Logger.AnalysisResult <>c__DisplayClass0_0::result
0x193a  ldarg.1
0x193b  call     T0x2B000001
0x1940  ldloc.0
0x1941  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__0()
0x1947  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x194c  callvirt T0x2B00001A
0x1951  ldloc.0
0x1952  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__1()
0x1958  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x195d  callvirt T0x2B00001B
0x1962  ldloc.0
0x1963  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__2()
0x1969  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x196e  callvirt T0x2B00001C
0x1973  ldloc.0
0x1974  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__3()
0x197a  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x197f  callvirt T0x2B00001D
0x1984  ldloc.0
0x1985  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__4()
0x198b  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1990  callvirt T0x2B00001E
0x1995  ldloc.0
0x1996  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__5()
0x199c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x19a1  callvirt T0x2B00001F
0x19a6  ldloc.0
0x19a7  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__6()
0x19ad  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x19b2  callvirt T0x2B000020
0x19b7  ldloc.0
0x19b8  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__7()
0x19be  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x19c3  callvirt T0x2B000021
0x19c8  ldloc.0
0x19c9  ldftn    instance void <>c__DisplayClass0_0::<Analyze>b__8()
0x19cf  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x19d4  callvirt instance void class Switch`1<class [mscorlib]System.Exception>::Default(class [mscorlib]System.Action)
0x19d9  nop
0x19da  ldloc.0
0x19db  ldfld    class Microsoft.Xrm.DataProvider.Logger.AnalysisResult <>c__DisplayClass0_0::result
0x19e0  stloc.1
0x19e1  br.s     loc_19E3
0x19e3  ldloc.1
0x19e4  ret
```
