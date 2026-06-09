# CDownloadUtilities::OpenSafeOpenDialog(HWND__ *,uint,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,uint,IUnknown *,int,int,int,int,ulong,int,uint *)

- ea: `0x1800f3e44`
- end: `0x1800f4315`
- name: `?OpenSafeOpenDialog@CDownloadUtilities@@SAIPEAUHWND__@@IPEBG11111_KIPEAUIUnknown@@HHHHKHPEAI@Z`
- size: `1233`
- prototype: `unsigned int __fastcall(HWND, unsigned int, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpSrcStr, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR pszPath, unsigned __int64, UINT CodePage, IUnknown *punk, int, int, int, int, unsigned int, int, unsigned int *)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d7770`
- `0x1800f381c`
- `0x1801053cc`
- `0x180190e80`

## callees

- `0x1800144d0`
- `0x1800184f0`
- `0x1800692fc`
- `0x1800a8e64`
- `0x1800d0978`
- `0x1800f3e44`
- `0x1800f5d68`
- `0x1800f60fc`
- `0x1803b2d14`
- `0x1804396f4`
- `0x1805312e8`
- `0x180531c5c`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `SHLWAPI!AssocIsDangerous` at `0x1800f3f1a`
- `SHLWAPI!AssocIsDangerous` at `0x1800f3f44`
- `SHLWAPI!AssocIsDangerous` at `0x1800f3f7d`
- `SHLWAPI!AssocIsDangerous` at `0x1800f3f1a`
- `SHLWAPI!AssocIsDangerous` at `0x1800f3f44`
- `SHLWAPI!AssocIsDangerous` at `0x1800f3f7d`
- `SHLWAPI!PathUndecorateW` at `0x1800f406a`
- `SHLWAPI!PathUndecorateW` at `0x1800f406a`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800f42a6`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800f42a6`
- `msvcrt!wcsnlen` at `0x1800f4095`
- `msvcrt!wcsnlen` at `0x1800f4095`
- `KERNEL32!LocalFree` at `0x1800f40f6`
- `KERNEL32!LocalFree` at `0x1800f40f6`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f412e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1800f412e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800f3f00`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1800f3f00`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800f4037`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1800f4037`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f42dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f42dc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800f4272`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800f4272`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800f3ecd`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1800f3ecd`
- `urlmon!__imp_?IECompatLogMimeSniffUnsafe@@YAXPEBG0@Z` at `0x1800f3fa5`
- `urlmon!__imp_?IECompatLogMimeSniffUnsafe@@YAXPEBG0@Z` at `0x1800f3fa5`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800f4180`
- `urlmon!__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z` at `0x1800f4180`

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
0x1800f3e44  mov     [rsp-8+arg_8], rbx
0x1800f3e49  push    rbp
0x1800f3e4a  push    rsi
0x1800f3e4b  push    rdi
0x1800f3e4c  push    r12
0x1800f3e4e  push    r13
0x1800f3e50  push    r14
0x1800f3e52  push    r15
0x1800f3e54  lea     rbp, [rsp-1580h]
0x1800f3e5c  mov     eax, 1680h
0x1800f3e61  call    _alloca_probe
0x1800f3e66  sub     rsp, rax
0x1800f3e69  mov     rax, cs:__security_cookie
0x1800f3e70  xor     rax, rsp
0x1800f3e73  mov     [rbp+15B0h+var_40], rax
0x1800f3e7a  mov     rax, [rbp+15B0h+arg_28]
0x1800f3e81  lea     rdx, IID_IDownloadManager; guidService
0x1800f3e88  mov     r14, [rbp+15B0h+pszPath]
0x1800f3e8f  mov     rsi, r9
0x1800f3e92  mov     rdi, [rbp+15B0h+lpSrcStr]
0x1800f3e99  lea     r9, [rsp+16B0h+ppvOut]; ppvOut
0x1800f3e9e  mov     [rsp+16B0h+var_1650], rax
0x1800f3ea3  mov     r15, r8
0x1800f3ea6  mov     rax, [rbp+15B0h+arg_88]
0x1800f3ead  lea     r8, _GUID_988934a4_064b_11d3_bb80_00104b35e7f9; riid
0x1800f3eb4  mov     [rsp+16B0h+var_1640], rcx
0x1800f3eb9  xor     r12d, r12d
0x1800f3ebc  mov     rcx, [rbp+15B0h+punk]; punk
0x1800f3ec3  mov     [rsp+16B0h+var_1648], rax
0x1800f3ec8  mov     [rsp+16B0h+ppvOut], r12
0x1800f3ecd  call    cs:__imp_IUnknown_QueryService
0x1800f3ed4  nop     dword ptr [rax+rax+00h]
0x1800f3ed9  test    eax, eax
0x1800f3edb  js      short loc_1800F3EF8
0x1800f3edd  mov     rcx, [rsp+16B0h+ppvOut]
0x1800f3ee2  mov     rax, [rcx]
0x1800f3ee5  mov     rax, [rax+10h]
0x1800f3ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3eee  mov     eax, 1106h
0x1800f3ef3  jmp     loc_1800F42EA
0x1800f3ef8  test    r14, r14
0x1800f3efb  jz      short loc_1800F3F30
0x1800f3efd  mov     rcx, r14; pszPath
0x1800f3f00  call    cs:__imp_PathFindExtensionW
0x1800f3f07  nop     dword ptr [rax+rax+00h]
0x1800f3f0c  test    rax, rax
0x1800f3f0f  jz      short loc_1800F3F30
0x1800f3f11  cmp     [rax], r12w
0x1800f3f15  jz      short loc_1800F3F30
0x1800f3f17  mov     rcx, rax; pszAssoc
0x1800f3f1a  call    cs:__imp_AssocIsDangerous
0x1800f3f21  nop     dword ptr [rax+rax+00h]
0x1800f3f26  test    eax, eax
0x1800f3f28  mov     ebx, r12d
0x1800f3f2b  setnz   bl
0x1800f3f2e  jmp     short loc_1800F3F35
0x1800f3f30  mov     ebx, 1
0x1800f3f35  mov     r13d, [rbp+15B0h+arg_60]
0x1800f3f3c  test    r15, r15
0x1800f3f3f  jz      short loc_1800F3F5E
0x1800f3f41  mov     rcx, r15; pszAssoc
0x1800f3f44  call    cs:__imp_AssocIsDangerous
0x1800f3f4b  nop     dword ptr [rax+rax+00h]
0x1800f3f50  test    eax, eax
0x1800f3f52  jz      short loc_1800F3F5E
0x1800f3f54  mov     ebx, 1
0x1800f3f59  jmp     loc_1800F3FF1
0x1800f3f5e  test    rdi, rdi
0x1800f3f61  jz      short loc_1800F3F75
0x1800f3f63  mov     edx, [rbp+15B0h+CodePage]; CodePage
0x1800f3f69  mov     rcx, rdi; lpSrcStr
0x1800f3f6c  call    ?UrlExtensionIsDangerous@CDownloadUtilities@@SAHPEBGK@Z; CDownloadUtilities::UrlExtensionIsDangerous(ushort const *,ulong)
0x1800f3f71  test    eax, eax
0x1800f3f73  jnz     short loc_1800F3F54
0x1800f3f75  test    rsi, rsi
0x1800f3f78  jz      short loc_1800F3FB3
0x1800f3f7a  mov     rcx, rsi; pszAssoc
0x1800f3f7d  call    cs:__imp_AssocIsDangerous
0x1800f3f84  nop     dword ptr [rax+rax+00h]
0x1800f3f89  test    eax, eax
0x1800f3f8b  jz      short loc_1800F3FB3
0x1800f3f8d  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x1800f3f94  jz      short loc_1800F3F54
0x1800f3f96  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1800f3f9b  test    eax, eax
0x1800f3f9d  jz      short loc_1800F3F54
0x1800f3f9f  mov     rdx, rsi
0x1800f3fa2  mov     rcx, rdi
0x1800f3fa5  call    cs:__imp_?IECompatLogMimeSniffUnsafe@@YAXPEBG0@Z; IECompatLogMimeSniffUnsafe(ushort const *,ushort const *)
0x1800f3fac  nop     dword ptr [rax+rax+00h]
0x1800f3fb1  jmp     short loc_1800F3F54
0x1800f3fb3  test    ebx, ebx
0x1800f3fb5  jnz     short loc_1800F3FF1
0x1800f3fb7  cmp     [rbp+15B0h+arg_58], r12d
0x1800f3fbe  jnz     short loc_1800F3FF1
0x1800f3fc0  cmp     [rbp+15B0h+arg_68], r12d
0x1800f3fc7  jnz     short loc_1800F3FF1
0x1800f3fc9  test    r13d, r13d
0x1800f3fcc  jnz     short loc_1800F3FF1
0x1800f3fce  cmp     [rbp+15B0h+arg_80], r12d
0x1800f3fd5  jnz     short loc_1800F3FF1
0x1800f3fd7  xor     r8d, r8d
0x1800f3fda  lea     r12d, [rbx+1]
0x1800f3fde  xor     edx, edx
0x1800f3fe0  mov     ecx, 60000013h
0x1800f3fe5  call    SHRestricted2W
0x1800f3fea  test    eax, eax
0x1800f3fec  jz      short loc_1800F3FF1
0x1800f3fee  xor     r12d, r12d
0x1800f3ff1  xor     eax, eax
0x1800f3ff3  lea     rcx, [rbp+15B0h+var_156E]; void *
0x1800f3ff7  xor     edx, edx; Val
0x1800f3ff9  mov     [rbp+15B0h+Source], ax
0x1800f3ffd  mov     r8d, 206h; Size
0x1800f4003  call    memset_0
0x1800f4008  xor     eax, eax
0x1800f400a  lea     rcx, [rbp+15B0h+var_108E]; void *
0x1800f4011  xor     edx, edx; Val
0x1800f4013  mov     [rbp+15B0h+var_1090], ax
0x1800f401a  mov     r8d, 1046h; Size
0x1800f4020  call    memset_0
0x1800f4025  test    r14, r14
0x1800f4028  mov     [rsp+16B0h+var_1670], 0
0x1800f4030  mov     rcx, r14
0x1800f4033  cmovz   rcx, rdi; pszPath
0x1800f4037  call    cs:__imp_PathFindFileNameW
0x1800f403e  nop     dword ptr [rax+rax+00h]
0x1800f4043  mov     esi, 104h
0x1800f4048  test    rax, rax
0x1800f404b  jz      short loc_1800F405B
0x1800f404d  mov     r8, rax; unsigned __int16 *
0x1800f4050  lea     rcx, [rbp+15B0h+Source]; unsigned __int16 *
0x1800f4054  mov     edx, esi; unsigned __int64
0x1800f4056  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f405b  mov     edx, esi; unsigned __int64
0x1800f405d  lea     rcx, [rbp+15B0h+Source]; unsigned __int16 *
0x1800f4061  call    DecodeCacheFilenameForDisplay
0x1800f4066  lea     rcx, [rbp+15B0h+Source]; pszPath
0x1800f406a  call    cs:__imp_PathUndecorateW
0x1800f4071  nop     dword ptr [rax+rax+00h]
0x1800f4076  test    r14, r14
0x1800f4079  jnz     short loc_1800F408C
0x1800f407b  lea     edx, [r14+2Eh]
0x1800f407f  lea     r8d, [r14+5Fh]
0x1800f4083  lea     rcx, [rbp+15B0h+Source]
0x1800f4087  call    SHReplaceChars
0x1800f408c  mov     edx, 103h; MaxCount
0x1800f4091  lea     rcx, [rbp+15B0h+Source]; Source
0x1800f4095  call    cs:__imp_wcsnlen
0x1800f409c  nop     dword ptr [rax+rax+00h]
0x1800f40a1  lea     rcx, [rbp+15B0h+Source]; unsigned __int16 *
0x1800f40a5  lea     edx, [rax+1]; unsigned int
0x1800f40a8  call    ?StripRTLCharactersInPlace@CDownloadFilePathUtilities@@SAJPEAGI@Z; CDownloadFilePathUtilities::StripRTLCharactersInPlace(ushort *,uint)
0x1800f40ad  xor     r14d, r14d
0x1800f40b0  mov     rcx, rdi; unsigned __int16 *
0x1800f40b3  mov     [rsp+16B0h+hMem], r14
0x1800f40b8  call    ?IsUrlHandledByBlobProtocol@@YA_NPEBG@Z; IsUrlHandledByBlobProtocol(ushort const *)
0x1800f40bd  mov     rcx, [rsp+16B0h+var_1650]
0x1800f40c2  lea     r9, [rsp+16B0h+var_1670]; int *
0x1800f40c7  test    al, al
0x1800f40c9  lea     r8, [rsp+16B0h+hMem]; unsigned __int16 **
0x1800f40ce  cmovz   rcx, rdi; unsigned __int16 *
0x1800f40d2  call    ?GetHostDisplayNameFromUrlInternal@@YAJPEBGIPEAPEAGPEAHHH@Z; GetHostDisplayNameFromUrlInternal(ushort const *,uint,ushort * *,int *,int,int)
0x1800f40d7  lea     rcx, [rbp+15B0h+var_1090]; unsigned __int16 *
0x1800f40de  mov     edx, 824h; unsigned __int64
0x1800f40e3  test    eax, eax
0x1800f40e5  js      short loc_1800F4108
0x1800f40e7  mov     r8, [rsp+16B0h+hMem]; unsigned __int16 *
0x1800f40ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f40f1  mov     rcx, [rsp+16B0h+hMem]; hMem
0x1800f40f6  call    cs:__imp_LocalFree
0x1800f40fd  nop     dword ptr [rax+rax+00h]
0x1800f4102  mov     esi, [rsp+16B0h+var_1670]
0x1800f4106  jmp     short loc_1800F4115
0x1800f4108  mov     r8, rdi; unsigned __int16 *
0x1800f410b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f4110  mov     esi, 1
0x1800f4115  mov     rcx, cs:g_hinstMUI; hInstance
0x1800f411c  lea     r8, [rbp+15B0h+Buffer]; lpBuffer
0x1800f4123  mov     r9d, 60h ; '`'; cchBufferMax
0x1800f4129  mov     edx, 8534h; uID
0x1800f412e  call    cs:__imp_LoadStringW
0x1800f4135  nop     dword ptr [rax+rax+00h]
0x1800f413a  xor     edx, edx; Val
0x1800f413c  lea     rcx, [rbp+15B0h+var_12A0]; void *
0x1800f4143  mov     r8d, 208h; Size
0x1800f4149  call    memset_0
0x1800f414e  xor     edx, edx
0x1800f4150  mov     [rsp+16B0h+bstrString], r14
0x1800f4155  lea     rax, [rsp+16B0h+bstrString]
0x1800f415a  mov     [rsp+16B0h+var_166C], r14d
0x1800f415f  mov     [rsp+16B0h+var_1680], rax
0x1800f4164  mov     r9d, 8000h
0x1800f416a  lea     rax, [rsp+16B0h+var_166C]
0x1800f416f  mov     [rsp+16B0h+var_1688], r14
0x1800f4174  lea     r8d, [rdx+1]
0x1800f4178  mov     [rsp+16B0h+var_1690], rax
0x1800f417d  mov     rcx, rdi
0x1800f4180  call    cs:__imp_?LCIEGetRedirectionPolicyForURL2@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURL2(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x1800f4187  nop     dword ptr [rax+rax+00h]
0x1800f418c  test    eax, eax
0x1800f418e  js      short loc_1800F41AB
0x1800f4190  mov     r8, [rsp+16B0h+bstrString]; unsigned __int16 *
0x1800f4195  test    r8, r8
0x1800f4198  jz      short loc_1800F41AB
0x1800f419a  mov     edx, 104h; unsigned __int64
0x1800f419f  lea     rcx, [rbp+15B0h+var_12A0]; unsigned __int16 *
0x1800f41a6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f41ab  neg     r13d
0x1800f41ae  mov     [rbp+15B0h+var_1628], ebx
0x1800f41b1  mov     ebx, [rbp+15B0h+arg_78]
0x1800f41b7  lea     rcx, [rbp+15B0h+var_15D0]; void *
0x1800f41bb  sbb     eax, eax
0x1800f41bd  mov     [rbp+15B0h+var_1630], r14d
0x1800f41c1  and     eax, 0FFFFFFFEh
0x1800f41c4  mov     [rbp+15B0h+var_1624], r12d
0x1800f41c8  add     eax, 3
0x1800f41cb  mov     [rbp+15B0h+var_1610], r15
0x1800f41cf  mov     [rbp+15B0h+var_162C], eax
0x1800f41d2  xor     edx, edx; Val
0x1800f41d4  lea     rax, [rbp+15B0h+Buffer]
0x1800f41db  mov     [rbp+15B0h+var_1600], r14
0x1800f41df  mov     [rbp+15B0h+var_1620], rax
0x1800f41e3  lea     rax, [rbp+15B0h+Source]
0x1800f41e7  mov     [rbp+15B0h+var_1618], rax
0x1800f41eb  lea     rax, [rbp+15B0h+var_1090]
0x1800f41f2  mov     [rbp+15B0h+var_1608], rax
0x1800f41f6  lea     rax, [rbp+15B0h+var_12A0]
0x1800f41fd  mov     [rbp+15B0h+var_15F8], rax
0x1800f4201  mov     rax, [rbp+15B0h+arg_40]
0x1800f4208  mov     [rbp+15B0h+var_15F0], rax
0x1800f420c  mov     eax, [rbp+15B0h+arg_70]
0x1800f4212  mov     [rbp+15B0h+var_15E8], eax
0x1800f4215  mov     eax, [rbp+15B0h+arg_58]
0x1800f421b  mov     [rbp+15B0h+var_15E0], eax
0x1800f421e  mov     eax, [rbp+15B0h+arg_80]
0x1800f4224  mov     [rbp+15B0h+var_15D8], eax
0x1800f4227  xor     eax, eax
0x1800f4229  mov     [rbp+15B0h+var_15E4], ebx
0x1800f422c  mov     [rbp+15B0h+var_15DC], esi
0x1800f422f  mov     [rbp+15B0h+var_15D4], eax
0x1800f4232  lea     r8d, [rax+48h]; Size
0x1800f4236  mov     [rbp+15B0h+var_15B4], eax
0x1800f4239  mov     [rbp+15B0h+var_158C], eax
0x1800f423c  call    memset_0
0x1800f4241  cmp     [rbp+15B0h+var_162C], 3
0x1800f4245  mov     [rbp+15B0h+var_1588], r14
0x1800f4249  mov     [rbp+15B0h+var_1580], 0FFFFFFFFFFFFFFFFh
0x1800f4251  jnz     short loc_1800F42BD
0x1800f4253  lea     rcx, ?FEATURE_DOWNLOAD_PROMPT_META_CONTROL@FCK@@3VCFeatureControlKey@@A; this
0x1800f425a  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800f425f  mov     esi, 1
0x1800f4264  cmp     eax, esi
0x1800f4266  jz      short loc_1800F42BD
0x1800f4268  test    sil, bl
0x1800f426b  jz      short loc_1800F428B
0x1800f426d  mov     ecx, 20000002h
0x1800f4272  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800f4279  nop     dword ptr [rax+rax+00h]
0x1800f427e  test    al, al
0x1800f4280  jnz     short loc_1800F4297
0x1800f4282  mov     [rbp+15B0h+var_162C], 2
0x1800f4289  jmp     short loc_1800F4297
0x1800f428b  mov     eax, [rbp+15B0h+var_162C]
0x1800f428e  test    bl, 2
0x1800f4291  cmovnz  eax, esi
0x1800f4294  mov     [rbp+15B0h+var_162C], eax
0x1800f4297  test    r15, r15
0x1800f429a  jz      short loc_1800F42BD
0x1800f429c  lea     rdx, aHtafile; "htafile"
0x1800f42a3  mov     rcx, r15; pszStr1
0x1800f42a6  call    cs:__imp_StrCmpICW
0x1800f42ad  nop     dword ptr [rax+rax+00h]
0x1800f42b2  mov     edx, [rbp+15B0h+var_162C]
0x1800f42b5  test    eax, eax
0x1800f42b7  cmovz   edx, esi; unsigned int
0x1800f42ba  mov     [rbp+15B0h+var_162C], edx
0x1800f42bd  mov     r9, [rsp+16B0h+var_1648]; unsigned int *
0x1800f42c2  lea     r8, [rbp+15B0h+var_1630]; struct SAFEOPENDLGPARAM *
0x1800f42c6  mov     rcx, [rsp+16B0h+var_1640]; HWND
0x1800f42cb  mov     [rsp+16B0h+var_1690], rdi; unsigned __int16 *
0x1800f42d0  call    ?ShowSafeOpenDialog@CDownloadUtilities@@SAIPEAUHWND__@@IPEAUSAFEOPENDLGPARAM@@PEAIPEBG@Z; CDownloadUtilities::ShowSafeOpenDialog(HWND__ *,uint,SAFEOPENDLGPARAM *,uint *,ushort const *)
0x1800f42d5  mov     rcx, [rsp+16B0h+bstrString]; bstrString
0x1800f42da  mov     ebx, eax
0x1800f42dc  call    cs:__imp_SysFreeString
0x1800f42e3  nop     dword ptr [rax+rax+00h]
0x1800f42e8  mov     eax, ebx
0x1800f42ea  mov     rcx, [rbp+15B0h+var_40]
0x1800f42f1  xor     rcx, rsp; StackCookie
0x1800f42f4  call    __security_check_cookie
0x1800f42f9  mov     rbx, [rsp+16B0h+arg_8]
0x1800f4301  add     rsp, 1680h
0x1800f4308  pop     r15
0x1800f430a  pop     r14
0x1800f430c  pop     r13
0x1800f430e  pop     r12
0x1800f4310  pop     rdi
0x1800f4311  pop     rsi
0x1800f4312  pop     rbp
0x1800f4313  retn
  ... truncated ...
```
