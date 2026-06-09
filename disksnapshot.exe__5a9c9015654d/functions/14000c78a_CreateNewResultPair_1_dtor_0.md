# _CreateNewResultPair_::_1_::dtor$0

- ea: `0x14000c78a`
- end: `0x14000c7a9`
- name: `_CreateNewResultPair_::_1_::dtor$0`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140001cb8`

## pseudocode

```c
void __fastcall CreateNewResultPair_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 96), (const struct std::nothrow_t *)std::nothrow);
}

```

## disassembly

```asm
0x14000c78a  push    rbp
0x14000c78c  sub     rsp, 20h
0x14000c790  mov     rbp, rdx
0x14000c793  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c79a  mov     rcx, [rbp+60h]; void *
0x14000c79e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c7a3  add     rsp, 20h
0x14000c7a7  pop     rbp
0x14000c7a8  retn
```
