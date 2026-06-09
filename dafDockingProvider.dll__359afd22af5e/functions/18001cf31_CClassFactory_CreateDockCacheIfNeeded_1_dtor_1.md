# _CClassFactory::CreateDockCacheIfNeeded_::_1_::dtor$1

- ea: `0x18001cf31`
- end: `0x18001cf50`
- name: `_CClassFactory::CreateDockCacheIfNeeded_::_1_::dtor$1`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001f1c`

## pseudocode

```c
void __fastcall CClassFactory::CreateDockCacheIfNeeded_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x18001cf31  push    rbp
0x18001cf33  sub     rsp, 20h
0x18001cf37  mov     rbp, rdx
0x18001cf3a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001cf41  mov     rcx, [rbp+50h]; Block
0x18001cf45  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001cf4a  add     rsp, 20h
0x18001cf4e  pop     rbp
0x18001cf4f  retn
```
