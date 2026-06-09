# std::unique_ptr<EapHost::TableDwordToGuidTuple,std::default_delete<EapHost::TableDwordToGuidTuple>>::~unique_ptr<EapHost::TableDwordToGuidTuple,std::default_delete<EapHost::TableDwordToGuidTuple>>(void)

- ea: `0x18000db5c`
- end: `0x18000dbc2`
- name: `??1?$unique_ptr@VTableDwordToGuidTuple@EapHost@@U?$default_delete@VTableDwordToGuidTuple@EapHost@@@std@@@std@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e540`

## callees

- `0x1800017a4`
- `0x18000daa4`
- `0x18000db5c`

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
      operator delete(v3);
    }
    operator delete(*v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000db5c  mov     [rsp+arg_0], rbx
0x18000db61  push    rdi
0x18000db62  sub     rsp, 20h
0x18000db66  mov     rbx, [rcx]
0x18000db69  test    rbx, rbx
0x18000db6c  jz      short loc_18000DBB6
0x18000db6e  mov     rax, [rbx]
0x18000db71  mov     rdi, [rax+8]
0x18000db75  jmp     short loc_18000DB96
0x18000db77  mov     r8, [rdi+10h]
0x18000db7b  mov     rdx, rbx
0x18000db7e  mov     rcx, rbx
0x18000db81  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKU_NdfGuidTuple@EapHost@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,EapHost::_NdfGuidTuple>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,EapHost::_NdfGuidTuple>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,EapHost::_NdfGuidTuple>,void *>> &,std::_Tree_node<std::pair<ulong const,EapHost::_NdfGuidTuple>,void *> *)
0x18000db86  mov     rcx, rdi; void *
0x18000db89  mov     edx, 50h ; 'P'; unsigned __int64
0x18000db8e  mov     rdi, [rdi]
0x18000db91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000db96  cmp     byte ptr [rdi+19h], 0
0x18000db9a  jz      short loc_18000DB77
0x18000db9c  mov     rcx, [rbx]; void *
0x18000db9f  mov     edx, 50h ; 'P'; unsigned __int64
0x18000dba4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dba9  mov     edx, 10h; unsigned __int64
0x18000dbae  mov     rcx, rbx; void *
0x18000dbb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dbb6  mov     rbx, [rsp+28h+arg_0]
0x18000dbbb  add     rsp, 20h
0x18000dbbf  pop     rdi
0x18000dbc0  retn
```
