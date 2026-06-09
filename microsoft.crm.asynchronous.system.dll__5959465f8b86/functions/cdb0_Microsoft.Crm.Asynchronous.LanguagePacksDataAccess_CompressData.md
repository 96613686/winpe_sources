# Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::CompressData

- ea: `0xcdb0`
- end: `0xcdd1`
- name: `Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::CompressData`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xcb60`

## pseudocode

```c

```

## disassembly

```asm
0xcdb0  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0xcdb5  ldarga.s 1
0xcdb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcdbc  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xcdc1  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xcdc6  call     unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CrmCompress::Compress(unsigned int8[])
0xcdcb  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0xcdd0  ret
```
