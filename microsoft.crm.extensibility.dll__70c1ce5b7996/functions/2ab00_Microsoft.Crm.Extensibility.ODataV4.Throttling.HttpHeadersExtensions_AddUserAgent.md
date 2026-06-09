# Microsoft.Crm.Extensibility.ODataV4.Throttling.HttpHeadersExtensions::AddUserAgent

- ea: `0x2ab00`
- end: `0x2ab22`
- name: `Microsoft.Crm.Extensibility.ODataV4.Throttling.HttpHeadersExtensions::AddUserAgent`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x2ab00`

## string_xrefs

- `0x2ab16`: `User-Agent`

## pseudocode

```c

```

## disassembly

```asm
0x2ab00  ldarg.0
0x2ab01  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.ProductInfoHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_UserAgent()
0x2ab06  brfalse.s loc_2AB15
0x2ab08  ldarg.0
0x2ab09  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.ProductInfoHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_UserAgent()
0x2ab0e  call     T0x2B0000FC
0x2ab13  brtrue.s loc_2AB21
0x2ab15  ldarg.0
0x2ab16  ldstr    aUserAgent// "User-Agent"
0x2ab1b  ldarg.1
0x2ab1c  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x2ab21  ret
```
