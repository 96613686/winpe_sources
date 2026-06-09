# Microsoft.Crm.Controls.CalendarRowData::Combine

- ea: `0xa2f0`
- end: `0xa2fd`
- name: `Microsoft.Crm.Controls.CalendarRowData::Combine`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xa2f1`: `Combine not supported`

## pseudocode

```c

```

## disassembly

```asm
0xa2f0  ldc.i4.0
0xa2f1  ldstr    aCombineNotSupp// "Combine not supported"
0xa2f6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xa2fb  ldarg.0
0xa2fc  ret
```
