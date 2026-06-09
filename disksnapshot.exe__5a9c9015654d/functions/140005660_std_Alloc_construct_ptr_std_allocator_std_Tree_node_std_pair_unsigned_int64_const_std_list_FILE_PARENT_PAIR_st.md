# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *,std::allocator<_FILE_PARENT_PAIR *>> *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *,std::allocator<_FILE_PARENT_PAIR *>> *>,void *>>>(void)

- ea: `0x140005660`
- end: `0x14000567c`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000c778`
- `0x14000c846`

## callees

- `0x140001cb8`
- `0x140005660`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, (const struct std::nothrow_t *)0x30);
}

```

## disassembly

```asm
0x140005660  sub     rsp, 28h
0x140005664  mov     rcx, [rcx+8]; void *
0x140005668  test    rcx, rcx
0x14000566b  jz      short loc_140005677
0x14000566d  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x140005672  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005677  add     rsp, 28h
0x14000567b  retn
```
