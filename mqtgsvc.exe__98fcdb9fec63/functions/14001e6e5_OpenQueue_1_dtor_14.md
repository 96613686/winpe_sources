# _OpenQueue_::_1_::dtor$14

- ea: `0x14001e6e5`
- end: `0x14001e70b`
- name: `_OpenQueue_::_1_::dtor$14`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003194`
- `0x14001e6e5`

## pseudocode

```c
void __fastcall OpenQueue_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 72) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 72) &= ~1u;
    _bstr_t::~_bstr_t((_bstr_t *)(a2 + 64));
  }
}

```

## disassembly

```asm
0x14001e6e5  push    rbp
0x14001e6e7  sub     rsp, 20h
0x14001e6eb  mov     rbp, rdx
0x14001e6ee  mov     eax, [rbp+48h]
0x14001e6f1  and     eax, 1
0x14001e6f4  test    eax, eax
0x14001e6f6  jz      short loc_14001E705
0x14001e6f8  and     dword ptr [rbp+48h], 0FFFFFFFEh
0x14001e6fc  lea     rcx, [rbp+40h]; this
0x14001e700  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001e705  add     rsp, 20h
0x14001e709  pop     rbp
0x14001e70a  retn
```
