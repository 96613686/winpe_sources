# std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::pair<_FILE_PARENT_PAIR *,_FILE_PARENT_PAIR *>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::pair<_FILE_PARENT_PAIR *,_FILE_PARENT_PAIR *>>,void *>>>(void)

- ea: `0x14000563c`
- end: `0x140005658`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@PEAU_FILE_PARENT_PAIR@@PEAU1@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000c766`
- `0x14000c8e1`
- `0x14000c905`

## callees

- `0x140001cb8`
- `0x14000563c`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring *,std::pair<_FILE_PARENT_PAIR *,_FILE_PARENT_PAIR *>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring *,std::pair<_FILE_PARENT_PAIR *,_FILE_PARENT_PAIR *>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x28);
}

```

## disassembly

```asm
0x14000563c  sub     rsp, 28h
0x140005640  mov     rcx, [rcx+8]; void *
0x140005644  test    rcx, rcx
0x140005647  jz      short loc_140005653
0x140005649  mov     edx, 28h ; '('; struct std::nothrow_t *
0x14000564e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005653  add     rsp, 28h
0x140005657  retn
```
