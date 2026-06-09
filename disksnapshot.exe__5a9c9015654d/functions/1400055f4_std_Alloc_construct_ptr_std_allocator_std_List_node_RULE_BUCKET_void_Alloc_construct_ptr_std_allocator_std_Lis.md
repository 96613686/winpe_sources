# std::_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>(void)

- ea: `0x1400055f4`
- end: `0x140005610`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAU_RULE_BUCKET@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000c7af`
- `0x14000c834`
- `0x14000c9e3`

## callees

- `0x140001cb8`
- `0x1400055f4`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<_RULE_BUCKET *,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x18);
}

```

## disassembly

```asm
0x1400055f4  sub     rsp, 28h
0x1400055f8  mov     rcx, [rcx+8]; void *
0x1400055fc  test    rcx, rcx
0x1400055ff  jz      short loc_14000560B
0x140005601  mov     edx, 18h; struct std::nothrow_t *
0x140005606  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000560b  add     rsp, 28h
0x14000560f  retn
```
