# LoadHelperClass(ATL::CRegKey &,ushort const *,ushort const *,void *)

- ea: `0x180007d5c`
- end: `0x18000841b`
- name: `?LoadHelperClass@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z`
- size: `1727`
- prototype: `int(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180008460`

## callees

- `0x180001f34`
- `0x1800053a8`
- `0x18000597c`
- `0x180005aac`
- `0x180007d5c`
- `0x18000a528`
- `0x18000a6c0`
- `0x18000ac44`
- `0x18000af14`
- `0x18000b17c`
- `0x18000b200`
- `0x18000c65c`
- `0x18000cb80`
- `0x180010564`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007e8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f35`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008036`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800081af`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008211`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000825d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800082d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008373`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000839b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083d0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007e8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f35`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008036`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800081af`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008211`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000825d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800082d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008373`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000839b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall LoadHelperClass(
        struct ATL::CRegKey *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 **a4)
{
  void *v7; // r13
  CNDFHelperClass *v8; // rax
  LPVOID *v9; // r12
  LPVOID ***v10; // rbx
  __int64 v11; // rdi
  LPVOID **v12; // rax
  LPVOID **v13; // rcx
  LPVOID **v14; // rcx
  int v15; // edi
  const unsigned __int16 *v16; // rbx
  __int64 v17; // rsi
  __int64 v18; // rsi
  const unsigned __int16 *v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rsi
  __int64 *v23; // rdx
  __int64 v24; // rax
  const unsigned __int16 *v25; // rbx
  __int64 v26; // rsi
  __int64 v27; // rcx
  __int64 *v28; // rdx
  const unsigned __int16 *v29; // rax
  CNDFHelperClass **v30; // rcx
  CNDFHelperClass *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  const unsigned __int16 *v34; // rbx
  void *v35; // rax
  __int64 v36; // rcx
  unsigned __int16 *v37; // rdx
  _QWORD *v38; // rcx
  __int64 v39; // rcx
  unsigned __int16 *v40; // rdx
  _QWORD *v41; // rcx
  __int64 v42; // rcx
  CNDFHelperClass *v43; // rbx
  int v45; // [rsp+30h] [rbp-49h] BYREF
  CNDFHelperClass *v46; // [rsp+38h] [rbp-41h] BYREF
  void *Src; // [rsp+40h] [rbp-39h] BYREF
  _QWORD *v48; // [rsp+48h] [rbp-31h] BYREF
  __int64 v49; // [rsp+50h] [rbp-29h]
  char v50[8]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v51; // [rsp+60h] [rbp-19h] BYREF
  __int64 v52; // [rsp+68h] [rbp-11h]
  void *v53; // [rsp+70h] [rbp-9h]
  void *v54[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v55; // [rsp+88h] [rbp+Fh]
  unsigned __int64 v56; // [rsp+90h] [rbp+17h]

  Src = 0;
  v7 = 0;
  v53 = 0;
  v8 = (CNDFHelperClass *)operator new(0x168u, (const struct std::nothrow_t *)&std::nothrow);
  v46 = v8;
  if ( v8 )
    v9 = (LPVOID *)CNDFHelperClass::CNDFHelperClass(v8);
  else
    v9 = 0;
  if ( v9
    && (v10 = (LPVOID ***)a4[3],
        v11 = 24,
        (v12 = (LPVOID **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow)) != 0) )
  {
    v13 = v12;
    do
    {
      *(_BYTE *)v13 = 0;
      v13 = (LPVOID **)((char *)v13 + 1);
      --v11;
    }
    while ( v11 );
    *v12 = v9;
    v14 = v10[1];
    if ( v14 )
    {
      v14[1] = (LPVOID *)v12;
      v10[1][1][2] = v10[1];
      v12 = (LPVOID **)v10[1][1];
    }
    else
    {
      *v10 = v12;
    }
    v10[1] = v12;
    v15 = CNDFHelperClass::SetRootData(v9, a2, a4[5], a3, (unsigned __int16 *)a4[4]);
  }
  else
  {
    v15 = -2147024882;
  }
  v16 = *a4;
  v56 = 7;
  v55 = 0;
  LOWORD(v54[0]) = 0;
  std::wstring::assign(v54, a2);
  v17 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                     v16,
                     &v46,
                     v54);
  if ( v56 >= 8 )
    operator delete(v54[0]);
  v56 = 7;
  v55 = 0;
  LOWORD(v54[0]) = 0;
  if ( v17 == *(_QWORD *)*a4 )
    v18 = 0;
  else
    v18 = *(_QWORD *)(v17 + 64);
  if ( v15 >= 0 && !v18 )
  {
    v15 = (*((__int64 (__fastcall **)(LPVOID *, void **))*v9 + 3))(v9, &Src);
    if ( v15 < 0 )
    {
      if ( v15 == -2147024894 )
        v15 = 0;
      goto LABEL_36;
    }
    v7 = Src;
    v53 = Src;
    v19 = a4[2];
    v56 = 7;
    v55 = 0;
    LOWORD(v54[0]) = 0;
    std::wstring::assign(v54, Src);
    v20 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                       v19,
                       &v46,
                       v54);
    if ( v56 >= 8 )
      operator delete(v54[0]);
    v56 = 7;
    v55 = 0;
    LOWORD(v54[0]) = 0;
    if ( v20 != *(_QWORD *)a4[2] )
    {
      v22 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                         *a4,
                         v50,
                         v20 + 64);
      if ( v22 == *(_QWORD *)*a4 || (v18 = *(_QWORD *)(v22 + 64)) == 0 )
      {
        v24 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                a4[1],
                v50,
                v20 + 64);
        if ( *(_QWORD *)v24 == *(_QWORD *)a4[1] )
        {
          v18 = 0;
          goto LABEL_36;
        }
        v18 = *(_QWORD *)(*(_QWORD *)v24 + 64LL);
        if ( v18 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
        {
          v23 = DuplicateExtHCComponent;
          goto LABEL_28;
        }
      }
      else if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      {
        v23 = DuplicateFirstPartyHCComponent;
LABEL_28:
        McTemplateU0zz_EventWriteTransfer(v21, v23, a2, Src);
      }
    }
LABEL_36:
    if ( v15 >= 0 && !v18 )
    {
      v25 = a4[1];
      v56 = 7;
      v55 = 0;
      LOWORD(v54[0]) = 0;
      std::wstring::assign(v54, a2);
      v26 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                         v25,
                         v50,
                         v54);
      if ( v56 >= 8 )
        operator delete(v54[0]);
      v56 = 7;
      v55 = 0;
      LOWORD(v54[0]) = 0;
      if ( v26 == *(_QWORD *)a4[1] )
        v18 = 0;
      else
        v18 = *(_QWORD *)(v26 + 64);
    }
  }
  v45 = 0;
  if ( v15 < 0 )
    goto LABEL_51;
  v15 = (*((__int64 (__fastcall **)(LPVOID *, int *))*v9 + 1))(v9, &v45);
  if ( v15 < 0 )
    goto LABEL_51;
  if ( v18 )
  {
    LODWORD(v46) = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, CNDFHelperClass **))(*(_QWORD *)v18 + 8LL))(v18, &v46);
    if ( v15 < 0 )
      goto LABEL_51;
    if ( (v45 & 0x20) != 0 )
    {
      v15 = -2147024844;
      if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      {
        v28 = DuplicateThirdPartyHC;
LABEL_50:
        McTemplateU0z_EventWriteTransfer(v27, v28, a2);
      }
LABEL_51:
      v29 = a4[3];
      v30 = (CNDFHelperClass **)*((_QWORD *)v29 + 1);
      if ( v30 )
      {
        v31 = v30[2];
        *((_QWORD *)v29 + 1) = v31;
        if ( v31 )
          *((_QWORD *)v31 + 1) = 0;
        else
          *(_QWORD *)v29 = 0;
        v43 = *v30;
        operator delete(v30);
        if ( v43 )
        {
          CNDFHelperClass::~CNDFHelperClass(v43);
          operator delete(v43);
        }
      }
      goto LABEL_88;
    }
    if ( (v45 & 0x10) != 0 && ((unsigned __int8)v46 & 0x20) == 0 )
    {
      v15 = -2147024844;
      if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) == 0 )
        goto LABEL_51;
      v28 = DuplicateFirstPartyExtHC;
      goto LABEL_50;
    }
    if ( ((unsigned __int8)v46 & 0x30) == 0 )
    {
      v15 = -2147024844;
      if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) == 0 )
        goto LABEL_51;
      v28 = DuplicateFirstPartyHC;
      goto LABEL_50;
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>(
    &v51,
    *a4);
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>(
    &v48,
    a4[1]);
  if ( (v45 & 0x30) != 0 )
  {
    v56 = 7;
    v55 = 0;
    LOWORD(v54[0]) = 0;
    std::wstring::assign(v54, a2);
    *(_QWORD *)std::map<std::wstring,CNDFHelperClass *>::operator[](&v48, v54) = v9;
    if ( v56 >= 8 )
      operator delete(v54[0]);
    if ( v18 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(v33, DuplicateExtHCReplaced, a2);
  }
  else
  {
    if ( v18 )
    {
      v56 = 7;
      v55 = 0;
      LOWORD(v54[0]) = 0;
      std::wstring::assign(v54, a2);
      std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
        &v48,
        v54);
      if ( v56 >= 8 )
        operator delete(v54[0]);
      if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(v32, DuplicateHCReplaced, a2);
    }
    v56 = 7;
    v55 = 0;
    LOWORD(v54[0]) = 0;
    std::wstring::assign(v54, a2);
    *(_QWORD *)std::map<std::wstring,CNDFHelperClass *>::operator[](&v51, v54) = v9;
    if ( v56 >= 8 )
      operator delete(v54[0]);
  }
  if ( Src )
  {
    v34 = a4[2];
    v56 = 7;
    v55 = 0;
    LOWORD(v54[0]) = 0;
    std::wstring::assign(v54, Src);
    v35 = (void *)std::map<std::wstring,std::wstring>::operator[](v34, v54);
    std::wstring::assign(v35, a2);
    if ( v56 >= 8 )
      operator delete(v54[0]);
    if ( v18 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
      McTemplateU0zz_EventWriteTransfer(v36, DuplicateHCComponentReplaced, a2, Src);
  }
  v37 = (unsigned __int16 *)*a4;
  if ( *a4 != (const unsigned __int16 *)&v51 )
  {
    v38 = *(_QWORD **)v37;
    *(_QWORD *)v37 = v51;
    v51 = v38;
    v39 = *((_QWORD *)v37 + 1);
    *((_QWORD *)v37 + 1) = v52;
    v52 = v39;
  }
  v40 = (unsigned __int16 *)a4[1];
  if ( v40 != (unsigned __int16 *)&v48 )
  {
    v41 = *(_QWORD **)v40;
    *(_QWORD *)v40 = v48;
    v48 = v41;
    v42 = *((_QWORD *)v40 + 1);
    *((_QWORD *)v40 + 1) = v49;
    v49 = v42;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
    &v48,
    v50,
    *v48,
    v48);
  operator delete(v48);
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
    &v51,
    v50,
    *v51,
    v51);
  operator delete(v51);
LABEL_88:
  if ( v7 )
    CoTaskMemFree(v7);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180007d5c  mov     [rsp-8+arg_0], rbx
0x180007d61  push    rbp
0x180007d62  push    rsi
0x180007d63  push    rdi
0x180007d64  push    r12
0x180007d66  push    r13
0x180007d68  push    r14
0x180007d6a  push    r15
0x180007d6c  lea     rbp, [rsp-27h]
0x180007d71  sub     rsp, 0A0h
0x180007d78  mov     rax, cs:__security_cookie
0x180007d7f  xor     rax, rsp
0x180007d82  mov     [rbp+57h+var_38], rax
0x180007d86  mov     r14, r9
0x180007d89  mov     rsi, r8
0x180007d8c  mov     r15, rdx
0x180007d8f  mov     [rbp+57h+Src], 0
0x180007d97  xor     r13d, r13d
0x180007d9a  mov     [rbp+57h+var_60], r13
0x180007d9e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007da5  mov     ecx, 168h; unsigned __int64
0x180007daa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007daf  mov     [rbp+57h+var_98], rax
0x180007db3  test    rax, rax
0x180007db6  jz      short loc_180007DC5
0x180007db8  mov     rcx, rax; this
0x180007dbb  call    ??0CNDFHelperClass@@QEAA@XZ; CNDFHelperClass::CNDFHelperClass(void)
0x180007dc0  mov     r12, rax
0x180007dc3  jmp     short loc_180007DC8
0x180007dc5  xor     r12d, r12d
0x180007dc8  test    r12, r12
0x180007dcb  jz      short loc_180007E44
0x180007dcd  mov     rbx, [r14+18h]
0x180007dd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007dd8  mov     edi, 18h
0x180007ddd  mov     ecx, edi; unsigned __int64
0x180007ddf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007de4  test    rax, rax
0x180007de7  jz      short loc_180007E44
0x180007de9  mov     rcx, rax
0x180007dec  mov     byte ptr [rcx], 0
0x180007def  inc     rcx
0x180007df2  sub     rdi, 1
0x180007df6  jnz     short loc_180007DEC
0x180007df8  mov     [rax], r12
0x180007dfb  mov     rcx, [rbx+8]
0x180007dff  test    rcx, rcx
0x180007e02  jz      short loc_180007E1E
0x180007e04  mov     [rcx+8], rax
0x180007e08  mov     rcx, [rbx+8]
0x180007e0c  mov     rax, [rcx+8]
0x180007e10  mov     [rax+10h], rcx
0x180007e14  mov     rax, [rbx+8]
0x180007e18  mov     rax, [rax+8]
0x180007e1c  jmp     short loc_180007E21
0x180007e1e  mov     [rbx], rax
0x180007e21  mov     [rbx+8], rax
0x180007e25  mov     rax, [r14+20h]
0x180007e29  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x180007e2e  mov     r9, rsi; unsigned __int16 *
0x180007e31  mov     r8, [r14+28h]; HKEY
0x180007e35  mov     rdx, r15; unsigned __int16 *
0x180007e38  mov     rcx, r12; this
0x180007e3b  call    ?SetRootData@CNDFHelperClass@@QEAAJPEBGPEAUHKEY__@@00@Z; CNDFHelperClass::SetRootData(ushort const *,HKEY__ *,ushort const *,ushort const *)
0x180007e40  mov     edi, eax
0x180007e42  jmp     short loc_180007E49
0x180007e44  mov     edi, 8007000Eh
0x180007e49  mov     rbx, [r14]
0x180007e4c  mov     [rbp+57h+var_40], 7
0x180007e54  mov     [rbp+57h+var_48], 0
0x180007e5c  xor     eax, eax
0x180007e5e  mov     word ptr [rbp+57h+var_58], ax
0x180007e62  mov     rdx, r15; Src
0x180007e65  lea     rcx, [rbp+57h+var_58]; void *
0x180007e69  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180007e6e  lea     r8, [rbp+57h+var_58]
0x180007e72  lea     rdx, [rbp+57h+var_98]
0x180007e76  mov     rcx, rbx
0x180007e79  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180007e7e  mov     rsi, [rax]
0x180007e81  cmp     [rbp+57h+var_40], 8
0x180007e86  jb      short loc_180007E98
0x180007e88  mov     rcx, [rbp+57h+var_58]
0x180007e8c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007e93  nop     dword ptr [rax+rax+00h]
0x180007e98  mov     [rbp+57h+var_40], 7
0x180007ea0  mov     [rbp+57h+var_48], 0
0x180007ea8  xor     eax, eax
0x180007eaa  mov     word ptr [rbp+57h+var_58], ax
0x180007eae  mov     rax, [r14]
0x180007eb1  cmp     rsi, [rax]
0x180007eb4  jnz     short loc_180007EBA
0x180007eb6  xor     esi, esi
0x180007eb8  jmp     short loc_180007EBE
0x180007eba  mov     rsi, [rsi+40h]
0x180007ebe  test    edi, edi
0x180007ec0  js      loc_180008069
0x180007ec6  test    rsi, rsi
0x180007ec9  jnz     loc_180008069
0x180007ecf  mov     rax, [r12]
0x180007ed3  lea     rdx, [rbp+57h+Src]
0x180007ed7  mov     rcx, r12
0x180007eda  mov     rax, [rax+18h]
0x180007ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ee3  mov     edi, eax
0x180007ee5  test    eax, eax
0x180007ee7  js      loc_180007FE2
0x180007eed  mov     r13, [rbp+57h+Src]
0x180007ef1  mov     [rbp+57h+var_60], r13
0x180007ef5  mov     rbx, [r14+10h]
0x180007ef9  mov     [rbp+57h+var_40], 7
0x180007f01  mov     [rbp+57h+var_48], rsi
0x180007f05  xor     eax, eax
0x180007f07  mov     word ptr [rbp+57h+var_58], ax
0x180007f0b  mov     rdx, r13; Src
0x180007f0e  lea     rcx, [rbp+57h+var_58]; void *
0x180007f12  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180007f17  lea     r8, [rbp+57h+var_58]
0x180007f1b  lea     rdx, [rbp+57h+var_98]
0x180007f1f  mov     rcx, rbx
0x180007f22  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180007f27  mov     rbx, [rax]
0x180007f2a  cmp     [rbp+57h+var_40], 8
0x180007f2f  jb      short loc_180007F41
0x180007f31  mov     rcx, [rbp+57h+var_58]
0x180007f35  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007f3c  nop     dword ptr [rax+rax+00h]
0x180007f41  mov     [rbp+57h+var_40], 7
0x180007f49  mov     [rbp+57h+var_48], 0
0x180007f51  xor     eax, eax
0x180007f53  mov     word ptr [rbp+57h+var_58], ax
0x180007f57  mov     rax, [r14+10h]
0x180007f5b  cmp     rbx, [rax]
0x180007f5e  jz      loc_180007FED
0x180007f64  lea     r8, [rbx+40h]
0x180007f68  lea     rdx, [rbp+57h+var_78]
0x180007f6c  mov     rcx, [r14]
0x180007f6f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180007f74  mov     rsi, [rax]
0x180007f77  mov     rax, [r14]
0x180007f7a  cmp     rsi, [rax]
0x180007f7d  jz      short loc_180007FA6
0x180007f7f  mov     rsi, [rsi+40h]
0x180007f83  test    rsi, rsi
0x180007f86  jz      short loc_180007FA6
0x180007f88  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x180007f8f  jz      short loc_180007FED
0x180007f91  lea     rdx, DuplicateFirstPartyHCComponent
0x180007f98  mov     r8, r15
0x180007f9b  mov     r9, [rbp+57h+Src]
0x180007f9f  call    McTemplateU0zz_EventWriteTransfer
0x180007fa4  jmp     short loc_180007FED
0x180007fa6  lea     r8, [rbx+40h]
0x180007faa  lea     rdx, [rbp+57h+var_78]
0x180007fae  mov     rcx, [r14+8]
0x180007fb2  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180007fb7  mov     rsi, [rax]
0x180007fba  mov     rax, [r14+8]
0x180007fbe  cmp     rsi, [rax]
0x180007fc1  jnz     short loc_180007FC7
0x180007fc3  xor     esi, esi
0x180007fc5  jmp     short loc_180007FED
0x180007fc7  mov     rsi, [rsi+40h]
0x180007fcb  test    rsi, rsi
0x180007fce  jz      short loc_180007FED
0x180007fd0  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x180007fd7  jz      short loc_180007FED
0x180007fd9  lea     rdx, DuplicateExtHCComponent
0x180007fe0  jmp     short loc_180007F98
0x180007fe2  xor     eax, eax
0x180007fe4  cmp     edi, 80070002h
0x180007fea  cmovz   edi, eax
0x180007fed  test    edi, edi
0x180007fef  js      short loc_180008069
0x180007ff1  test    rsi, rsi
0x180007ff4  jnz     short loc_180008069
0x180007ff6  mov     rbx, [r14+8]
0x180007ffa  mov     [rbp+57h+var_40], 7
0x180008002  mov     [rbp+57h+var_48], rsi
0x180008006  xor     eax, eax
0x180008008  mov     word ptr [rbp+57h+var_58], ax
0x18000800c  mov     rdx, r15; Src
0x18000800f  lea     rcx, [rbp+57h+var_58]; void *
0x180008013  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180008018  lea     r8, [rbp+57h+var_58]
0x18000801c  lea     rdx, [rbp+57h+var_78]
0x180008020  mov     rcx, rbx
0x180008023  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180008028  mov     rsi, [rax]
0x18000802b  cmp     [rbp+57h+var_40], 8
0x180008030  jb      short loc_180008042
0x180008032  mov     rcx, [rbp+57h+var_58]
0x180008036  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000803d  nop     dword ptr [rax+rax+00h]
0x180008042  mov     [rbp+57h+var_40], 7
0x18000804a  mov     [rbp+57h+var_48], 0
0x180008052  xor     eax, eax
0x180008054  mov     word ptr [rbp+57h+var_58], ax
0x180008058  mov     rax, [r14+8]
0x18000805c  cmp     rsi, [rax]
0x18000805f  jnz     short loc_180008065
0x180008061  xor     esi, esi
0x180008063  jmp     short loc_180008069
0x180008065  mov     rsi, [rsi+40h]
0x180008069  mov     [rbp+57h+var_A0], 0
0x180008070  test    edi, edi
0x180008072  js      short loc_1800080DA
0x180008074  mov     rax, [r12]
0x180008078  lea     rdx, [rbp+57h+var_A0]
0x18000807c  mov     rcx, r12
0x18000807f  mov     rax, [rax+8]
0x180008083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008088  mov     edi, eax
0x18000808a  test    eax, eax
0x18000808c  js      short loc_1800080DA
0x18000808e  test    rsi, rsi
0x180008091  jz      loc_180008149
0x180008097  mov     dword ptr [rbp+57h+var_98], 0
0x18000809e  mov     rax, [rsi]
0x1800080a1  lea     rdx, [rbp+57h+var_98]
0x1800080a5  mov     rcx, rsi
0x1800080a8  mov     rax, [rax+8]
0x1800080ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b1  mov     edi, eax
0x1800080b3  test    eax, eax
0x1800080b5  js      short loc_1800080DA
0x1800080b7  test    byte ptr [rbp+57h+var_A0], 20h
0x1800080bb  jz      short loc_180008109
0x1800080bd  mov     edi, 80070034h
0x1800080c2  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x1800080c9  jz      short loc_1800080DA
0x1800080cb  lea     rdx, DuplicateThirdPartyHC
0x1800080d2  mov     r8, r15
0x1800080d5  call    McTemplateU0z_EventWriteTransfer
0x1800080da  mov     rax, [r14+18h]
0x1800080de  mov     rcx, [rax+8]
0x1800080e2  test    rcx, rcx
0x1800080e5  jz      loc_1800083DD
0x1800080eb  mov     rdx, [rcx+10h]
0x1800080ef  mov     [rax+8], rdx
0x1800080f3  test    rdx, rdx
0x1800080f6  jz      loc_1800083AA
0x1800080fc  mov     qword ptr [rdx+8], 0
0x180008104  jmp     loc_1800083B1
0x180008109  test    byte ptr [rbp+57h+var_A0], 10h
0x18000810d  jz      short loc_18000812C
0x18000810f  test    byte ptr [rbp+57h+var_98], 20h
0x180008113  jnz     short loc_18000812C
0x180008115  mov     edi, 80070034h
0x18000811a  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x180008121  jz      short loc_1800080DA
0x180008123  lea     rdx, DuplicateFirstPartyExtHC
0x18000812a  jmp     short loc_1800080D2
0x18000812c  test    byte ptr [rbp+57h+var_98], 30h
0x180008130  jnz     short loc_180008149
0x180008132  mov     edi, 80070034h
0x180008137  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000813e  jz      short loc_1800080DA
0x180008140  lea     rdx, DuplicateFirstPartyHC
0x180008147  jmp     short loc_1800080D2
0x180008149  mov     rdx, [r14]
0x18000814c  lea     rcx, [rbp+57h+var_70]
0x180008150  call    ??0?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>> const &,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>> const &)
0x180008155  nop
0x180008156  mov     rdx, [r14+8]
0x18000815a  lea     rcx, [rbp+57h+var_88]
0x18000815e  call    ??0?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>> const &,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>> const &)
0x180008163  nop
0x180008164  test    byte ptr [rbp+57h+var_A0], 30h
0x180008168  jnz     loc_18000821F
0x18000816e  test    rsi, rsi
0x180008171  jz      short loc_1800081D3
0x180008173  mov     [rbp+57h+var_40], 7
0x18000817b  mov     [rbp+57h+var_48], 0
0x180008183  xor     eax, eax
0x180008185  mov     word ptr [rbp+57h+var_58], ax
0x180008189  mov     rdx, r15; Src
0x18000818c  lea     rcx, [rbp+57h+var_58]; void *
0x180008190  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180008195  nop
0x180008196  lea     rdx, [rbp+57h+var_58]
0x18000819a  lea     rcx, [rbp+57h+var_88]
0x18000819e  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(std::wstring const &)
0x1800081a3  nop
0x1800081a4  cmp     [rbp+57h+var_40], 8
0x1800081a9  jb      short loc_1800081BB
0x1800081ab  mov     rcx, [rbp+57h+var_58]
0x1800081af  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800081b6  nop     dword ptr [rax+rax+00h]
0x1800081bb  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 2
0x1800081c2  jz      short loc_1800081D3
0x1800081c4  mov     r8, r15
0x1800081c7  lea     rdx, DuplicateHCReplaced
0x1800081ce  call    McTemplateU0z_EventWriteTransfer
0x1800081d3  mov     [rbp+57h+var_40], 7
0x1800081db  mov     [rbp+57h+var_48], 0
0x1800081e3  xor     eax, eax
0x1800081e5  mov     word ptr [rbp+57h+var_58], ax
0x1800081e9  mov     rdx, r15; Src
0x1800081ec  lea     rcx, [rbp+57h+var_58]; void *
  ... truncated ...
```
