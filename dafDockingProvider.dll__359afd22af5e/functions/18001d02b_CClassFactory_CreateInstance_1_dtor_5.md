# _CClassFactory::CreateInstance_::_1_::dtor$5

- ea: `0x18001d02b`
- end: `0x18001d04a`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$5`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001f1c`

## pseudocode

```c
void __fastcall CClassFactory::CreateInstance_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x18001d02b  push    rbp
0x18001d02d  sub     rsp, 20h
0x18001d031  mov     rbp, rdx
0x18001d034  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001d03b  mov     rcx, [rbp+20h]; Block
0x18001d03f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d044  add     rsp, 20h
0x18001d048  pop     rbp
0x18001d049  retn
```
