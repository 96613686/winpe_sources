# Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.ctor_1

- ea: `0x8c0`
- end: `0x8f6`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.ctor_1`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8a0`
- `0x8b0`

## pseudocode

```c

```

## disassembly

```asm
0x8c0  ldarg.0
0x8c1  call     instance void [System.Net.Http]System.Net.Http.HttpContent::.ctor()
0x8c6  ldarg.1
0x8c7  ldstr    aContent// "content"
0x8cc  call     T0x2B00001B
0x8d1  call     T0x2B00001C
0x8d6  pop
0x8d7  ldarg.0
0x8d8  ldarg.1
0x8d9  stfld    object Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::content
0x8de  ldarg.0
0x8df  ldarg.2
0x8e0  stfld    class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::<Serializer>k__BackingField
0x8e5  ldarg.0
0x8e6  call     instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x8eb  ldsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::ContentType
0x8f0  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x8f5  ret
```
