# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::Get

- ea: `0x900`
- end: `0x933`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::Get`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x860`
- `0x8a0`
- `0x900`

## pseudocode

```c

```

## disassembly

```asm
0x900  call     class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpMethod::get_Get()
0x905  ldarg.1
0x906  newobj   instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::.ctor(class [System.Net.Http]System.Net.Http.HttpMethod, string)
0x90b  stloc.0
0x90c  ldarg.0
0x90d  ldloc.0
0x90e  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::Send(class [System.Net.Http]System.Net.Http.HttpClient client, class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x913  stloc.1
0x914  ldloc.1
0x915  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x91a  call     string Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::ReadAsString(class [System.Net.Http]System.Net.Http.HttpContent content)
0x91f  call     T0x2B000009
0x924  stloc.2
0x925  leave.s  loc_931
0x927  ldloc.1
0x928  brfalse.s loc_930
0x92a  ldloc.1
0x92b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x930  endfinally
0x931  ldloc.2
0x932  ret
```
