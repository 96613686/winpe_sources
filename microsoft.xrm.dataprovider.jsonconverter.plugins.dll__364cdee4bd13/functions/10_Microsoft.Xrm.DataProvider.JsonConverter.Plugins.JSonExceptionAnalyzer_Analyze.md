# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JSonExceptionAnalyzer::Analyze

- ea: `0x10`
- end: `0x65`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JSonExceptionAnalyzer::Analyze`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x10`
- `0x18a0`
- `0x18d0`
- `0x1b40`

## pseudocode

```c

```

## disassembly

```asm
0x10  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x15  stloc.0
0x16  ldloc.0
0x17  ldarg.0
0x18  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JSonExceptionAnalyzer <>c__DisplayClass1_0::<>4__this
0x1d  nop
0x1e  ldloc.0
0x1f  newobj   instance void Microsoft.Xrm.DataProvider.Logger.AnalysisResult::.ctor()
0x24  dup
0x25  ldc.i4.4
0x26  callvirt instance void Microsoft.Xrm.DataProvider.Logger.AnalysisResult::set_LogLevel(valuetype [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LogLevel value)
0x2b  nop
0x2c  stfld    class Microsoft.Xrm.DataProvider.Logger.AnalysisResult <>c__DisplayClass1_0::result
0x31  ldarg.1
0x32  call     T0x2B000001
0x37  ldloc.0
0x38  ldftn    instance void <>c__DisplayClass1_0::<Analyze>b__0()
0x3e  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x43  callvirt T0x2B000002
0x48  ldloc.0
0x49  ldftn    instance void <>c__DisplayClass1_0::<Analyze>b__1(class [mscorlib]System.Exception ex)
0x4f  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.Exception>::.ctor(object, native int)
0x54  callvirt instance void class Switch`1<class [mscorlib]System.Exception>::Default(class [mscorlib]System.Action`1<var<u1>>)
0x59  nop
0x5a  ldloc.0
0x5b  ldfld    class Microsoft.Xrm.DataProvider.Logger.AnalysisResult <>c__DisplayClass1_0::result
0x60  stloc.1
0x61  br.s     loc_63
0x63  ldloc.1
0x64  ret
```
