# Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::SerializeToStreamAsync

- ea: `0x910`
- end: `0x951`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::SerializeToStreamAsync`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldloca.s 0
0x912  ldarg.0
0x913  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent <SerializeToStreamAsync>d__9::<>4__this
0x918  ldloca.s 0
0x91a  ldarg.1
0x91b  stfld    class [mscorlib]System.IO.Stream <SerializeToStreamAsync>d__9::stream
0x920  ldloca.s 0
0x922  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x927  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__9::<>t__builder
0x92c  ldloca.s 0
0x92e  ldc.i4.m1
0x92f  stfld    int32 <SerializeToStreamAsync>d__9::<>1__state
0x934  ldloc.0
0x935  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__9::<>t__builder
0x93a  stloc.1
0x93b  ldloca.s 1
0x93d  ldloca.s 0
0x93f  call     T0x2B00001D
0x944  ldloca.s 0
0x946  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__9::<>t__builder
0x94b  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x950  ret
```
