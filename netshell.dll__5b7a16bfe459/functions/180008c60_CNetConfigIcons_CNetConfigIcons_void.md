# CNetConfigIcons::~CNetConfigIcons(void)

- ea: `0x180008c60`
- end: `0x180008d65`
- name: `??1CNetConfigIcons@@UEAA@XZ`
- size: `261`
- prototype: `void __fastcall(CNetConfigIcons *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800438a0`

## callees

- `0x180008c60`
- `0x18001717c`
- `0x18001773c`
- `0x18001e5b0`
- `0x180060960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d10`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d10`
- `GDI32!DeleteObject` at `0x180008d06`
- `GDI32!DeleteObject` at `0x180008d06`

## pseudocode

```c
void __fastcall CNetConfigIcons::~CNetConfigIcons(CNetConfigIcons *this)
{
  __int64 *v2; // rbx
  __int64 *v3; // rdi
  __int64 **v4; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CNetConfigIcons::`vftable';
  v2 = (__int64 *)**((_QWORD **)this + 7);
  while ( 1 )
  {
    v3 = (__int64 *)*((_QWORD *)this + 7);
    if ( v2 == v3 )
      break;
    ImageList_Destroy((HIMAGELIST)v2[5]);
    v4 = (__int64 **)v2[2];
    if ( *((_BYTE *)v4 + 25) )
    {
      for ( i = (__int64 *)v2[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v2 != (__int64 *)i[2] )
          break;
        v2 = i;
      }
      v2 = i;
    }
    else
    {
      v2 = (__int64 *)v2[2];
      for ( j = *v4; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v2 = j;
    }
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,_IMAGELIST *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,_IMAGELIST *>,void *>>>(
    (char *)this + 56,
    (char *)this + 56,
    v3[1]);
  v3[1] = (__int64)v3;
  *v3 = (__int64)v3;
  v3[2] = (__int64)v3;
  *((_QWORD *)this + 8) = 0;
  v7 = (void *)*((_QWORD *)this + 13);
  if ( v7 )
    DeleteObject(v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *>>>(
    (char *)this + 80,
    (char *)this + 80,
    *(_QWORD *)(*((_QWORD *)this + 10) + 8LL));
  operator delete(*((void **)this + 10), 0x48u);
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,_IMAGELIST *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,_IMAGELIST *>,void *>>>(
    (char *)this + 56,
    (char *)this + 56,
    *(_QWORD *)(*((_QWORD *)this + 7) + 8LL));
  operator delete(*((void **)this + 7), 0x30u);
}

```

## disassembly

```asm
0x180008c60  push    rbx
0x180008c62  push    rsi
0x180008c63  push    rdi
0x180008c64  push    r14
0x180008c66  sub     rsp, 28h
0x180008c6a  mov     r14, rcx
0x180008c6d  lea     rax, ??_7CNetConfigIcons@@6B@; const CNetConfigIcons::`vftable'
0x180008c74  mov     [rcx], rax
0x180008c77  mov     rbx, [rcx+38h]
0x180008c7b  mov     rbx, [rbx]
0x180008c7e  mov     rdi, [r14+38h]
0x180008c82  cmp     rbx, rdi
0x180008c85  jz      short loc_180008CD9
0x180008c87  mov     rcx, [rbx+28h]; himl
0x180008c8b  call    ImageList_Destroy
0x180008c90  mov     rcx, [rbx+10h]
0x180008c94  cmp     byte ptr [rcx+19h], 0
0x180008c98  jz      short loc_180008CBC
0x180008c9a  mov     rax, [rbx+8]
0x180008c9e  cmp     byte ptr [rax+19h], 0
0x180008ca2  jnz     short loc_180008CB7
0x180008ca4  cmp     rbx, [rax+10h]
0x180008ca8  jnz     short loc_180008CB7
0x180008caa  mov     rbx, rax
0x180008cad  mov     rax, [rax+8]
0x180008cb1  cmp     byte ptr [rax+19h], 0
0x180008cb5  jz      short loc_180008CA4
0x180008cb7  mov     rbx, rax
0x180008cba  jmp     short loc_180008C7E
0x180008cbc  mov     rbx, rcx
0x180008cbf  mov     rcx, [rcx]
0x180008cc2  cmp     byte ptr [rcx+19h], 0
0x180008cc6  jnz     short loc_180008C7E
0x180008cc8  mov     rbx, rcx
0x180008ccb  mov     rax, [rcx]
0x180008cce  mov     rcx, rax
0x180008cd1  cmp     byte ptr [rax+19h], 0
0x180008cd5  jz      short loc_180008CC8
0x180008cd7  jmp     short loc_180008C7E
0x180008cd9  mov     r8, [rdi+8]
0x180008cdd  lea     rdx, [r14+38h]
0x180008ce1  lea     rcx, [r14+38h]
0x180008ce5  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,_IMAGELIST *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,_IMAGELIST *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,_IMAGELIST *>,void *>> &,std::_Tree_node<std::pair<ulong const,_IMAGELIST *>,void *> *)
0x180008cea  mov     [rdi+8], rdi
0x180008cee  mov     [rdi], rdi
0x180008cf1  mov     [rdi+10h], rdi
0x180008cf5  mov     qword ptr [r14+40h], 0
0x180008cfd  mov     rcx, [r14+68h]; ho
0x180008d01  test    rcx, rcx
0x180008d04  jz      short loc_180008D0C
0x180008d06  call    cs:__imp_DeleteObject
0x180008d0c  lea     rcx, [r14+8]; lpCriticalSection
0x180008d10  call    cs:__imp_DeleteCriticalSection
0x180008d16  mov     r8, [r14+50h]
0x180008d1a  mov     r8, [r8+8]
0x180008d1e  lea     rdx, [r14+50h]
0x180008d22  lea     rcx, [r14+50h]
0x180008d26  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &,std::_Tree_node<std::pair<std::wstring const,ulong>,void *> *)
0x180008d2b  mov     edx, 48h ; 'H'; unsigned __int64
0x180008d30  mov     rcx, [r14+50h]; void *
0x180008d34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d39  mov     r8, [r14+38h]
0x180008d3d  mov     r8, [r8+8]
0x180008d41  lea     rdx, [r14+38h]
0x180008d45  lea     rcx, [r14+38h]
0x180008d49  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,_IMAGELIST *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,_IMAGELIST *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,_IMAGELIST *>,void *>> &,std::_Tree_node<std::pair<ulong const,_IMAGELIST *>,void *> *)
0x180008d4e  mov     edx, 30h ; '0'; unsigned __int64
0x180008d53  mov     rcx, [r14+38h]; void *
0x180008d57  add     rsp, 28h
0x180008d5b  pop     r14
0x180008d5d  pop     rdi
0x180008d5e  pop     rsi
0x180008d5f  pop     rbx
0x180008d60  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
