# CDownloadUtilities::OpenSafeOpenDialog(HWND__ *,uint,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,uint,IUnknown *,int,int,int,int,ulong,int,uint *)

- ea: `0x1800ea15c`
- end: `0x1800ea5d2`
- name: `?OpenSafeOpenDialog@CDownloadUtilities@@SAIPEAUHWND__@@IPEBG11111_KIPEAUIUnknown@@HHHHKHPEAI@Z`
- size: `1142`
- prototype: `unsigned int __fastcall(HWND, unsigned int, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpSrcStr, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR pszPath, unsigned __int64, UINT CodePage, IUnknown *punk, int, int, int, int, unsigned int, int, unsigned int *)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cf5c0`
- `0x1800e9ba4`
- `0x1800fa348`
- `0x18017e744`

## callees

- `0x180011230`
- `0x180015150`
- `0x180065a9c`
- `0x1800a2bf8`
- `0x1800c912c`
- `0x1800ea15c`
- `0x1800ebe70`
- `0x1800ec164`
- `0x1803823a0`
- `0x1804022d0`
- `0x1804f1e20`
- `0x1804f2710`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `SHLWAPI!AssocIsDangerous` at `0x1800ea226`
- `SHLWAPI!AssocIsDangerous` at `0x1800ea24a`
- `SHLWAPI!AssocIsDangerous` at `0x1800ea27d`
- `SHLWAPI!AssocIsDangerous` at `0x1800ea226`
- `SHLWAPI!AssocIsDangerous` at `0x1800ea24a`
- `SHLWAPI!AssocIsDangerous` at `0x1800ea27d`
- `SHLWAPI!PathUndecorateW` at `0x1800ea358`
- `SHLWAPI!PathUndecorateW` at `0x1800ea358`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800ea570`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800ea570`
- `msvcrt!wcsnlen` at `0x1800ea37d`
- `msvcrt!wcsnlen` at `0x1800ea37d`
- `KERNEL32!LocalFree` at `0x1800ea3d8`
- `KERNEL32!LocalFree` at `0x1800ea3d8`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800ea40a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800ea40a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800ea212`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800ea212`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800ea32b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800ea32b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ea5a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ea5a0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ea542`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ea542`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800ea1e5`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800ea1e5`
- `urlmon!__imp_?IECompatLogMimeSniffUnsafe@@YAXPEBG0@Z` at `0x1800ea29f`
- `urlmon!__imp_?IECompatLogMimeSniffUnsafe@@YAXPEBG0@Z` at `0x1800ea29f`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800ea456`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800ea456`

## pseudocode

```c
__int64 __fastcall CDownloadUtilities::OpenSafeOpenDialog(
        HWND a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR lpSrcStr,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        LPCWSTR pszPath,
        unsigned __int64 a9,
        UINT CodePage,
        IUnknown *punk,
        int a12,
        int a13,
        int a14,
        int a15,
        unsigned int a16,
        int a17,
        unsigned int *a18)
{
  BOOL v20; // r12d
  LPWSTR ExtensionW; // rax
  BOOL v23; // ebx
  const WCHAR *v24; // rcx
  const unsigned __int16 *FileNameW; // rax
  int v26; // eax
  bool v27; // al
  unsigned int v28; // edx
  const unsigned __int16 *v29; // rcx
  int v30; // esi
  unsigned int v31; // edx
  int v32; // eax
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+28h] [rbp-D8h]
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v38; // [rsp+44h] [rbp-BCh] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  void *ppvOut; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v42; // [rsp+60h] [rbp-A0h]
  unsigned int *v43; // [rsp+68h] [rbp-98h]
  HWND v44; // [rsp+70h] [rbp-90h]
  int v45; // [rsp+80h] [rbp-80h] BYREF
  int v46; // [rsp+84h] [rbp-7Ch]
  BOOL v47; // [rsp+88h] [rbp-78h]
  BOOL v48; // [rsp+8Ch] [rbp-74h]
  WCHAR *v49; // [rsp+90h] [rbp-70h]
  WCHAR *p_Source; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v51; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v52; // [rsp+A8h] [rbp-58h]
  __int64 v53; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v54; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v55; // [rsp+C0h] [rbp-40h]
  int v56; // [rsp+C8h] [rbp-38h]
  unsigned int v57; // [rsp+CCh] [rbp-34h]
  int v58; // [rsp+D0h] [rbp-30h]
  int v59; // [rsp+D4h] [rbp-2Ch]
  int v60; // [rsp+D8h] [rbp-28h]
  int v61; // [rsp+DCh] [rbp-24h]
  _BYTE v62[28]; // [rsp+E0h] [rbp-20h] BYREF
  int v63; // [rsp+FCh] [rbp-4h]
  int v64; // [rsp+124h] [rbp+24h]
  __int64 v65; // [rsp+128h] [rbp+28h]
  __int64 v66; // [rsp+130h] [rbp+30h]
  WCHAR Source; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v68[526]; // [rsp+142h] [rbp+42h] BYREF
  WCHAR Buffer[96]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v70[264]; // [rsp+410h] [rbp+310h] BYREF
  unsigned __int16 v71; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v72[4174]; // [rsp+622h] [rbp+522h] BYREF

  v42 = a6;
  v44 = a1;
  v20 = 0;
  v43 = a18;
  ppvOut = 0;
  if ( IUnknown_QueryService(punk, &IID_IDownloadManager, &GUID_988934a4_064b_11d3_bb80_00104b35e7f9, &ppvOut) >= 0 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    return 4358;
  }
  v23 = !pszPath || (ExtensionW = PathFindExtensionW(pszPath)) == 0 || !*ExtensionW || AssocIsDangerous(ExtensionW);
  if ( (!a3 || !AssocIsDangerous(a3))
    && (!lpSrcStr || !(unsigned int)CDownloadUtilities::UrlExtensionIsDangerous(lpSrcStr, CodePage)) )
  {
    if ( !a4 || !AssocIsDangerous(a4) )
    {
      if ( !v23 && !a12 && !a14 && !a13 && !a17 )
        v20 = SHRestricted2W(1610612755, 0, 0) == 0;
      goto LABEL_24;
    }
    if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
      IECompatLogMimeSniffUnsafe(lpSrcStr, a4);
  }
  v23 = 1;
LABEL_24:
  Source = 0;
  memset_0(v68, 0, 0x206u);
  v71 = 0;
  memset_0(v72, 0, 0x1046u);
  v37 = 0;
  v24 = pszPath;
  if ( !pszPath )
    v24 = lpSrcStr;
  FileNameW = PathFindFileNameW(v24);
  if ( FileNameW )
    StringCchCopyW(&Source, 0x104u, FileNameW);
  DecodeCacheFilenameForDisplay(&Source, 0x104u);
  PathUndecorateW(&Source);
  if ( !pszPath )
    SHReplaceChars(&Source, 46, 95);
  v26 = wcsnlen(&Source, 0x103u);
  CDownloadFilePathUtilities::StripRTLCharactersInPlace(&Source, v26 + 1);
  hMem = 0;
  v27 = IsUrlHandledByBlobProtocol(lpSrcStr);
  v29 = v42;
  if ( !v27 )
    v29 = lpSrcStr;
  if ( (int)GetHostDisplayNameFromUrlInternal(v29, v28, (unsigned __int16 **)&hMem, &v37, v35, v36) < 0 )
  {
    StringCchCopyW(&v71, 0x824u, lpSrcStr);
    v30 = 1;
  }
  else
  {
    StringCchCopyW(&v71, 0x824u, (const unsigned __int16 *)hMem);
    LocalFree(hMem);
    v30 = v37;
  }
  LoadStringW(g_hinstMUI, 0x8534u, Buffer, 96);
  memset_0(v70, 0, 0x208u);
  bstrString = 0;
  v38 = 0;
  if ( (int)LCIEGetRedirectionPolicyForURL2(lpSrcStr, 0, 1, 0x8000u, &v38, 0, &bstrString) >= 0 && bstrString )
    StringCchCopyW(v70, 0x104u, bstrString);
  v47 = v23;
  v45 = 0;
  v48 = v20;
  v51 = a3;
  v46 = a13 != 0 ? 1 : 3;
  v53 = 0;
  v49 = Buffer;
  p_Source = &Source;
  v52 = &v71;
  v54 = v70;
  v55 = a9;
  v56 = a15;
  v58 = a12;
  v60 = a17;
  v57 = a16;
  v59 = v30;
  v61 = 0;
  v63 = 0;
  v64 = 0;
  memset_0(v62, 0, 0x48u);
  v65 = 0;
  v66 = -1;
  if ( v46 == 3
    && (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_DOWNLOAD_PROMPT_META_CONTROL) != 1 )
  {
    if ( (a16 & 1) != 0 )
    {
      if ( !(unsigned __int8)IEConfiguration_GetBool(536870914) )
        v46 = 2;
    }
    else
    {
      v32 = v46;
      if ( (a16 & 2) != 0 )
        v32 = 1;
      v46 = v32;
    }
    if ( a3 )
    {
      v33 = StrCmpICW(a3, L"htafile");
      v31 = v46;
      if ( !v33 )
        v31 = 1;
      v46 = v31;
    }
  }
  v34 = CDownloadUtilities::ShowSafeOpenDialog(v44, v31, (struct SAFEOPENDLGPARAM *)&v45, v43, lpSrcStr);
  SysFreeString(bstrString);
  return v34;
}

```

## disassembly

```asm
0x1800ea15c  mov     [rsp-8+arg_8], rbx
0x1800ea161  push    rbp
0x1800ea162  push    rsi
0x1800ea163  push    rdi
0x1800ea164  push    r12
0x1800ea166  push    r13
0x1800ea168  push    r14
0x1800ea16a  push    r15
0x1800ea16c  lea     rbp, [rsp-1580h]
0x1800ea174  mov     eax, 1680h
0x1800ea179  call    _alloca_probe
0x1800ea17e  sub     rsp, rax
0x1800ea181  mov     rax, cs:__security_cookie
0x1800ea188  xor     rax, rsp
0x1800ea18b  mov     [rbp+15B0h+var_40], rax
0x1800ea192  mov     rax, [rbp+15B0h+arg_28]
0x1800ea199  lea     rdx, IID_IDownloadManager; guidService
0x1800ea1a0  mov     r14, [rbp+15B0h+pszPath]
0x1800ea1a7  mov     rsi, r9
0x1800ea1aa  mov     rdi, [rbp+15B0h+lpSrcStr]
0x1800ea1b1  lea     r9, [rsp+16B0h+ppvOut]; ppvOut
0x1800ea1b6  mov     [rsp+16B0h+var_1650], rax
0x1800ea1bb  mov     r15, r8
0x1800ea1be  mov     rax, [rbp+15B0h+arg_88]
0x1800ea1c5  lea     r8, _GUID_988934a4_064b_11d3_bb80_00104b35e7f9; riid
0x1800ea1cc  mov     [rsp+16B0h+var_1640], rcx
0x1800ea1d1  xor     r12d, r12d
0x1800ea1d4  mov     rcx, [rbp+15B0h+punk]; punk
0x1800ea1db  mov     [rsp+16B0h+var_1648], rax
0x1800ea1e0  mov     [rsp+16B0h+ppvOut], r12
0x1800ea1e5  call    cs:__imp_IUnknown_QueryService
0x1800ea1eb  test    eax, eax
0x1800ea1ed  js      short loc_1800EA20A
0x1800ea1ef  mov     rcx, [rsp+16B0h+ppvOut]
0x1800ea1f4  mov     rax, [rcx]
0x1800ea1f7  mov     rax, [rax+10h]
0x1800ea1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea200  mov     eax, 1106h
0x1800ea205  jmp     loc_1800EA5A8
0x1800ea20a  test    r14, r14
0x1800ea20d  jz      short loc_1800EA236
0x1800ea20f  mov     rcx, r14; pszPath
0x1800ea212  call    cs:__imp_PathFindExtensionW
0x1800ea218  test    rax, rax
0x1800ea21b  jz      short loc_1800EA236
0x1800ea21d  cmp     [rax], r12w
0x1800ea221  jz      short loc_1800EA236
0x1800ea223  mov     rcx, rax; pszAssoc
0x1800ea226  call    cs:__imp_AssocIsDangerous
0x1800ea22c  test    eax, eax
0x1800ea22e  mov     ebx, r12d
0x1800ea231  setnz   bl
0x1800ea234  jmp     short loc_1800EA23B
0x1800ea236  mov     ebx, 1
0x1800ea23b  mov     r13d, [rbp+15B0h+arg_60]
0x1800ea242  test    r15, r15
0x1800ea245  jz      short loc_1800EA25E
0x1800ea247  mov     rcx, r15; pszAssoc
0x1800ea24a  call    cs:__imp_AssocIsDangerous
0x1800ea250  test    eax, eax
0x1800ea252  jz      short loc_1800EA25E
0x1800ea254  mov     ebx, 1
0x1800ea259  jmp     loc_1800EA2E5
0x1800ea25e  test    rdi, rdi
0x1800ea261  jz      short loc_1800EA275
0x1800ea263  mov     edx, [rbp+15B0h+CodePage]; CodePage
0x1800ea269  mov     rcx, rdi; lpSrcStr
0x1800ea26c  call    ?UrlExtensionIsDangerous@CDownloadUtilities@@SAHPEBGK@Z; CDownloadUtilities::UrlExtensionIsDangerous(ushort const *,ulong)
0x1800ea271  test    eax, eax
0x1800ea273  jnz     short loc_1800EA254
0x1800ea275  test    rsi, rsi
0x1800ea278  jz      short loc_1800EA2A7
0x1800ea27a  mov     rcx, rsi; pszAssoc
0x1800ea27d  call    cs:__imp_AssocIsDangerous
0x1800ea283  test    eax, eax
0x1800ea285  jz      short loc_1800EA2A7
0x1800ea287  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x1800ea28e  jz      short loc_1800EA254
0x1800ea290  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1800ea295  test    eax, eax
0x1800ea297  jz      short loc_1800EA254
0x1800ea299  mov     rdx, rsi
0x1800ea29c  mov     rcx, rdi
0x1800ea29f  call    cs:__imp_?IECompatLogMimeSniffUnsafe@@YAXPEBG0@Z; IECompatLogMimeSniffUnsafe(ushort const *,ushort const *)
0x1800ea2a5  jmp     short loc_1800EA254
0x1800ea2a7  test    ebx, ebx
0x1800ea2a9  jnz     short loc_1800EA2E5
0x1800ea2ab  cmp     [rbp+15B0h+arg_58], r12d
0x1800ea2b2  jnz     short loc_1800EA2E5
0x1800ea2b4  cmp     [rbp+15B0h+arg_68], r12d
0x1800ea2bb  jnz     short loc_1800EA2E5
0x1800ea2bd  test    r13d, r13d
0x1800ea2c0  jnz     short loc_1800EA2E5
0x1800ea2c2  cmp     [rbp+15B0h+arg_80], r12d
0x1800ea2c9  jnz     short loc_1800EA2E5
0x1800ea2cb  xor     r8d, r8d
0x1800ea2ce  lea     r12d, [rbx+1]
0x1800ea2d2  xor     edx, edx
0x1800ea2d4  mov     ecx, 60000013h
0x1800ea2d9  call    SHRestricted2W
0x1800ea2de  test    eax, eax
0x1800ea2e0  jz      short loc_1800EA2E5
0x1800ea2e2  xor     r12d, r12d
0x1800ea2e5  xor     eax, eax
0x1800ea2e7  lea     rcx, [rbp+15B0h+var_156E]; void *
0x1800ea2eb  xor     edx, edx; Val
0x1800ea2ed  mov     [rbp+15B0h+Source], ax
0x1800ea2f1  mov     r8d, 206h; Size
0x1800ea2f7  call    memset_0
0x1800ea2fc  xor     eax, eax
0x1800ea2fe  lea     rcx, [rbp+15B0h+var_108E]; void *
0x1800ea305  xor     edx, edx; Val
0x1800ea307  mov     [rbp+15B0h+var_1090], ax
0x1800ea30e  mov     r8d, 1046h; Size
0x1800ea314  call    memset_0
0x1800ea319  test    r14, r14
0x1800ea31c  mov     [rsp+16B0h+var_1670], 0
0x1800ea324  mov     rcx, r14
0x1800ea327  cmovz   rcx, rdi; pszPath
0x1800ea32b  call    cs:__imp_PathFindFileNameW
0x1800ea331  mov     esi, 104h
0x1800ea336  test    rax, rax
0x1800ea339  jz      short loc_1800EA349
0x1800ea33b  mov     r8, rax; unsigned __int16 *
0x1800ea33e  lea     rcx, [rbp+15B0h+Source]; unsigned __int16 *
0x1800ea342  mov     edx, esi; unsigned __int64
0x1800ea344  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ea349  mov     edx, esi; unsigned __int64
0x1800ea34b  lea     rcx, [rbp+15B0h+Source]; unsigned __int16 *
0x1800ea34f  call    DecodeCacheFilenameForDisplay
0x1800ea354  lea     rcx, [rbp+15B0h+Source]; pszPath
0x1800ea358  call    cs:__imp_PathUndecorateW
0x1800ea35e  test    r14, r14
0x1800ea361  jnz     short loc_1800EA374
0x1800ea363  lea     edx, [r14+2Eh]
0x1800ea367  lea     r8d, [r14+5Fh]
0x1800ea36b  lea     rcx, [rbp+15B0h+Source]
0x1800ea36f  call    SHReplaceChars
0x1800ea374  mov     edx, 103h; MaxCount
0x1800ea379  lea     rcx, [rbp+15B0h+Source]; Source
0x1800ea37d  call    cs:__imp_wcsnlen
0x1800ea383  lea     rcx, [rbp+15B0h+Source]; unsigned __int16 *
0x1800ea387  lea     edx, [rax+1]; unsigned int
0x1800ea38a  call    ?StripRTLCharactersInPlace@CDownloadFilePathUtilities@@SAJPEAGI@Z; CDownloadFilePathUtilities::StripRTLCharactersInPlace(ushort *,uint)
0x1800ea38f  xor     r14d, r14d
0x1800ea392  mov     rcx, rdi; unsigned __int16 *
0x1800ea395  mov     [rsp+16B0h+hMem], r14
0x1800ea39a  call    ?IsUrlHandledByBlobProtocol@@YA_NPEBG@Z; IsUrlHandledByBlobProtocol(ushort const *)
0x1800ea39f  mov     rcx, [rsp+16B0h+var_1650]
0x1800ea3a4  lea     r9, [rsp+16B0h+var_1670]; int *
0x1800ea3a9  test    al, al
0x1800ea3ab  lea     r8, [rsp+16B0h+hMem]; unsigned __int16 **
0x1800ea3b0  cmovz   rcx, rdi; unsigned __int16 *
0x1800ea3b4  call    ?GetHostDisplayNameFromUrlInternal@@YAJPEBGIPEAPEAGPEAHHH@Z; GetHostDisplayNameFromUrlInternal(ushort const *,uint,ushort * *,int *,int,int)
0x1800ea3b9  lea     rcx, [rbp+15B0h+var_1090]; unsigned __int16 *
0x1800ea3c0  mov     edx, 824h; unsigned __int64
0x1800ea3c5  test    eax, eax
0x1800ea3c7  js      short loc_1800EA3E4
0x1800ea3c9  mov     r8, [rsp+16B0h+hMem]; unsigned __int16 *
0x1800ea3ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ea3d3  mov     rcx, [rsp+16B0h+hMem]; hMem
0x1800ea3d8  call    cs:__imp_LocalFree
0x1800ea3de  mov     esi, [rsp+16B0h+var_1670]
0x1800ea3e2  jmp     short loc_1800EA3F1
0x1800ea3e4  mov     r8, rdi; unsigned __int16 *
0x1800ea3e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ea3ec  mov     esi, 1
0x1800ea3f1  mov     rcx, cs:g_hinstMUI; hInstance
0x1800ea3f8  lea     r8, [rbp+15B0h+Buffer]; lpBuffer
0x1800ea3ff  mov     r9d, 60h ; '`'; cchBufferMax
0x1800ea405  mov     edx, 8534h; uID
0x1800ea40a  call    cs:__imp_LoadStringW
0x1800ea410  xor     edx, edx; Val
0x1800ea412  lea     rcx, [rbp+15B0h+var_12A0]; void *
0x1800ea419  mov     r8d, 208h; Size
0x1800ea41f  call    memset_0
0x1800ea424  xor     edx, edx
0x1800ea426  mov     [rsp+16B0h+bstrString], r14
0x1800ea42b  lea     rax, [rsp+16B0h+bstrString]
0x1800ea430  mov     [rsp+16B0h+var_166C], r14d
0x1800ea435  mov     [rsp+16B0h+var_1680], rax
0x1800ea43a  mov     r9d, 8000h
0x1800ea440  lea     rax, [rsp+16B0h+var_166C]
0x1800ea445  mov     [rsp+16B0h+var_1688], r14
0x1800ea44a  lea     r8d, [rdx+1]
0x1800ea44e  mov     [rsp+16B0h+var_1690], rax
0x1800ea453  mov     rcx, rdi
0x1800ea456  call    cs:__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x1800ea45c  test    eax, eax
0x1800ea45e  js      short loc_1800EA47B
0x1800ea460  mov     r8, [rsp+16B0h+bstrString]; unsigned __int16 *
0x1800ea465  test    r8, r8
0x1800ea468  jz      short loc_1800EA47B
0x1800ea46a  mov     edx, 104h; unsigned __int64
0x1800ea46f  lea     rcx, [rbp+15B0h+var_12A0]; unsigned __int16 *
0x1800ea476  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ea47b  neg     r13d
0x1800ea47e  mov     [rbp+15B0h+var_1628], ebx
0x1800ea481  mov     ebx, [rbp+15B0h+arg_78]
0x1800ea487  lea     rcx, [rbp+15B0h+var_15D0]; void *
0x1800ea48b  sbb     eax, eax
0x1800ea48d  mov     [rbp+15B0h+var_1630], r14d
0x1800ea491  and     eax, 0FFFFFFFEh
0x1800ea494  mov     [rbp+15B0h+var_1624], r12d
0x1800ea498  add     eax, 3
0x1800ea49b  mov     [rbp+15B0h+var_1610], r15
0x1800ea49f  mov     [rbp+15B0h+var_162C], eax
0x1800ea4a2  xor     edx, edx; Val
0x1800ea4a4  lea     rax, [rbp+15B0h+Buffer]
0x1800ea4ab  mov     [rbp+15B0h+var_1600], r14
0x1800ea4af  mov     [rbp+15B0h+var_1620], rax
0x1800ea4b3  lea     rax, [rbp+15B0h+Source]
0x1800ea4b7  mov     [rbp+15B0h+var_1618], rax
0x1800ea4bb  lea     rax, [rbp+15B0h+var_1090]
0x1800ea4c2  mov     [rbp+15B0h+var_1608], rax
0x1800ea4c6  lea     rax, [rbp+15B0h+var_12A0]
0x1800ea4cd  mov     [rbp+15B0h+var_15F8], rax
0x1800ea4d1  mov     rax, [rbp+15B0h+arg_40]
0x1800ea4d8  mov     [rbp+15B0h+var_15F0], rax
0x1800ea4dc  mov     eax, [rbp+15B0h+arg_70]
0x1800ea4e2  mov     [rbp+15B0h+var_15E8], eax
0x1800ea4e5  mov     eax, [rbp+15B0h+arg_58]
0x1800ea4eb  mov     [rbp+15B0h+var_15E0], eax
0x1800ea4ee  mov     eax, [rbp+15B0h+arg_80]
0x1800ea4f4  mov     [rbp+15B0h+var_15D8], eax
0x1800ea4f7  xor     eax, eax
0x1800ea4f9  mov     [rbp+15B0h+var_15E4], ebx
0x1800ea4fc  mov     [rbp+15B0h+var_15DC], esi
0x1800ea4ff  mov     [rbp+15B0h+var_15D4], eax
0x1800ea502  lea     r8d, [rax+48h]; Size
0x1800ea506  mov     [rbp+15B0h+var_15B4], eax
0x1800ea509  mov     [rbp+15B0h+var_158C], eax
0x1800ea50c  call    memset_0
0x1800ea511  cmp     [rbp+15B0h+var_162C], 3
0x1800ea515  mov     [rbp+15B0h+var_1588], r14
0x1800ea519  mov     [rbp+15B0h+var_1580], 0FFFFFFFFFFFFFFFFh
0x1800ea521  jnz     short loc_1800EA581
0x1800ea523  lea     rcx, ?FEATURE_DOWNLOAD_PROMPT_META_CONTROL@FCK@@3VCFeatureControlKey@@A; this
0x1800ea52a  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800ea52f  mov     esi, 1
0x1800ea534  cmp     eax, esi
0x1800ea536  jz      short loc_1800EA581
0x1800ea538  test    sil, bl
0x1800ea53b  jz      short loc_1800EA555
0x1800ea53d  mov     ecx, 20000002h
0x1800ea542  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ea548  test    al, al
0x1800ea54a  jnz     short loc_1800EA561
0x1800ea54c  mov     [rbp+15B0h+var_162C], 2
0x1800ea553  jmp     short loc_1800EA561
0x1800ea555  mov     eax, [rbp+15B0h+var_162C]
0x1800ea558  test    bl, 2
0x1800ea55b  cmovnz  eax, esi
0x1800ea55e  mov     [rbp+15B0h+var_162C], eax
0x1800ea561  test    r15, r15
0x1800ea564  jz      short loc_1800EA581
0x1800ea566  lea     rdx, aHtafile; "htafile"
0x1800ea56d  mov     rcx, r15; pszStr1
0x1800ea570  call    cs:__imp_StrCmpICW
0x1800ea576  mov     edx, [rbp+15B0h+var_162C]
0x1800ea579  test    eax, eax
0x1800ea57b  cmovz   edx, esi; unsigned int
0x1800ea57e  mov     [rbp+15B0h+var_162C], edx
0x1800ea581  mov     r9, [rsp+16B0h+var_1648]; unsigned int *
0x1800ea586  lea     r8, [rbp+15B0h+var_1630]; struct SAFEOPENDLGPARAM *
0x1800ea58a  mov     rcx, [rsp+16B0h+var_1640]; HWND
0x1800ea58f  mov     [rsp+16B0h+var_1690], rdi; unsigned __int16 *
0x1800ea594  call    ?ShowSafeOpenDialog@CDownloadUtilities@@SAIPEAUHWND__@@IPEAUSAFEOPENDLGPARAM@@PEAIPEBG@Z; CDownloadUtilities::ShowSafeOpenDialog(HWND__ *,uint,SAFEOPENDLGPARAM *,uint *,ushort const *)
0x1800ea599  mov     rcx, [rsp+16B0h+bstrString]; bstrString
0x1800ea59e  mov     ebx, eax
0x1800ea5a0  call    cs:__imp_SysFreeString
0x1800ea5a6  mov     eax, ebx
0x1800ea5a8  mov     rcx, [rbp+15B0h+var_40]
0x1800ea5af  xor     rcx, rsp; StackCookie
0x1800ea5b2  call    __security_check_cookie
0x1800ea5b7  mov     rbx, [rsp+16B0h+arg_8]
0x1800ea5bf  add     rsp, 1680h
0x1800ea5c6  pop     r15
0x1800ea5c8  pop     r14
0x1800ea5ca  pop     r13
0x1800ea5cc  pop     r12
0x1800ea5ce  pop     rdi
0x1800ea5cf  pop     rsi
0x1800ea5d0  pop     rbp
0x1800ea5d1  retn
```
