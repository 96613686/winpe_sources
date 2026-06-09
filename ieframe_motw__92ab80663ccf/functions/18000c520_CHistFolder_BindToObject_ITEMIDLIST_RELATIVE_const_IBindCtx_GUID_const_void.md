# CHistFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x18000c520`
- end: `0x18000cd3e`
- name: `?BindToObject@CHistFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `2078`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c520`
- `0x18017b928`
- `0x18017be14`

## callees

- `0x180007010`
- `0x18000bc6c`
- `0x18000c520`
- `0x18000cd50`
- `0x1800144d0`
- `0x18003c480`
- `0x18003dfc0`
- `0x180053e90`
- `0x1800bf0d8`
- `0x1800c18bc`
- `0x18017b928`
- `0x18017c730`
- `0x180591eea`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x18000c9cb`
- `SHLWAPI!StrRetToBufW` at `0x18000c9cb`
- `KERNEL32!GetLongPathNameW` at `0x18000ccf3`
- `KERNEL32!GetLongPathNameW` at `0x18000ccf3`
- `KERNEL32!LocalAlloc` at `0x18000cc61`
- `KERNEL32!LocalAlloc` at `0x18000cc61`
- `KERNEL32!LocalFree` at `0x18000cc32`
- `KERNEL32!LocalFree` at `0x18000cc32`
- `KERNEL32!GetProcessHeap` at `0x18000c627`
- `KERNEL32!GetProcessHeap` at `0x18000c627`
- `KERNEL32!HeapAlloc` at `0x18000c641`
- `KERNEL32!HeapAlloc` at `0x18000c641`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000ca36`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000cd13`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000ca36`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x18000cd13`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x18000c8d3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x18000c8d3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000c730`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000c730`
- `SHELL32!SHGetFolderPathW` at `0x18000c7cf`
- `SHELL32!SHGetFolderPathW` at `0x18000c7cf`
- `SHELL32!__imp_ILClone` at `0x18000c58b`
- `SHELL32!__imp_ILClone` at `0x18000ca4f`
- `SHELL32!__imp_ILClone` at `0x18000c58b`
- `SHELL32!__imp_ILClone` at `0x18000ca4f`
- `SHELL32!__imp_ILCloneFirst` at `0x18000c866`
- `SHELL32!__imp_ILCloneFirst` at `0x18000c866`
- `SHELL32!__imp_ILCombine` at `0x18000c6f0`
- `SHELL32!__imp_ILCombine` at `0x18000cb3b`
- `SHELL32!__imp_ILCombine` at `0x18000c6f0`
- `SHELL32!__imp_ILCombine` at `0x18000cb3b`
- `SHELL32!__imp_ILFree` at `0x18000c741`
- `SHELL32!__imp_ILFree` at `0x18000c76a`
- `SHELL32!__imp_ILFree` at `0x18000c7a0`
- `SHELL32!__imp_ILFree` at `0x18000cb23`
- `SHELL32!__imp_ILFree` at `0x18000cba7`
- `SHELL32!__imp_ILFree` at `0x18000c741`
- `SHELL32!__imp_ILFree` at `0x18000c76a`
- `SHELL32!__imp_ILFree` at `0x18000c7a0`
- `SHELL32!__imp_ILFree` at `0x18000cb23`
- `SHELL32!__imp_ILFree` at `0x18000cba7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000c901`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000cca4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000c901`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000cca4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x18000ca03`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x18000ca03`

## pseudocode

```c
__int64 __fastcall CHistFolder::BindToObject(
        LPCITEMIDLIST *this,
        const ITEMIDLIST *a2,
        struct IBindCtx *a3,
        struct _GUID *a4,
        void **a5)
{
  const ITEMIDLIST *v7; // r12
  HRESULT Interface; // ebx
  LPITEMIDLIST v10; // r14
  int v11; // edi
  unsigned __int16 *p_cb; // rcx
  unsigned __int16 v13; // ax
  HANDLE ProcessHeap; // rax
  _DWORD *v15; // rax
  _DWORD *v16; // rsi
  void *v17; // rcx
  const unsigned __int16 *v18; // rbx
  unsigned int v19; // edx
  LPITEMIDLIST v20; // r12
  void *v22; // rax
  __int64 v23; // rax
  LPITEMIDLIST v24; // rax
  struct _CurrentSearches *v25; // rdx
  struct _CurrentSearches *Search; // rax
  CHistFolder *v27; // rcx
  void **v28; // r13
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned int v32; // ebx
  HRESULT v33; // edi
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  HRESULT v37; // r13d
  LPCITEMIDLIST v38; // r13
  unsigned int v39; // edi
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  LPITEMIDLIST v43; // rax
  IID *v44; // rbx
  ITEMIDLIST *v45; // rcx
  LPITEMIDLIST v46; // rax
  const struct _ITEMIDLIST_RELATIVE *v47; // rdx
  CHistFolder *v48; // rcx
  __int64 v49; // rax
  unsigned __int64 v50; // rdi
  unsigned __int16 *v51; // rax
  unsigned int v52; // [rsp+30h] [rbp-D0h]
  CHistFolder *v53; // [rsp+30h] [rbp-D0h]
  HRESULT v54; // [rsp+30h] [rbp-D0h]
  LPITEMIDLIST v55; // [rsp+38h] [rbp-C8h] BYREF
  void **ppv; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v57; // [rsp+48h] [rbp-B8h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST v59; // [rsp+58h] [rbp-A8h]
  LPCITEMIDLIST pidl; // [rsp+60h] [rbp-A0h]
  IID *riid; // [rsp+68h] [rbp-98h]
  STRRET pstr; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszBuf[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR psz2[264]; // [rsp+490h] [rbp+390h] BYREF

  riid = a4;
  v57 = (struct _FILETIME)a2;
  v7 = a2;
  ppv = a5;
  *a5 = 0;
  if ( ((unsigned __int8)a2 & 3) == 0 )
  {
    v10 = (LPITEMIDLIST)a2;
    Interface = 0;
    goto LABEL_6;
  }
  if ( a2 )
  {
    Interface = 0;
    v10 = ILClone(a2);
    if ( !v10 )
      Interface = -2147024882;
  }
  else
  {
    v10 = 0;
    Interface = -2147024809;
  }
  if ( Interface >= 0 )
  {
LABEL_6:
    if ( v10->mkid.cb >= 8u && *(_WORD *)v10->mkid.abID == 25446 )
    {
      Interface = -2147467259;
      if ( *(USHORT *)((char *)&v7[1].mkid.cb + 1) == 1
        || *(USHORT *)((char *)&v7[1].mkid.cb + 1) == 2
        || *(USHORT *)((char *)&v7[1].mkid.cb + 1) == 3
        || *(USHORT *)((char *)&v7[1].mkid.cb + 1) == 19524 )
      {
        v22 = operator new(0x290u);
        if ( v22 )
        {
          v23 = CHistFolder::CHistFolder(v22, 3);
          v53 = (CHistFolder *)v23;
          if ( v23 )
          {
            *(_DWORD *)(v23 + 128) = *(unsigned __int16 *)((char *)&v7[1].mkid.cb + 1);
            v24 = ILCloneFirst(v7);
            v55 = v24;
            if ( !v24 )
            {
              v28 = (void **)v53;
              goto LABEL_85;
            }
            if ( *(USHORT *)((char *)&v7[1].mkid.cb + 1) == 19524 )
            {
              v57 = *(struct _FILETIME *)v7[2].mkid.abID;
              Search = _CurrentSearches::s_FindSearch(&v57, v25);
              v27 = v53;
              *((_QWORD *)v53 + 81) = Search;
              if ( !Search )
              {
                v28 = (void **)v53;
LABEL_83:
                ILFree(v55);
LABEL_85:
                v48 = (CHistFolder *)v28;
                goto LABEL_86;
              }
              v24 = v55;
            }
            else
            {
              v27 = v53;
            }
            v45 = (ITEMIDLIST *)*((_QWORD *)v27 + 13);
            if ( v45 )
            {
              ILFree(v45);
              v24 = v55;
            }
            v46 = ILCombine(this[13], v24);
            v28 = (void **)v53;
            *((_QWORD *)v53 + 13) = v46;
            v47 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v7 + v7->mkid.cb);
            if ( *(_WORD *)v47 )
            {
              ppv = 0;
              Interface = CHistFolder::BindToObject(v53, v47, a3, a4, (void **)&ppv);
              v48 = v53;
              if ( Interface < 0 )
              {
LABEL_86:
                CHistFolder::Release(v48);
                goto LABEL_28;
              }
              CHistFolder::Release(v53);
              v28 = ppv;
            }
            Interface = CHistFolder::QueryInterface((CHistFolder *)v28, a4, a5);
            goto LABEL_83;
          }
        }
        Interface = -2147024882;
      }
LABEL_28:
      if ( v10 != v7 )
        ILFree(v10);
      return (unsigned int)Interface;
    }
    if ( *((_DWORD *)this + 32) )
    {
      Interface = CHistFolder::_ViewType_BindToObject((CHistFolder *)this, v7, a3, a4, a5);
      goto LABEL_28;
    }
    v11 = *((_DWORD *)this + 13);
    p_cb = &v10->mkid.cb;
    if ( v10->mkid.cb )
    {
      while ( 1 )
      {
        if ( Interface < 0 )
          goto LABEL_28;
        switch ( v11 )
        {
          case 1:
            v13 = p_cb[1];
            if ( v13 != 25444 && v13 != 25449 )
            {
              Interface = -2147467259;
              goto LABEL_14;
            }
            v11 = 2;
            break;
          case 2:
            if ( p_cb[1] != 25445 )
            {
              Interface = -2147467259;
              goto LABEL_14;
            }
            v11 = 3;
            break;
          case 3:
            if ( p_cb[1] != 25448 )
            {
              Interface = -2147467259;
              goto LABEL_14;
            }
            break;
          default:
            Interface = -2147467259;
            goto LABEL_14;
        }
        p_cb = (unsigned __int16 *)((char *)p_cb + *p_cb);
LABEL_14:
        if ( !*p_cb )
        {
          if ( Interface < 0 )
            goto LABEL_28;
          break;
        }
      }
    }
    ProcessHeap = GetProcessHeap();
    v15 = HeapAlloc(ProcessHeap, 8u, 0x290u);
    v16 = v15;
    if ( !v15 )
      std::_Xbad_alloc();
    v15[13] = v11;
    *(_QWORD *)v15 = &CHistFolder::`vftable'{for `IShellFolder2'};
    v15[12] = 1;
    *((_QWORD *)v15 + 1) = &CHistFolder::`vftable'{for `IShellIcon'};
    *((_QWORD *)v15 + 2) = &CHistFolder::`vftable'{for `IShellFolderViewType'};
    *((_QWORD *)v15 + 3) = &CHistFolder::`vftable'{for `IShellFolderSearchable'};
    *((_QWORD *)v15 + 4) = &CHistFolder::`vftable'{for `IBrowserHistSFPrivate'};
    *((_QWORD *)v15 + 5) = &CHistFolder::`vftable'{for `IPersistFolder2'};
    *((_QWORD *)v15 + 7) = 0;
    *((_QWORD *)v15 + 8) = 0;
    *((_QWORD *)v15 + 11) = 0;
    *((_QWORD *)v15 + 13) = 0;
    *((_QWORD *)v15 + 15) = 0;
    *((_QWORD *)v15 + 81) = 0;
    _InterlockedIncrement(&g_cRefThisDll);
    v17 = (void *)*((_QWORD *)v15 + 7);
    v18 = (const unsigned __int16 *)this[7];
    if ( v17 )
    {
      LocalFree(v17);
      *((_QWORD *)v16 + 7) = 0;
    }
    if ( v18 )
    {
      v49 = -1;
      do
        ++v49;
      while ( v18[v49] );
      v50 = (int)v49 + 1;
      v51 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v50);
      *((_QWORD *)v16 + 7) = v51;
      if ( !v51 )
        goto LABEL_22;
      StringCchCopyW(v51, v50, v18);
    }
    v20 = ILCombine(this[13], v10);
    if ( !v20 )
    {
      v7 = (const ITEMIDLIST *)v57;
LABEL_22:
      Interface = -2147024882;
      goto LABEL_26;
    }
    ILFree(*((LPITEMIDLIST *)v16 + 13));
    if ( v16[13] != 1 )
      goto LABEL_65;
    if ( SHGetFolderPathW(0, 34, 0, 0, psz2) < 0 )
      goto LABEL_33;
    PathRemoveBackslashW(psz2);
    if ( IEShimsDisableRedirection::SetEnabled )
      v32 = IEShimsDisableRedirection::SetEnabled(0, v29, v30, v31);
    else
      v32 = v52;
    pszBuf[0] = 0;
    v54 = CoInitializeEx(0, 6u);
    v33 = v54;
    if ( v54 < 0 )
    {
      v33 = CoInitializeEx(0, 4u);
      v54 = v33;
    }
    v55 = 0;
    ppidlLast = 0;
    v37 = SHBindToParent_0(v20, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&v55, &ppidlLast);
    if ( v37 >= 0 )
    {
      v38 = ppidlLast;
      v59 = v55;
      pidl = ppidlLast;
      if ( IEShimsDisableRedirection::SetEnabled )
        v39 = IEShimsDisableRedirection::SetEnabled(0, v34, v35, v36);
      else
        v39 = v54;
      pszBuf[0] = 0;
      memset_0(&pstr, 0, sizeof(pstr));
      v37 = (*(__int64 (__fastcall **)(LPITEMIDLIST, LPCITEMIDLIST, __int64, STRRET *))(*(_QWORD *)&v59->mkid.cb + 88LL))(
              v59,
              v38,
              0x8000,
              &pstr);
      if ( v37 >= 0 )
        v37 = StrRetToBufW(&pstr, pidl, pszBuf, 0x104u);
      if ( IEShimsDisableRedirection::SetEnabled )
        IEShimsDisableRedirection::SetEnabled(v39, v40, v41, v42);
      (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v55->mkid.cb + 16LL))(v55);
      v33 = v54;
    }
    if ( v33 >= 0 )
      CoUninitialize();
    if ( IEShimsDisableRedirection::SetEnabled )
      IEShimsDisableRedirection::SetEnabled(v32, v34, v35, v36);
    if ( v37 < 0
      || StrCmpIW(pszBuf, psz2) && (!GetLongPathNameW(pszBuf, (LPWSTR)&pstr, 0x104u) || StrCmpIW((PCWSTR)&pstr, psz2)) )
    {
LABEL_33:
      Interface = -2147467259;
    }
    else
    {
LABEL_65:
      v43 = ILClone(v20);
      *((_QWORD *)v16 + 13) = v43;
      if ( v43 )
      {
        Interface = CHistFolder::_ExtractInfoFromPidl((CHistFolder *)v16);
        if ( Interface >= 0 )
        {
          v44 = riid;
          if ( !memcmp_0(riid, &IID_IPersistFolder, 0x10u) )
          {
            if ( v16[13] != 1 )
            {
              Interface = -2147467262;
              *ppv = 0;
              goto LABEL_25;
            }
          }
          else if ( !memcmp_0(v44, &CLSID_HistFolder, 0x10u) )
          {
            *ppv = v16;
            _InterlockedIncrement(v16 + 12);
            Interface = 0;
            goto LABEL_25;
          }
          Interface = QISearch(v16, &stru_180596CB0, v44, ppv);
        }
      }
      else
      {
        Interface = -2147024882;
      }
    }
LABEL_25:
    ILFree(v20);
    v7 = (const ITEMIDLIST *)v57;
LABEL_26:
    if ( _InterlockedExchangeAdd(v16 + 12, 0xFFFFFFFF) == 1 )
      CHistFolder::`scalar deleting destructor'((CHistFolder *)v16, v19);
    goto LABEL_28;
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000c520  push    rbp
0x18000c522  push    rbx
0x18000c523  push    rsi
0x18000c524  push    rdi
0x18000c525  push    r12
0x18000c527  push    r13
0x18000c529  push    r14
0x18000c52b  push    r15
0x18000c52d  lea     rbp, [rsp-5B8h]
0x18000c535  sub     rsp, 6B8h
0x18000c53c  mov     rax, cs:__security_cookie
0x18000c543  xor     rax, rsp
0x18000c546  mov     [rbp+5F0h+var_50], rax
0x18000c54d  mov     r15, [rbp+5F0h+arg_20]
0x18000c554  mov     rdi, r9
0x18000c557  mov     [rsp+6F0h+riid], r9
0x18000c55c  mov     rsi, r8
0x18000c55f  mov     qword ptr [rsp+6F0h+var_6A8.dwLowDateTime], rdx
0x18000c564  mov     r12, rdx
0x18000c567  mov     [rsp+6F0h+ppv], r15
0x18000c56c  mov     r13, rcx
0x18000c56f  mov     qword ptr [r15], 0
0x18000c576  test    dl, 3
0x18000c579  jz      loc_18000C8C2
0x18000c57f  test    rdx, rdx
0x18000c582  jz      loc_18000CB01
0x18000c588  mov     rcx, rdx; pidl
0x18000c58b  call    cs:__imp_ILClone
0x18000c592  nop     dword ptr [rax+rax+00h]
0x18000c597  xor     ebx, ebx
0x18000c599  mov     r14, rax
0x18000c59c  test    rax, rax
0x18000c59f  mov     eax, 8007000Eh
0x18000c5a4  cmovz   ebx, eax
0x18000c5a7  test    ebx, ebx
0x18000c5a9  js      loc_18000C776
0x18000c5af  movzx   eax, word ptr [r14]
0x18000c5b3  cmp     ax, 8
0x18000c5b7  jnb     loc_18000C7F3
0x18000c5bd  cmp     dword ptr [r13+80h], 0
0x18000c5c5  jnz     loc_18000CBD1
0x18000c5cb  mov     edi, [r13+34h]
0x18000c5cf  mov     rcx, r14
0x18000c5d2  test    ax, ax
0x18000c5d5  jz      short loc_18000C627
0x18000c5d7  mov     r10d, 6368h
0x18000c5dd  mov     r11d, 6365h
0x18000c5e3  mov     r8d, 6369h
0x18000c5e9  mov     r9d, 6364h
0x18000c5ef  test    ebx, ebx
0x18000c5f1  js      loc_18000C762
0x18000c5f7  cmp     edi, 1
0x18000c5fa  jnz     loc_18000CAE3
0x18000c600  movzx   eax, word ptr [rcx+2]
0x18000c604  cmp     ax, r9w
0x18000c608  jnz     loc_18000CC1E
0x18000c60e  mov     edi, 2
0x18000c613  movzx   eax, word ptr [rcx]
0x18000c616  add     rcx, rax
0x18000c619  cmp     word ptr [rcx], 0
0x18000c61d  jnz     short loc_18000C5EF
0x18000c61f  test    ebx, ebx
0x18000c621  js      loc_18000C762
0x18000c627  call    cs:__imp_GetProcessHeap
0x18000c62e  nop     dword ptr [rax+rax+00h]
0x18000c633  mov     edx, 8; dwFlags
0x18000c638  mov     r8d, 290h; dwBytes
0x18000c63e  mov     rcx, rax; hHeap
0x18000c641  call    cs:__imp_HeapAlloc
0x18000c648  nop     dword ptr [rax+rax+00h]
0x18000c64d  mov     rsi, rax
0x18000c650  test    rax, rax
0x18000c653  jz      loc_18000C7ED
0x18000c659  lea     rax, ??_7CHistFolder@@6BIShellFolder2@@@; const CHistFolder::`vftable'{for `IShellFolder2'}
0x18000c660  mov     [rsi+34h], edi
0x18000c663  xor     edi, edi
0x18000c665  mov     [rsi], rax
0x18000c668  lea     rax, ??_7CHistFolder@@6BIShellIcon@@@; const CHistFolder::`vftable'{for `IShellIcon'}
0x18000c66f  mov     dword ptr [rsi+30h], 1
0x18000c676  mov     [rsi+8], rax
0x18000c67a  lea     rax, ??_7CHistFolder@@6BIShellFolderViewType@@@; const CHistFolder::`vftable'{for `IShellFolderViewType'}
0x18000c681  mov     [rsi+10h], rax
0x18000c685  lea     rax, ??_7CHistFolder@@6BIShellFolderSearchable@@@; const CHistFolder::`vftable'{for `IShellFolderSearchable'}
0x18000c68c  mov     [rsi+18h], rax
0x18000c690  lea     rax, ??_7CHistFolder@@6BIBrowserHistSFPrivate@@@; const CHistFolder::`vftable'{for `IBrowserHistSFPrivate'}
0x18000c697  mov     [rsi+20h], rax
0x18000c69b  lea     rax, ??_7CHistFolder@@6BIPersistFolder2@@@; const CHistFolder::`vftable'{for `IPersistFolder2'}
0x18000c6a2  mov     [rsi+28h], rax
0x18000c6a6  mov     [rsi+38h], rdi
0x18000c6aa  mov     [rsi+40h], rdi
0x18000c6ae  mov     [rsi+58h], rdi
0x18000c6b2  mov     [rsi+68h], rdi
0x18000c6b6  mov     [rsi+78h], rdi
0x18000c6ba  mov     [rsi+288h], rdi
0x18000c6c1  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000c6c8  mov     rcx, [rsi+38h]; hMem
0x18000c6cc  mov     rbx, [r13+38h]
0x18000c6d0  test    rcx, rcx
0x18000c6d3  jnz     loc_18000CC32
0x18000c6d9  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000c6e0  test    rbx, rbx
0x18000c6e3  jnz     loc_18000CC47
0x18000c6e9  mov     rcx, [r13+68h]; pidl1
0x18000c6ed  mov     rdx, r14; pidl2
0x18000c6f0  call    cs:__imp_ILCombine
0x18000c6f7  nop     dword ptr [rax+rax+00h]
0x18000c6fc  mov     r12, rax
0x18000c6ff  test    rax, rax
0x18000c702  jnz     loc_18000C79C
0x18000c708  mov     r12, qword ptr [rsp+6F0h+var_6A8.dwLowDateTime]
0x18000c70d  mov     ebx, 8007000Eh
0x18000c712  jmp     short loc_18000C752
0x18000c714  cmp     dword ptr [rsi+34h], 1
0x18000c718  jnz     loc_18000CD2C
0x18000c71e  mov     r9, [rsp+6F0h+ppv]; ppv
0x18000c723  lea     rdx, stru_180596CB0; pqit
0x18000c72a  mov     r8, rbx; riid
0x18000c72d  mov     rcx, rsi; that
0x18000c730  call    cs:__imp_QISearch
0x18000c737  nop     dword ptr [rax+rax+00h]
0x18000c73c  mov     ebx, eax
0x18000c73e  mov     rcx, r12; pidl
0x18000c741  call    cs:__imp_ILFree
0x18000c748  nop     dword ptr [rax+rax+00h]
0x18000c74d  mov     r12, qword ptr [rsp+6F0h+var_6A8.dwLowDateTime]
0x18000c752  lock xadd [rsi+30h], r15d
0x18000c758  cmp     r15d, 1
0x18000c75c  jz      loc_18000CAD6
0x18000c762  cmp     r14, r12
0x18000c765  jz      short loc_18000C776
0x18000c767  mov     rcx, r14; pidl
0x18000c76a  call    cs:__imp_ILFree
0x18000c771  nop     dword ptr [rax+rax+00h]
0x18000c776  mov     eax, ebx
0x18000c778  mov     rcx, [rbp+5F0h+var_50]
0x18000c77f  xor     rcx, rsp; StackCookie
0x18000c782  call    __security_check_cookie
0x18000c787  add     rsp, 6B8h
0x18000c78e  pop     r15
0x18000c790  pop     r14
0x18000c792  pop     r13
0x18000c794  pop     r12
0x18000c796  pop     rdi
0x18000c797  pop     rsi
0x18000c798  pop     rbx
0x18000c799  pop     rbp
0x18000c79a  retn
0x18000c79c  mov     rcx, [rsi+68h]; pidl
0x18000c7a0  call    cs:__imp_ILFree
0x18000c7a7  nop     dword ptr [rax+rax+00h]
0x18000c7ac  cmp     dword ptr [rsi+34h], 1
0x18000c7b0  jnz     loc_18000CA4C
0x18000c7b6  lea     rax, [rbp+5F0h+psz2]
0x18000c7bd  xor     r9d, r9d; dwFlags
0x18000c7c0  xor     r8d, r8d; hToken
0x18000c7c3  mov     [rsp+6F0h+pszPath], rax; pszPath
0x18000c7c8  mov     edx, 22h ; '"'; csidl
0x18000c7cd  xor     ecx, ecx; hwnd
0x18000c7cf  call    cs:__imp_SHGetFolderPathW
0x18000c7d6  nop     dword ptr [rax+rax+00h]
0x18000c7db  test    eax, eax
0x18000c7dd  jns     loc_18000C8CC
0x18000c7e3  mov     ebx, 80004005h
0x18000c7e8  jmp     loc_18000C73E
0x18000c7ed  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000c7f3  mov     ecx, 6366h
0x18000c7f8  cmp     [r14+2], cx
0x18000c7fd  jnz     loc_18000C5BD
0x18000c803  movzx   ecx, word ptr [r12+4]
0x18000c809  mov     ebx, 80004005h
0x18000c80e  sub     ecx, 1
0x18000c811  jz      short loc_18000C829
0x18000c813  sub     ecx, 1
0x18000c816  jz      short loc_18000C829
0x18000c818  sub     ecx, 1
0x18000c81b  jz      short loc_18000C829
0x18000c81d  cmp     ecx, 4C41h
0x18000c823  jnz     loc_18000C762
0x18000c829  mov     ecx, 290h; dwBytes
0x18000c82e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c833  test    rax, rax
0x18000c836  jz      loc_18000CBC7
0x18000c83c  mov     edx, 3
0x18000c841  mov     rcx, rax
0x18000c844  call    ??0CHistFolder@@QEAA@W4FOLDER_TYPE@@@Z; CHistFolder::CHistFolder(FOLDER_TYPE)
0x18000c849  mov     [rsp+6F0h+var_6C0], rax
0x18000c84e  test    rax, rax
0x18000c851  jz      loc_18000CBC7
0x18000c857  movzx   ecx, word ptr [r12+4]
0x18000c85d  mov     [rax+80h], ecx
0x18000c863  mov     rcx, r12; pidl
0x18000c866  call    cs:__imp_ILCloneFirst
0x18000c86d  nop     dword ptr [rax+rax+00h]
0x18000c872  mov     [rsp+6F0h+var_6B8], rax
0x18000c877  test    rax, rax
0x18000c87a  jz      loc_18000CBB5
0x18000c880  mov     ecx, 4C44h
0x18000c885  cmp     [r12+4], cx
0x18000c88b  jnz     loc_18000CB0E
0x18000c891  mov     rcx, [r12+8]
0x18000c896  mov     qword ptr [rsp+6F0h+var_6A8.dwLowDateTime], rcx
0x18000c89b  lea     rcx, [rsp+6F0h+var_6A8]; struct _FILETIME *
0x18000c8a0  call    ?s_FindSearch@_CurrentSearches@@SAPEAV1@AEBU_FILETIME@@PEAV1@@Z; _CurrentSearches::s_FindSearch(_FILETIME const &,_CurrentSearches *)
0x18000c8a5  mov     rcx, [rsp+6F0h+var_6C0]
0x18000c8aa  mov     [rcx+288h], rax
0x18000c8b1  test    rax, rax
0x18000c8b4  jnz     loc_18000CB15
0x18000c8ba  mov     r13, rcx
0x18000c8bd  jmp     loc_18000CBA2
0x18000c8c2  mov     r14, r12
0x18000c8c5  xor     ebx, ebx
0x18000c8c7  jmp     loc_18000C5AF
0x18000c8cc  lea     rcx, [rbp+5F0h+psz2]; pszPath
0x18000c8d3  call    cs:__imp_PathRemoveBackslashW
0x18000c8da  nop     dword ptr [rax+rax+00h]
0x18000c8df  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000c8e6  test    rax, rax
0x18000c8e9  jnz     loc_18000CC8F
0x18000c8ef  mov     ebx, dword ptr [rsp+6F0h+var_6C0]
0x18000c8f3  mov     edx, 6; dwCoInit
0x18000c8f8  mov     [rbp+5F0h+pszBuf], di
0x18000c8ff  xor     ecx, ecx; pvReserved
0x18000c901  call    cs:__imp_CoInitializeEx
0x18000c908  nop     dword ptr [rax+rax+00h]
0x18000c90d  mov     dword ptr [rsp+6F0h+var_6C0], eax
0x18000c911  mov     edi, eax
0x18000c913  test    eax, eax
0x18000c915  js      loc_18000CC9D
0x18000c91b  xor     eax, eax
0x18000c91d  lea     r9, [rsp+6F0h+ppidlLast]; ppidlLast
0x18000c922  lea     r8, [rsp+6F0h+var_6B8]; ppv
0x18000c927  mov     [rsp+6F0h+var_6B8], rax
0x18000c92c  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000c933  mov     [rsp+6F0h+ppidlLast], rax
0x18000c938  mov     rcx, r12; pidl
0x18000c93b  call    SHBindToParent_0
0x18000c940  mov     r13d, eax
0x18000c943  test    eax, eax
0x18000c945  js      loc_18000C9FF
0x18000c94b  mov     rax, [rsp+6F0h+var_6B8]
0x18000c950  mov     r13, [rsp+6F0h+ppidlLast]
0x18000c955  mov     [rsp+6F0h+var_698], rax
0x18000c95a  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000c961  mov     [rsp+6F0h+pidl], r13
0x18000c966  test    rax, rax
0x18000c969  jnz     loc_18000CCBB
0x18000c96f  mov     edi, dword ptr [rsp+6F0h+var_6C0]
0x18000c973  xor     eax, eax
0x18000c975  lea     rcx, [rsp+6F0h+pstr]; void *
0x18000c97a  xor     edx, edx; Val
0x18000c97c  mov     [rbp+5F0h+pszBuf], ax
0x18000c983  mov     r8d, 110h; Size
0x18000c989  call    memset_0
0x18000c98e  mov     rcx, [rsp+6F0h+var_698]
0x18000c993  lea     r9, [rsp+6F0h+pstr]
0x18000c998  mov     r8d, 8000h
0x18000c99e  mov     rdx, r13
0x18000c9a1  mov     rax, [rcx]
0x18000c9a4  mov     rax, [rax+58h]
0x18000c9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ad  mov     r13d, eax
0x18000c9b0  test    eax, eax
0x18000c9b2  js      short loc_18000C9DA
0x18000c9b4  mov     rdx, [rsp+6F0h+pidl]; pidl
0x18000c9b9  lea     r8, [rbp+5F0h+pszBuf]; pszBuf
0x18000c9c0  mov     r9d, 104h; cchBuf
0x18000c9c6  lea     rcx, [rsp+6F0h+pstr]; pstr
0x18000c9cb  call    cs:__imp_StrRetToBufW
0x18000c9d2  nop     dword ptr [rax+rax+00h]
0x18000c9d7  mov     r13d, eax
0x18000c9da  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000c9e1  test    rax, rax
0x18000c9e4  jnz     loc_18000CCC9
0x18000c9ea  mov     rcx, [rsp+6F0h+var_6B8]
0x18000c9ef  mov     rax, [rcx]
0x18000c9f2  mov     rax, [rax+10h]
0x18000c9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9fb  mov     edi, dword ptr [rsp+6F0h+var_6C0]
0x18000c9ff  test    edi, edi
0x18000ca01  js      short loc_18000CA0F
0x18000ca03  call    cs:__imp_CoUninitialize
0x18000ca0a  nop     dword ptr [rax+rax+00h]
0x18000ca0f  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18000ca16  test    rax, rax
0x18000ca19  jnz     loc_18000CCD5
0x18000ca1f  test    r13d, r13d
0x18000ca22  js      loc_18000C7E3
0x18000ca28  lea     rdx, [rbp+5F0h+psz2]; psz2
0x18000ca2f  lea     rcx, [rbp+5F0h+pszBuf]; psz1
0x18000ca36  call    cs:__imp_StrCmpIW
0x18000ca3d  nop     dword ptr [rax+rax+00h]
0x18000ca42  test    eax, eax
0x18000ca44  jnz     loc_18000CCE1
0x18000ca4a  xor     edi, edi
0x18000ca4c  mov     rcx, r12; pidl
0x18000ca4f  call    cs:__imp_ILClone
0x18000ca56  nop     dword ptr [rax+rax+00h]
0x18000ca5b  mov     ebx, edi
0x18000ca5d  mov     ecx, 8007000Eh
0x18000ca62  test    rax, rax
  ... truncated ...
```
