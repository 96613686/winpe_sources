# Microsoft.Crm.Asynchronous.ImportOperation::CompressData

- ea: `0xab10`
- end: `0xab26`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::CompressData`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1d5e0`

## pseudocode

```c

```

## disassembly

```asm
0xab10  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0xab15  ldarg.0
0xab16  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xab1b  call     unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CrmCompress::Compress(unsigned int8[])
0xab20  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0xab25  ret
```
