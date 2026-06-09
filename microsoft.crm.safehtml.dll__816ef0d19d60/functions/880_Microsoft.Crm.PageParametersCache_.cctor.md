# Microsoft.Crm.PageParametersCache::.cctor

- ea: `0x880`
- end: `0x894`
- name: `Microsoft.Crm.PageParametersCache::.cctor`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x880  ldc.r8   1.0
0x889  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x88e  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.PageParametersCache::LockTimeout
0x893  ret
```
