# Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::TryComputeLength

- ea: `0x960`
- end: `0x9c3`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::TryComputeLength`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x900`
- `0x960`

## pseudocode

```c

```

## disassembly

```asm
0x960  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x965  stloc.0
0x966  ldloc.0
0x967  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x96c  ldc.i4   0x400
0x971  ldc.i4.1
0x972  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding, int32, bool)
0x977  stloc.1
0x978  ldloc.1
0x979  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x97e  stloc.2
0x97f  ldarg.0
0x980  call     instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::get_Serializer()
0x985  ldloc.2
0x986  ldarg.0
0x987  ldfld    object Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::content
0x98c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0x991  ldloc.1
0x992  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x997  leave.s  loc_9AD
0x999  ldloc.2
0x99a  brfalse.s loc_9A2
0x99c  ldloc.2
0x99d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9a2  endfinally
0x9a3  ldloc.1
0x9a4  brfalse.s loc_9AC
0x9a6  ldloc.1
0x9a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9ac  endfinally
0x9ad  ldarg.1
0x9ae  ldloc.0
0x9af  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x9b4  stind.i8
0x9b5  leave.s  loc_9C1
0x9b7  ldloc.0
0x9b8  brfalse.s loc_9C0
0x9ba  ldloc.0
0x9bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c0  endfinally
0x9c1  ldc.i4.1
0x9c2  ret
```
