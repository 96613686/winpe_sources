# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::Send

- ea: `0x860`
- end: `0x891`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::Send`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x900`

## callees

- `0xbb0`

## pseudocode

```c

```

## disassembly

```asm
0x860  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x865  dup
0x866  ldarg.0
0x867  stfld    class [System.Net.Http]System.Net.Http.HttpClient <>c__DisplayClass2_0::client
0x86c  dup
0x86d  ldarg.1
0x86e  stfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass2_0::request
0x873  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <>c__DisplayClass2_0::<Send>b__0()
0x879  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>>::.ctor(object, native int)
0x87e  call     T0x2B000007
0x883  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x888  stloc.0
0x889  ldloca.s 0
0x88b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x890  ret
```
