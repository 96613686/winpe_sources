# Microsoft.Crm.Sandbox.KeyVaultClientProvider::GetExceptionMessage

- ea: `0x7e0`
- end: `0x7fb`
- name: `Microsoft.Crm.Sandbox.KeyVaultClientProvider::GetExceptionMessage`
- size: `27`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x470`
- `0x500`
- `0x590`
- `0x620`
- `0x6c0`
- `0x750`

## callees

- `0x7e0`

## pseudocode

```c

```

## disassembly

```asm
0x7e0  ldarg.0
0x7e1  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x7e6  brfalse.s loc_7F4
0x7e8  ldarg.0
0x7e9  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x7ee  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7f3  ret
0x7f4  ldarg.0
0x7f5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7fa  ret
```
