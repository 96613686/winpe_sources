# CHistFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x1800054c0`
- end: `0x180005c4d`
- name: `?BindToObject@CHistFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `1933`
- prototype: `__int64 __fastcall(CHistFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800054c0`
- `0x18016a310`
- `0x18016a784`

## callees

- `0x180004ca4`
- `0x1800054c0`
- `0x180005c60`
- `0x180011230`
- `0x18002acc0`
- `0x18003c030`
- `0x18003d6d0`
- `0x180050780`
- `0x1800b83c8`
- `0x1800bab8c`
- `0x18016a310`
- `0x18016b010`
- `0x18054e27a`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x180005922`
- `SHLWAPI!StrRetToBufW` at `0x180005922`
- `KERNEL32!GetLongPathNameW` at `0x180005c0e`
- `KERNEL32!GetLongPathNameW` at `0x180005c0e`
- `KERNEL32!LocalAlloc` at `0x180005b88`
- `KERNEL32!LocalAlloc` at `0x180005b88`
- `KERNEL32!LocalFree` at `0x180005b5f`
- `KERNEL32!LocalFree` at `0x180005b5f`
- `KERNEL32!GetProcessHeap` at `0x1800055c1`
- `KERNEL32!GetProcessHeap` at `0x1800055c1`
- `KERNEL32!HeapAlloc` at `0x1800055d5`
- `KERNEL32!HeapAlloc` at `0x1800055d5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180005981`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180005c28`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180005981`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180005c28`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x180005836`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBackslashW` at `0x180005836`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x1800056b8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x1800056b8`
- `SHELL32!SHGetFolderPathW` at `0x18000573e`
- `SHELL32!SHGetFolderPathW` at `0x18000573e`
- `SHELL32!__imp_ILClone` at `0x18000552b`
- `SHELL32!__imp_ILClone` at `0x180005994`
- `SHELL32!__imp_ILClone` at `0x18000552b`
- `SHELL32!__imp_ILClone` at `0x180005994`
- `SHELL32!__imp_ILCloneFirst` at `0x1800057cf`
- `SHELL32!__imp_ILCloneFirst` at `0x1800057cf`
- `SHELL32!__imp_ILCombine` at `0x18000567e`
- `SHELL32!__imp_ILCombine` at `0x180005a74`
- `SHELL32!__imp_ILCombine` at `0x18000567e`
- `SHELL32!__imp_ILCombine` at `0x180005a74`
- `SHELL32!__imp_ILFree` at `0x1800056c3`
- `SHELL32!__imp_ILFree` at `0x1800056e6`
- `SHELL32!__imp_ILFree` at `0x180005715`
- `SHELL32!__imp_ILFree` at `0x180005a62`
- `SHELL32!__imp_ILFree` at `0x180005ada`
- `SHELL32!__imp_ILFree` at `0x1800056c3`
- `SHELL32!__imp_ILFree` at `0x1800056e6`
- `SHELL32!__imp_ILFree` at `0x180005715`
- `SHELL32!__imp_ILFree` at `0x180005a62`
- `SHELL32!__imp_ILFree` at `0x180005ada`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000585e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180005bc5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18000585e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180005bc5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180005954`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180005954`

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
          Interface = QISearch(v16, &pqit, v44, ppv);
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
0x1800054c0  push    rbp
0x1800054c2  push    rbx
0x1800054c3  push    rsi
0x1800054c4  push    rdi
0x1800054c5  push    r12
0x1800054c7  push    r13
0x1800054c9  push    r14
0x1800054cb  push    r15
0x1800054cd  lea     rbp, [rsp-5B8h]
0x1800054d5  sub     rsp, 6B8h
0x1800054dc  mov     rax, cs:__security_cookie
0x1800054e3  xor     rax, rsp
0x1800054e6  mov     [rbp+5F0h+var_50], rax
0x1800054ed  mov     r15, [rbp+5F0h+arg_20]
0x1800054f4  mov     rdi, r9
0x1800054f7  mov     [rsp+6F0h+riid], r9
0x1800054fc  mov     rsi, r8
0x1800054ff  mov     qword ptr [rsp+6F0h+var_6A8.dwLowDateTime], rdx
0x180005504  mov     r12, rdx
0x180005507  mov     [rsp+6F0h+ppv], r15
0x18000550c  mov     r13, rcx
0x18000550f  mov     qword ptr [r15], 0
0x180005516  test    dl, 3
0x180005519  jz      loc_180005825
0x18000551f  test    rdx, rdx
0x180005522  jz      loc_180005A40
0x180005528  mov     rcx, rdx; pidl
0x18000552b  call    cs:__imp_ILClone
0x180005531  xor     ebx, ebx
0x180005533  mov     r14, rax
0x180005536  test    rax, rax
0x180005539  mov     eax, 8007000Eh
0x18000553e  cmovz   ebx, eax
0x180005541  test    ebx, ebx
0x180005543  js      loc_1800056EC
0x180005549  movzx   eax, word ptr [r14]
0x18000554d  cmp     ax, 8
0x180005551  jnb     loc_18000575C
0x180005557  cmp     dword ptr [r13+80h], 0
0x18000555f  jnz     loc_180005AFE
0x180005565  mov     edi, [r13+34h]
0x180005569  mov     rcx, r14
0x18000556c  test    ax, ax
0x18000556f  jz      short loc_1800055C1
0x180005571  mov     r10d, 6368h
0x180005577  mov     r11d, 6365h
0x18000557d  mov     r8d, 6369h
0x180005583  mov     r9d, 6364h
0x180005589  test    ebx, ebx
0x18000558b  js      loc_1800056DE
0x180005591  cmp     edi, 1
0x180005594  jnz     loc_180005A22
0x18000559a  movzx   eax, word ptr [rcx+2]
0x18000559e  cmp     ax, r9w
0x1800055a2  jnz     loc_180005B4B
0x1800055a8  mov     edi, 2
0x1800055ad  movzx   eax, word ptr [rcx]
0x1800055b0  add     rcx, rax
0x1800055b3  cmp     word ptr [rcx], 0
0x1800055b7  jnz     short loc_180005589
0x1800055b9  test    ebx, ebx
0x1800055bb  js      loc_1800056DE
0x1800055c1  call    cs:__imp_GetProcessHeap
0x1800055c7  mov     edx, 8; dwFlags
0x1800055cc  mov     r8d, 290h; dwBytes
0x1800055d2  mov     rcx, rax; hHeap
0x1800055d5  call    cs:__imp_HeapAlloc
0x1800055db  mov     rsi, rax
0x1800055de  test    rax, rax
0x1800055e1  jz      loc_180005756
0x1800055e7  lea     rax, ??_7CHistFolder@@6BIShellFolder2@@@; const CHistFolder::`vftable'{for `IShellFolder2'}
0x1800055ee  mov     [rsi+34h], edi
0x1800055f1  xor     edi, edi
0x1800055f3  mov     [rsi], rax
0x1800055f6  lea     rax, ??_7CHistFolder@@6BIShellIcon@@@; const CHistFolder::`vftable'{for `IShellIcon'}
0x1800055fd  mov     dword ptr [rsi+30h], 1
0x180005604  mov     [rsi+8], rax
0x180005608  lea     rax, ??_7CHistFolder@@6BIShellFolderViewType@@@; const CHistFolder::`vftable'{for `IShellFolderViewType'}
0x18000560f  mov     [rsi+10h], rax
0x180005613  lea     rax, ??_7CHistFolder@@6BIShellFolderSearchable@@@; const CHistFolder::`vftable'{for `IShellFolderSearchable'}
0x18000561a  mov     [rsi+18h], rax
0x18000561e  lea     rax, ??_7CHistFolder@@6BIBrowserHistSFPrivate@@@; const CHistFolder::`vftable'{for `IBrowserHistSFPrivate'}
0x180005625  mov     [rsi+20h], rax
0x180005629  lea     rax, ??_7CHistFolder@@6BIPersistFolder2@@@; const CHistFolder::`vftable'{for `IPersistFolder2'}
0x180005630  mov     [rsi+28h], rax
0x180005634  mov     [rsi+38h], rdi
0x180005638  mov     [rsi+40h], rdi
0x18000563c  mov     [rsi+58h], rdi
0x180005640  mov     [rsi+68h], rdi
0x180005644  mov     [rsi+78h], rdi
0x180005648  mov     [rsi+288h], rdi
0x18000564f  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180005656  mov     rcx, [rsi+38h]; hMem
0x18000565a  mov     rbx, [r13+38h]
0x18000565e  test    rcx, rcx
0x180005661  jnz     loc_180005B5F
0x180005667  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000566e  test    rbx, rbx
0x180005671  jnz     loc_180005B6E
0x180005677  mov     rcx, [r13+68h]; pidl1
0x18000567b  mov     rdx, r14; pidl2
0x18000567e  call    cs:__imp_ILCombine
0x180005684  mov     r12, rax
0x180005687  test    rax, rax
0x18000568a  jnz     loc_180005711
0x180005690  mov     r12, qword ptr [rsp+6F0h+var_6A8.dwLowDateTime]
0x180005695  mov     ebx, 8007000Eh
0x18000569a  jmp     short loc_1800056CE
0x18000569c  cmp     dword ptr [rsi+34h], 1
0x1800056a0  jnz     loc_180005C3B
0x1800056a6  mov     r9, [rsp+6F0h+ppv]; ppv
0x1800056ab  lea     rdx, pqit; pqit
0x1800056b2  mov     r8, rbx; riid
0x1800056b5  mov     rcx, rsi; that
0x1800056b8  call    cs:__imp_QISearch
0x1800056be  mov     ebx, eax
0x1800056c0  mov     rcx, r12; pidl
0x1800056c3  call    cs:__imp_ILFree
0x1800056c9  mov     r12, qword ptr [rsp+6F0h+var_6A8.dwLowDateTime]
0x1800056ce  lock xadd [rsi+30h], r15d
0x1800056d4  cmp     r15d, 1
0x1800056d8  jz      loc_180005A15
0x1800056de  cmp     r14, r12
0x1800056e1  jz      short loc_1800056EC
0x1800056e3  mov     rcx, r14; pidl
0x1800056e6  call    cs:__imp_ILFree
0x1800056ec  mov     eax, ebx
0x1800056ee  mov     rcx, [rbp+5F0h+var_50]
0x1800056f5  xor     rcx, rsp; StackCookie
0x1800056f8  call    __security_check_cookie
0x1800056fd  add     rsp, 6B8h
0x180005704  pop     r15
0x180005706  pop     r14
0x180005708  pop     r13
0x18000570a  pop     r12
0x18000570c  pop     rdi
0x18000570d  pop     rsi
0x18000570e  pop     rbx
0x18000570f  pop     rbp
0x180005710  retn
0x180005711  mov     rcx, [rsi+68h]; pidl
0x180005715  call    cs:__imp_ILFree
0x18000571b  cmp     dword ptr [rsi+34h], 1
0x18000571f  jnz     loc_180005991
0x180005725  lea     rax, [rbp+5F0h+psz2]
0x18000572c  xor     r9d, r9d; dwFlags
0x18000572f  xor     r8d, r8d; hToken
0x180005732  mov     [rsp+6F0h+pszPath], rax; pszPath
0x180005737  mov     edx, 22h ; '"'; csidl
0x18000573c  xor     ecx, ecx; hwnd
0x18000573e  call    cs:__imp_SHGetFolderPathW
0x180005744  test    eax, eax
0x180005746  jns     loc_18000582F
0x18000574c  mov     ebx, 80004005h
0x180005751  jmp     loc_1800056C0
0x180005756  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000575c  mov     ecx, 6366h
0x180005761  cmp     [r14+2], cx
0x180005766  jnz     loc_180005557
0x18000576c  movzx   ecx, word ptr [r12+4]
0x180005772  mov     ebx, 80004005h
0x180005777  sub     ecx, 1
0x18000577a  jz      short loc_180005792
0x18000577c  sub     ecx, 1
0x18000577f  jz      short loc_180005792
0x180005781  sub     ecx, 1
0x180005784  jz      short loc_180005792
0x180005786  cmp     ecx, 4C41h
0x18000578c  jnz     loc_1800056DE
0x180005792  mov     ecx, 290h; dwBytes
0x180005797  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000579c  test    rax, rax
0x18000579f  jz      loc_180005AF4
0x1800057a5  mov     edx, 3
0x1800057aa  mov     rcx, rax
0x1800057ad  call    ??0CHistFolder@@QEAA@W4FOLDER_TYPE@@@Z; CHistFolder::CHistFolder(FOLDER_TYPE)
0x1800057b2  mov     [rsp+6F0h+var_6C0], rax
0x1800057b7  test    rax, rax
0x1800057ba  jz      loc_180005AF4
0x1800057c0  movzx   ecx, word ptr [r12+4]
0x1800057c6  mov     [rax+80h], ecx
0x1800057cc  mov     rcx, r12; pidl
0x1800057cf  call    cs:__imp_ILCloneFirst
0x1800057d5  mov     [rsp+6F0h+var_6B8], rax
0x1800057da  test    rax, rax
0x1800057dd  jz      loc_180005AE2
0x1800057e3  mov     ecx, 4C44h
0x1800057e8  cmp     [r12+4], cx
0x1800057ee  jnz     loc_180005A4D
0x1800057f4  mov     rcx, [r12+8]
0x1800057f9  mov     qword ptr [rsp+6F0h+var_6A8.dwLowDateTime], rcx
0x1800057fe  lea     rcx, [rsp+6F0h+var_6A8]; struct _FILETIME *
0x180005803  call    ?s_FindSearch@_CurrentSearches@@SAPEAV1@AEBU_FILETIME@@PEAV1@@Z; _CurrentSearches::s_FindSearch(_FILETIME const &,_CurrentSearches *)
0x180005808  mov     rcx, [rsp+6F0h+var_6C0]
0x18000580d  mov     [rcx+288h], rax
0x180005814  test    rax, rax
0x180005817  jnz     loc_180005A54
0x18000581d  mov     r13, rcx
0x180005820  jmp     loc_180005AD5
0x180005825  mov     r14, r12
0x180005828  xor     ebx, ebx
0x18000582a  jmp     loc_180005549
0x18000582f  lea     rcx, [rbp+5F0h+psz2]; pszPath
0x180005836  call    cs:__imp_PathRemoveBackslashW
0x18000583c  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180005843  test    rax, rax
0x180005846  jnz     loc_180005BB0
0x18000584c  mov     ebx, dword ptr [rsp+6F0h+var_6C0]
0x180005850  mov     edx, 6; dwCoInit
0x180005855  mov     [rbp+5F0h+pszBuf], di
0x18000585c  xor     ecx, ecx; pvReserved
0x18000585e  call    cs:__imp_CoInitializeEx
0x180005864  mov     dword ptr [rsp+6F0h+var_6C0], eax
0x180005868  mov     edi, eax
0x18000586a  test    eax, eax
0x18000586c  js      loc_180005BBE
0x180005872  xor     eax, eax
0x180005874  lea     r9, [rsp+6F0h+ppidlLast]; ppidlLast
0x180005879  lea     r8, [rsp+6F0h+var_6B8]; ppv
0x18000587e  mov     [rsp+6F0h+var_6B8], rax
0x180005883  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000588a  mov     [rsp+6F0h+ppidlLast], rax
0x18000588f  mov     rcx, r12; pidl
0x180005892  call    SHBindToParent_0
0x180005897  mov     r13d, eax
0x18000589a  test    eax, eax
0x18000589c  js      loc_180005950
0x1800058a2  mov     rax, [rsp+6F0h+var_6B8]
0x1800058a7  mov     r13, [rsp+6F0h+ppidlLast]
0x1800058ac  mov     [rsp+6F0h+var_698], rax
0x1800058b1  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x1800058b8  mov     [rsp+6F0h+pidl], r13
0x1800058bd  test    rax, rax
0x1800058c0  jnz     loc_180005BD6
0x1800058c6  mov     edi, dword ptr [rsp+6F0h+var_6C0]
0x1800058ca  xor     eax, eax
0x1800058cc  lea     rcx, [rsp+6F0h+pstr]; void *
0x1800058d1  xor     edx, edx; Val
0x1800058d3  mov     [rbp+5F0h+pszBuf], ax
0x1800058da  mov     r8d, 110h; Size
0x1800058e0  call    memset_0
0x1800058e5  mov     rcx, [rsp+6F0h+var_698]
0x1800058ea  lea     r9, [rsp+6F0h+pstr]
0x1800058ef  mov     r8d, 8000h
0x1800058f5  mov     rdx, r13
0x1800058f8  mov     rax, [rcx]
0x1800058fb  mov     rax, [rax+58h]
0x1800058ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005904  mov     r13d, eax
0x180005907  test    eax, eax
0x180005909  js      short loc_18000592B
0x18000590b  mov     rdx, [rsp+6F0h+pidl]; pidl
0x180005910  lea     r8, [rbp+5F0h+pszBuf]; pszBuf
0x180005917  mov     r9d, 104h; cchBuf
0x18000591d  lea     rcx, [rsp+6F0h+pstr]; pstr
0x180005922  call    cs:__imp_StrRetToBufW
0x180005928  mov     r13d, eax
0x18000592b  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180005932  test    rax, rax
0x180005935  jnz     loc_180005BE4
0x18000593b  mov     rcx, [rsp+6F0h+var_6B8]
0x180005940  mov     rax, [rcx]
0x180005943  mov     rax, [rax+10h]
0x180005947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594c  mov     edi, dword ptr [rsp+6F0h+var_6C0]
0x180005950  test    edi, edi
0x180005952  js      short loc_18000595A
0x180005954  call    cs:__imp_CoUninitialize
0x18000595a  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180005961  test    rax, rax
0x180005964  jnz     loc_180005BF0
0x18000596a  test    r13d, r13d
0x18000596d  js      loc_18000574C
0x180005973  lea     rdx, [rbp+5F0h+psz2]; psz2
0x18000597a  lea     rcx, [rbp+5F0h+pszBuf]; psz1
0x180005981  call    cs:__imp_StrCmpIW
0x180005987  test    eax, eax
0x180005989  jnz     loc_180005BFC
0x18000598f  xor     edi, edi
0x180005991  mov     rcx, r12; pidl
0x180005994  call    cs:__imp_ILClone
0x18000599a  mov     ebx, edi
0x18000599c  mov     ecx, 8007000Eh
0x1800059a1  test    rax, rax
0x1800059a4  mov     [rsi+68h], rax
0x1800059a8  cmovz   ebx, ecx
0x1800059ab  jz      loc_1800056C0
0x1800059b1  mov     rcx, rsi; this
0x1800059b4  call    ?_ExtractInfoFromPidl@CHistFolder@@QEAAJXZ; CHistFolder::_ExtractInfoFromPidl(void)
0x1800059b9  mov     ebx, eax
0x1800059bb  test    eax, eax
0x1800059bd  js      loc_1800056C0
0x1800059c3  mov     rbx, [rsp+6F0h+riid]
0x1800059c8  lea     rdx, IID_IPersistFolder; Buf2
0x1800059cf  mov     rcx, rbx; Buf1
0x1800059d2  mov     r8d, 10h; Size
0x1800059d8  call    memcmp_0
0x1800059dd  test    eax, eax
0x1800059df  jz      loc_18000569C
0x1800059e5  mov     r8d, 10h; Size
  ... truncated ...
```
