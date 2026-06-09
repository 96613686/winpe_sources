# CHistFolder::_NotifyWrite(ushort const *,int,_FILETIME const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180008330`
- end: `0x180009311`
- name: `?_NotifyWrite@CHistFolder@@IEAAJPEBGHPEBU_FILETIME@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `4065`
- prototype: `int(CHistFolder *__hidden this, const unsigned __int16 *, int, const struct _FILETIME *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006e10`
- `0x180007fc0`

## callees

- `0x180008330`
- `0x180009318`
- `0x18000a0f8`
- `0x18000c5c0`
- `0x180011230`
- `0x18004d3d0`
- `0x180056a6c`
- `0x1800bc150`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008cf6`
- `msvcrt!memcpy_s` at `0x180008cf6`
- `KERNEL32!CompareFileTime` at `0x1800089fc`
- `KERNEL32!CompareFileTime` at `0x180008a94`
- `KERNEL32!CompareFileTime` at `0x1800089fc`
- `KERNEL32!CompareFileTime` at `0x180008a94`
- `KERNEL32!FileTimeToSystemTime` at `0x180008b8a`
- `KERNEL32!FileTimeToSystemTime` at `0x180008b9b`
- `KERNEL32!FileTimeToSystemTime` at `0x180008b8a`
- `KERNEL32!FileTimeToSystemTime` at `0x180008b9b`
- `KERNEL32!LocalAlloc` at `0x180008769`
- `KERNEL32!LocalAlloc` at `0x180008769`
- `KERNEL32!LocalFree` at `0x1800085aa`
- `KERNEL32!LocalFree` at `0x1800085aa`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180008479`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180008fdb`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18000905e`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x1800090f6`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180009131`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180009229`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180008479`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180008fdb`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18000905e`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x1800090f6`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180009131`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180009229`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180008687`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800086d3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180008a6c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180008687`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800086d3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x180008a6c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x180008987`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x180008987`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000845e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180008fbf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180009042`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800090db`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000911d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000920d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000845e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180008fbf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180009042`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800090db`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000911d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000920d`
- `SHELL32!SHChangeNotify` at `0x180008d6f`
- `SHELL32!SHChangeNotify` at `0x180008eaa`
- `SHELL32!SHChangeNotify` at `0x180008f35`
- `SHELL32!SHChangeNotify` at `0x18000900a`
- `SHELL32!SHChangeNotify` at `0x1800092e9`
- `SHELL32!SHChangeNotify` at `0x180008d6f`
- `SHELL32!SHChangeNotify` at `0x180008eaa`
- `SHELL32!SHChangeNotify` at `0x180008f35`
- `SHELL32!SHChangeNotify` at `0x18000900a`
- `SHELL32!SHChangeNotify` at `0x1800092e9`
- `SHELL32!__imp_ILFindLastID` at `0x180008d2b`
- `SHELL32!__imp_ILFindLastID` at `0x180008d2b`
- `SHELL32!__imp_ILCombine` at `0x180008d12`
- `SHELL32!__imp_ILCombine` at `0x180008d50`
- `SHELL32!__imp_ILCombine` at `0x180008dac`
- `SHELL32!__imp_ILCombine` at `0x180008df8`
- `SHELL32!__imp_ILCombine` at `0x180008e7b`
- `SHELL32!__imp_ILCombine` at `0x180008e8f`
- `SHELL32!__imp_ILCombine` at `0x180008f74`
- `SHELL32!__imp_ILCombine` at `0x180008f97`
- `SHELL32!__imp_ILCombine` at `0x180008fef`
- `SHELL32!__imp_ILCombine` at `0x180008d12`
- `SHELL32!__imp_ILCombine` at `0x180008d50`
- `SHELL32!__imp_ILCombine` at `0x180008dac`
- `SHELL32!__imp_ILCombine` at `0x180008df8`
- `SHELL32!__imp_ILCombine` at `0x180008e7b`
- `SHELL32!__imp_ILCombine` at `0x180008e8f`
- `SHELL32!__imp_ILCombine` at `0x180008f74`
- `SHELL32!__imp_ILCombine` at `0x180008f97`
- `SHELL32!__imp_ILCombine` at `0x180008fef`
- `SHELL32!__imp_ILFree` at `0x18000859c`
- `SHELL32!__imp_ILFree` at `0x180008e1f`
- `SHELL32!__imp_ILFree` at `0x180008eb3`
- `SHELL32!__imp_ILFree` at `0x180008ebc`
- `SHELL32!__imp_ILFree` at `0x180008ec5`
- `SHELL32!__imp_ILFree` at `0x180008fac`
- `SHELL32!__imp_ILFree` at `0x180009013`
- `SHELL32!__imp_ILFree` at `0x18000901c`
- `SHELL32!__imp_ILFree` at `0x1800092f2`
- `SHELL32!__imp_ILFree` at `0x180009300`
- `SHELL32!__imp_ILFree` at `0x18000859c`
- `SHELL32!__imp_ILFree` at `0x180008e1f`
- `SHELL32!__imp_ILFree` at `0x180008eb3`
- `SHELL32!__imp_ILFree` at `0x180008ebc`
- `SHELL32!__imp_ILFree` at `0x180008ec5`
- `SHELL32!__imp_ILFree` at `0x180008fac`
- `SHELL32!__imp_ILFree` at `0x180009013`
- `SHELL32!__imp_ILFree` at `0x18000901c`
- `SHELL32!__imp_ILFree` at `0x1800092f2`
- `SHELL32!__imp_ILFree` at `0x180009300`
- `SHELL32!__imp_SHFree` at `0x180008db8`
- `SHELL32!__imp_SHFree` at `0x180008e04`
- `SHELL32!__imp_SHFree` at `0x180008f80`
- `SHELL32!__imp_SHFree` at `0x180008db8`
- `SHELL32!__imp_SHFree` at `0x180008e04`
- `SHELL32!__imp_SHFree` at `0x180008f80`
- `SHELL32!__imp_SHAlloc` at `0x180008d83`
- `SHELL32!__imp_SHAlloc` at `0x180008dcc`
- `SHELL32!__imp_SHAlloc` at `0x180008f40`
- `SHELL32!__imp_SHAlloc` at `0x180008d83`
- `SHELL32!__imp_SHAlloc` at `0x180008dcc`
- `SHELL32!__imp_SHAlloc` at `0x180008f40`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1800084c3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180008613`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1800084c3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180008613`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800091cf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800091d9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800091cf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800091d9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180008c26`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180008c26`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x1800084f5`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x1800084f5`
- `WININET!GetUrlCacheEntryInfoW` at `0x1800089ae`
- `WININET!GetUrlCacheEntryInfoW` at `0x1800089ae`
- `WININET!CommitUrlCacheEntryW` at `0x180009296`
- `WININET!CommitUrlCacheEntryW` at `0x180009296`

## pseudocode

```c
__int64 __fastcall CHistFolder::_NotifyWrite(
        CHistFolder *this,
        const unsigned __int16 *a2,
        __int64 a3,
        const struct _FILETIME *a4,
        struct _ITEMIDLIST_ABSOLUTE **a5)
{
  const WCHAR *v8; // rsi
  _WORD *v9; // rcx
  __int16 v10; // dx
  LPVOID *ppv; // r14
  __int64 (__fastcall ***v12)(CClassFactory *__hidden, const struct _GUID *, void **); // rbx
  signed int v13; // r15d
  __int64 (__fastcall ***i)(CClassFactory *__hidden, const struct _GUID *, void **); // rcx
  GUID *v15; // rax
  int v16; // eax
  unsigned __int64 j; // rcx
  GUID **v18; // r8
  GUID *v19; // rdx
  const WCHAR *v20; // rax
  LPVOID v21; // rdi
  int pszProtocol; // edi
  GUID *v23; // rax
  int v24; // eax
  unsigned __int64 k; // rcx
  GUID **v26; // r8
  GUID *v27; // rdx
  _WORD *v29; // r12
  __int64 *v30; // rbx
  FILETIME v31; // r13
  LPVOID *v32; // r14
  const WCHAR *v33; // rbx
  bool v34; // sf
  UINT v35; // edi
  WCHAR v36; // ax
  UINT nScheme; // esi
  HRESULT v38; // eax
  UINT v39; // ecx
  int v40; // r12d
  __int64 v41; // rbx
  unsigned __int16 v42; // bx
  _WORD *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdi
  unsigned int v46; // esi
  _WORD *v47; // rax
  unsigned __int16 v48; // r10
  unsigned __int16 *v49; // r11
  unsigned __int16 v50; // r9
  unsigned __int64 v51; // r8
  __int64 v52; // rcx
  _WORD *v53; // rdx
  _WORD *v54; // r9
  const WCHAR *v55; // r13
  int v56; // ebx
  _WORD *v57; // rdx
  void *v58; // rax
  unsigned __int64 v59; // r8
  __int64 v60; // rcx
  _WORD *v61; // r9
  WCHAR *v62; // r10
  __int64 v63; // r9
  unsigned int v64; // eax
  __int64 v65; // r8
  unsigned __int16 *v66; // rbx
  const WCHAR *v67; // rdx
  __int64 v68; // rcx
  CHistFolder *v69; // r15
  DWORD v70; // esi
  const WCHAR *v71; // r14
  const WCHAR *v72; // rcx
  CHistFolder *v73; // rcx
  __int64 v74; // rsi
  int m; // r14d
  __int64 v76; // r12
  __int64 v77; // r15
  const FILETIME *v78; // r13
  LPWSTR v79; // rax
  int Error; // r13d
  CHistFolder *v81; // r12
  __int16 *v82; // r14
  __int16 v83; // r15
  int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // rax
  __int64 v87; // rax
  CHAR *v88; // rsi
  unsigned __int64 v89; // rcx
  _WORD *v90; // rdx
  const ITEMIDLIST *v91; // rax
  ITEMIDLIST *v92; // rdi
  const ITEMIDLIST *ID; // rsi
  LPITEMIDLIST v94; // rax
  ITEMIDLIST *v95; // r14
  const ITEMIDLIST *v96; // r12
  char *v97; // rax
  void *v98; // rbx
  const ITEMIDLIST *v99; // rdx
  LPITEMIDLIST v100; // r15
  char *v101; // rax
  void *v102; // rbx
  LPITEMIDLIST v103; // rsi
  __int64 v104; // rax
  const ITEMIDLIST *v105; // rax
  ITEMIDLIST *v106; // rbx
  LPITEMIDLIST v107; // rax
  ITEMIDLIST *v108; // r15
  char *v109; // rax
  void *v110; // rbx
  LPITEMIDLIST v111; // r14
  LPITEMIDLIST v112; // rax
  ITEMIDLIST *v113; // rbx
  const WCHAR *v114; // rax
  LPITEMIDLIST v115; // rax
  ITEMIDLIST *v116; // rbx
  const WCHAR *v117; // rax
  const unsigned __int16 *v118; // rdx
  FILETIME v119; // r9
  char v120[8]; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcchOut; // [rsp+70h] [rbp-90h] BYREF
  __int16 v123; // [rsp+74h] [rbp-8Ch]
  CHistFolder *v124; // [rsp+78h] [rbp-88h]
  void *lpMem; // [rsp+80h] [rbp-80h]
  int v126; // [rsp+88h] [rbp-78h]
  int v127; // [rsp+8Ch] [rbp-74h]
  LPCWSTR lpszUrlName; // [rsp+90h] [rbp-70h]
  const WCHAR *v129; // [rsp+98h] [rbp-68h]
  PARSEDURLW ppu; // [rsp+A0h] [rbp-60h] BYREF
  _WORD *v131; // [rsp+C8h] [rbp-38h]
  struct _ITEMIDLIST_ABSOLUTE **v132; // [rsp+D0h] [rbp-30h]
  LPVOID v133[2]; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+E8h] [rbp-18h]
  __int128 v135; // [rsp+F8h] [rbp-8h]
  __int64 v136; // [rsp+108h] [rbp+8h]
  _WORD Source[264]; // [rsp+110h] [rbp+10h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+320h] [rbp+220h] BYREF
  FILETIME *lpFileTime2[2]; // [rsp+330h] [rbp+230h] BYREF
  CHAR pszSrc[272]; // [rsp+340h] [rbp+240h] BYREF
  CHAR pszDst[2]; // [rsp+450h] [rbp+350h] BYREF
  __int16 v142; // [rsp+452h] [rbp+352h]
  WCHAR pwszDst[1046]; // [rsp+454h] [rbp+354h] BYREF

  lpFileTime2[0] = (FILETIME *)a4;
  lpszUrlName = a2;
  v124 = this;
  v132 = a5;
  *(_QWORD *)&SystemTime.wYear = 0;
  if ( a2 && ((v20 = StrChrW(a2, 0x40u)) != 0 && *v20 || (v20 = StrChrW(a2, 0x20u)) != 0 && *v20) )
    v8 = CharNextW(v20);
  else
    v8 = 0;
  v9 = (_WORD *)*((_QWORD *)this + 14);
  v129 = v8;
  v131 = v9;
  v10 = *v9;
  *v9 = 0;
  v123 = v10;
  v136 = 0;
  *(_OWORD *)v133 = 0;
  *(_OWORD *)pv = 0;
  v135 = 0;
  if ( !v8 )
  {
    *v9 = v10;
    return 2147549183LL;
  }
  ppv = (LPVOID *)((char *)this + 120);
  v12 = &off_180551220;
  v13 = -2147467259;
  pcchOut = -2147467259;
  if ( !*ppv )
  {
    for ( i = &off_180551220; ; i += 7 )
    {
      v15 = (GUID *)i[1];
      if ( !v15 )
        break;
      if ( &CLSID_CUrlHistory == v15 )
      {
        if ( ((unsigned int (__fastcall *)(__int64 (__fastcall ***)(CClassFactory *__hidden, const struct _GUID *, void **), _QWORD, GUID *, LPVOID *))(*i)[3])(
               i,
               0,
               &IID_IUrlHistoryPriv,
               ppv) != -2147221231 )
          goto LABEL_22;
        break;
      }
    }
    v16 = -2147221231;
    for ( j = 0; j < 2; ++j )
    {
      v18 = (GUID **)*(&funcs_1800076AA + 2 * j + 1);
      v19 = *v18;
      if ( *v18 )
      {
        while ( v19 != &CLSID_CUrlHistory )
        {
          v19 = v18[1];
          ++v18;
          if ( !v19 )
            goto LABEL_14;
        }
        if ( *v18 )
        {
          v16 = ((__int64 (__fastcall *)(GUID *, _QWORD, GUID *, LPVOID *))*(&funcs_1800076AA + 2 * j))(
                  &CLSID_CUrlHistory,
                  0,
                  &IID_IUrlHistoryPriv,
                  ppv);
          break;
        }
      }
LABEL_14:
      ;
    }
    if ( v16 == -2147221231 )
      CoCreateInstance(&CLSID_CUrlHistory, 0, 1u, &IID_IUrlHistoryPriv, ppv);
  }
LABEL_22:
  if ( *ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 8LL))(*ppv);
  v21 = *ppv;
  if ( *ppv )
  {
    if ( SHUnicodeToAnsi(v8, pszDst, 2084) )
    {
      v13 = (*(__int64 (__fastcall **)(LPVOID, CHAR *, _QWORD, LPVOID *))(*(_QWORD *)v21 + 80LL))(v21, pszDst, 0, v133);
      pcchOut = v13;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
  }
  pszProtocol = 0;
  v127 = 0;
  if ( !*ppv )
  {
    while ( 1 )
    {
      v23 = (GUID *)v12[1];
      if ( !v23 )
        break;
      if ( &CLSID_CUrlHistory == v23 )
      {
        if ( ((unsigned int (__fastcall *)(__int64 (__fastcall ***)(CClassFactory *__hidden, const struct _GUID *, void **), _QWORD, GUID *, LPVOID *))(*v12)[3])(
               v12,
               0,
               &IID_IUrlHistoryPriv,
               ppv) != -2147221231 )
          goto LABEL_45;
        break;
      }
      v12 += 7;
    }
    v24 = -2147221231;
    for ( k = 0; k < 2; ++k )
    {
      v26 = (GUID **)*(&funcs_1800076AA + 2 * k + 1);
      v27 = *v26;
      if ( *v26 )
      {
        while ( v27 != &CLSID_CUrlHistory )
        {
          v27 = v26[1];
          ++v26;
          if ( !v27 )
            goto LABEL_37;
        }
        if ( *v26 )
        {
          v24 = ((__int64 (__fastcall *)(GUID *, _QWORD, GUID *, LPVOID *))*(&funcs_1800076AA + 2 * k))(
                  &CLSID_CUrlHistory,
                  0,
                  &IID_IUrlHistoryPriv,
                  ppv);
          break;
        }
      }
LABEL_37:
      ;
    }
    if ( v24 == -2147221231 )
      CoCreateInstance(&CLSID_CUrlHistory, 0, 1u, &IID_IUrlHistoryPriv, ppv);
  }
LABEL_45:
  if ( *ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 8LL))(*ppv);
  v30 = (__int64 *)*ppv;
  if ( *ppv )
  {
    v104 = *v30;
    memset(&ppu, 0, 24);
    if ( (*(int (__fastcall **)(__int64 *, const WCHAR *, const PROPERTYKEY *, PARSEDURLW *))(v104 + 120))(
           v30,
           v8,
           &PKEY_History_VisitCount,
           &ppu) >= 0 )
    {
      if ( LOWORD(ppu.cbSize) == 19 )
        pszProtocol = (int)ppu.pszProtocol;
      v127 = pszProtocol;
    }
    (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
  }
  v31 = *a4;
  v32 = v133;
  if ( v13 < 0 )
    v32 = 0;
  if ( v32 && (v33 = (const WCHAR *)v32[2]) != 0 )
  {
    memset(&ppu, 0, sizeof(ppu));
    ppu.cbSize = 40;
    v34 = ParseURLW(v33, &ppu) < 0;
    v35 = -1;
    v36 = *v33;
    nScheme = -1;
    if ( !v34 )
      nScheme = ppu.nScheme;
    if ( v36 != 92 && (!v36 || v33[1] != 58) )
    {
      memset(&ppu, 0, sizeof(ppu));
      ppu.cbSize = 40;
      v38 = ParseURLW(v33, &ppu);
      v39 = -1;
      if ( v38 >= 0 )
        v39 = ppu.nScheme;
      if ( v39 != 9 && ((nScheme + 1) & 0xFFFFFFFE) == 0 )
      {
        v40 = 1;
        v41 = -1;
        do
          ++v41;
        while ( *((_WORD *)v32[2] + v41) );
        v42 = 2 * (v41 + 1);
        lpMem = 0;
        goto LABEL_64;
      }
    }
  }
  else
  {
    v35 = -1;
  }
  v79 = 0;
  lpMem = 0;
  hMem = 0;
  if ( a2 )
  {
    v117 = StrChrW(a2, 0x40u);
    if ( v117 && *v117 || (v117 = StrChrW(a2, 0x20u)) != 0 && *v117 )
      v79 = CharNextW(v117);
    else
      v79 = 0;
  }
  if ( *v79 == 92 || *v79 && v79[1] == 58 )
    goto LABEL_222;
  memset(&ppu, 0, sizeof(ppu));
  ppu.cbSize = 40;
  if ( ParseURLW(v79, &ppu) >= 0 )
    v35 = ppu.nScheme;
  if ( v35 == 9 )
  {
LABEL_222:
    if ( v32 )
    {
      v118 = (const unsigned __int16 *)v32[1];
      if ( v118 )
      {
        if ( (int)_CopyPrefix(a2, v118, (unsigned __int16 **)&hMem) >= 0 )
        {
          lpMem = hMem;
          v43 = hMem;
          *(_DWORD *)v120 = 1;
          v42 = 0;
          v40 = 0;
          goto LABEL_65;
        }
        lpMem = hMem;
      }
    }
  }
  v42 = 0;
  v40 = 0;
LABEL_64:
  v43 = lpszUrlName;
  *(_DWORD *)v120 = 0;
LABEL_65:
  v44 = -1;
  do
    ++v44;
  while ( v43[v44] );
  hMem = 0;
  v45 = 2147483646;
  v126 = (unsigned __int16)(2 * (v44 + 1));
  v46 = v42 + v126 + 44;
  if ( v46 < 4 )
  {
    v29 = 0;
LABEL_103:
    v55 = lpszUrlName;
    v56 = *(_DWORD *)v120;
LABEL_89:
    v58 = lpMem;
    goto LABEL_90;
  }
  v47 = LocalAlloc(0x40u, v46);
  hMem = v47;
  if ( !v47 )
  {
    hMem = 0;
    v29 = 0;
    goto LABEL_103;
  }
  v48 = v126;
  v49 = v47 + 2;
  v47[1] = 25448;
  *v47 = v46 - 2;
  v47[2] = 40;
  v47[3] = v32 != 0;
  if ( v40 )
    v50 = v48 + 40;
  else
    v50 = 0;
  *((_DWORD *)v47 + 7) = v127;
  v47[4] = v50;
  *(FILETIME *)(v47 + 6) = v31;
  *((_QWORD *)v47 + 4) = 0;
  if ( !v32 )
  {
    *(FILETIME *)(v47 + 10) = v31;
LABEL_205:
    hMem = v47;
    v29 = v47;
    goto LABEL_80;
  }
  *(_QWORD *)(v47 + 10) = v32[3];
  if ( !v40 )
    goto LABEL_205;
  v51 = (unsigned __int64)v42 >> 1;
  if ( !v51 )
    goto LABEL_205;
  v29 = hMem;
  v52 = 2147483646;
  v53 = v32[2];
  v54 = (char *)hMem + v50;
  while ( v52 && *v53 )
  {
    *v54++ = *v53++;
    --v52;
    if ( !--v51 )
    {
      --v54;
      break;
    }
  }
  *v54 = 0;
LABEL_80:
  v55 = lpszUrlName;
  v56 = *(_DWORD *)v120;
  v57 = lpszUrlName;
  v58 = lpMem;
  if ( *(_DWORD *)v120 )
    v57 = lpMem;
  v59 = (unsigned __int64)v48 >> 1;
  if ( v59 )
  {
    v60 = 2147483646;
    v61 = (_WORD *)((char *)v29 + *v49);
    while ( v60 && *v57 )
    {
      *v61++ = *v57++;
      --v60;
      if ( !--v59 )
      {
        --v61;
        break;
      }
    }
    *v61 = 0;
    goto LABEL_89;
  }
LABEL_90:
  if ( v56 )
    operator delete(v58);
  if ( (pcchOut & 0x80000000) == 0 )
  {
    CoTaskMemFree(pv[0]);
    CoTaskMemFree(v133[1]);
  }
  if ( !v29 )
  {
    Error = -2147024882;
    goto LABEL_42;
  }
  v62 = (WCHAR *)v129;
  v63 = v129 - v55;
  v64 = 2085 - v63;
  if ( (unsigned int)(2085 - v63) <= 7 )
  {
LABEL_219:
    Error = -2147024882;
    goto LABEL_41;
  }
  v65 = v64;
  v66 = (unsigned __int16 *)(v129 + 7);
  if ( v64 <= 0x7FFFFFFFuLL )
  {
    v67 = L":Host: ";
    v68 = 2147483646;
    if ( v64 )
    {
      while ( v68 )
      {
        if ( !*v67 )
        {
          if ( !v65 )
            goto LABEL_101;
          break;
        }
        *v62++ = *v67++;
        --v68;
        if ( !--v65 )
          goto LABEL_101;
      }
    }
    else
    {
LABEL_101:
      --v62;
    }
  }
  v69 = v124;
  *v62 = 0;
  v70 = 2078 - v63;
  if ( !*((_WORD *)v69 + 68) )
    _GetLocalHost((LPWSTR)v69 + 68, 0x100u);
  if ( v29[1] == 25448
    && (v71 = (_WORD *)((char *)v29 + (unsigned __int16)v29[2])) != 0
    && ((v114 = StrChrW(v71, 0x40u)) != 0 && *v114 || (v114 = StrChrW(v71, 0x20u)) != 0 && *v114) )
  {
    v72 = CharNextW(v114);
  }
  else
  {
    v72 = 0;
  }
  pcchOut = v70;
  *v66 = 0;
  if ( UrlGetPartW(v72, v66, &pcchOut, 2u, 0) || !*v66 )
    StringCchCopyW(v66, v70, (const unsigned __int16 *)v69 + 68);
  pcchOut = 0;
  if ( !GetUrlCacheEntryInfoW(v55, 0, 0) )
  {
    v119 = *lpFileTime2[0];
    pcchOut = 1;
    if ( !CommitUrlCacheEntryW(v55, 0, *(FILETIME *)&SystemTime.wYear, v119, 0x200004u, 0, 0, 0, 0) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_41;
    }
  }
  v73 = v69;
  if ( *((_QWORD *)v69 + 11) )
  {
    v74 = 0;
    for ( m = 0; m < *((_DWORD *)v73 + 21); ++m )
    {
      v76 = 60LL * m;
      v77 = v76 + *((_QWORD *)v73 + 11);
      if ( *(_WORD *)(v77 + 58) == 1 )
      {
        v78 = lpFileTime2[0];
        if ( CompareFileTime((const FILETIME *)(v76 + *((_QWORD *)v73 + 11)), lpFileTime2[0]) <= 0
          && CompareFileTime(v78, (const FILETIME *)(v77 + 8)) < 0 )
        {
          v74 = v76 + *((_QWORD *)v124 + 11);
          if ( (unsigned int)(*(_QWORD *)(v74 + 8) / 864000000000LL) - (unsigned int)(*(_QWORD *)v74 / 864000000000LL) == 7 )
          {
            Error = 0;
            goto LABEL_132;
          }
        }
        v73 = v124;
      }
    }
    Error = v74 == 0;
LABEL_132:
    memset_0(Source, 0, 0x206u);
    memset_0(pszDst, 0, 0x23Eu);
    v81 = v124;
    v82 = (__int16 *)*((_QWORD *)v124 + 14);
    v83 = *v82;
    *v82 = 0;
    memset_0(pszDst, 0, 0x23Eu);
    v142 = *(_WORD *)(v74 + 56);
    v84 = *(unsigned __int16 *)(v74 + 58);
    SystemTime = 0;
    *(_OWORD *)lpFileTime2 = 0;
    if ( (_WORD)v84 )
      StringCchPrintfA(v120, 3u, "%02lu", v84);
    else
      v120[0] = 0;
    FileTimeToSystemTime((const FILETIME *)v74, &SystemTime);
    FileTimeToSystemTime((const FILETIME *)(v74 + 8), (LPSYSTEMTIME)lpFileTime2);
    StringCchPrintfA(
      pszSrc,
      0x104u,
      "%s%s%04lu%02lu%02lu%04lu%02lu%02lu",
      "MSHist",
      v120,
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      LOWORD(lpFileTime2[0]),
      WORD1(lpFileTime2[0]),
      HIWORD(lpFileTime2[0]));
    SHAnsiToUnicode(pszSrc, pwszDst, 25);
    v85 = -1;
    v86 = -1;
    do
      ++v86;
    while ( pwszDst[v86] );
    v87 = (unsigned __int16)(2 * (v86 + 3));
    v88 = &pszDst[v87];
    *(_WORD *)pszDst = v87;
    v89 = (unsigned __int64)(568 - v87) >> 1;
    if ( v89 )
    {
      if ( v89 > 0x7FFFFFFF )
      {
        *((_WORD *)v88 + 2) = 0;
      }
      else
      {
        v90 = v88 + 4;
        while ( v45 && *v66 )
        {
          *v90++ = *v66++;
          --v45;
          if ( !--v89 )
          {
            --v90;
            break;
          }
        }
        *v90 = 0;
        v85 = -1;
      }
    }
    Source[1] = 25445;
    do
      ++v85;
    while ( *(_WORD *)&v88[2 * v85 + 4] );
    Source[0] = 2 * (v85 + 3);
    memcpy_s(v88, 572LL - *(unsigned __int16 *)pszDst, Source, 4u);
    *(_WORD *)&v88[Source[0]] = 0;
    v91 = ILCombine(*((LPCITEMIDLIST *)v81 + 13), (LPCITEMIDLIST)pszDst);
    *v82 = v83;
    v92 = (ITEMIDLIST *)v91;
    if ( v91 )
    {
      ID = ILFindLastID(v91);
      if ( pcchOut )
      {
        SHChangeNotify(8, 0, v92, 0);
        v109 = (char *)SHAlloc(0xAu);
        v110 = v109;
        if ( v109 )
        {
          *(_DWORD *)(v109 + 6) = 0;
          *(_DWORD *)v109 = 1667629064;
          *((_WORD *)v109 + 2) = 1;
          if ( !ID )
          {
            v111 = (LPITEMIDLIST)v109;
            goto LABEL_171;
          }
          v111 = ILCombine((LPCITEMIDLIST)v109, ID);
          SHFree(v110);
          if ( v111 )
          {
LABEL_171:
            v112 = ILCombine(*((LPCITEMIDLIST *)v81 + 13), v111);
            v113 = v112;
            if ( v112 )
            {
              SHChangeNotify(8, 0, v112, 0);
              ILFree(v113);
            }
            ILFree(v111);
          }
        }
      }
      v29 = hMem;
      v94 = ILCombine(v92, (LPCITEMIDLIST)hMem);
      v95 = v94;
      if ( v94 )
      {
        SHChangeNotify(2, 0, v94, 0);
        v96 = (const ITEMIDLIST *)*((_QWORD *)v124 + 13);
        v97 = (char *)SHAlloc(0xAu);
        v98 = v97;
        if ( v97 )
        {
          *(_DWORD *)(v97 + 6) = 0;
          v99 = (const ITEMIDLIST *)hMem;
          *(_DWORD *)v97 = 1667629064;
          *((_WORD *)v97 + 2) = 3;
          v100 = ILCombine((LPCITEMIDLIST)v97, v99);
          SHFree(v98);
          if ( v100 )
          {
            v115 = ILCombine(v96, v100);
            v116 = v115;
            if ( v115 )
            {
              SHChangeNotify(2, 0, v115, 0);
              ILFree(v116);
            }
            ILFree(v100);
          }
        }
        v101 = (char *)SHAlloc(0xAu);
        v102 = v101;
        if ( !v101 )
          goto LABEL_154;
        *(_DWORD *)(v101 + 6) = 0;
        *(_DWORD *)v101 = 1667629064;
        *((_WORD *)v101 + 2) = 1;
        if ( ID )
        {
          v103 = ILCombine((LPCITEMIDLIST)v101, ID);
          SHFree(v102);
          if ( !v103 )
          {
LABEL_154:
            if ( v132 )
              *v132 = (struct _ITEMIDLIST_ABSOLUTE *)v95;
            else
              ILFree(v95);
            ILFree(v92);
            v29 = hMem;
            goto LABEL_41;
          }
        }
        else
        {
          v103 = (LPITEMIDLIST)v101;
        }
        v105 = ILCombine(v103, (LPCITEMIDLIST)hMem);
        v106 = (ITEMIDLIST *)v105;
        if ( v105 )
        {
          v107 = ILCombine(v96, v105);
          v108 = v107;
          if ( v107 )
          {
            SHChangeNotify(2, 0, v107, 0);
            ILFree(v108);
          }
          ILFree(v106);
        }
        ILFree(v103);
        goto LABEL_154;
      }
      ILFree(v92);
      goto LABEL_219;
    }
    v29 = hMem;
    Error = -2147024882;
  }
  else
  {
    Error = -2147467259;
  }
LABEL_41:
  LocalFree(v29);
LABEL_42:
  *v131 = v123;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180008330  push    rbp
0x180008332  push    rbx
0x180008333  push    rsi
0x180008334  push    rdi
0x180008335  push    r12
0x180008337  push    r13
0x180008339  lea     rbp, [rsp-0B98h]
0x180008341  sub     rsp, 0C98h
0x180008348  mov     rax, cs:__security_cookie
0x18000834f  xor     rax, rsp
0x180008352  mov     [rbp+0BC0h+var_40], rax
0x180008359  mov     rax, [rbp+0BC0h+arg_20]
0x180008360  xor     edi, edi
0x180008362  mov     [rbp+0BC0h+lpFileTime2], r9
0x180008369  mov     r13, r9
0x18000836c  mov     [rbp+0BC0h+lpszUrlName], rdx
0x180008370  mov     r12, rdx
0x180008373  mov     [rsp+0CC0h+var_C48], rcx
0x180008378  mov     rbx, rcx
0x18000837b  mov     [rbp+0BC0h+var_BF0], rax
0x18000837f  mov     qword ptr [rbp+0BC0h+SystemTime.wYear], rdi
0x180008386  test    rdx, rdx
0x180008389  jnz     loc_180008456
0x18000838f  mov     rsi, rdi
0x180008392  mov     rcx, [rbx+70h]
0x180008396  xorps   xmm0, xmm0
0x180008399  xor     eax, eax
0x18000839b  mov     [rbp+0BC0h+var_C28], rsi
0x18000839f  mov     [rbp+0BC0h+var_BF8], rcx
0x1800083a3  movzx   edx, word ptr [rcx]
0x1800083a6  mov     [rcx], di
0x1800083a9  mov     [rsp+0CC0h+var_C4C], dx
0x1800083ae  mov     [rbp+0BC0h+var_BB8], rax
0x1800083b2  movups  xmmword ptr [rbp+0BC0h+var_BE8], xmm0
0x1800083b6  movups  xmmword ptr [rbp+0BC0h+pv], xmm0
0x1800083ba  movups  [rbp+0BC0h+var_BC8], xmm0
0x1800083be  test    rsi, rsi
0x1800083c1  jz      loc_18000858C
0x1800083c7  lea     rdi, CLSID_CUrlHistory
0x1800083ce  mov     [rsp+0CC0h+arg_10], r14
0x1800083d6  lea     r14, [rbx+78h]
0x1800083da  mov     [rsp+0CC0h+var_30], r15
0x1800083e2  lea     rbx, off_180551220
0x1800083e9  mov     r15d, 80004005h
0x1800083ef  lea     r11, funcs_1800076AA
0x1800083f6  mov     [rsp+0CC0h+pcchOut], r15d
0x1800083fb  cmp     [r14], rax
0x1800083fe  jnz     loc_1800084C9
0x180008404  mov     rcx, rbx
0x180008407  mov     rax, [rcx+8]
0x18000840b  test    rax, rax
0x18000840e  jz      short loc_18000841F
0x180008410  cmp     rdi, rax
0x180008413  jz      loc_180008EFB
0x180008419  add     rcx, 38h ; '8'
0x18000841d  jmp     short loc_180008407
0x18000841f  mov     eax, 80040111h
0x180008424  xor     ecx, ecx
0x180008426  cmp     rcx, 2
0x18000842a  jnb     short loc_1800084A5
0x18000842c  mov     r10, rcx
0x18000842f  add     r10, r10
0x180008432  mov     r8, [r11+r10*8+8]
0x180008437  mov     rdx, [r8]
0x18000843a  test    rdx, rdx
0x18000843d  jz      short loc_180008451
0x18000843f  cmp     rdx, rdi
0x180008442  jz      short loc_180008487
0x180008444  mov     rdx, [r8+8]
0x180008448  add     r8, 8
0x18000844c  test    rdx, rdx
0x18000844f  jnz     short loc_18000843F
0x180008451  inc     rcx
0x180008454  jmp     short loc_180008426
0x180008456  mov     edx, 40h ; '@'; wMatch
0x18000845b  mov     rcx, r12; pszStart
0x18000845e  call    cs:__imp_StrChrW
0x180008464  test    rax, rax
0x180008467  jz      loc_1800090D3
0x18000846d  cmp     [rax], di
0x180008470  jz      loc_1800090D3
0x180008476  mov     rcx, rax; lpsz
0x180008479  call    cs:__imp_CharNextW
0x18000847f  mov     rsi, rax
0x180008482  jmp     loc_180008392
0x180008487  cmp     qword ptr [r8], 0
0x18000848b  jz      short loc_180008451
0x18000848d  mov     rax, ds:(funcs_1800076AA - 180552950h)[r11+r10*8]
0x180008491  lea     r8, IID_IUrlHistoryPriv
0x180008498  mov     r9, r14
0x18000849b  xor     edx, edx
0x18000849d  mov     rcx, rdi
0x1800084a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a5  cmp     eax, 80040111h
0x1800084aa  jnz     short loc_1800084C9
0x1800084ac  lea     r9, IID_IUrlHistoryPriv; riid
0x1800084b3  mov     [rsp+0CC0h+ppv], r14; ppv
0x1800084b8  xor     edx, edx; pUnkOuter
0x1800084ba  mov     r8d, 1; dwClsContext
0x1800084c0  mov     rcx, rdi; rclsid
0x1800084c3  call    cs:__imp_CoCreateInstance
0x1800084c9  mov     rcx, [r14]
0x1800084cc  test    rcx, rcx
0x1800084cf  jz      short loc_1800084DD
0x1800084d1  mov     rax, [rcx]
0x1800084d4  mov     rax, [rax+8]
0x1800084d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084dd  mov     rdi, [r14]
0x1800084e0  test    rdi, rdi
0x1800084e3  jz      short loc_180008512
0x1800084e5  mov     r8d, 824h; cchBuf
0x1800084eb  lea     rdx, [rbp+0BC0h+pszDst]; pszDst
0x1800084f2  mov     rcx, rsi; pwszSrc
0x1800084f5  call    cs:__imp_SHUnicodeToAnsi
0x1800084fb  test    eax, eax
0x1800084fd  jnz     loc_180009078
0x180008503  mov     rdx, [rdi]
0x180008506  mov     rcx, rdi
0x180008509  mov     rax, [rdx+10h]
0x18000850d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008512  xor     edi, edi
0x180008514  mov     [rbp+0BC0h+var_C34], edi
0x180008517  cmp     [r14], rdi
0x18000851a  jnz     loc_180008619
0x180008520  lea     rcx, CLSID_CUrlHistory
0x180008527  mov     rax, [rbx+8]
0x18000852b  test    rax, rax
0x18000852e  jz      short loc_18000853F
0x180008530  cmp     rcx, rax
0x180008533  jz      loc_180008ED0
0x180008539  add     rbx, 38h ; '8'
0x18000853d  jmp     short loc_180008527
0x18000853f  mov     eax, 80040111h
0x180008544  lea     r11, funcs_1800076AA
0x18000854b  xor     ecx, ecx
0x18000854d  cmp     rcx, 2
0x180008551  jnb     loc_1800085EE
0x180008557  mov     r10, rcx
0x18000855a  add     r10, r10
0x18000855d  mov     r8, [r11+r10*8+8]
0x180008562  mov     rdx, [r8]
0x180008565  test    rdx, rdx
0x180008568  jz      short loc_180008587
0x18000856a  lea     rbx, CLSID_CUrlHistory
0x180008571  cmp     rdx, rbx
0x180008574  jz      loc_1800090A1
0x18000857a  mov     rdx, [r8+8]
0x18000857e  add     r8, 8
0x180008582  test    rdx, rdx
0x180008585  jnz     short loc_180008571
0x180008587  inc     rcx
0x18000858a  jmp     short loc_18000854D
0x18000858c  mov     [rcx], dx
0x18000858f  mov     eax, 8000FFFFh
0x180008594  jmp     short loc_1800085CF
0x180008596  mov     [rax], r14
0x180008599  mov     rcx, rdi; pidl
0x18000859c  call    cs:__imp_ILFree
0x1800085a2  mov     r12, [rsp+0CC0h+hMem]
0x1800085a7  mov     rcx, r12; hMem
0x1800085aa  call    cs:__imp_LocalFree
0x1800085b0  mov     rax, [rbp+0BC0h+var_BF8]
0x1800085b4  movzx   ecx, [rsp+0CC0h+var_C4C]
0x1800085b9  mov     r14, [rsp+0CC0h+arg_10]
0x1800085c1  mov     r15, [rsp+0CC0h+var_30]
0x1800085c9  mov     [rax], cx
0x1800085cc  mov     eax, r13d
0x1800085cf  mov     rcx, [rbp+0BC0h+var_40]
0x1800085d6  xor     rcx, rsp; StackCookie
0x1800085d9  call    __security_check_cookie
0x1800085de  add     rsp, 0C98h
0x1800085e5  pop     r13
0x1800085e7  pop     r12
0x1800085e9  pop     rdi
0x1800085ea  pop     rsi
0x1800085eb  pop     rbx
0x1800085ec  pop     rbp
0x1800085ed  retn
0x1800085ee  lea     rbx, CLSID_CUrlHistory
0x1800085f5  cmp     eax, 80040111h
0x1800085fa  jnz     short loc_180008619
0x1800085fc  lea     r9, IID_IUrlHistoryPriv; riid
0x180008603  mov     [rsp+0CC0h+ppv], r14; ppv
0x180008608  xor     edx, edx; pUnkOuter
0x18000860a  mov     r8d, 1; dwClsContext
0x180008610  mov     rcx, rbx; rclsid
0x180008613  call    cs:__imp_CoCreateInstance
0x180008619  mov     rcx, [r14]
0x18000861c  test    rcx, rcx
0x18000861f  jz      short loc_18000862D
0x180008621  mov     rax, [rcx]
0x180008624  mov     rax, [rax+8]
0x180008628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000862d  mov     rbx, [r14]
0x180008630  test    rbx, rbx
0x180008633  jnz     loc_180008E2A
0x180008639  mov     r13, [r13+0]
0x18000863d  lea     r14, [rbp+0BC0h+var_BE8]
0x180008641  xor     eax, eax
0x180008643  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000864a  test    r15d, r15d
0x18000864d  cmovs   r14, rax
0x180008651  test    r14, r14
0x180008654  jz      loc_180008A14
0x18000865a  mov     rbx, [r14+10h]
0x18000865e  test    rbx, rbx
0x180008661  jz      loc_180008A14
0x180008667  xorps   xmm0, xmm0
0x18000866a  mov     qword ptr [rbp+0BC0h+ppu.cchSuffix], rax
0x18000866e  movups  xmmword ptr [rbp+0BC0h+ppu.cbSize], xmm0
0x180008672  mov     r15d, 28h ; '('
0x180008678  lea     rdx, [rbp+0BC0h+ppu]; ppu
0x18000867c  mov     rcx, rbx; pcszURL
0x18000867f  mov     [rbp+0BC0h+ppu.cbSize], r15d
0x180008683  movups  xmmword ptr [rbp+0BC0h+ppu.cchProtocol], xmm0
0x180008687  call    cs:__imp_ParseURLW
0x18000868d  test    eax, eax
0x18000868f  mov     edi, 0FFFFFFFFh
0x180008694  movzx   eax, word ptr [rbx]
0x180008697  mov     esi, edi
0x180008699  cmovns  esi, [rbp+0BC0h+ppu.nScheme]
0x18000869d  cmp     ax, 5Ch ; '\'
0x1800086a1  jz      loc_1800090C7
0x1800086a7  test    ax, ax
0x1800086aa  jz      short loc_1800086B7
0x1800086ac  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800086b1  jz      loc_1800090C7
0x1800086b7  xorps   xmm0, xmm0
0x1800086ba  lea     rdx, [rbp+0BC0h+ppu]; ppu
0x1800086be  xor     eax, eax
0x1800086c0  mov     rcx, rbx; pcszURL
0x1800086c3  movups  xmmword ptr [rbp+0BC0h+ppu.cbSize], xmm0
0x1800086c7  mov     [rbp+0BC0h+ppu.cbSize], r15d
0x1800086cb  movups  xmmword ptr [rbp+0BC0h+ppu.cchProtocol], xmm0
0x1800086cf  mov     qword ptr [rbp+0BC0h+ppu.cchSuffix], rax
0x1800086d3  call    cs:__imp_ParseURLW
0x1800086d9  test    eax, eax
0x1800086db  mov     ecx, edi
0x1800086dd  cmovns  ecx, [rbp+0BC0h+ppu.nScheme]
0x1800086e1  cmp     ecx, 9
0x1800086e4  jz      loc_1800090C7
0x1800086ea  lea     eax, [rsi+1]
0x1800086ed  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800086f4  test    eax, 0FFFFFFFEh
0x1800086f9  jnz     loc_180008A1F
0x1800086ff  mov     rax, [r14+10h]
0x180008703  mov     r12d, 1
0x180008709  mov     rbx, rsi
0x18000870c  nop     dword ptr [rax+00h]
0x180008710  inc     rbx
0x180008713  cmp     word ptr [rax+rbx*2], 0
0x180008718  jnz     short loc_180008710
0x18000871a  inc     bx
0x18000871d  add     bx, bx
0x180008720  xor     edx, edx
0x180008722  mov     [rbp+0BC0h+lpMem], rdx
0x180008726  mov     rcx, [rbp+0BC0h+lpszUrlName]
0x18000872a  mov     dword ptr [rsp+0CC0h+var_C60], edx
0x18000872e  mov     rax, rsi
0x180008731  inc     rax
0x180008734  cmp     word ptr [rcx+rax*2], 0
0x180008739  jnz     short loc_180008731
0x18000873b  inc     ax
0x18000873e  mov     [rsp+0CC0h+hMem], rdx
0x180008743  add     ax, ax
0x180008746  mov     edi, 7FFFFFFEh
0x18000874b  movzx   ecx, ax
0x18000874e  movzx   eax, bx
0x180008751  mov     [rbp+0BC0h+var_C38], ecx
0x180008754  lea     esi, [rcx+2Ch]
0x180008757  add     esi, eax
0x180008759  cmp     esi, 4
0x18000875c  jb      loc_180008918
0x180008762  mov     edx, esi; uBytes
0x180008764  mov     ecx, 40h ; '@'; uFlags
0x180008769  call    cs:__imp_LocalAlloc
0x18000876f  mov     [rsp+0CC0h+hMem], rax
0x180008774  mov     rcx, rax
0x180008777  test    rax, rax
0x18000877a  jz      loc_1800091B1
0x180008780  mov     r10d, [rbp+0BC0h+var_C38]
0x180008784  lea     r11, [rax+4]
0x180008788  mov     word ptr [rax+2], 6368h
0x18000878e  sub     si, 2
0x180008792  mov     [rax], si
0x180008795  xor     eax, eax
0x180008797  test    r14, r14
0x18000879a  mov     [r11], r15w
0x18000879e  setnz   al
0x1800087a1  mov     [rcx+6], ax
0x1800087a5  test    r12d, r12d
0x1800087a8  jz      loc_180009198
0x1800087ae  lea     r9d, [r10+28h]
0x1800087b2  mov     eax, [rbp+0BC0h+var_C34]
0x1800087b5  mov     [rcx+1Ch], eax
0x1800087b8  mov     [rcx+8], r9w
0x1800087bd  mov     [rcx+0Ch], r13
0x1800087c1  mov     qword ptr [rcx+20h], 0
0x1800087c9  test    r14, r14
0x1800087cc  jz      loc_1800091A0
  ... truncated ...
```
