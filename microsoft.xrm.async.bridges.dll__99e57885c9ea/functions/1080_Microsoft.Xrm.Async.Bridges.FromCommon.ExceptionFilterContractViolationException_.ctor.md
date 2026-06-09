# Microsoft.Xrm.Async.Bridges.FromCommon.ExceptionFilterContractViolationException::.ctor

- ea: `0x1080`
- end: `0x1093`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExceptionFilterContractViolationException::.ctor`
- size: `19`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3570`
- `0x39e0`
- `0x3bc0`
- `0x3eb0`

## pseudocode

```c

```

## disassembly

```asm
0x1080  ldarg.0
0x1081  ldstr    aTheExceptionFi// "The exception filter {0} did not return"...
0x1086  ldarg.1
0x1087  call     string [mscorlib]System.String::Format(string, object)
0x108c  ldarg.2
0x108d  call     instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x1092  ret
```
