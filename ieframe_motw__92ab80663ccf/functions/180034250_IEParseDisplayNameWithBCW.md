# IEParseDisplayNameWithBCW

- ea: `0x180034250`
- end: `0x1800347c3`
- name: `IEParseDisplayNameWithBCW`
- size: `1395`
- prototype: ``
- caller_count: `23`
- callee_count: `20`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180073110`
- `0x1800bc3c0`
- `0x18011ecd8`
- `0x18014f9dc`
- `0x180188118`
- `0x1801881c8`
- `0x180197a54`
- `0x180197f18`
- `0x180198670`
- `0x18019f3a0`
- `0x1801b0750`
- `0x1801b3534`
- `0x1801b6680`
- `0x1801b7524`
- `0x180262d84`
- `0x180268d2c`
- `0x180274a14`
- `0x180282f8c`
- `0x180292cd4`
- `0x1802a7a18`
- `0x1802acf24`
- `0x18032f4f0`
- `0x18042dad0`

## callees

- `0x180006100`
- `0x180007010`
- `0x180015644`
- `0x180034250`
- `0x1800352ec`
- `0x180035380`
- `0x1800353f0`
- `0x180035448`
- `0x18005bbec`
- `0x18006dc60`
- `0x180070630`
- `0x1800bf0d8`
- `0x1800c0b58`
- `0x18011eafc`
- `0x18051c514`
- `0x180524bb8`
- `0x180524c50`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003477b`
- `KERNEL32!LocalFree` at `0x18003478a`
- `KERNEL32!LocalFree` at `0x18003477b`
- `KERNEL32!LocalFree` at `0x18003478a`
- `KERNEL32!GetProcessHeap` at `0x1800343c6`
- `KERNEL32!GetProcessHeap` at `0x1800343c6`
- `KERNEL32!HeapAlloc` at `0x1800343de`
- `KERNEL32!HeapAlloc` at `0x1800343de`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800342cf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x1800342cf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x18003433d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetPartW` at `0x18003433d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800345a7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800345bf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800345a7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x1800345bf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180034552`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800346cb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180034552`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800346cb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x1800342f1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlGetLocationW` at `0x1800342f1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlAlloc` at `0x180034366`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlAlloc` at `0x180034366`
- `SHELL32!SHParseDisplayName` at `0x180034662`
- `SHELL32!SHParseDisplayName` at `0x180034662`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800344ce`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800344ce`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034680`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034695`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034680`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180034695`

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
    if ( dword_18069F770 )
      goto LABEL_44;
    goto LABEL_43;
  }
  IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
  if ( IsFeatureEnabledInternal >= 0 )
  {
    dword_18069F770 = IsFeatureEnabledInternal == 0;
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
0x180034250  push    rbp
0x180034252  push    rbx
0x180034253  push    rsi
0x180034254  push    rdi
0x180034255  push    r12
0x180034257  push    r13
0x180034259  push    r14
0x18003425b  push    r15
0x18003425d  lea     rbp, [rsp-1408h]
0x180034265  mov     eax, 1508h
0x18003426a  call    _alloca_probe
0x18003426f  sub     rsp, rax
0x180034272  mov     rax, cs:__security_cookie
0x180034279  xor     rax, rsp
0x18003427c  mov     [rbp+1440h+var_50], rax
0x180034283  xor     r14d, r14d
0x180034286  mov     [rsp+1540h+pcchPath], ecx
0x18003428a  mov     [rsp+1540h+ppszOut], r14
0x18003428f  mov     r15, r9
0x180034292  mov     [rsp+1540h+ppbc], r14
0x180034297  mov     rsi, r8
0x18003429a  mov     rdi, rdx
0x18003429d  mov     ebx, ecx
0x18003429f  mov     r12d, r14d
0x1800342a2  test    rdx, rdx
0x1800342a5  jz      loc_1800343C3
0x1800342ab  xorps   xmm0, xmm0
0x1800342ae  lea     rdx, [rsp+1540h+ppu]; ppu
0x1800342b3  xor     eax, eax
0x1800342b5  mov     rcx, rdi; pcszURL
0x1800342b8  movups  xmmword ptr [rsp+1540h+ppu.cbSize], xmm0
0x1800342bd  mov     [rsp+1540h+ppu.cbSize], 28h ; '('
0x1800342c5  movups  xmmword ptr [rsp+1540h+ppu.cchProtocol], xmm0
0x1800342ca  mov     qword ptr [rsp+1540h+ppu.cchSuffix], rax
0x1800342cf  call    cs:__imp_ParseURLW
0x1800342d6  nop     dword ptr [rax+rax+00h]
0x1800342db  test    eax, eax
0x1800342dd  js      loc_1800343C3
0x1800342e3  cmp     [rsp+1540h+ppu.nScheme], 9
0x1800342e8  jnz     loc_1800343C3
0x1800342ee  mov     rcx, rdi; pszURL
0x1800342f1  call    cs:__imp_UrlGetLocationW
0x1800342f8  nop     dword ptr [rax+rax+00h]
0x1800342fd  lea     r9, [rsp+1540h+ppbc]; void **
0x180034302  mov     r8d, 1048h; unsigned __int64
0x180034308  lea     edx, [r14+40h]; unsigned int
0x18003430c  mov     r13, rax
0x18003430f  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180034314  mov     r12, [rsp+1540h+ppbc]
0x180034319  mov     ebx, eax
0x18003431b  test    eax, eax
0x18003431d  js      short loc_18003435B
0x18003431f  lea     rdx, [r12+2]; pszOut
0x180034324  mov     [rsp+1540h+pcchOut], 823h
0x18003432c  lea     r9d, [r14+6]; dwPart
0x180034330  mov     [rsp+1540h+dwFlags], r14d; dwFlags
0x180034335  lea     r8, [rsp+1540h+pcchOut]; pcchOut
0x18003433a  mov     rcx, rdi; pszIn
0x18003433d  call    cs:__imp_UrlGetPartW
0x180034344  nop     dword ptr [rax+rax+00h]
0x180034349  test    eax, eax
0x18003434b  js      short loc_18003435B
0x18003434d  cmp     [rsp+1540h+pcchOut], r14d
0x180034352  jz      short loc_18003435B
0x180034354  mov     word ptr [r12], 3Fh ; '?'
0x18003435b  xor     r8d, r8d; dwFlags
0x18003435e  lea     rdx, [rsp+1540h+ppszOut]; ppszOut
0x180034363  mov     rcx, rdi; pszIn
0x180034366  call    cs:__imp_PathCreateFromUrlAlloc
0x18003436d  nop     dword ptr [rax+rax+00h]
0x180034372  test    eax, eax
0x180034374  js      short loc_1800343B5
0x180034376  mov     rdi, [rsp+1540h+ppszOut]
0x18003437b  test    rdi, rdi
0x18003437e  jz      short loc_1800343A4
0x180034380  movzx   eax, word ptr [rdi]
0x180034383  test    ax, ax
0x180034386  jz      short loc_1800343A4
0x180034388  cmp     ax, 2Fh ; '/'
0x18003438c  jnz     short loc_180034393
0x18003438e  mov     word ptr [rdi], 5Ch ; '\'
0x180034393  add     rdi, 2
0x180034397  movzx   eax, word ptr [rdi]
0x18003439a  test    ax, ax
0x18003439d  jnz     short loc_180034388
0x18003439f  mov     rdi, [rsp+1540h+ppszOut]
0x1800343a4  mov     rcx, rdi; pszPath
0x1800343a7  call    PathIsAbsolute
0x1800343ac  test    eax, eax
0x1800343ae  jnz     short loc_1800343B5
0x1800343b0  mov     ebx, 80004005h
0x1800343b5  test    ebx, ebx
0x1800343b7  js      loc_180034776
0x1800343bd  mov     ebx, [rsp+1540h+pcchPath]
0x1800343c1  jmp     short loc_1800343C6
0x1800343c3  mov     r13, r14
0x1800343c6  call    cs:__imp_GetProcessHeap
0x1800343cd  nop     dword ptr [rax+rax+00h]
0x1800343d2  mov     edx, 8; dwFlags
0x1800343d7  mov     rcx, rax; hHeap
0x1800343da  lea     r8d, [rdx+8]; dwBytes
0x1800343de  call    cs:__imp_HeapAlloc
0x1800343e5  nop     dword ptr [rax+rax+00h]
0x1800343ea  test    rax, rax
0x1800343ed  jnz     short loc_1800343F5
0x1800343ef  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800343f5  mov     edx, ebx; unsigned int
0x1800343f7  mov     rcx, rax; this
0x1800343fa  call    ??0CDwnCodePage@@QEAA@I@Z; CDwnCodePage::CDwnCodePage(uint)
0x1800343ff  mov     r14, rax
0x180034402  mov     [rsp+1540h+ppbc], rsi
0x180034407  xor     eax, eax
0x180034409  mov     [r15], rax
0x18003440c  test    rsi, rsi
0x18003440f  jz      short loc_180034424
0x180034411  mov     rdx, [rsi]
0x180034414  mov     rcx, rsi
0x180034417  mov     rax, [rdx+8]
0x18003441b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034420  xor     esi, esi
0x180034422  jmp     short loc_180034438
0x180034424  lea     rdx, [rsp+1540h+ppbc]; ppbc
0x180034429  xor     ecx, ecx; reserved
0x18003442b  call    CreateBindCtx_0
0x180034430  xor     esi, esi
0x180034432  mov     ebx, eax
0x180034434  test    eax, eax
0x180034436  js      short loc_1800344AD
0x180034438  mov     rbx, [rsp+1540h+ppbc]
0x18003443d  test    r14, r14
0x180034440  jnz     short loc_18003446E
0x180034442  lea     ecx, [r14+18h]; dwBytes
0x180034446  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003444b  test    rax, rax
0x18003444e  jz      short loc_180034467
0x180034450  mov     rcx, rax; this
0x180034453  call    ??0CDummyOleWindow@@QEAA@XZ; CDummyOleWindow::CDummyOleWindow(void)
0x180034458  mov     rsi, rax
0x18003445b  test    rax, rax
0x18003445e  jz      short loc_180034465
0x180034460  mov     r8, rax
0x180034463  jmp     short loc_180034471
0x180034465  xor     esi, esi
0x180034467  mov     ebx, 8007000Eh
0x18003446c  jmp     short loc_1800344A3
0x18003446e  mov     r8, r14
0x180034471  mov     rax, [rbx]
0x180034474  lea     rdx, aCdwncodepage; "CDwnCodePage"
0x18003447b  mov     rcx, rbx
0x18003447e  mov     rax, [rax+48h]
0x180034482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034487  mov     ebx, eax
0x180034489  test    rsi, rsi
0x18003448c  jz      short loc_18003449D
0x18003448e  mov     rax, [rsi]
0x180034491  mov     rcx, rsi
0x180034494  mov     rax, [rax+10h]
0x180034498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003449d  xor     esi, esi
0x18003449f  test    ebx, ebx
0x1800344a1  jns     short loc_1800344AD
0x1800344a3  lea     rcx, [rsp+1540h+ppbc]
0x1800344a8  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x1800344ad  test    r14, r14
0x1800344b0  jz      short loc_1800344BA
0x1800344b2  mov     rcx, r14; this
0x1800344b5  call    ?Release@CDwnCodePage@@UEAAKXZ; CDwnCodePage::Release(void)
0x1800344ba  test    ebx, ebx
0x1800344bc  js      loc_18003470C
0x1800344c2  mov     rcx, cs:?FEATURE_INTERNET_SHELL_FOLDERS@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_INTERNET_SHELL_FOLDERS
0x1800344c9  test    rcx, rcx
0x1800344cc  jz      short loc_1800344F0
0x1800344ce  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x1800344d5  nop     dword ptr [rax+rax+00h]
0x1800344da  test    eax, eax
0x1800344dc  js      short loc_1800344FA
0x1800344de  mov     ecx, esi
0x1800344e0  setz    cl
0x1800344e3  mov     cs:dword_18069F770, ecx
0x1800344e9  mov     cs:?FEATURE_INTERNET_SHELL_FOLDERS@FCK@@3VCFeatureControlKey@@A, rsi; CFeatureControlKey FCK::FEATURE_INTERNET_SHELL_FOLDERS
0x1800344f0  mov     eax, cs:dword_18069F770
0x1800344f6  test    eax, eax
0x1800344f8  jnz     short loc_18003450E
0x1800344fa  mov     rcx, [rsp+1540h+ppbc]
0x1800344ff  lea     rdx, aDoNotBindToInt; "Do not bind to Internet shell folder ha"...
0x180034506  xor     r8d, r8d
0x180034509  call    BindCtx_AddObjectParam
0x18003450e  test    rdi, rdi
0x180034511  jz      short loc_180034524
0x180034513  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180034517  xor     r14d, r14d
0x18003451a  inc     rsi
0x18003451d  cmp     [rdi+rsi*2], r14w
0x180034522  jnz     short loc_18003451A
0x180034524  test    esi, esi
0x180034526  jz      loc_180034705
0x18003452c  mov     rcx, rdi
0x18003452f  call    IsFileUrlW
0x180034534  test    eax, eax
0x180034536  jz      short loc_18003456F
0x180034538  xor     r9d, r9d; dwFlags
0x18003453b  mov     [rsp+1540h+pcchOut], 104h
0x180034543  lea     r8, [rsp+1540h+pcchOut]; pcchPath
0x180034548  mov     rcx, rdi; pszUrl
0x18003454b  lea     rdx, [rbp+1440h+pszPath]; pszPath
0x180034552  call    cs:__imp_PathCreateFromUrlW
0x180034559  nop     dword ptr [rax+rax+00h]
0x18003455e  mov     ebx, eax
0x180034560  test    eax, eax
0x180034562  js      short loc_18003456F
0x180034564  mov     esi, [rsp+1540h+pcchOut]
0x180034568  lea     rdi, [rbp+1440h+pszPath]
0x18003456f  mov     rcx, rdi
0x180034572  call    PathIsFilePath
0x180034577  mov     r14d, eax
0x18003457a  test    eax, eax
0x18003457c  jz      short loc_1800345E3
0x18003457e  mov     edx, 104h; unsigned __int64
0x180034583  cmp     esi, edx
0x180034585  jnb     short loc_1800345D7
0x180034587  xor     r9d, r9d; enum PATHCCH_OPTIONS
0x18003458a  lea     rcx, [rbp+1440h+pszStart]; unsigned __int16 *
0x18003458e  mov     r8, rdi; unsigned __int16 *
0x180034591  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x180034596  xor     esi, esi
0x180034598  test    eax, eax
0x18003459a  js      short loc_1800345D9
0x18003459c  lea     edx, [rsi+2Ah]; wMatch
0x18003459f  lea     rcx, [rbp+1440h+pszStart]; pszStart
0x1800345a3  lea     rdi, [rbp+1440h+pszStart]
0x1800345a7  call    cs:__imp_StrChrW
0x1800345ae  nop     dword ptr [rax+rax+00h]
0x1800345b3  test    rax, rax
0x1800345b6  jnz     short loc_1800345D0
0x1800345b8  lea     edx, [rsi+3Fh]; wMatch
0x1800345bb  lea     rcx, [rbp+1440h+pszStart]; pszStart
0x1800345bf  call    cs:__imp_StrChrW
0x1800345c6  nop     dword ptr [rax+rax+00h]
0x1800345cb  test    rax, rax
0x1800345ce  jz      short loc_1800345E5
0x1800345d0  mov     ebx, 80004005h
0x1800345d5  jmp     short loc_1800345E5
0x1800345d7  xor     esi, esi
0x1800345d9  mov     ebx, 80070003h
0x1800345de  jmp     loc_18003470C
0x1800345e3  xor     esi, esi
0x1800345e5  test    ebx, ebx
0x1800345e7  js      loc_18003470C
0x1800345ed  test    r14d, r14d
0x1800345f0  jnz     short loc_18003464F
0x1800345f2  mov     rcx, [rsp+1540h+ppbc]
0x1800345f7  mov     qword ptr [rsp+1540h+pcchOut], rsi
0x1800345fc  test    rcx, rcx
0x1800345ff  jz      short loc_180034635
0x180034601  mov     rax, [rcx]
0x180034604  lea     r8, [rsp+1540h+pcchOut]
0x180034609  lea     rdx, aParsePreferFol; "Parse Prefer Folder Browsing"
0x180034610  mov     rax, [rax+50h]
0x180034614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034619  test    eax, eax
0x18003461b  js      short loc_180034630
0x18003461d  mov     rcx, qword ptr [rsp+1540h+pcchOut]
0x180034622  mov     rax, [rcx]
0x180034625  mov     rax, [rax+10h]
0x180034629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003462e  jmp     short loc_18003464F
0x180034630  mov     rcx, [rsp+1540h+ppbc]
0x180034635  mov     edx, [rsp+1540h+pcchPath]; unsigned int
0x180034639  mov     r8, rcx; struct IBindCtx *
0x18003463c  mov     rcx, rdi; unsigned __int16 *
0x18003463f  mov     r9, r15; struct _ITEMIDLIST_ABSOLUTE **
0x180034642  call    ?_IEParseDisplayNameDirect@@YA_NPEBGIPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _IEParseDisplayNameDirect(ushort const *,uint,IBindCtx *,_ITEMIDLIST_ABSOLUTE * *)
0x180034647  test    al, al
0x180034649  jnz     loc_18003470C
0x18003464f  mov     rdx, [rsp+1540h+ppbc]; pbc
0x180034654  xor     r9d, r9d; sfgaoIn
0x180034657  mov     r8, r15; ppidl
0x18003465a  mov     qword ptr [rsp+1540h+dwFlags], rsi; psfgaoOut
0x18003465f  mov     rcx, rdi; pszName
0x180034662  call    cs:__imp_SHParseDisplayName
0x180034669  nop     dword ptr [rax+rax+00h]
0x18003466e  mov     ebx, eax
0x180034670  cmp     eax, 80070005h
0x180034675  jnz     loc_18003470C
0x18003467b  mov     ecx, 1000001Ah
0x180034680  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180034687  nop     dword ptr [rax+rax+00h]
0x18003468c  test    al, al
0x18003468e  jz      short loc_18003470C
0x180034690  mov     ecx, 20000003h
0x180034695  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18003469c  nop     dword ptr [rax+rax+00h]
0x1800346a1  test    al, al
0x1800346a3  jz      short loc_18003470C
0x1800346a5  mov     rcx, rdi
0x1800346a8  mov     [rsp+1540h+pcchPath], 825h
0x1800346b0  call    IsFileUrlW
0x1800346b5  test    eax, eax
0x1800346b7  jz      short loc_1800346E2
0x1800346b9  xor     r9d, r9d; dwFlags
  ... truncated ...
```
