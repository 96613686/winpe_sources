# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::PostAsJson

- ea: `0x8c0`
- end: `0x8f8`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::PostAsJson`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x8c0  newobj   instance void class <>c__DisplayClass4_0`1<mvar<u1>>::.ctor()
0x8c5  dup
0x8c6  ldarg.0
0x8c7  stfld    class [System.Net.Http]System.Net.Http.HttpClient class <>c__DisplayClass4_0`1<mvar<u1>>::client
0x8cc  dup
0x8cd  ldarg.1
0x8ce  stfld    string class <>c__DisplayClass4_0`1<mvar<u1>>::requestUri
0x8d3  dup
0x8d4  ldarg.2
0x8d5  stfld    var<u1> class <>c__DisplayClass4_0`1<mvar<u1>>::body
0x8da  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> class <>c__DisplayClass4_0`1<mvar<u1>>::<PostAsJson>b__0()
0x8e0  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>>::.ctor(object, native int)
0x8e5  call     T0x2B000007
0x8ea  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x8ef  stloc.0
0x8f0  ldloca.s 0
0x8f2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x8f7  ret
```
