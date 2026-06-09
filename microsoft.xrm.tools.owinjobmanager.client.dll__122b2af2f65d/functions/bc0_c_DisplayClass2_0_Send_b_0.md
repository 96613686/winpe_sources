# <>c__DisplayClass2_0::<Send>b__0

- ea: `0xbc0`
- end: `0xbd2`
- name: `<>c__DisplayClass2_0::<Send>b__0`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0xbc0  ldarg.0
0xbc1  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <>c__DisplayClass2_0::client
0xbc6  ldarg.0
0xbc7  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass2_0::request
0xbcc  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::SendAsync(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0xbd1  ret
```
