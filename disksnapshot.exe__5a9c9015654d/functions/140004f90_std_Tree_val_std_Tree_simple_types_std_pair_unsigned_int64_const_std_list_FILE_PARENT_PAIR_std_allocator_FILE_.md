# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *,std::allocator<_FILE_PARENT_PAIR *>> *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *,std::allocator<_FILE_PARENT_PAIR *>> *>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *,std::allocator<_FILE_PARENT_PAIR *>> *>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *,std::allocator<_FILE_PARENT_PAIR *>> *>,void *> *)

- ea: `0x140004f90`
- end: `0x140004fe4`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@PEAX@1@@Z`
- size: `84`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140004f90`
- `0x140005e10`

## callees

- `0x140001cb8`
- `0x140004f90`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  void *v6; // rcx

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = v3;
      v3 = (_QWORD *)*v3;
      operator delete(v6, (const struct std::nothrow_t *)0x30);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x140004f90  mov     [rsp+arg_0], rbx
0x140004f95  mov     [rsp+arg_8], rsi
0x140004f9a  push    rdi
0x140004f9b  sub     rsp, 20h
0x140004f9f  cmp     byte ptr [r8+19h], 0
0x140004fa4  mov     rbx, r8
0x140004fa7  mov     rdi, rdx
0x140004faa  mov     rsi, rcx
0x140004fad  jnz     short loc_140004FD4
0x140004faf  mov     r8, [rbx+10h]
0x140004fb3  mov     rdx, rdi
0x140004fb6  mov     rcx, rsi
0x140004fb9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAV?$list@PEAU_FILE_PARENT_PAIR@@V?$allocator@PEAU_FILE_PARENT_PAIR@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::list<_FILE_PARENT_PAIR *> *>,void *> *)
0x140004fbe  mov     rcx, rbx; void *
0x140004fc1  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x140004fc6  mov     rbx, [rbx]
0x140004fc9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004fce  cmp     byte ptr [rbx+19h], 0
0x140004fd2  jz      short loc_140004FAF
0x140004fd4  mov     rbx, [rsp+28h+arg_0]
0x140004fd9  mov     rsi, [rsp+28h+arg_8]
0x140004fde  add     rsp, 20h
0x140004fe2  pop     rdi
0x140004fe3  retn
```
