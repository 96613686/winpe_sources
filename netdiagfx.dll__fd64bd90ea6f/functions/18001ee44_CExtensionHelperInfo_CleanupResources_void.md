# CExtensionHelperInfo::CleanupResources(void)

- ea: `0x18001ee44`
- end: `0x18001ef04`
- name: `?CleanupResources@CExtensionHelperInfo@@QEAAXXZ`
- size: `192`
- prototype: `void __fastcall(CExtensionHelperInfo *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e9ec`

## callees

- `0x180005048`
- `0x180016780`
- `0x18001ee44`
- `0x18001f188`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ee76`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ee76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eed4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eee5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eed4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eee5`

## pseudocode

```c
void __fastcall CExtensionHelperInfo::CleanupResources(CExtensionHelperInfo *this)
{
  _QWORD **v1; // r14
  _QWORD *v3; // rbx
  struct tagHELPER_ATTRIBUTE *v4; // rdi
  __int64 v5; // rcx
  _QWORD *i; // rax
  unsigned int j; // ebx

  v1 = (_QWORD **)((char *)this + 72);
  if ( *((_QWORD *)this + 10) )
  {
    v3 = (_QWORD *)**v1;
    while ( v3 != *v1 )
    {
      v4 = (struct tagHELPER_ATTRIBUTE *)v3[5];
      FreeMatchValue(v4);
      operator delete(v4);
      if ( !*((_BYTE *)v3 + 25) )
      {
        v5 = v3[2];
        if ( *(_BYTE *)(v5 + 25) )
        {
          for ( i = (_QWORD *)v3[1]; !*((_BYTE *)i + 25) && v3 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
            v3 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min((_QWORD *)v5);
        }
        v3 = i;
      }
    }
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CHelperInfo *>>,0>>::clear(v1);
  }
  if ( *((_QWORD *)this + 7) )
  {
    for ( j = 0; j < *((_DWORD *)this + 16); ++j )
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 7) + 16LL * j));
    CoTaskMemFree(*((LPVOID *)this + 7));
    *((_QWORD *)this + 7) = 0;
    *((_DWORD *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001ee44  push    rbx
0x18001ee46  push    rsi
0x18001ee47  push    rdi
0x18001ee48  push    r14
0x18001ee4a  sub     rsp, 28h
0x18001ee4e  lea     r14, [rcx+48h]
0x18001ee52  mov     rsi, rcx
0x18001ee55  cmp     qword ptr [r14+8], 0
0x18001ee5a  jz      short loc_18001EEB9
0x18001ee5c  mov     rbx, [r14]
0x18001ee5f  mov     rbx, [rbx]
0x18001ee62  cmp     rbx, [r14]
0x18001ee65  jz      short loc_18001EEB1
0x18001ee67  mov     rdi, [rbx+28h]
0x18001ee6b  mov     rcx, rdi; struct tagHELPER_ATTRIBUTE *
0x18001ee6e  call    ?FreeMatchValue@@YAXPEAUtagHELPER_ATTRIBUTE@@@Z; FreeMatchValue(tagHELPER_ATTRIBUTE *)
0x18001ee73  mov     rcx, rdi
0x18001ee76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ee7c  cmp     byte ptr [rbx+19h], 0
0x18001ee80  jnz     short loc_18001EE62
0x18001ee82  mov     rcx, [rbx+10h]
0x18001ee86  cmp     byte ptr [rcx+19h], 0
0x18001ee8a  jnz     short loc_18001EE93
0x18001ee8c  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x18001ee91  jmp     short loc_18001EEAC
0x18001ee93  mov     rax, [rbx+8]
0x18001ee97  jmp     short loc_18001EEA6
0x18001ee99  cmp     rbx, [rax+10h]
0x18001ee9d  jnz     short loc_18001EEAC
0x18001ee9f  mov     rbx, rax
0x18001eea2  mov     rax, [rax+8]
0x18001eea6  cmp     byte ptr [rax+19h], 0
0x18001eeaa  jz      short loc_18001EE99
0x18001eeac  mov     rbx, rax
0x18001eeaf  jmp     short loc_18001EE62
0x18001eeb1  mov     rcx, r14
0x18001eeb4  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperInfo *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperInfo *>>,0>>::clear(void)
0x18001eeb9  cmp     qword ptr [rsi+38h], 0
0x18001eebe  jz      short loc_18001EEFA
0x18001eec0  xor     ebx, ebx
0x18001eec2  cmp     [rsi+40h], ebx
0x18001eec5  jbe     short loc_18001EEE1
0x18001eec7  mov     rcx, [rsi+38h]
0x18001eecb  mov     eax, ebx
0x18001eecd  add     rax, rax
0x18001eed0  mov     rcx, [rcx+rax*8]; pv
0x18001eed4  call    cs:__imp_CoTaskMemFree
0x18001eeda  inc     ebx
0x18001eedc  cmp     ebx, [rsi+40h]
0x18001eedf  jb      short loc_18001EEC7
0x18001eee1  mov     rcx, [rsi+38h]; pv
0x18001eee5  call    cs:__imp_CoTaskMemFree
0x18001eeeb  mov     qword ptr [rsi+38h], 0
0x18001eef3  mov     dword ptr [rsi+40h], 0
0x18001eefa  add     rsp, 28h
0x18001eefe  pop     r14
0x18001ef00  pop     rdi
0x18001ef01  pop     rsi
0x18001ef02  pop     rbx
0x18001ef03  retn
```
