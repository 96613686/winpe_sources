# CMVUISelection2::Get(_MVUIITem *)

- ea: `0x180027220`
- end: `0x18002749e`
- name: `?Get@CMVUISelection2@@UEAAJPEAU_MVUIITem@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(CMVUISelection2 *__hidden this, struct _MVUIITem *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076a4`
- `0x180010084`
- `0x180027220`
- `0x1800276b0`
- `0x180027ab4`
- `0x180027b08`
- `0x18002a190`
- `0x18002b1a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027312`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002731c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002736f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027379`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027399`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800273a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027400`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002740a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027448`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027452`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027312`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002731c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002736f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027379`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027399`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800273a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027400`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002740a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027448`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002741b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002741b`

## pseudocode

```c
__int64 __fastcall CMVUISelection2::Get(CMVUISelection2 *this, struct _MVUIITem *a2)
{
  __int64 result; // rax
  unsigned int i; // esi
  ProfileSelection **v6; // r15
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *KeyValue; // rdi
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rdx
  signed __int64 v12; // rdi
  int v13; // ecx
  int v14; // r15d
  void **v15; // rdi
  ProfileSelection **v16; // rax
  ProfileSelection *v17; // rsi
  void **v18; // rdi
  void **v19; // rdi
  const unsigned __int16 *v20; // rax
  int v21; // eax
  const char *v22; // r9
  unsigned int v23; // edi
  void **v24; // rbx
  void **v25; // rbx
  ProfileSelection *v26[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pv; // [rsp+68h] [rbp+10h] BYREF
  void **v29; // [rsp+70h] [rbp+18h] BYREF

  if ( a2 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      *((_QWORD *)a2 + 1) = 0;
      *(_DWORD *)a2 = -1;
      pv = 0;
      try
      {
        ProfileSelection::Query(v26, **((_QWORD **)this + 3));
        if ( v26[0] )
        {
          for ( i = 0; i < CandidateList::GetCount(*((CandidateList **)this + 3)); ++i )
          {
            v6 = (ProfileSelection **)CandidateList::GetAt(*((_QWORD *)this + 3), &v29, i);
            KeyValue = ProfileSelection::GetKeyValue(v26[0], v7);
            v10 = ProfileSelection::GetKeyValue(*v6, v9);
            v12 = (char *)KeyValue - (char *)v10;
            do
            {
              v13 = *(const unsigned __int16 *)((char *)v10 + v12);
              v14 = *v10 - v13;
              if ( v14 )
                break;
              ++v10;
            }
            while ( v13 );
            v15 = v29;
            if ( v29 )
            {
              std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(v29);
              operator delete(*v15);
              operator delete(v15);
            }
            if ( !v14 )
            {
              if ( i != -1 )
                goto LABEL_23;
              break;
            }
          }
        }
        v16 = (ProfileSelection **)CandidateList::GetAt(*((_QWORD *)this + 3), &v29, 0);
        if ( v26 != v16 )
        {
          v17 = *v16;
          *v16 = 0;
          v18 = (void **)v26[0];
          if ( v17 != v26[0] )
          {
            if ( v26[0] )
            {
              std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear((_QWORD *)v26[0]);
              operator delete(*v18);
              operator delete(v18);
            }
            v26[0] = v17;
          }
        }
        v19 = v29;
        if ( v29 )
        {
          std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(v29);
          operator delete(*v19);
          operator delete(v19);
        }
        i = 0;
LABEL_23:
        pv = 0;
        v20 = ProfileSelection::GetKeyValue(v26[0], v11);
        v21 = CoAllocString(v20, (unsigned __int16 **)&pv);
        v23 = v21;
        if ( v21 >= 0 )
        {
          *((_QWORD *)a2 + 1) = pv;
          *(_DWORD *)a2 = i;
          v25 = (void **)v26[0];
          if ( v26[0] )
          {
            std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear((_QWORD *)v26[0]);
            operator delete(*v25);
            operator delete(v25);
          }
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B7,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
            (const char *)(unsigned int)v21,
            (int)v26[0]);
          v24 = (void **)v26[0];
          if ( v26[0] )
          {
            std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear((_QWORD *)v26[0]);
            operator delete(*v24);
            operator delete(v24);
          }
          if ( pv )
            CoTaskMemFree(pv);
          result = v23;
        }
      }
      catch ( ... )
      {
        LODWORD(pv) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1BE,
                        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
                        v22);
        return (unsigned int)pv;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
        (const char *)0x8007139FLL,
        (int)v26[0]);
      return 2147947423LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)0x80004003LL,
      (int)v26[0]);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180027220  mov     [rsp+arg_0], rbx
0x180027225  push    rsi
0x180027226  push    rdi
0x180027227  push    r12
0x180027229  push    r14
0x18002722b  push    r15
0x18002722d  sub     rsp, 30h
0x180027231  mov     r12, rdx
0x180027234  mov     r14, rcx
0x180027237  test    rdx, rdx
0x18002723a  jnz     short loc_180027261
0x18002723c  mov     rcx, [rsp+58h]; this
0x180027241  mov     ebx, 80004003h
0x180027246  mov     r9d, ebx; char *
0x180027249  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180027250  mov     edx, 199h; void *
0x180027255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002725a  mov     eax, ebx
0x18002725c  jmp     loc_180027483
0x180027261  cmp     qword ptr [rcx+18h], 0
0x180027266  jz      loc_18002745D
0x18002726c  mov     qword ptr [rdx+8], 0
0x180027274  mov     dword ptr [rdx], 0FFFFFFFFh
0x18002727a  xor     ebx, ebx
0x18002727c  mov     [rsp+58h+pv], rbx
0x180027281  mov     rdx, [rcx+18h]
0x180027285  lea     r8, [rdx+8]
0x180027289  cmp     qword ptr [r8+18h], 8
0x18002728e  jb      short loc_180027293
0x180027290  mov     r8, [r8]
0x180027293  mov     rdx, [rdx]
0x180027296  lea     rcx, [rsp+58h+var_38]
0x18002729b  call    ?Query@ProfileSelection@@SA?AV?$unique_ptr@VProfileSelection@@U?$default_delete@VProfileSelection@@@std@@@std@@PEAUIMVCellularV2@@PEBG@Z; ProfileSelection::Query(IMVCellularV2 *,ushort const *)
0x1800272a0  nop
0x1800272a1  cmp     [rsp+58h+var_38], 0
0x1800272a7  jz      loc_180027330
0x1800272ad  xor     esi, esi
0x1800272af  mov     rcx, [r14+18h]; this
0x1800272b3  call    ?GetCount@CandidateList@@QEAAKXZ; CandidateList::GetCount(void)
0x1800272b8  cmp     esi, eax
0x1800272ba  jnb     short loc_180027330
0x1800272bc  mov     r8d, esi
0x1800272bf  lea     rdx, [rsp+58h+arg_10]
0x1800272c4  mov     rcx, [r14+18h]
0x1800272c8  call    ?GetAt@CandidateList@@QEAA?AV?$unique_ptr@VProfileSelection@@U?$default_delete@VProfileSelection@@@std@@@std@@K@Z; CandidateList::GetAt(ulong)
0x1800272cd  mov     r15, rax
0x1800272d0  mov     rcx, [rsp+58h+var_38]; this
0x1800272d5  call    ?GetKeyValue@ProfileSelection@@IEBAPEBGPEBG@Z; ProfileSelection::GetKeyValue(ushort const *)
0x1800272da  mov     rdi, rax
0x1800272dd  mov     rcx, [r15]; this
0x1800272e0  call    ?GetKeyValue@ProfileSelection@@IEBAPEBGPEBG@Z; ProfileSelection::GetKeyValue(ushort const *)
0x1800272e5  sub     rdi, rax
0x1800272e8  movzx   r15d, word ptr [rax]
0x1800272ec  movzx   ecx, word ptr [rax+rdi]
0x1800272f0  sub     r15d, ecx
0x1800272f3  jnz     short loc_1800272FD
0x1800272f5  add     rax, 2
0x1800272f9  test    ecx, ecx
0x1800272fb  jnz     short loc_1800272E8
0x1800272fd  mov     rdi, [rsp+58h+arg_10]
0x180027302  test    rdi, rdi
0x180027305  jz      short loc_180027322
0x180027307  mov     rcx, rdi
0x18002730a  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x18002730f  mov     rcx, [rdi]
0x180027312  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027318  nop
0x180027319  mov     rcx, rdi
0x18002731c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027322  test    r15d, r15d
0x180027325  jnz     loc_180027495
0x18002732b  cmp     esi, 0FFFFFFFFh
0x18002732e  jnz     short loc_1800273AB
0x180027330  xor     r8d, r8d
0x180027333  lea     rdx, [rsp+58h+arg_10]
0x180027338  mov     rcx, [r14+18h]
0x18002733c  call    ?GetAt@CandidateList@@QEAA?AV?$unique_ptr@VProfileSelection@@U?$default_delete@VProfileSelection@@@std@@@std@@K@Z; CandidateList::GetAt(ulong)
0x180027341  lea     rcx, [rsp+58h+var_38]
0x180027346  cmp     rcx, rax
0x180027349  jz      short loc_180027384
0x18002734b  mov     rsi, [rax]
0x18002734e  mov     qword ptr [rax], 0
0x180027355  mov     rdi, [rsp+58h+var_38]
0x18002735a  cmp     rsi, rdi
0x18002735d  jz      short loc_180027384
0x18002735f  test    rdi, rdi
0x180027362  jz      short loc_18002737F
0x180027364  mov     rcx, rdi
0x180027367  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x18002736c  mov     rcx, [rdi]
0x18002736f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027375  nop
0x180027376  mov     rcx, rdi
0x180027379  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002737f  mov     [rsp+58h+var_38], rsi; int
0x180027384  mov     rdi, [rsp+58h+arg_10]
0x180027389  test    rdi, rdi
0x18002738c  jz      short loc_1800273A9
0x18002738e  mov     rcx, rdi
0x180027391  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x180027396  mov     rcx, [rdi]
0x180027399  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002739f  nop
0x1800273a0  mov     rcx, rdi
0x1800273a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800273a9  xor     esi, esi
0x1800273ab  mov     [rsp+58h+pv], 0
0x1800273b4  mov     rcx, [rsp+58h+var_38]; this
0x1800273b9  call    ?GetKeyValue@ProfileSelection@@IEBAPEBGPEBG@Z; ProfileSelection::GetKeyValue(ushort const *)
0x1800273be  lea     rdx, [rsp+58h+pv]; unsigned __int16 **
0x1800273c3  mov     rcx, rax; unsigned __int16 *
0x1800273c6  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x1800273cb  mov     edi, eax
0x1800273cd  test    eax, eax
0x1800273cf  jns     short loc_180027425
0x1800273d1  mov     rcx, [rsp+58h]; this
0x1800273d6  mov     r9d, eax; char *
0x1800273d9  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800273e0  mov     edx, 1B7h; void *
0x1800273e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800273ea  nop
0x1800273eb  mov     rbx, [rsp+58h+var_38]
0x1800273f0  test    rbx, rbx
0x1800273f3  jz      short loc_180027411
0x1800273f5  mov     rcx, rbx
0x1800273f8  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x1800273fd  mov     rcx, [rbx]
0x180027400  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027406  nop
0x180027407  mov     rcx, rbx
0x18002740a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027410  nop
0x180027411  mov     rcx, [rsp+58h+pv]; pv
0x180027416  test    rcx, rcx
0x180027419  jz      short loc_180027421
0x18002741b  call    cs:__imp_CoTaskMemFree
0x180027421  mov     eax, edi
0x180027423  jmp     short loc_180027483
0x180027425  mov     rax, [rsp+58h+pv]
0x18002742a  mov     [r12+8], rax
0x18002742f  mov     [r12], esi
0x180027433  mov     rbx, [rsp+58h+var_38]
0x180027438  test    rbx, rbx
0x18002743b  jz      short loc_180027459
0x18002743d  mov     rcx, rbx
0x180027440  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x180027445  mov     rcx, [rbx]
0x180027448  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002744e  nop
0x18002744f  mov     rcx, rbx
0x180027452  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027458  nop
0x180027459  xor     eax, eax
0x18002745b  jmp     short loc_180027483
0x18002745d  mov     rcx, [rsp+58h]; this
0x180027462  mov     ebx, 8007139Fh
0x180027467  mov     r9d, ebx; char *
0x18002746a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180027471  mov     edx, 19Ah; void *
0x180027476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002747b  mov     eax, ebx
0x18002747d  jmp     short loc_180027483
0x18002747f  mov     eax, dword ptr [rsp+58h+pv]
0x180027483  mov     rbx, [rsp+58h+arg_0]
0x180027488  add     rsp, 30h
0x18002748c  pop     r15
0x18002748e  pop     r14
0x180027490  pop     r12
0x180027492  pop     rdi
0x180027493  pop     rsi
0x180027494  retn
0x180027495  inc     esi
0x180027497  jmp     loc_1800272AF
```
