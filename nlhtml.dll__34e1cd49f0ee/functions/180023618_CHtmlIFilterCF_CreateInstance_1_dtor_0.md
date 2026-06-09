# _CHtmlIFilterCF::CreateInstance_::_1_::dtor$0

- ea: `0x180023618`
- end: `0x180023637`
- name: `_CHtmlIFilterCF::CreateInstance_::_1_::dtor$0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180014544`

## pseudocode

```c
void __fastcall CHtmlIFilterCF::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x180023618  push    rbp
0x18002361a  sub     rsp, 20h
0x18002361e  mov     rbp, rdx
0x180023621  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180023628  mov     rcx, [rbp+48h]; Block
0x18002362c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023631  add     rsp, 20h
0x180023635  pop     rbp
0x180023636  retn
```
