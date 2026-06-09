# CHistFolder::_NotifyWrite(ushort const *,int,_FILETIME const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x18000f640`
- end: `0x180010714`
- name: `?_NotifyWrite@CHistFolder@@IEAAJPEBGHPEBU_FILETIME@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `4308`
- prototype: `int(CHistFolder *__hidden this, const unsigned __int16 *, int, const struct _FILETIME *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e020`
- `0x18000f2a0`

## callees

- `0x1800096a0`
- `0x18000bc38`
- `0x18000f640`
- `0x18001071c`
- `0x180010c30`
- `0x1800144d0`
- `0x1800509d0`
- `0x18005a4a0`
- `0x1800c2e80`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010086`
- `msvcrt!memcpy_s` at `0x180010086`
- `KERNEL32!CompareFileTime` at `0x18000fd68`
- `KERNEL32!CompareFileTime` at `0x18000fe0b`
- `KERNEL32!CompareFileTime` at `0x18000fd68`
- `KERNEL32!CompareFileTime` at `0x18000fe0b`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ff07`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ff1e`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ff07`
- `KERNEL32!FileTimeToSystemTime` at `0x18000ff1e`
- `KERNEL32!LocalAlloc` at `0x18000fab9`
- `KERNEL32!LocalAlloc` at `0x18000fab9`
- `KERNEL32!LocalFree` at `0x18000f8dc`
- `KERNEL32!LocalFree` at `0x18000f8dc`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18000f793`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180010405`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18000f793`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x180010405`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18000f9c6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18000fa18`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18000fddd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18000f9c6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18000fa18`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18000fddd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x18000fce7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x18000fce7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000f772`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800103e3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800104f4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800105fe`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x18000f772`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800103e3`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800104f4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800105fe`
- `SHELL32!SHChangeNotify` at `0x180010117`
- `SHELL32!SHChangeNotify` at `0x180010292`
- `SHELL32!SHChangeNotify` at `0x180010335`
- `SHELL32!SHChangeNotify` at `0x180010440`
- `SHELL32!SHChangeNotify` at `0x1800106da`
- `SHELL32!SHChangeNotify` at `0x180010117`
- `SHELL32!SHChangeNotify` at `0x180010292`
- `SHELL32!SHChangeNotify` at `0x180010335`
- `SHELL32!SHChangeNotify` at `0x180010440`
- `SHELL32!SHChangeNotify` at `0x1800106da`
- `SHELL32!__imp_ILFindLastID` at `0x1800100c7`
- `SHELL32!__imp_ILFindLastID` at `0x1800100c7`
- `SHELL32!__imp_ILCombine` at `0x1800100a8`
- `SHELL32!__imp_ILCombine` at `0x1800100f2`
- `SHELL32!__imp_ILCombine` at `0x180010160`
- `SHELL32!__imp_ILCombine` at `0x1800101c2`
- `SHELL32!__imp_ILCombine` at `0x180010257`
- `SHELL32!__imp_ILCombine` at `0x180010271`
- `SHELL32!__imp_ILCombine` at `0x180010380`
- `SHELL32!__imp_ILCombine` at `0x1800103af`
- `SHELL32!__imp_ILCombine` at `0x18001041f`
- `SHELL32!__imp_ILCombine` at `0x1800100a8`
- `SHELL32!__imp_ILCombine` at `0x1800100f2`
- `SHELL32!__imp_ILCombine` at `0x180010160`
- `SHELL32!__imp_ILCombine` at `0x1800101c2`
- `SHELL32!__imp_ILCombine` at `0x180010257`
- `SHELL32!__imp_ILCombine` at `0x180010271`
- `SHELL32!__imp_ILCombine` at `0x180010380`
- `SHELL32!__imp_ILCombine` at `0x1800103af`
- `SHELL32!__imp_ILCombine` at `0x18001041f`
- `SHELL32!__imp_ILFree` at `0x18000f8c8`
- `SHELL32!__imp_ILFree` at `0x1800101f5`
- `SHELL32!__imp_ILFree` at `0x1800102a1`
- `SHELL32!__imp_ILFree` at `0x1800102b0`
- `SHELL32!__imp_ILFree` at `0x1800102bf`
- `SHELL32!__imp_ILFree` at `0x1800103ca`
- `SHELL32!__imp_ILFree` at `0x18001044f`
- `SHELL32!__imp_ILFree` at `0x18001045e`
- `SHELL32!__imp_ILFree` at `0x1800106e9`
- `SHELL32!__imp_ILFree` at `0x1800106fd`
- `SHELL32!__imp_ILFree` at `0x18000f8c8`
- `SHELL32!__imp_ILFree` at `0x1800101f5`
- `SHELL32!__imp_ILFree` at `0x1800102a1`
- `SHELL32!__imp_ILFree` at `0x1800102b0`
- `SHELL32!__imp_ILFree` at `0x1800102bf`
- `SHELL32!__imp_ILFree` at `0x1800103ca`
- `SHELL32!__imp_ILFree` at `0x18001044f`
- `SHELL32!__imp_ILFree` at `0x18001045e`
- `SHELL32!__imp_ILFree` at `0x1800106e9`
- `SHELL32!__imp_ILFree` at `0x1800106fd`
- `SHELL32!__imp_SHFree` at `0x180010172`
- `SHELL32!__imp_SHFree` at `0x1800101d4`
- `SHELL32!__imp_SHFree` at `0x180010392`
- `SHELL32!__imp_SHFree` at `0x180010172`
- `SHELL32!__imp_SHFree` at `0x1800101d4`
- `SHELL32!__imp_SHFree` at `0x180010392`
- `SHELL32!__imp_SHAlloc` at `0x180010131`
- `SHELL32!__imp_SHAlloc` at `0x18001018c`
- `SHELL32!__imp_SHAlloc` at `0x180010346`
- `SHELL32!__imp_SHAlloc` at `0x180010131`
- `SHELL32!__imp_SHAlloc` at `0x18001018c`
- `SHELL32!__imp_SHAlloc` at `0x180010346`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18000f7e3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18000f94c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18000f7e3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18000f94c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800105b4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800105c4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800105b4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800105c4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000ffaf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18000ffaf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000f81b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHUnicodeToAnsi` at `0x18000f81b`
- `WININET!GetUrlCacheEntryInfoW` at `0x18000fd14`
- `WININET!GetUrlCacheEntryInfoW` at `0x18000fd14`
- `WININET!CommitUrlCacheEntryW` at `0x180010681`
- `WININET!CommitUrlCacheEntryW` at `0x180010681`

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
  __int64 v79; // rax
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
  const unsigned __int16 *v117; // rdx
  FILETIME v118; // r9
  char v119[8]; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcchOut; // [rsp+70h] [rbp-90h] BYREF
  __int16 v122; // [rsp+74h] [rbp-8Ch]
  CHistFolder *v123; // [rsp+78h] [rbp-88h]
  void *lpMem; // [rsp+80h] [rbp-80h]
  int v125; // [rsp+88h] [rbp-78h]
  int v126; // [rsp+8Ch] [rbp-74h]
  LPCWSTR lpszUrlName; // [rsp+90h] [rbp-70h]
  const WCHAR *v128; // [rsp+98h] [rbp-68h]
  PARSEDURLW ppu; // [rsp+A0h] [rbp-60h] BYREF
  _WORD *v130; // [rsp+C8h] [rbp-38h]
  struct _ITEMIDLIST_ABSOLUTE **v131; // [rsp+D0h] [rbp-30h]
  LPVOID v132[2]; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+E8h] [rbp-18h]
  __int128 v134; // [rsp+F8h] [rbp-8h]
  __int64 v135; // [rsp+108h] [rbp+8h]
  _WORD Source[264]; // [rsp+110h] [rbp+10h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+320h] [rbp+220h] BYREF
  FILETIME *lpFileTime2[2]; // [rsp+330h] [rbp+230h] BYREF
  CHAR pszSrc[272]; // [rsp+340h] [rbp+240h] BYREF
  CHAR pszDst[2]; // [rsp+450h] [rbp+350h] BYREF
  __int16 v141; // [rsp+452h] [rbp+352h]
  WCHAR pwszDst[1046]; // [rsp+454h] [rbp+354h] BYREF

  lpFileTime2[0] = (FILETIME *)a4;
  lpszUrlName = a2;
  v123 = this;
  v131 = a5;
  *(_QWORD *)&SystemTime.wYear = 0;
  if ( a2 && ((v20 = StrChrW(a2, 0x40u)) != 0 && *v20 || (v20 = StrChrW(a2, 0x20u)) != 0 && *v20) )
    v8 = CharNextW(v20);
  else
    v8 = 0;
  v9 = (_WORD *)*((_QWORD *)this + 14);
  v128 = v8;
  v130 = v9;
  v10 = *v9;
  *v9 = 0;
  v122 = v10;
  v135 = 0;
  *(_OWORD *)v132 = 0;
  *(_OWORD *)pv = 0;
  v134 = 0;
  if ( !v8 )
  {
    *v9 = v10;
    return 2147549183LL;
  }
  ppv = (LPVOID *)((char *)this + 120);
  v12 = &off_180595220;
  v13 = -2147467259;
  pcchOut = -2147467259;
  if ( !*ppv )
  {
    for ( i = &off_180595220; ; i += 7 )
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
      v18 = (GUID **)*(&funcs_18000E8DA + 2 * j + 1);
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
          v16 = ((__int64 (__fastcall *)(GUID *, _QWORD, GUID *, LPVOID *))*(&funcs_18000E8DA + 2 * j))(
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
      v13 = (*(__int64 (__fastcall **)(LPVOID, CHAR *, _QWORD, LPVOID *))(*(_QWORD *)v21 + 80LL))(v21, pszDst, 0, v132);
      pcchOut = v13;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
  }
  pszProtocol = 0;
  v126 = 0;
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
      v26 = (GUID **)*(&funcs_18000E8DA + 2 * k + 1);
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
          v24 = ((__int64 (__fastcall *)(GUID *, _QWORD, GUID *, LPVOID *))*(&funcs_18000E8DA + 2 * k))(
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
      v126 = pszProtocol;
    }
    (*(void (__fastcall **)(__int64 *))(*v30 + 16))(v30);
  }
  v31 = *a4;
  v32 = v132;
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
  lpMem = 0;
  hMem = 0;
  v79 = StripHistoryUrlToUrl(a2);
  if ( *(_WORD *)v79 == 92 || *(_WORD *)v79 && *(_WORD *)(v79 + 2) == 58 )
    goto LABEL_215;
  memset(&ppu, 0, sizeof(ppu));
  ppu.cbSize = 40;
  if ( ParseURLW((LPCWSTR)v79, &ppu) >= 0 )
    v35 = ppu.nScheme;
  if ( v35 == 9 )
  {
LABEL_215:
    if ( v32 )
    {
      v117 = (const unsigned __int16 *)v32[1];
      if ( v117 )
      {
        if ( (int)_CopyPrefix(a2, v117, (unsigned __int16 **)&hMem) >= 0 )
        {
          lpMem = hMem;
          v43 = hMem;
          *(_DWORD *)v119 = 1;
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
  *(_DWORD *)v119 = 0;
LABEL_65:
  v44 = -1;
  do
    ++v44;
  while ( v43[v44] );
  hMem = 0;
  v45 = 2147483646;
  v125 = (unsigned __int16)(2 * (v44 + 1));
  v46 = v42 + v125 + 44;
  if ( v46 < 4 )
  {
    v29 = 0;
LABEL_103:
    v55 = lpszUrlName;
    v56 = *(_DWORD *)v119;
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
  v48 = v125;
  v49 = v47 + 2;
  v47[1] = 25448;
  *v47 = v46 - 2;
  v47[2] = 40;
  v47[3] = v32 != 0;
  if ( v40 )
    v50 = v48 + 40;
  else
    v50 = 0;
  *((_DWORD *)v47 + 7) = v126;
  v47[4] = v50;
  *(FILETIME *)(v47 + 6) = v31;
  *((_QWORD *)v47 + 4) = 0;
  if ( !v32 )
  {
    *(FILETIME *)(v47 + 10) = v31;
LABEL_198:
    hMem = v47;
    v29 = v47;
    goto LABEL_80;
  }
  *(_QWORD *)(v47 + 10) = v32[3];
  if ( !v40 )
    goto LABEL_198;
  v51 = (unsigned __int64)v42 >> 1;
  if ( !v51 )
    goto LABEL_198;
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
  v56 = *(_DWORD *)v119;
  v57 = lpszUrlName;
  v58 = lpMem;
  if ( *(_DWORD *)v119 )
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
    CoTaskMemFree(v132[1]);
  }
  if ( !v29 )
  {
    Error = -2147024882;
    goto LABEL_42;
  }
  v62 = (WCHAR *)v128;
  v63 = v128 - v55;
  v64 = 2085 - v63;
  if ( (unsigned int)(2085 - v63) <= 7 )
  {
LABEL_212:
    Error = -2147024882;
    goto LABEL_41;
  }
  v65 = v64;
  v66 = (unsigned __int16 *)(v128 + 7);
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
  v69 = v123;
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
    v118 = *lpFileTime2[0];
    pcchOut = 1;
    if ( !CommitUrlCacheEntryW(v55, 0, *(FILETIME *)&SystemTime.wYear, v118, 0x200004u, 0, 0, 0, 0) )
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
          v74 = v76 + *((_QWORD *)v123 + 11);
          if ( (unsigned int)(*(_QWORD *)(v74 + 8) / 864000000000LL) - (unsigned int)(*(_QWORD *)v74 / 864000000000LL) == 7 )
          {
            Error = 0;
            goto LABEL_131;
          }
        }
        v73 = v123;
      }
    }
    Error = v74 == 0;
LABEL_131:
    memset_0(Source, 0, 0x206u);
    memset_0(pszDst, 0, 0x23Eu);
    v81 = v123;
    v82 = (__int16 *)*((_QWORD *)v123 + 14);
    v83 = *v82;
    *v82 = 0;
    memset_0(pszDst, 0, 0x23Eu);
    v141 = *(_WORD *)(v74 + 56);
    v84 = *(unsigned __int16 *)(v74 + 58);
    SystemTime = 0;
    *(_OWORD *)lpFileTime2 = 0;
    if ( (_WORD)v84 )
      StringCchPrintfA(v119, 3u, "%02lu", v84);
    else
      v119[0] = 0;
    FileTimeToSystemTime((const FILETIME *)v74, &SystemTime);
    FileTimeToSystemTime((const FILETIME *)(v74 + 8), (LPSYSTEMTIME)lpFileTime2);
    StringCchPrintfA(
      pszSrc,
      0x104u,
      "%s%s%04lu%02lu%02lu%04lu%02lu%02lu",
      "MSHist",
      v119,
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
            goto LABEL_170;
          }
          v111 = ILCombine((LPCITEMIDLIST)v109, ID);
          SHFree(v110);
          if ( v111 )
          {
LABEL_170:
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
        v96 = (const ITEMIDLIST *)*((_QWORD *)v123 + 13);
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
          goto LABEL_153;
        *(_DWORD *)(v101 + 6) = 0;
        *(_DWORD *)v101 = 1667629064;
        *((_WORD *)v101 + 2) = 1;
        if ( ID )
        {
          v103 = ILCombine((LPCITEMIDLIST)v101, ID);
          SHFree(v102);
          if ( !v103 )
          {
LABEL_153:
            if ( v131 )
              *v131 = (struct _ITEMIDLIST_ABSOLUTE *)v95;
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
        goto LABEL_153;
      }
      ILFree(v92);
      goto LABEL_212;
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
  *v130 = v122;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000f640  push    rbp
0x18000f642  push    rbx
0x18000f643  push    rsi
0x18000f644  push    rdi
0x18000f645  push    r12
0x18000f647  push    r13
0x18000f649  lea     rbp, [rsp-0B98h]
0x18000f651  sub     rsp, 0C98h
0x18000f658  mov     rax, cs:__security_cookie
0x18000f65f  xor     rax, rsp
0x18000f662  mov     [rbp+0BC0h+var_40], rax
0x18000f669  mov     rax, [rbp+0BC0h+arg_20]
0x18000f670  xor     edi, edi
0x18000f672  mov     [rbp+0BC0h+lpFileTime2], r9
0x18000f679  mov     r13, r9
0x18000f67c  mov     [rbp+0BC0h+lpszUrlName], rdx
0x18000f680  mov     r12, rdx
0x18000f683  mov     [rsp+0CC0h+var_C48], rcx
0x18000f688  mov     rbx, rcx
0x18000f68b  mov     [rbp+0BC0h+var_BF0], rax
0x18000f68f  mov     qword ptr [rbp+0BC0h+SystemTime.wYear], rdi
0x18000f696  test    rdx, rdx
0x18000f699  jnz     loc_18000F76A
0x18000f69f  mov     rsi, rdi
0x18000f6a2  mov     rcx, [rbx+70h]
0x18000f6a6  xorps   xmm0, xmm0
0x18000f6a9  xor     eax, eax
0x18000f6ab  mov     [rbp+0BC0h+var_C28], rsi
0x18000f6af  mov     [rbp+0BC0h+var_BF8], rcx
0x18000f6b3  movzx   edx, word ptr [rcx]
0x18000f6b6  mov     [rcx], di
0x18000f6b9  mov     [rsp+0CC0h+var_C4C], dx
0x18000f6be  mov     [rbp+0BC0h+var_BB8], rax
0x18000f6c2  movups  xmmword ptr [rbp+0BC0h+var_BE8], xmm0
0x18000f6c6  movups  xmmword ptr [rbp+0BC0h+pv], xmm0
0x18000f6ca  movups  [rbp+0BC0h+var_BC8], xmm0
0x18000f6ce  test    rsi, rsi
0x18000f6d1  jz      loc_18000F8B8
0x18000f6d7  lea     rdi, CLSID_CUrlHistory
0x18000f6de  mov     [rsp+0CC0h+arg_10], r14
0x18000f6e6  lea     r14, [rbx+78h]
0x18000f6ea  mov     [rsp+0CC0h+var_30], r15
0x18000f6f2  lea     rbx, off_180595220
0x18000f6f9  mov     r15d, 80004005h
0x18000f6ff  lea     r11, funcs_18000E8DA
0x18000f706  mov     [rsp+0CC0h+pcchOut], r15d
0x18000f70b  cmp     [r14], rax
0x18000f70e  jnz     loc_18000F7EF
0x18000f714  mov     rcx, rbx
0x18000f717  mov     rax, [rcx+8]
0x18000f71b  test    rax, rax
0x18000f71e  jz      short loc_18000F72F
0x18000f720  cmp     rdi, rax
0x18000f723  jz      loc_1800102FB
0x18000f729  add     rcx, 38h ; '8'
0x18000f72d  jmp     short loc_18000F717
0x18000f72f  mov     eax, 80040111h
0x18000f734  xor     ecx, ecx
0x18000f736  cmp     rcx, 2
0x18000f73a  jnb     loc_18000F7C5
0x18000f740  mov     r10, rcx
0x18000f743  add     r10, r10
0x18000f746  mov     r8, [r11+r10*8+8]
0x18000f74b  mov     rdx, [r8]
0x18000f74e  test    rdx, rdx
0x18000f751  jz      short loc_18000F765
0x18000f753  cmp     rdx, rdi
0x18000f756  jz      short loc_18000F7A7
0x18000f758  mov     rdx, [r8+8]
0x18000f75c  add     r8, 8
0x18000f760  test    rdx, rdx
0x18000f763  jnz     short loc_18000F753
0x18000f765  inc     rcx
0x18000f768  jmp     short loc_18000F736
0x18000f76a  mov     edx, 40h ; '@'; wMatch
0x18000f76f  mov     rcx, r12; pszStart
0x18000f772  call    cs:__imp_StrChrW
0x18000f779  nop     dword ptr [rax+rax+00h]
0x18000f77e  test    rax, rax
0x18000f781  jz      loc_1800104EC
0x18000f787  cmp     [rax], di
0x18000f78a  jz      loc_1800104EC
0x18000f790  mov     rcx, rax; lpsz
0x18000f793  call    cs:__imp_CharNextW
0x18000f79a  nop     dword ptr [rax+rax+00h]
0x18000f79f  mov     rsi, rax
0x18000f7a2  jmp     loc_18000F6A2
0x18000f7a7  cmp     qword ptr [r8], 0
0x18000f7ab  jz      short loc_18000F765
0x18000f7ad  mov     rax, ds:(funcs_18000E8DA - 180596950h)[r11+r10*8]
0x18000f7b1  lea     r8, IID_IUrlHistoryPriv
0x18000f7b8  mov     r9, r14
0x18000f7bb  xor     edx, edx
0x18000f7bd  mov     rcx, rdi
0x18000f7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7c5  cmp     eax, 80040111h
0x18000f7ca  jnz     short loc_18000F7EF
0x18000f7cc  lea     r9, IID_IUrlHistoryPriv; riid
0x18000f7d3  mov     [rsp+0CC0h+ppv], r14; ppv
0x18000f7d8  xor     edx, edx; pUnkOuter
0x18000f7da  mov     r8d, 1; dwClsContext
0x18000f7e0  mov     rcx, rdi; rclsid
0x18000f7e3  call    cs:__imp_CoCreateInstance
0x18000f7ea  nop     dword ptr [rax+rax+00h]
0x18000f7ef  mov     rcx, [r14]
0x18000f7f2  test    rcx, rcx
0x18000f7f5  jz      short loc_18000F803
0x18000f7f7  mov     rax, [rcx]
0x18000f7fa  mov     rax, [rax+8]
0x18000f7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f803  mov     rdi, [r14]
0x18000f806  test    rdi, rdi
0x18000f809  jz      short loc_18000F83E
0x18000f80b  mov     r8d, 824h; cchBuf
0x18000f811  lea     rdx, [rbp+0BC0h+pszDst]; pszDst
0x18000f818  mov     rcx, rsi; pwszSrc
0x18000f81b  call    cs:__imp_SHUnicodeToAnsi
0x18000f822  nop     dword ptr [rax+rax+00h]
0x18000f827  test    eax, eax
0x18000f829  jnz     loc_180010491
0x18000f82f  mov     rdx, [rdi]
0x18000f832  mov     rcx, rdi
0x18000f835  mov     rax, [rdx+10h]
0x18000f839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f83e  xor     edi, edi
0x18000f840  mov     [rbp+0BC0h+var_C34], edi
0x18000f843  cmp     [r14], rdi
0x18000f846  jnz     loc_18000F958
0x18000f84c  lea     rcx, CLSID_CUrlHistory
0x18000f853  mov     rax, [rbx+8]
0x18000f857  test    rax, rax
0x18000f85a  jz      short loc_18000F86B
0x18000f85c  cmp     rcx, rax
0x18000f85f  jz      loc_1800102D0
0x18000f865  add     rbx, 38h ; '8'
0x18000f869  jmp     short loc_18000F853
0x18000f86b  mov     eax, 80040111h
0x18000f870  lea     r11, funcs_18000E8DA
0x18000f877  xor     ecx, ecx
0x18000f879  cmp     rcx, 2
0x18000f87d  jnb     loc_18000F927
0x18000f883  mov     r10, rcx
0x18000f886  add     r10, r10
0x18000f889  mov     r8, [r11+r10*8+8]
0x18000f88e  mov     rdx, [r8]
0x18000f891  test    rdx, rdx
0x18000f894  jz      short loc_18000F8B3
0x18000f896  lea     rbx, CLSID_CUrlHistory
0x18000f89d  cmp     rdx, rbx
0x18000f8a0  jz      loc_1800104BA
0x18000f8a6  mov     rdx, [r8+8]
0x18000f8aa  add     r8, 8
0x18000f8ae  test    rdx, rdx
0x18000f8b1  jnz     short loc_18000F89D
0x18000f8b3  inc     rcx
0x18000f8b6  jmp     short loc_18000F879
0x18000f8b8  mov     [rcx], dx
0x18000f8bb  mov     eax, 8000FFFFh
0x18000f8c0  jmp     short loc_18000F907
0x18000f8c2  mov     [rax], r14
0x18000f8c5  mov     rcx, rdi; pidl
0x18000f8c8  call    cs:__imp_ILFree
0x18000f8cf  nop     dword ptr [rax+rax+00h]
0x18000f8d4  mov     r12, [rsp+0CC0h+hMem]
0x18000f8d9  mov     rcx, r12; hMem
0x18000f8dc  call    cs:__imp_LocalFree
0x18000f8e3  nop     dword ptr [rax+rax+00h]
0x18000f8e8  mov     rax, [rbp+0BC0h+var_BF8]
0x18000f8ec  movzx   ecx, [rsp+0CC0h+var_C4C]
0x18000f8f1  mov     r14, [rsp+0CC0h+arg_10]
0x18000f8f9  mov     r15, [rsp+0CC0h+var_30]
0x18000f901  mov     [rax], cx
0x18000f904  mov     eax, r13d
0x18000f907  mov     rcx, [rbp+0BC0h+var_40]
0x18000f90e  xor     rcx, rsp; StackCookie
0x18000f911  call    __security_check_cookie
0x18000f916  add     rsp, 0C98h
0x18000f91d  pop     r13
0x18000f91f  pop     r12
0x18000f921  pop     rdi
0x18000f922  pop     rsi
0x18000f923  pop     rbx
0x18000f924  pop     rbp
0x18000f925  retn
0x18000f927  lea     rbx, CLSID_CUrlHistory
0x18000f92e  cmp     eax, 80040111h
0x18000f933  jnz     short loc_18000F958
0x18000f935  lea     r9, IID_IUrlHistoryPriv; riid
0x18000f93c  mov     [rsp+0CC0h+ppv], r14; ppv
0x18000f941  xor     edx, edx; pUnkOuter
0x18000f943  mov     r8d, 1; dwClsContext
0x18000f949  mov     rcx, rbx; rclsid
0x18000f94c  call    cs:__imp_CoCreateInstance
0x18000f953  nop     dword ptr [rax+rax+00h]
0x18000f958  mov     rcx, [r14]
0x18000f95b  test    rcx, rcx
0x18000f95e  jz      short loc_18000F96C
0x18000f960  mov     rax, [rcx]
0x18000f963  mov     rax, [rax+8]
0x18000f967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f96c  mov     rbx, [r14]
0x18000f96f  test    rbx, rbx
0x18000f972  jnz     loc_180010206
0x18000f978  mov     r13, [r13+0]
0x18000f97c  lea     r14, [rbp+0BC0h+var_BE8]
0x18000f980  xor     eax, eax
0x18000f982  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000f989  test    r15d, r15d
0x18000f98c  cmovs   r14, rax
0x18000f990  test    r14, r14
0x18000f993  jz      loc_18000FD86
0x18000f999  mov     rbx, [r14+10h]
0x18000f99d  test    rbx, rbx
0x18000f9a0  jz      loc_18000FD86
0x18000f9a6  xorps   xmm0, xmm0
0x18000f9a9  mov     qword ptr [rbp+0BC0h+ppu.cchSuffix], rax
0x18000f9ad  movups  xmmword ptr [rbp+0BC0h+ppu.cbSize], xmm0
0x18000f9b1  mov     r15d, 28h ; '('
0x18000f9b7  lea     rdx, [rbp+0BC0h+ppu]; ppu
0x18000f9bb  mov     rcx, rbx; pcszURL
0x18000f9be  mov     [rbp+0BC0h+ppu.cbSize], r15d
0x18000f9c2  movups  xmmword ptr [rbp+0BC0h+ppu.cchProtocol], xmm0
0x18000f9c6  call    cs:__imp_ParseURLW
0x18000f9cd  nop     dword ptr [rax+rax+00h]
0x18000f9d2  test    eax, eax
0x18000f9d4  mov     edi, 0FFFFFFFFh
0x18000f9d9  movzx   eax, word ptr [rbx]
0x18000f9dc  mov     esi, edi
0x18000f9de  cmovns  esi, [rbp+0BC0h+ppu.nScheme]
0x18000f9e2  cmp     ax, 5Ch ; '\'
0x18000f9e6  jz      loc_1800104E0
0x18000f9ec  test    ax, ax
0x18000f9ef  jz      short loc_18000F9FC
0x18000f9f1  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18000f9f6  jz      loc_1800104E0
0x18000f9fc  xorps   xmm0, xmm0
0x18000f9ff  lea     rdx, [rbp+0BC0h+ppu]; ppu
0x18000fa03  xor     eax, eax
0x18000fa05  mov     rcx, rbx; pcszURL
0x18000fa08  movups  xmmword ptr [rbp+0BC0h+ppu.cbSize], xmm0
0x18000fa0c  mov     [rbp+0BC0h+ppu.cbSize], r15d
0x18000fa10  movups  xmmword ptr [rbp+0BC0h+ppu.cchProtocol], xmm0
0x18000fa14  mov     qword ptr [rbp+0BC0h+ppu.cchSuffix], rax
0x18000fa18  call    cs:__imp_ParseURLW
0x18000fa1f  nop     dword ptr [rax+rax+00h]
0x18000fa24  test    eax, eax
0x18000fa26  mov     ecx, edi
0x18000fa28  cmovns  ecx, [rbp+0BC0h+ppu.nScheme]
0x18000fa2c  cmp     ecx, 9
0x18000fa2f  jz      loc_1800104E0
0x18000fa35  lea     eax, [rsi+1]
0x18000fa38  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000fa3f  test    eax, 0FFFFFFFEh
0x18000fa44  jnz     loc_18000FD91
0x18000fa4a  mov     rax, [r14+10h]
0x18000fa4e  mov     r12d, 1
0x18000fa54  mov     rbx, rsi
0x18000fa57  nop     word ptr [rax+rax+00000000h]
0x18000fa60  inc     rbx
0x18000fa63  cmp     word ptr [rax+rbx*2], 0
0x18000fa68  jnz     short loc_18000FA60
0x18000fa6a  inc     bx
0x18000fa6d  add     bx, bx
0x18000fa70  xor     edx, edx
0x18000fa72  mov     [rbp+0BC0h+lpMem], rdx
0x18000fa76  mov     rcx, [rbp+0BC0h+lpszUrlName]
0x18000fa7a  mov     dword ptr [rsp+0CC0h+var_C60], edx
0x18000fa7e  mov     rax, rsi
0x18000fa81  inc     rax
0x18000fa84  cmp     word ptr [rcx+rax*2], 0
0x18000fa89  jnz     short loc_18000FA81
0x18000fa8b  inc     ax
0x18000fa8e  mov     [rsp+0CC0h+hMem], rdx
0x18000fa93  add     ax, ax
0x18000fa96  mov     edi, 7FFFFFFEh
0x18000fa9b  movzx   ecx, ax
0x18000fa9e  movzx   eax, bx
0x18000faa1  mov     [rbp+0BC0h+var_C38], ecx
0x18000faa4  lea     esi, [rcx+2Ch]
0x18000faa7  add     esi, eax
0x18000faa9  cmp     esi, 4
0x18000faac  jb      loc_18000FC78
0x18000fab2  mov     edx, esi; uBytes
0x18000fab4  mov     ecx, 40h ; '@'; uFlags
0x18000fab9  call    cs:__imp_LocalAlloc
0x18000fac0  nop     dword ptr [rax+rax+00h]
0x18000fac5  mov     [rsp+0CC0h+hMem], rax
0x18000faca  mov     rcx, rax
0x18000facd  test    rax, rax
0x18000fad0  jz      loc_180010596
0x18000fad6  mov     r10d, [rbp+0BC0h+var_C38]
0x18000fada  lea     r11, [rax+4]
0x18000fade  mov     word ptr [rax+2], 6368h
0x18000fae4  sub     si, 2
0x18000fae8  mov     [rax], si
0x18000faeb  xor     eax, eax
0x18000faed  test    r14, r14
0x18000faf0  mov     [r11], r15w
0x18000faf4  setnz   al
0x18000faf7  mov     [rcx+6], ax
  ... truncated ...
```
