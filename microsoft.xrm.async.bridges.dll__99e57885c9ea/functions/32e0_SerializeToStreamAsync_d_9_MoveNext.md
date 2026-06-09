# <SerializeToStreamAsync>d__9::MoveNext

- ea: `0x32e0`
- end: `0x3417`
- name: `<SerializeToStreamAsync>d__9::MoveNext`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x900`
- `0x32e0`

## pseudocode

```c

```

## disassembly

```asm
0x32e0  ldarg.0
0x32e1  ldfld    int32 <SerializeToStreamAsync>d__9::<>1__state
0x32e6  stloc.0
0x32e7  ldloc.0
0x32e8  brfalse.s loc_3306
0x32ea  ldarg.0
0x32eb  ldarg.0
0x32ec  ldfld    class [mscorlib]System.IO.Stream <SerializeToStreamAsync>d__9::stream
0x32f1  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x32f6  ldc.i4   0x400
0x32fb  ldc.i4.1
0x32fc  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding, int32, bool)
0x3301  stfld    class [mscorlib]System.IO.StreamWriter <SerializeToStreamAsync>d__9::<streamWriter>5__2
0x3306  nop
0x3307  ldloc.0
0x3308  brfalse.s loc_331B
0x330a  ldarg.0
0x330b  ldarg.0
0x330c  ldfld    class [mscorlib]System.IO.StreamWriter <SerializeToStreamAsync>d__9::<streamWriter>5__2
0x3311  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x3316  stfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter <SerializeToStreamAsync>d__9::<jsonWriter>5__1
0x331b  nop
0x331c  ldloc.0
0x331d  brfalse.s loc_337D
0x331f  ldarg.0
0x3320  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent <SerializeToStreamAsync>d__9::<>4__this
0x3325  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::get_Serializer()
0x332a  ldarg.0
0x332b  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter <SerializeToStreamAsync>d__9::<jsonWriter>5__1
0x3330  ldarg.0
0x3331  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent <SerializeToStreamAsync>d__9::<>4__this
0x3336  ldfld    object Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::content
0x333b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0x3340  ldarg.0
0x3341  ldfld    class [mscorlib]System.IO.StreamWriter <SerializeToStreamAsync>d__9::<streamWriter>5__2
0x3346  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.IO.TextWriter::FlushAsync()
0x334b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x3350  stloc.1
0x3351  ldloca.s 1
0x3353  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x3358  brtrue.s loc_3399
0x335a  ldarg.0
0x335b  ldc.i4.0
0x335c  dup
0x335d  stloc.0
0x335e  stfld    int32 <SerializeToStreamAsync>d__9::<>1__state
0x3363  ldarg.0
0x3364  ldloc.1
0x3365  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__9::<>u__1
0x336a  ldarg.0
0x336b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__9::<>t__builder
0x3370  ldloca.s 1
0x3372  ldarg.0
0x3373  call     T0x2B00007B
0x3378  leave    loc_3416
0x337d  ldarg.0
0x337e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__9::<>u__1
0x3383  stloc.1
0x3384  ldarg.0
0x3385  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__9::<>u__1
0x338a  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x3390  ldarg.0
0x3391  ldc.i4.m1
0x3392  dup
0x3393  stloc.0
0x3394  stfld    int32 <SerializeToStreamAsync>d__9::<>1__state
0x3399  ldloca.s 1
0x339b  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x33a0  ldloca.s 1
0x33a2  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x33a8  leave.s  loc_33C2
0x33aa  ldloc.0
0x33ab  ldc.i4.0
0x33ac  bge.s    loc_33C1
0x33ae  ldarg.0
0x33af  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter <SerializeToStreamAsync>d__9::<jsonWriter>5__1
0x33b4  brfalse.s loc_33C1
0x33b6  ldarg.0
0x33b7  ldfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter <SerializeToStreamAsync>d__9::<jsonWriter>5__1
0x33bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33c1  endfinally
0x33c2  ldarg.0
0x33c3  ldnull
0x33c4  stfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter <SerializeToStreamAsync>d__9::<jsonWriter>5__1
0x33c9  leave.s  loc_33E3
0x33cb  ldloc.0
0x33cc  ldc.i4.0
0x33cd  bge.s    loc_33E2
0x33cf  ldarg.0
0x33d0  ldfld    class [mscorlib]System.IO.StreamWriter <SerializeToStreamAsync>d__9::<streamWriter>5__2
0x33d5  brfalse.s loc_33E2
0x33d7  ldarg.0
0x33d8  ldfld    class [mscorlib]System.IO.StreamWriter <SerializeToStreamAsync>d__9::<streamWriter>5__2
0x33dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33e2  endfinally
0x33e3  ldarg.0
0x33e4  ldnull
0x33e5  stfld    class [mscorlib]System.IO.StreamWriter <SerializeToStreamAsync>d__9::<streamWriter>5__2
0x33ea  leave.s  loc_3403
0x33ec  stloc.2
0x33ed  ldarg.0
0x33ee  ldc.i4.s 0xFE
0x33f0  stfld    int32 <SerializeToStreamAsync>d__9::<>1__state
0x33f5  ldarg.0
0x33f6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__9::<>t__builder
0x33fb  ldloc.2
0x33fc  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x3401  leave.s  loc_3416
0x3403  ldarg.0
0x3404  ldc.i4.s 0xFE
0x3406  stfld    int32 <SerializeToStreamAsync>d__9::<>1__state
0x340b  ldarg.0
0x340c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__9::<>t__builder
0x3411  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x3416  ret
```
