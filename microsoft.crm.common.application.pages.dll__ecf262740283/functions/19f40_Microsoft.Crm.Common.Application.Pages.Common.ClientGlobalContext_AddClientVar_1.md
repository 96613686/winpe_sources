# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar_1

- ea: `0x19f40`
- end: `0x19f55`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar_1`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1a050`
- `0x1a5b0`
- `0x1a8e0`

## callees

- `0x19f80`

## pseudocode

```c

```

## disassembly

```asm
0x19f40  ldarg.0
0x19f41  ldarg.1
0x19f42  ldarg.2
0x19f43  ldarga.s 3
0x19f45  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19f4a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x19f4f  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarInternal(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x19f54  ret
```
