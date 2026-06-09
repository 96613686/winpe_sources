# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar_0

- ea: `0x19f20`
- end: `0x19f38`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar_0`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a050`
- `0x1a550`
- `0x1a5b0`
- `0x1a8e0`

## callees

- `0x19f20`
- `0x19f80`

## pseudocode

```c

```

## disassembly

```asm
0x19f20  ldarg.0
0x19f21  ldarg.1
0x19f22  ldarg.2
0x19f23  ldarg.3
0x19f24  brtrue.s loc_19F2D
0x19f26  ldstr    aFalse// "false"
0x19f2b  br.s     loc_19F32
0x19f2d  ldstr    aTrue// "true"
0x19f32  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarInternal(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x19f37  ret
```
