# _CreateBucket_::_1_::dtor$0

- ea: `0x14000c9be`
- end: `0x14000c9dd`
- name: `_CreateBucket_::_1_::dtor$0`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140001cb8`

## pseudocode

```c
void __fastcall CreateBucket_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80), (const struct std::nothrow_t *)std::nothrow);
}

```

## disassembly

```asm
0x14000c9be  push    rbp
0x14000c9c0  sub     rsp, 20h
0x14000c9c4  mov     rbp, rdx
0x14000c9c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c9ce  mov     rcx, [rbp+50h]; void *
0x14000c9d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c9d7  add     rsp, 20h
0x14000c9db  pop     rbp
0x14000c9dc  retn
```
