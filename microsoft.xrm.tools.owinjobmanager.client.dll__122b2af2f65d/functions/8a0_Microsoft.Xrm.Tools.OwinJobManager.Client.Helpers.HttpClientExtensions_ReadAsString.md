# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::ReadAsString

- ea: `0x8a0`
- end: `0x8bf`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::ReadAsString`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x900`
- `0x940`

## pseudocode

```c

```

## disassembly

```asm
0x8a0  ldarg.0
0x8a1  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0x8a7  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<string>>::.ctor(object, native int)
0x8ac  call     T0x2B000008
0x8b1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x8b6  stloc.0
0x8b7  ldloca.s 0
0x8b9  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x8be  ret
```
