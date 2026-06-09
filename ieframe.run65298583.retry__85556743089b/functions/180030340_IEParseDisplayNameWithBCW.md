# IEParseDisplayNameWithBCW

- ea: `0x180030340`
- end: `0x18003084e`
- name: `IEParseDisplayNameWithBCW`
- size: `1294`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `23`
- callee_count: `20`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006d850`
- `0x1800b58f0`
- `0x1801129dc`
- `0x180140814`
- `0x1801762f4`
- `0x18017638c`
- `0x180184d0c`
- `0x180185198`
- `0x180185884`
- `0x18018bdd0`
- `0x18019c060`
- `0x18019eb34`
- `0x1801a1b50`
- `0x1801a29a4`
- `0x180244bbc`
- `0x18024a4a4`
- `0x1802556d0`
- `0x18026301c`
- `0x1802720a8`
- `0x180285bcc`
- `0x18028ad14`
- `0x180305c9c`
- `0x1803f7410`

## callees

- `0x180012310`
- `0x180019450`
- `0x18002acc0`
- `0x180030340`
- `0x180031308`
- `0x180031390`
- `0x1800313f8`
- `0x180031448`
- `0x180058dbc`
- `0x18006950c`
- `0x18006c110`
- `0x1800b83c8`
- `0x1800b9e28`
- `0x180112814`
- `0x1804de9ac`
- `0x1804e6624`
- `0x1804e66bc`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180030813`
- `KERNEL32!LocalFree` at `0x18003081c`
- `KERNEL32!LocalFree` at `0x180030813`
- `KERNEL32!LocalFree` at `0x18003081c`
- `KERNEL32!GetProcessHeap` at `0x18003049e`
- `KERNEL32!GetProcessHeap` at `0x18003049e`
- `KERNEL32!HeapAlloc` at `0x1800304b0`
- `KERNEL32!HeapAlloc` at `0x1800304b0`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800303bf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800303bf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x180030421`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x180030421`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180030667`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180030679`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180030667`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180030679`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180030618`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180030769`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180030618`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180030769`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x1800303db`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x1800303db`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlAlloc` at `0x180030444`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlAlloc` at `0x180030444`
- `SHELL32!SHParseDisplayName` at `0x180030716`
- `SHELL32!SHParseDisplayName` at `0x180030716`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18003059a`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x18003059a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003072a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180030739`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003072a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180030739`

## pseudocode

```c
__int64 __fastcall IEParseDisplayNameWithBCW(DWORD a1, const WCHAR *a2, IBindCtx *a3, struct _ITEMIDLIST_ABSOLUTE **a4)
{
  WCHAR *v6; // rdi
  DWORD v7; // ebx
  LPBC v8; // r12
  LPCWSTR LocationW; // r13
  void *v10; // rcx
  int v11; // eax
  HRESULT v12; // ebx
  WCHAR v13; // ax
  HANDLE ProcessHeap; // rax
  CDwnCodePage *v15; // rax
  CDwnCodePage *v16; // r14
  __int64 v17; // rsi
  LPBC v18; // rbx
  CDummyOleWindow *v19; // rax
  CDummyOleWindow *v20; // rax
  CDummyOleWindow *v21; // r8
  int IsFeatureEnabledInternal; // eax
  int IsFilePath; // r14d
  struct IBindCtx *v24; // rcx
  HRESULT v25; // eax
  WCHAR *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  DWORD pcchOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchPath; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszOut; // [rsp+48h] [rbp-B8h] BYREF
  PARSEDURLW ppu; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszStart[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPath[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR v38[2088]; // [rsp+4A0h] [rbp+3A0h] BYREF

  pcchPath = a1;
  ppszOut = 0;
  ppbc = 0;
  v6 = (WCHAR *)a2;
  v7 = a1;
  v8 = 0;
  if ( a2 && (memset(&ppu, 0, sizeof(ppu)), ppu.cbSize = 40, ParseURLW(a2, &ppu) >= 0) && ppu.nScheme == 9 )
  {
    LocationW = UrlGetLocationW(v6);
    v11 = CTLocalAllocPolicy::Alloc(v10, 0x40u, 0x1048u, (void **)&ppbc);
    v8 = ppbc;
    v12 = v11;
    if ( v11 >= 0 )
    {
      pcchOut[0] = 2083;
      if ( UrlGetPartW(v6, (PWSTR)&ppbc->lpVtbl + 1, pcchOut, 6u, 0) >= 0 )
      {
        if ( pcchOut[0] )
          LOWORD(v8->lpVtbl) = 63;
      }
    }
    if ( PathCreateFromUrlAlloc(v6, &ppszOut, 0) >= 0 )
    {
      v6 = ppszOut;
      if ( ppszOut )
      {
        v13 = *ppszOut;
        if ( *ppszOut )
        {
          do
          {
            if ( v13 == 47 )
              *v6 = 92;
            v13 = *++v6;
          }
          while ( *v6 );
          v6 = ppszOut;
        }
      }
      if ( !(unsigned int)PathIsAbsolute(v6) )
        v12 = -2147467259;
    }
    if ( v12 < 0 )
      goto LABEL_83;
    v7 = pcchPath;
  }
  else
  {
    LocationW = 0;
  }
  ProcessHeap = GetProcessHeap();
  v15 = (CDwnCodePage *)HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v15 )
    std::_Xbad_alloc();
  v16 = CDwnCodePage::CDwnCodePage(v15, v7);
  ppbc = a3;
  *a4 = 0;
  if ( a3 )
  {
    ((void (__fastcall *)(IBindCtx *))a3->lpVtbl->AddRef)(a3);
    v17 = 0;
  }
  else
  {
    v17 = 0;
    v12 = CreateBindCtx_0(0, &ppbc);
    if ( v12 < 0 )
      goto LABEL_36;
  }
  v18 = ppbc;
  if ( !v16 )
  {
    v19 = (CDummyOleWindow *)operator new(0x18u);
    if ( v19 )
    {
      v20 = CDummyOleWindow::CDummyOleWindow(v19);
      v17 = (__int64)v20;
      if ( v20 )
      {
        v21 = v20;
        goto LABEL_32;
      }
      LODWORD(v17) = 0;
    }
    v12 = -2147024882;
LABEL_35:
    IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&ppbc);
    goto LABEL_36;
  }
  v21 = v16;
LABEL_32:
  v12 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, CDummyOleWindow *))v18->lpVtbl->RegisterObjectParam)(
          v18,
          L"CDwnCodePage",
          v21);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  LODWORD(v17) = 0;
  if ( v12 < 0 )
    goto LABEL_35;
LABEL_36:
  if ( v16 )
    CDwnCodePage::Release(v16);
  if ( v12 < 0 )
    goto LABEL_74;
  if ( !FCK::FEATURE_INTERNET_SHELL_FOLDERS )
  {
LABEL_42:
    if ( dword_18065B780 )
      goto LABEL_44;
    goto LABEL_43;
  }
  IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
  if ( IsFeatureEnabledInternal >= 0 )
  {
    dword_18065B780 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_INTERNET_SHELL_FOLDERS = 0;
    goto LABEL_42;
  }
LABEL_43:
  BindCtx_AddObjectParam(ppbc, L"Do not bind to Internet shell folder handlers", 0);
LABEL_44:
  if ( v6 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v6[v17] );
  }
  if ( !(_DWORD)v17 )
  {
    v12 = -2147467259;
    goto LABEL_74;
  }
  if ( (unsigned int)IsFileUrlW(v6) )
  {
    pcchOut[0] = 260;
    v12 = PathCreateFromUrlW(v6, pszPath, pcchOut, 0);
    if ( v12 >= 0 )
    {
      LODWORD(v17) = pcchOut[0];
      v6 = pszPath;
    }
  }
  IsFilePath = PathIsFilePath(v6);
  if ( IsFilePath )
  {
    if ( (unsigned int)v17 >= 0x104 || PathCchCanonicalizeEx(pszStart, 0x104u, v6, PATHCCH_NONE) < 0 )
    {
      v12 = -2147024893;
      goto LABEL_74;
    }
    v6 = pszStart;
    if ( StrChrW(pszStart, 0x2Au) || StrChrW(pszStart, 0x3Fu) )
      v12 = -2147467259;
  }
  if ( v12 >= 0 )
  {
    if ( !IsFilePath )
    {
      v24 = ppbc;
      *(_QWORD *)pcchOut = 0;
      if ( ppbc )
      {
        if ( ((int (__fastcall *)(LPBC, const wchar_t *, DWORD *))ppbc->lpVtbl->GetObjectParam)(
               ppbc,
               L"Parse Prefer Folder Browsing",
               pcchOut) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcchOut + 16LL))(*(_QWORD *)pcchOut);
          goto LABEL_65;
        }
        v24 = ppbc;
      }
      if ( _IEParseDisplayNameDirect(v6, pcchPath, v24, a4) )
        goto LABEL_74;
    }
LABEL_65:
    v12 = SHParseDisplayName(v6, ppbc, (LPITEMIDLIST *)a4, 0, 0);
    if ( v12 == -2147024891
      && (unsigned __int8)IEConfiguration_GetBool(268435482)
      && (unsigned __int8)IEConfiguration_GetBool(536870915) )
    {
      pcchPath = 2085;
      if ( !(unsigned int)IsFileUrlW(v6) || (v25 = PathCreateFromUrlW(v6, v38, &pcchPath, 0), v26 = v38, v25 < 0) )
        v26 = v6;
      *(_QWORD *)pcchOut = 0;
      SHSimpleIDListFromFindData(v26);
      v27 = *(_QWORD *)pcchOut;
      *a4 = *(struct _ITEMIDLIST_ABSOLUTE **)pcchOut;
      if ( v27 )
        v12 = 0;
    }
  }
LABEL_74:
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( v12 >= 0 )
  {
    if ( LocationW )
    {
      v28 = ILAppendHiddenStringW((LPITEMIDLIST)*a4);
      *a4 = (struct _ITEMIDLIST_ABSOLUTE *)v28;
      if ( !v28 )
      {
        v12 = -2147024882;
        goto LABEL_83;
      }
      v12 = 0;
    }
    if ( v8 && LOWORD(v8->lpVtbl) == 63 )
    {
      v29 = ILAppendHiddenStringW((LPITEMIDLIST)*a4);
      *a4 = (struct _ITEMIDLIST_ABSOLUTE *)v29;
      v12 = v29 == 0 ? 0x8007000E : 0;
    }
  }
LABEL_83:
  LocalFree(ppszOut);
  LocalFree(v8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180030340  push    rbp
0x180030342  push    rbx
0x180030343  push    rsi
0x180030344  push    rdi
0x180030345  push    r12
0x180030347  push    r13
0x180030349  push    r14
0x18003034b  push    r15
0x18003034d  lea     rbp, [rsp-1408h]
0x180030355  mov     eax, 1508h
0x18003035a  call    _alloca_probe
0x18003035f  sub     rsp, rax
0x180030362  mov     rax, cs:__security_cookie
0x180030369  xor     rax, rsp
0x18003036c  mov     [rbp+1440h+var_50], rax
0x180030373  xor     r14d, r14d
0x180030376  mov     [rsp+1540h+pcchPath], ecx
0x18003037a  mov     [rsp+1540h+ppszOut], r14
0x18003037f  mov     r15, r9
0x180030382  mov     [rsp+1540h+ppbc], r14
0x180030387  mov     rsi, r8
0x18003038a  mov     rdi, rdx
0x18003038d  mov     ebx, ecx
0x18003038f  mov     r12d, r14d
0x180030392  test    rdx, rdx
0x180030395  jz      loc_18003049B
0x18003039b  xorps   xmm0, xmm0
0x18003039e  lea     rdx, [rsp+1540h+ppu]; ppu
0x1800303a3  xor     eax, eax
0x1800303a5  mov     rcx, rdi; pcszURL
0x1800303a8  movups  xmmword ptr [rsp+1540h+ppu.cbSize], xmm0
0x1800303ad  mov     [rsp+1540h+ppu.cbSize], 28h ; '('
0x1800303b5  movups  xmmword ptr [rsp+1540h+ppu.cchProtocol], xmm0
0x1800303ba  mov     qword ptr [rsp+1540h+ppu.cchSuffix], rax
0x1800303bf  call    cs:__imp_ParseURLW
0x1800303c5  test    eax, eax
0x1800303c7  js      loc_18003049B
0x1800303cd  cmp     [rsp+1540h+ppu.nScheme], 9
0x1800303d2  jnz     loc_18003049B
0x1800303d8  mov     rcx, rdi; pszURL
0x1800303db  call    cs:__imp_UrlGetLocationW
0x1800303e1  lea     r9, [rsp+1540h+ppbc]; void **
0x1800303e6  mov     r8d, 1048h; unsigned __int64
0x1800303ec  lea     edx, [r14+40h]; unsigned int
0x1800303f0  mov     r13, rax
0x1800303f3  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800303f8  mov     r12, [rsp+1540h+ppbc]
0x1800303fd  mov     ebx, eax
0x1800303ff  test    eax, eax
0x180030401  js      short loc_180030439
0x180030403  lea     rdx, [r12+2]; pszOut
0x180030408  mov     [rsp+1540h+pcchOut], 823h
0x180030410  lea     r9d, [r14+6]; dwPart
0x180030414  mov     [rsp+1540h+dwFlags], r14d; dwFlags
0x180030419  lea     r8, [rsp+1540h+pcchOut]; pcchOut
0x18003041e  mov     rcx, rdi; pszIn
0x180030421  call    cs:__imp_UrlGetPartW
0x180030427  test    eax, eax
0x180030429  js      short loc_180030439
0x18003042b  cmp     [rsp+1540h+pcchOut], r14d
0x180030430  jz      short loc_180030439
0x180030432  mov     word ptr [r12], 3Fh ; '?'
0x180030439  xor     r8d, r8d; dwFlags
0x18003043c  lea     rdx, [rsp+1540h+ppszOut]; ppszOut
0x180030441  mov     rcx, rdi; pszIn
0x180030444  call    cs:__imp_PathCreateFromUrlAlloc
0x18003044a  test    eax, eax
0x18003044c  js      short loc_18003048D
0x18003044e  mov     rdi, [rsp+1540h+ppszOut]
0x180030453  test    rdi, rdi
0x180030456  jz      short loc_18003047C
0x180030458  movzx   eax, word ptr [rdi]
0x18003045b  test    ax, ax
0x18003045e  jz      short loc_18003047C
0x180030460  cmp     ax, 2Fh ; '/'
0x180030464  jnz     short loc_18003046B
0x180030466  mov     word ptr [rdi], 5Ch ; '\'
0x18003046b  add     rdi, 2
0x18003046f  movzx   eax, word ptr [rdi]
0x180030472  test    ax, ax
0x180030475  jnz     short loc_180030460
0x180030477  mov     rdi, [rsp+1540h+ppszOut]
0x18003047c  mov     rcx, rdi; pszPath
0x18003047f  call    PathIsAbsolute
0x180030484  test    eax, eax
0x180030486  jnz     short loc_18003048D
0x180030488  mov     ebx, 80004005h
0x18003048d  test    ebx, ebx
0x18003048f  js      loc_18003080E
0x180030495  mov     ebx, [rsp+1540h+pcchPath]
0x180030499  jmp     short loc_18003049E
0x18003049b  mov     r13, r14
0x18003049e  call    cs:__imp_GetProcessHeap
0x1800304a4  mov     edx, 8; dwFlags
0x1800304a9  mov     rcx, rax; hHeap
0x1800304ac  lea     r8d, [rdx+8]; dwBytes
0x1800304b0  call    cs:__imp_HeapAlloc
0x1800304b6  test    rax, rax
0x1800304b9  jnz     short loc_1800304C1
0x1800304bb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800304c1  mov     edx, ebx; unsigned int
0x1800304c3  mov     rcx, rax; this
0x1800304c6  call    ??0CDwnCodePage@@QEAA@I@Z; CDwnCodePage::CDwnCodePage(uint)
0x1800304cb  mov     r14, rax
0x1800304ce  mov     [rsp+1540h+ppbc], rsi
0x1800304d3  xor     eax, eax
0x1800304d5  mov     [r15], rax
0x1800304d8  test    rsi, rsi
0x1800304db  jz      short loc_1800304F0
0x1800304dd  mov     rdx, [rsi]
0x1800304e0  mov     rcx, rsi
0x1800304e3  mov     rax, [rdx+8]
0x1800304e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304ec  xor     esi, esi
0x1800304ee  jmp     short loc_180030504
0x1800304f0  lea     rdx, [rsp+1540h+ppbc]; ppbc
0x1800304f5  xor     ecx, ecx; reserved
0x1800304f7  call    CreateBindCtx_0
0x1800304fc  xor     esi, esi
0x1800304fe  mov     ebx, eax
0x180030500  test    eax, eax
0x180030502  js      short loc_180030579
0x180030504  mov     rbx, [rsp+1540h+ppbc]
0x180030509  test    r14, r14
0x18003050c  jnz     short loc_18003053A
0x18003050e  lea     ecx, [r14+18h]; dwBytes
0x180030512  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030517  test    rax, rax
0x18003051a  jz      short loc_180030533
0x18003051c  mov     rcx, rax; this
0x18003051f  call    ??0CDummyOleWindow@@QEAA@XZ; CDummyOleWindow::CDummyOleWindow(void)
0x180030524  mov     rsi, rax
0x180030527  test    rax, rax
0x18003052a  jz      short loc_180030531
0x18003052c  mov     r8, rax
0x18003052f  jmp     short loc_18003053D
0x180030531  xor     esi, esi
0x180030533  mov     ebx, 8007000Eh
0x180030538  jmp     short loc_18003056F
0x18003053a  mov     r8, r14
0x18003053d  mov     rax, [rbx]
0x180030540  lea     rdx, aCdwncodepage; "CDwnCodePage"
0x180030547  mov     rcx, rbx
0x18003054a  mov     rax, [rax+48h]
0x18003054e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030553  mov     ebx, eax
0x180030555  test    rsi, rsi
0x180030558  jz      short loc_180030569
0x18003055a  mov     rax, [rsi]
0x18003055d  mov     rcx, rsi
0x180030560  mov     rax, [rax+10h]
0x180030564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030569  xor     esi, esi
0x18003056b  test    ebx, ebx
0x18003056d  jns     short loc_180030579
0x18003056f  lea     rcx, [rsp+1540h+ppbc]
0x180030574  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x180030579  test    r14, r14
0x18003057c  jz      short loc_180030586
0x18003057e  mov     rcx, r14; this
0x180030581  call    ?Release@CDwnCodePage@@UEAAKXZ; CDwnCodePage::Release(void)
0x180030586  test    ebx, ebx
0x180030588  js      loc_1800307A4
0x18003058e  mov     rcx, cs:?FEATURE_INTERNET_SHELL_FOLDERS@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_INTERNET_SHELL_FOLDERS
0x180030595  test    rcx, rcx
0x180030598  jz      short loc_1800305B6
0x18003059a  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x1800305a0  test    eax, eax
0x1800305a2  js      short loc_1800305C0
0x1800305a4  mov     ecx, esi
0x1800305a6  setz    cl
0x1800305a9  mov     cs:dword_18065B780, ecx
0x1800305af  mov     cs:?FEATURE_INTERNET_SHELL_FOLDERS@FCK@@3VCFeatureControlKey@@A, rsi; CFeatureControlKey FCK::FEATURE_INTERNET_SHELL_FOLDERS
0x1800305b6  mov     eax, cs:dword_18065B780
0x1800305bc  test    eax, eax
0x1800305be  jnz     short loc_1800305D4
0x1800305c0  mov     rcx, [rsp+1540h+ppbc]
0x1800305c5  lea     rdx, aDoNotBindToInt; "Do not bind to Internet shell folder ha"...
0x1800305cc  xor     r8d, r8d
0x1800305cf  call    BindCtx_AddObjectParam
0x1800305d4  test    rdi, rdi
0x1800305d7  jz      short loc_1800305EA
0x1800305d9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800305dd  xor     r14d, r14d
0x1800305e0  inc     rsi
0x1800305e3  cmp     [rdi+rsi*2], r14w
0x1800305e8  jnz     short loc_1800305E0
0x1800305ea  test    esi, esi
0x1800305ec  jz      loc_18003079D
0x1800305f2  mov     rcx, rdi
0x1800305f5  call    IsFileUrlW
0x1800305fa  test    eax, eax
0x1800305fc  jz      short loc_18003062F
0x1800305fe  xor     r9d, r9d; dwFlags
0x180030601  mov     [rsp+1540h+pcchOut], 104h
0x180030609  lea     r8, [rsp+1540h+pcchOut]; pcchPath
0x18003060e  mov     rcx, rdi; pszUrl
0x180030611  lea     rdx, [rbp+1440h+pszPath]; pszPath
0x180030618  call    cs:__imp_PathCreateFromUrlW
0x18003061e  mov     ebx, eax
0x180030620  test    eax, eax
0x180030622  js      short loc_18003062F
0x180030624  mov     esi, [rsp+1540h+pcchOut]
0x180030628  lea     rdi, [rbp+1440h+pszPath]
0x18003062f  mov     rcx, rdi
0x180030632  call    PathIsFilePath
0x180030637  mov     r14d, eax
0x18003063a  test    eax, eax
0x18003063c  jz      short loc_180030697
0x18003063e  mov     edx, 104h; unsigned __int64
0x180030643  cmp     esi, edx
0x180030645  jnb     short loc_18003068B
0x180030647  xor     r9d, r9d; enum PATHCCH_OPTIONS
0x18003064a  lea     rcx, [rbp+1440h+pszStart]; unsigned __int16 *
0x18003064e  mov     r8, rdi; unsigned __int16 *
0x180030651  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x180030656  xor     esi, esi
0x180030658  test    eax, eax
0x18003065a  js      short loc_18003068D
0x18003065c  lea     edx, [rsi+2Ah]; wMatch
0x18003065f  lea     rcx, [rbp+1440h+pszStart]; pszStart
0x180030663  lea     rdi, [rbp+1440h+pszStart]
0x180030667  call    cs:__imp_StrChrW
0x18003066d  test    rax, rax
0x180030670  jnz     short loc_180030684
0x180030672  lea     edx, [rsi+3Fh]; wMatch
0x180030675  lea     rcx, [rbp+1440h+pszStart]; pszStart
0x180030679  call    cs:__imp_StrChrW
0x18003067f  test    rax, rax
0x180030682  jz      short loc_180030699
0x180030684  mov     ebx, 80004005h
0x180030689  jmp     short loc_180030699
0x18003068b  xor     esi, esi
0x18003068d  mov     ebx, 80070003h
0x180030692  jmp     loc_1800307A4
0x180030697  xor     esi, esi
0x180030699  test    ebx, ebx
0x18003069b  js      loc_1800307A4
0x1800306a1  test    r14d, r14d
0x1800306a4  jnz     short loc_180030703
0x1800306a6  mov     rcx, [rsp+1540h+ppbc]
0x1800306ab  mov     qword ptr [rsp+1540h+pcchOut], rsi
0x1800306b0  test    rcx, rcx
0x1800306b3  jz      short loc_1800306E9
0x1800306b5  mov     rax, [rcx]
0x1800306b8  lea     r8, [rsp+1540h+pcchOut]
0x1800306bd  lea     rdx, aParsePreferFol; "Parse Prefer Folder Browsing"
0x1800306c4  mov     rax, [rax+50h]
0x1800306c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306cd  test    eax, eax
0x1800306cf  js      short loc_1800306E4
0x1800306d1  mov     rcx, qword ptr [rsp+1540h+pcchOut]
0x1800306d6  mov     rax, [rcx]
0x1800306d9  mov     rax, [rax+10h]
0x1800306dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306e2  jmp     short loc_180030703
0x1800306e4  mov     rcx, [rsp+1540h+ppbc]
0x1800306e9  mov     edx, [rsp+1540h+pcchPath]; unsigned int
0x1800306ed  mov     r8, rcx; struct IBindCtx *
0x1800306f0  mov     rcx, rdi; unsigned __int16 *
0x1800306f3  mov     r9, r15; struct _ITEMIDLIST_ABSOLUTE **
0x1800306f6  call    ?_IEParseDisplayNameDirect@@YA_NPEBGIPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _IEParseDisplayNameDirect(ushort const *,uint,IBindCtx *,_ITEMIDLIST_ABSOLUTE * *)
0x1800306fb  test    al, al
0x1800306fd  jnz     loc_1800307A4
0x180030703  mov     rdx, [rsp+1540h+ppbc]; pbc
0x180030708  xor     r9d, r9d; sfgaoIn
0x18003070b  mov     r8, r15; ppidl
0x18003070e  mov     qword ptr [rsp+1540h+dwFlags], rsi; psfgaoOut
0x180030713  mov     rcx, rdi; pszName
0x180030716  call    cs:__imp_SHParseDisplayName
0x18003071c  mov     ebx, eax
0x18003071e  cmp     eax, 80070005h
0x180030723  jnz     short loc_1800307A4
0x180030725  mov     ecx, 1000001Ah
0x18003072a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180030730  test    al, al
0x180030732  jz      short loc_1800307A4
0x180030734  mov     ecx, 20000003h
0x180030739  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18003073f  test    al, al
0x180030741  jz      short loc_1800307A4
0x180030743  mov     rcx, rdi
0x180030746  mov     [rsp+1540h+pcchPath], 825h
0x18003074e  call    IsFileUrlW
0x180030753  test    eax, eax
0x180030755  jz      short loc_18003077A
0x180030757  xor     r9d, r9d; dwFlags
0x18003075a  lea     r8, [rsp+1540h+pcchPath]; pcchPath
0x18003075f  lea     rdx, [rbp+1440h+var_10A0]; pszPath
0x180030766  mov     rcx, rdi; pszUrl
0x180030769  call    cs:__imp_PathCreateFromUrlW
0x18003076f  lea     rcx, [rbp+1440h+var_10A0]
0x180030776  test    eax, eax
0x180030778  jns     short loc_18003077D
0x18003077a  mov     rcx, rdi; pszName
0x18003077d  lea     r8, [rsp+1540h+pcchOut]
0x180030782  mov     qword ptr [rsp+1540h+pcchOut], rsi
0x180030787  call    SHSimpleIDListFromFindData
0x18003078c  mov     rax, qword ptr [rsp+1540h+pcchOut]
0x180030791  mov     [r15], rax
  ... truncated ...
```
