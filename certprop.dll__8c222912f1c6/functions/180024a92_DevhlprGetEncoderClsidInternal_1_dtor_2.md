# _DevhlprGetEncoderClsidInternal_::_1_::dtor$2

- ea: `0x180024a92`
- end: `0x180024a9e`
- name: `_DevhlprGetEncoderClsidInternal_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008554`

## pseudocode

```c
void __fastcall DevhlprGetEncoderClsidInternal_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::vector<unsigned char>::_Tidy(a2 + 56);
}

```

## disassembly

```asm
0x180024a92  lea     rcx, [rdx+38h]
0x180024a99  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
```
