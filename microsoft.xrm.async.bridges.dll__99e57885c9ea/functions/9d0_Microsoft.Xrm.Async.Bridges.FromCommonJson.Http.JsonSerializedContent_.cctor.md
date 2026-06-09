# Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.cctor

- ea: `0x9d0`
- end: `0x9ea`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.cctor`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x9d0`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x9d0  ldstr    aApplicationJso// "application/json"
0x9d5  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::Parse(string)
0x9da  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::ContentType
0x9df  call     class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::CreateDefault()
0x9e4  stsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::DefaultJsonSerializer
0x9e9  ret
```
