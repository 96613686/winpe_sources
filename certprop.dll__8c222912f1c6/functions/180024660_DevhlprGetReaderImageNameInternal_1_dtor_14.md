# _DevhlprGetReaderImageNameInternal_::_1_::dtor$14

- ea: `0x180024660`
- end: `0x18002466c`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$14`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008554`

## pseudocode

```c
void __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  std::vector<unsigned char>::_Tidy(a2 + 120);
}

```

## disassembly

```asm
0x180024660  lea     rcx, [rdx+78h]
0x180024667  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
```
