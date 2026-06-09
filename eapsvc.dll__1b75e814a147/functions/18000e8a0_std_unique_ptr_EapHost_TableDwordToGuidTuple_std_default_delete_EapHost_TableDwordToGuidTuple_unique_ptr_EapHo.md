# std::unique_ptr<EapHost::TableDwordToGuidTuple,std::default_delete<EapHost::TableDwordToGuidTuple>>::~unique_ptr<EapHost::TableDwordToGuidTuple,std::default_delete<EapHost::TableDwordToGuidTuple>>(void)

- ea: `0x18000e8a0`
- end: `0x18000e905`
- name: `??1?$unique_ptr@VTableDwordToGuidTuple@EapHost@@U?$default_delete@VTableDwordToGuidTuple@EapHost@@@std@@@std@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(void ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800161b0`

## callees

- `0x180002330`
- `0x18000e7e8`
- `0x18000e8a0`

## pseudocode

```c
void __fastcall std::unique_ptr<EapHost::TableDwordToGuidTuple>::~unique_ptr<EapHost::TableDwordToGuidTuple>(
        void ***a1)
{
  void **v1; // rbx
  _QWORD *v2; // rdi
  void *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (_QWORD *)*((_QWORD *)*v1 + 1);
    while ( !*((_BYTE *)v2 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,EapHost::_NdfGuidTuple>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,EapHost::_NdfGuidTuple>,void *>>>(
        v1,
        v1,
        v2[2]);
      v3 = v2;
      v2 = (_QWORD *)*v2;
      operator delete(v3, 0x50u);
    }
    operator delete(*v1, 0x50u);
    operator delete(v1, 0x10u);
  }
}

```

## disassembly

```asm
0x18000e8a0  mov     [rsp+arg_0], rbx
0x18000e8a5  push    rdi
0x18000e8a6  sub     rsp, 20h
0x18000e8aa  mov     rbx, [rcx]
0x18000e8ad  test    rbx, rbx
0x18000e8b0  jz      short loc_18000E8FA
0x18000e8b2  mov     rax, [rbx]
0x18000e8b5  mov     rdi, [rax+8]
0x18000e8b9  jmp     short loc_18000E8DA
0x18000e8bb  mov     r8, [rdi+10h]
0x18000e8bf  mov     rdx, rbx
0x18000e8c2  mov     rcx, rbx
0x18000e8c5  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,EapHost::_NdfGuidTuple>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,EapHost::_NdfGuidTuple>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,EapHost::_NdfGuidTuple>,void *>> &,std::_Tree_node<std::pair<ulong const,EapHost::_NdfGuidTuple>,void *> *)
0x18000e8ca  mov     rcx, rdi; void *
0x18000e8cd  mov     edx, 50h ; 'P'; unsigned __int64
0x18000e8d2  mov     rdi, [rdi]
0x18000e8d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e8da  cmp     byte ptr [rdi+19h], 0
0x18000e8de  jz      short loc_18000E8BB
0x18000e8e0  mov     rcx, [rbx]; void *
0x18000e8e3  mov     edx, 50h ; 'P'; unsigned __int64
0x18000e8e8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e8ed  mov     edx, 10h; unsigned __int64
0x18000e8f2  mov     rcx, rbx; void *
0x18000e8f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e8fa  mov     rbx, [rsp+28h+arg_0]
0x18000e8ff  add     rsp, 20h
0x18000e903  pop     rdi
0x18000e904  retn
```
