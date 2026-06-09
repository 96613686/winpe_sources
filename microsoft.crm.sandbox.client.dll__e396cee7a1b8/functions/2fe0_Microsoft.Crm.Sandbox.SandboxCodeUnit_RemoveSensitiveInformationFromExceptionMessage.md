# Microsoft.Crm.Sandbox.SandboxCodeUnit::RemoveSensitiveInformationFromExceptionMessage

- ea: `0x2fe0`
- end: `0x2ff0`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::RemoveSensitiveInformationFromExceptionMessage`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x23d0`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldstr    aRedacted// "redacted"
0x2fe5  stloc.0
0x2fe6  ldarg.1
0x2fe7  ldarg.2
0x2fe8  ldloc.0
0x2fe9  ldc.i4.1
0x2fea  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2fef  ret
```
