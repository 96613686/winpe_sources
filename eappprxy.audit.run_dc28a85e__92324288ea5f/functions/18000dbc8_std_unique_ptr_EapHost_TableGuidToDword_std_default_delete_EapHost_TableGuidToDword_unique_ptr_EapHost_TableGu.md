# std::unique_ptr<EapHost::TableGuidToDword,std::default_delete<EapHost::TableGuidToDword>>::~unique_ptr<EapHost::TableGuidToDword,std::default_delete<EapHost::TableGuidToDword>>(void)

- ea: `0x18000dbc8`
- end: `0x18000dc2e`
- name: `??1?$unique_ptr@VTableGuidToDword@EapHost@@U?$default_delete@VTableGuidToDword@EapHost@@@std@@@std@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e4f0`

## callees

- `0x1800017a4`
- `0x18000db00`
- `0x18000dbc8`

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
      operator delete(v3);
    }
    operator delete(*v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000dbc8  mov     [rsp+arg_0], rbx
0x18000dbcd  push    rdi
0x18000dbce  sub     rsp, 20h
0x18000dbd2  mov     rbx, [rcx]
0x18000dbd5  test    rbx, rbx
0x18000dbd8  jz      short loc_18000DC22
0x18000dbda  mov     rax, [rbx]
0x18000dbdd  mov     rdi, [rax+8]
0x18000dbe1  jmp     short loc_18000DC02
0x18000dbe3  mov     r8, [rdi+10h]
0x18000dbe7  mov     rdx, rbx
0x18000dbea  mov     rcx, rbx
0x18000dbed  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>> &,std::_Tree_node<std::pair<_GUID const,ulong>,void *> *)
0x18000dbf2  mov     rcx, rdi; void *
0x18000dbf5  mov     edx, 30h ; '0'; unsigned __int64
0x18000dbfa  mov     rdi, [rdi]
0x18000dbfd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc02  cmp     byte ptr [rdi+19h], 0
0x18000dc06  jz      short loc_18000DBE3
0x18000dc08  mov     rcx, [rbx]; void *
0x18000dc0b  mov     edx, 30h ; '0'; unsigned __int64
0x18000dc10  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc15  mov     edx, 10h; unsigned __int64
0x18000dc1a  mov     rcx, rbx; void *
0x18000dc1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc22  mov     rbx, [rsp+28h+arg_0]
0x18000dc27  add     rsp, 20h
0x18000dc2b  pop     rdi
0x18000dc2c  retn
```
