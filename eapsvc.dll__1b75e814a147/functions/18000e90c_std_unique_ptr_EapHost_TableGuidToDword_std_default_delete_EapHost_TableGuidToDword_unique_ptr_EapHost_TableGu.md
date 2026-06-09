# std::unique_ptr<EapHost::TableGuidToDword,std::default_delete<EapHost::TableGuidToDword>>::~unique_ptr<EapHost::TableGuidToDword,std::default_delete<EapHost::TableGuidToDword>>(void)

- ea: `0x18000e90c`
- end: `0x18000e971`
- name: `??1?$unique_ptr@VTableGuidToDword@EapHost@@U?$default_delete@VTableGuidToDword@EapHost@@@std@@@std@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(void ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180016160`

## callees

- `0x180002330`
- `0x18000e844`
- `0x18000e90c`

## pseudocode

```c
void __fastcall std::unique_ptr<EapHost::TableGuidToDword>::~unique_ptr<EapHost::TableGuidToDword>(void ***a1)
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
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,unsigned long>,void *>>>(
        v1,
        v1,
        v2[2]);
      v3 = v2;
      v2 = (_QWORD *)*v2;
      operator delete(v3, 0x30u);
    }
    operator delete(*v1, 0x30u);
    operator delete(v1, 0x10u);
  }
}

```

## disassembly

```asm
0x18000e90c  mov     [rsp+arg_0], rbx
0x18000e911  push    rdi
0x18000e912  sub     rsp, 20h
0x18000e916  mov     rbx, [rcx]
0x18000e919  test    rbx, rbx
0x18000e91c  jz      short loc_18000E966
0x18000e91e  mov     rax, [rbx]
0x18000e921  mov     rdi, [rax+8]
0x18000e925  jmp     short loc_18000E946
0x18000e927  mov     r8, [rdi+10h]
0x18000e92b  mov     rdx, rbx
0x18000e92e  mov     rcx, rbx
0x18000e931  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>> &,std::_Tree_node<std::pair<_GUID const,ulong>,void *> *)
0x18000e936  mov     rcx, rdi; void *
0x18000e939  mov     edx, 30h ; '0'; unsigned __int64
0x18000e93e  mov     rdi, [rdi]
0x18000e941  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e946  cmp     byte ptr [rdi+19h], 0
0x18000e94a  jz      short loc_18000E927
0x18000e94c  mov     rcx, [rbx]; void *
0x18000e94f  mov     edx, 30h ; '0'; unsigned __int64
0x18000e954  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e959  mov     edx, 10h; unsigned __int64
0x18000e95e  mov     rcx, rbx; void *
0x18000e961  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e966  mov     rbx, [rsp+28h+arg_0]
0x18000e96b  add     rsp, 20h
0x18000e96f  pop     rdi
0x18000e970  retn
```
