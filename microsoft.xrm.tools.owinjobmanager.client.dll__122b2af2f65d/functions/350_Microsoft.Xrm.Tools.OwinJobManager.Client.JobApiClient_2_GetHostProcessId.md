# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetHostProcessId

- ea: `0x350`
- end: `0x373`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetHostProcessId`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x350  ldarg.0
0x351  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x356  ldstr    a0ProcessId// "{0}/process/id"
0x35b  ldarg.0
0x35c  ldfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0x361  call     string [mscorlib]System.String::Format(string, object)
0x366  ldc.i4.s 0xA
0x368  ldc.i4   0xBB8
0x36d  call     T0x2B000001
0x372  ret
```
