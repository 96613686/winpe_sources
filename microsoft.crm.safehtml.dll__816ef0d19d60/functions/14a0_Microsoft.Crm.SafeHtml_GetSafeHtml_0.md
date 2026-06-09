# Microsoft.Crm.SafeHtml::GetSafeHtml_0

- ea: `0x14a0`
- end: `0x14b3`
- name: `Microsoft.Crm.SafeHtml::GetSafeHtml_0`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1490`
- `0x18a0`

## callees

- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0x14a0  ldsfld   string [mscorlib]System.String::Empty
0x14a5  stloc.0
0x14a6  ldarg.2
0x14a7  ldarg.0
0x14a8  ldarg.1
0x14a9  ldloca.s 0
0x14ab  call     bool Microsoft.Crm.SafeHtml::BuildSafeHtml(string existingHtml, valuetype SafeHtmlFlags flags, [out] string& newHtml)
0x14b0  stind.i1
0x14b1  ldloc.0
0x14b2  ret
```
