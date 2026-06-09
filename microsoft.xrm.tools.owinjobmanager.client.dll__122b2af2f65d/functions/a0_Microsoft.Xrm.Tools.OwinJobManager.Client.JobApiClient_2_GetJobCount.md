# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetJobCount

- ea: `0xa0`
- end: `0xc3`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetJobCount`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xa0  ldarg.0
0xa1  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0xa6  ldstr    a0Count// "{0}/count"
0xab  ldarg.0
0xac  ldfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0xb1  call     string [mscorlib]System.String::Format(string, object)
0xb6  ldc.i4.s 0xA
0xb8  ldc.i4   0xBB8
0xbd  call     T0x2B000001
0xc2  ret
```
