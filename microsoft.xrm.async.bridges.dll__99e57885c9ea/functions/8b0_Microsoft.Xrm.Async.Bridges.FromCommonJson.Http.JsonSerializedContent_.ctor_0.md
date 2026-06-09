# Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.ctor_0

- ea: `0x8b0`
- end: `0x8be`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.ctor_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8c0`

## pseudocode

```c

```

## disassembly

```asm
0x8b0  ldarg.0
0x8b1  ldarg.1
0x8b2  ldarg.2
0x8b3  call     class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Create(class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x8b8  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.ctor(object content, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer serializer)
0x8bd  ret
```
