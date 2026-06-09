# Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::UrlsHaveSamePath

- ea: `0x44a0`
- end: `0x44cd`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::UrlsHaveSamePath`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3dd0`

## pseudocode

```c

```

## disassembly

```asm
0x44a0  ldarg.0
0x44a1  ldc.i4.1
0x44a2  newarr   [mscorlib]System.Char
0x44a7  dup
0x44a8  ldc.i4.0
0x44a9  ldc.i4.s 0x3F
0x44ab  stelem.i2
0x44ac  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x44b1  ldc.i4.0
0x44b2  ldelem.ref
0x44b3  ldarg.1
0x44b4  ldc.i4.1
0x44b5  newarr   [mscorlib]System.Char
0x44ba  dup
0x44bb  ldc.i4.0
0x44bc  ldc.i4.s 0x3F
0x44be  stelem.i2
0x44bf  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x44c4  ldc.i4.0
0x44c5  ldelem.ref
0x44c6  ldc.i4.5
0x44c7  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x44cc  ret
```
