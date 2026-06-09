# _TokenizedString::TokenizedString_::_1_::dtor$0

- ea: `0x14000e0b5`
- end: `0x14000e0c1`
- name: `_TokenizedString::TokenizedString_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400039d0`

## pseudocode

```c
__int64 __fastcall TokenizedString::TokenizedString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short const *>::~vector<unsigned short const *>(*(_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x14000e0b5  mov     rcx, [rdx+60h]
0x14000e0bc  jmp     ??1?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::~vector<ushort const *>(void)
```
