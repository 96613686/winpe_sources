# PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x180031afc`
- end: `0x1800320a2`
- name: `?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1446`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031ab0`

## callees

- `0x180001b14`
- `0x180001c10`
- `0x18000300c`
- `0x1800090e0`
- `0x18000918c`
- `0x180009fac`
- `0x18000fc30`
- `0x18000fcac`
- `0x1800112a4`
- `0x1800126bc`
- `0x180026454`
- `0x180031afc`
- `0x1800320a8`
- `0x180032c64`
- `0x1800358a0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180031cdd`
- `msvcrt!_wcsnicmp` at `0x180031cdd`
- `msvcrt!_wcsicmp` at `0x180031e84`
- `msvcrt!_wcsicmp` at `0x180031e84`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031c63`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031cf2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031d58`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031f6a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031c63`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031cf2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031d58`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031f6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031d0a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031d70`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031f4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031d0a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031d70`
- `msvcrt!??3@YAXPEAX@Z` at `0x180031f4a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180031c03`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180031fb0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180031c03`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180031fb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031fd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031fd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031b71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031b71`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031d94`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031d94`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180031e60`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180031e60`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180031e29`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180031e29`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions(__int64 a1, wchar_t *a2)
{
  __int64 v4; // rbx
  void *v5; // rdi
  unsigned int v6; // eax
  DWORD v7; // r15d
  DWORD i; // edx
  BYTE *lpData; // rsi
  const char *v10; // r9
  unsigned int v11; // eax
  _WORD *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rbx
  __int64 v15; // rdi
  const unsigned __int16 *v16; // rdx
  size_t v17; // r8
  const wchar_t *v18; // rcx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  unsigned __int16 **v22; // rax
  const WCHAR *v23; // rcx
  DWORD FileAttributesW; // eax
  __int64 v25; // r8
  const wchar_t *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  const WCHAR *v29; // rcx
  LPWSTR FileNameW; // rbx
  const WCHAR *v31; // rcx
  HRESULT Extension; // eax
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  wchar_t **v36; // rax
  _QWORD *v37; // rcx
  unsigned int v38; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *v46; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR ppszExt; // [rsp+58h] [rbp-A8h] BYREF
  void *v48; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String2[3]; // [rsp+68h] [rbp-98h] BYREF
  void *v50; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v53; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v54[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v55; // [rsp+C8h] [rbp-38h]
  _BYTE v56[16]; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v57; // [rsp+E0h] [rbp-20h]
  int v58; // [rsp+E8h] [rbp-18h]
  int v59; // [rsp+ECh] [rbp-14h]
  WCHAR ValueName[16]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  String2[2] = a2;
  v4 = PackageCollector::s_registryCache;
  v5 = qword_18004A3C0;
  if ( (void *)PackageCollector::s_registryCache == qword_18004A3C0 )
  {
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\PackageLocations", 0, 0x20019u, &hKey);
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        (const char *)v6,
        phkResult);
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      cchValueName = 15;
      cbData = 0;
      v38 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, &cbData);
      if ( v38 == 259 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return std::vector<std::wstring>::_Tidy(a2);
      }
      if ( v38 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v38,
          phkResultb);
      if ( cchValueName >= 0x10 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x8000FFFFLL,
          phkResultb);
      lpData = (BYTE *)operator new[](cbData);
      v48 = lpData;
      if ( !lpData )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          v10);
      cchValueName = 15;
      v11 = RegEnumValueW(hKey, v7, ValueName, &cchValueName, 0, 0, lpData, &cbData);
      if ( v11 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v11,
          phkResulta);
      v12 = *(_WORD **)expanded_wstring::expanded_wstring((expanded_wstring *)&v50, (const unsigned __int16 *)lpData);
      v53 = 7;
      v52 = 0;
      LOWORD(String1[0]) = 0;
      if ( *v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
      }
      std::wstring::assign(String1, v12);
      operator delete[](v50);
      v14 = *(_QWORD *)a2;
      v15 = *((_QWORD *)a2 + 1);
      while ( v14 != v15 )
      {
        v55 = 7;
        v54[2] = 0;
        LOWORD(v54[0]) = 0;
        std::wstring::assign(v54);
        v16 = (const unsigned __int16 *)v54;
        if ( v55 >= 8 )
          v16 = v54[0];
        expanded_wstring::expanded_wstring((expanded_wstring *)String2, v16);
        v17 = -1;
        do
          ++v17;
        while ( String2[0][v17] );
        v18 = (const wchar_t *)String1;
        if ( v53 >= 8 )
          v18 = String1[0];
        if ( !_wcsnicmp(v18, String2[0], v17) )
        {
          if ( (unsigned int)dword_1800495B0 > 4 )
          {
            v22 = v54;
            if ( v55 >= 8 )
              v22 = (unsigned __int16 **)v54[0];
            v46 = v22;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v19,
              (unsigned int)&word_1800419DE,
              v20,
              v21,
              (__int64)&v46);
          }
          operator delete[](String2[0]);
          if ( v55 >= 8 )
            operator delete(v54[0]);
          LOWORD(v54[0]) = 0;
          goto LABEL_57;
        }
        operator delete[](String2[0]);
        if ( v55 >= 8 )
          operator delete(v54[0]);
        v14 += 32;
      }
      v23 = (const WCHAR *)String1;
      if ( v53 >= 8 )
        v23 = String1[0];
      FileAttributesW = GetFileAttributesW(v23);
      if ( FileAttributesW == -1 )
      {
        if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          v26 = (const wchar_t *)String1;
          if ( v53 >= 8 )
            v26 = String1[0];
          if ( v26 )
          {
            v27 = -1;
            do
              ++v27;
            while ( v26[v27] );
            v28 = (unsigned int)(2 * v27 + 2);
          }
          else
          {
            v26 = L"NULL";
            v28 = 10;
          }
          v57 = v26;
          v58 = v28;
          v59 = 0;
          McGenEventWrite_EventWriteTransfer(v28, ProvisioningSearchPathNotExist, v25, 2, v56);
        }
        goto LABEL_57;
      }
      if ( (FileAttributesW & 0x10) != 0 )
        goto LABEL_54;
      v29 = (const WCHAR *)String1;
      if ( v53 >= 8 )
        v29 = String1[0];
      FileNameW = PathFindFileNameW(v29);
      if ( FileNameW )
        break;
LABEL_57:
      if ( v53 >= 8 )
        operator delete(String1[0]);
      LOWORD(String1[0]) = 0;
      v52 = 0;
      v53 = 7;
      operator delete[](lpData);
      ++v7;
    }
    ppszExt = 0;
    v31 = (const WCHAR *)String1;
    if ( v53 >= 8 )
      v31 = String1[0];
    Extension = PathCchFindExtension(v31, v52 + 1, &ppszExt);
    if ( Extension < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        (const char *)(unsigned int)Extension,
        phkResulta);
    if ( _wcsicmp(ppszExt, L".ppkg") )
    {
      if ( (unsigned int)dword_1800495B0 > 2 )
      {
        v46 = FileNameW;
        v36 = String1;
        if ( v53 >= 8 )
          v36 = (wchar_t **)String1[0];
        v48 = v36;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v33,
          (unsigned int)&dword_1800419AC,
          v34,
          v35,
          (__int64)&v48,
          (__int64)&v46);
      }
      goto LABEL_57;
    }
LABEL_54:
    v37 = qword_18004A3C0;
    if ( qword_18004A3C0 == (void *)qword_18004A3C8 )
    {
      std::vector<std::wstring>::_Reserve(&PackageCollector::s_registryCache);
      v37 = qword_18004A3C0;
    }
    v37[3] = 7;
    v37[2] = 0;
    *(_WORD *)v37 = 0;
    std::wstring::assign(v37);
    qword_18004A3C0 = (char *)qword_18004A3C0 + 32;
    PackageCollector::AddSearchPath(a1, (char *)qword_18004A3C0 - 32);
    goto LABEL_57;
  }
  do
  {
    PackageCollector::AddSearchPath(a1, v4);
    v4 += 32;
  }
  while ( (void *)v4 != v5 );
  return std::vector<std::wstring>::_Tidy(a2);
}

```

## disassembly

```asm
0x180031afc  mov     [rsp-8+arg_10], rbx
0x180031b01  push    rbp
0x180031b02  push    rsi
0x180031b03  push    rdi
0x180031b04  push    r12
0x180031b06  push    r13
0x180031b08  push    r14
0x180031b0a  push    r15
0x180031b0c  lea     rbp, [rsp-20h]
0x180031b11  sub     rsp, 120h
0x180031b18  mov     rax, cs:__security_cookie
0x180031b1f  xor     rax, rsp
0x180031b22  mov     [rbp+50h+var_40], rax
0x180031b26  mov     r14, rdx
0x180031b29  mov     r12, rcx
0x180031b2c  mov     [rsp+150h+var_D8], rdx
0x180031b31  mov     rbx, cs:?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x180031b38  mov     rdi, cs:qword_18004A3C0
0x180031b3f  cmp     rbx, rdi
0x180031b42  jnz     loc_180032013
0x180031b48  xor     r13d, r13d
0x180031b4b  mov     [rsp+150h+hKey], r13
0x180031b50  lea     rax, [rsp+150h+hKey]
0x180031b55  mov     [rsp+150h+phkResult], rax; unsigned int
0x180031b5a  mov     r9d, 20019h; samDesired
0x180031b60  xor     r8d, r8d; ulOptions
0x180031b63  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x180031b6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031b71  call    cs:__imp_RegOpenKeyExW
0x180031b78  nop     dword ptr [rax+rax+00h]
0x180031b7d  mov     rcx, [rbp+58h]; this
0x180031b81  test    eax, eax
0x180031b83  jnz     loc_180032039
0x180031b89  mov     r15d, r13d
0x180031b8c  xor     edx, edx
0x180031b8e  jmp     loc_180031F7C
0x180031b93  mov     rcx, [rbp+58h]; this
0x180031b97  test    eax, eax
0x180031b99  jnz     loc_180032024
0x180031b9f  cmp     [rsp+150h+cchValueName], 10h
0x180031ba4  setb    al
0x180031ba7  mov     rcx, [rbp+58h]; this
0x180031bab  test    al, al
0x180031bad  jz      loc_18003208A
0x180031bb3  mov     ecx, [rsp+150h+cbData]; unsigned __int64
0x180031bb7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031bbc  mov     rsi, rax
0x180031bbf  mov     [rsp+150h+var_F0], rax
0x180031bc4  mov     rcx, [rbp+58h]; this
0x180031bc8  test    rax, rax
0x180031bcb  jz      loc_180032078
0x180031bd1  mov     [rsp+150h+cchValueName], 0Fh
0x180031bd9  lea     rax, [rsp+150h+cbData]
0x180031bde  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180031be3  mov     [rsp+150h+lpData], rsi; lpData
0x180031be8  mov     [rsp+150h+lpType], r13; lpType
0x180031bed  mov     [rsp+150h+phkResult], r13; unsigned int
0x180031bf2  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x180031bf7  lea     r8, [rbp+50h+ValueName]; lpValueName
0x180031bfb  mov     edx, r15d; dwIndex
0x180031bfe  mov     rcx, [rsp+150h+hKey]; hKey
0x180031c03  call    cs:__imp_RegEnumValueW
0x180031c0a  nop     dword ptr [rax+rax+00h]
0x180031c0f  mov     rcx, [rbp+58h]; this
0x180031c13  test    eax, eax
0x180031c15  jnz     loc_180032063
0x180031c1b  mov     rdx, rsi; unsigned __int16 *
0x180031c1e  lea     rcx, [rbp+50h+var_D0]; this
0x180031c22  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180031c27  nop
0x180031c28  mov     rdx, [rax]; Src
0x180031c2b  mov     [rbp+50h+var_A8], 7
0x180031c33  mov     [rbp+50h+var_B0], r13
0x180031c37  mov     word ptr [rbp+50h+String1], r13w
0x180031c3c  cmp     [rdx], r13w
0x180031c40  jnz     short loc_180031C47
0x180031c42  mov     r8, r13
0x180031c45  jmp     short loc_180031C55
0x180031c47  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031c4b  inc     r8
0x180031c4e  cmp     [rdx+r8*2], r13w
0x180031c53  jnz     short loc_180031C4B
0x180031c55  lea     rcx, [rbp+50h+String1]; void *
0x180031c59  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180031c5e  nop
0x180031c5f  mov     rcx, [rbp+50h+var_D0]
0x180031c63  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031c6a  nop     dword ptr [rax+rax+00h]
0x180031c6f  mov     rbx, [r14]
0x180031c72  mov     rdi, [r14+8]
0x180031c76  cmp     rbx, rdi
0x180031c79  jz      loc_180031D86
0x180031c7f  mov     [rbp+50h+var_88], 7
0x180031c87  mov     [rbp+50h+var_90], r13
0x180031c8b  mov     word ptr [rbp+50h+var_A0], r13w
0x180031c90  or      r9, 0FFFFFFFFFFFFFFFFh
0x180031c94  xor     r8d, r8d
0x180031c97  mov     rdx, rbx
0x180031c9a  lea     rcx, [rbp+50h+var_A0]; void *
0x180031c9e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180031ca3  nop
0x180031ca4  lea     rdx, [rbp+50h+var_A0]
0x180031ca8  cmp     [rbp+50h+var_88], 8
0x180031cad  cmovnb  rdx, [rbp+50h+var_A0]; unsigned __int16 *
0x180031cb2  lea     rcx, [rsp+150h+String2]; this
0x180031cb7  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180031cbc  mov     rdx, [rsp+150h+String2]; String2
0x180031cc1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031cc5  inc     r8; MaxCount
0x180031cc8  cmp     [rdx+r8*2], r13w
0x180031ccd  jnz     short loc_180031CC5
0x180031ccf  lea     rcx, [rbp+50h+String1]
0x180031cd3  cmp     [rbp+50h+var_A8], 8
0x180031cd8  cmovnb  rcx, [rbp+50h+String1]; String1
0x180031cdd  call    cs:__imp__wcsnicmp
0x180031ce4  nop     dword ptr [rax+rax+00h]
0x180031ce9  test    eax, eax
0x180031ceb  jz      short loc_180031D1F
0x180031ced  mov     rcx, [rsp+150h+String2]
0x180031cf2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031cf9  nop     dword ptr [rax+rax+00h]
0x180031cfe  nop
0x180031cff  cmp     [rbp+50h+var_88], 8
0x180031d04  jb      short loc_180031D16
0x180031d06  mov     rcx, [rbp+50h+var_A0]
0x180031d0a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031d11  nop     dword ptr [rax+rax+00h]
0x180031d16  add     rbx, 20h ; ' '
0x180031d1a  jmp     loc_180031C76
0x180031d1f  mov     eax, cs:dword_1800495B0
0x180031d25  cmp     eax, 4
0x180031d28  jbe     short loc_180031D53
0x180031d2a  lea     rax, [rbp+50h+var_A0]
0x180031d2e  cmp     [rbp+50h+var_88], 8
0x180031d33  cmovnb  rax, [rbp+50h+var_A0]
0x180031d38  mov     [rsp+150h+var_100], rax
0x180031d3d  lea     rax, [rsp+150h+var_100]
0x180031d42  mov     [rsp+150h+phkResult], rax
0x180031d47  lea     rdx, word_1800419DE
0x180031d4e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180031d53  mov     rcx, [rsp+150h+String2]
0x180031d58  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031d5f  nop     dword ptr [rax+rax+00h]
0x180031d64  nop
0x180031d65  cmp     [rbp+50h+var_88], 8
0x180031d6a  jb      short loc_180031D7C
0x180031d6c  mov     rcx, [rbp+50h+var_A0]
0x180031d70  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031d77  nop     dword ptr [rax+rax+00h]
0x180031d7c  mov     word ptr [rbp+50h+var_A0], r13w
0x180031d81  jmp     loc_180031F3F
0x180031d86  lea     rcx, [rbp+50h+String1]
0x180031d8a  cmp     [rbp+50h+var_A8], 8
0x180031d8f  cmovnb  rcx, [rbp+50h+String1]; lpFileName
0x180031d94  call    cs:__imp_GetFileAttributesW
0x180031d9b  nop     dword ptr [rax+rax+00h]
0x180031da0  cmp     eax, 0FFFFFFFFh
0x180031da3  jnz     short loc_180031E13
0x180031da5  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 4
0x180031dac  jz      loc_180031F3F
0x180031db2  lea     rax, [rbp+50h+String1]
0x180031db6  cmp     [rbp+50h+var_A8], 8
0x180031dbb  cmovnb  rax, [rbp+50h+String1]
0x180031dc0  test    rax, rax
0x180031dc3  jz      short loc_180031DDC
0x180031dc5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180031dc9  inc     rcx
0x180031dcc  cmp     [rax+rcx*2], r13w
0x180031dd1  jnz     short loc_180031DC9
0x180031dd3  lea     ecx, ds:2[rcx*2]
0x180031dda  jmp     short loc_180031DE8
0x180031ddc  lea     rax, aNull; "NULL"
0x180031de3  mov     ecx, 0Ah
0x180031de8  mov     [rbp+50h+var_70], rax
0x180031dec  mov     [rbp+50h+var_68], ecx
0x180031def  mov     [rbp+50h+var_64], r13d
0x180031df3  lea     rax, [rbp+50h+var_80]
0x180031df7  mov     [rsp+150h+phkResult], rax
0x180031dfc  mov     r9d, 2
0x180031e02  lea     rdx, ProvisioningSearchPathNotExist
0x180031e09  call    McGenEventWrite_EventWriteTransfer
0x180031e0e  jmp     loc_180031F3F
0x180031e13  test    al, 10h
0x180031e15  jnz     loc_180031EDD
0x180031e1b  lea     rcx, [rbp+50h+String1]
0x180031e1f  cmp     [rbp+50h+var_A8], 8
0x180031e24  cmovnb  rcx, [rbp+50h+String1]; pszPath
0x180031e29  call    cs:__imp_PathFindFileNameW
0x180031e30  nop     dword ptr [rax+rax+00h]
0x180031e35  mov     rbx, rax
0x180031e38  test    rax, rax
0x180031e3b  jz      loc_180031F3F
0x180031e41  mov     [rsp+150h+ppszExt], r13
0x180031e46  mov     rdx, [rbp+50h+var_B0]
0x180031e4a  lea     rcx, [rbp+50h+String1]
0x180031e4e  cmp     [rbp+50h+var_A8], 8
0x180031e53  cmovnb  rcx, [rbp+50h+String1]; pszPath
0x180031e58  inc     rdx; cchPath
0x180031e5b  lea     r8, [rsp+150h+ppszExt]; ppszExt
0x180031e60  call    cs:__imp_PathCchFindExtension
0x180031e67  nop     dword ptr [rax+rax+00h]
0x180031e6c  mov     rcx, [rbp+58h]; this
0x180031e70  test    eax, eax
0x180031e72  js      loc_18003204E
0x180031e78  lea     rdx, aPpkg_0; ".ppkg"
0x180031e7f  mov     rcx, [rsp+150h+ppszExt]; String1
0x180031e84  call    cs:__imp__wcsicmp
0x180031e8b  nop     dword ptr [rax+rax+00h]
0x180031e90  test    eax, eax
0x180031e92  jz      short loc_180031EDD
0x180031e94  mov     eax, cs:dword_1800495B0
0x180031e9a  cmp     eax, 2
0x180031e9d  jbe     loc_180031F3F
0x180031ea3  mov     [rsp+150h+var_100], rbx
0x180031ea8  lea     rax, [rbp+50h+String1]
0x180031eac  cmp     [rbp+50h+var_A8], 8
0x180031eb1  cmovnb  rax, [rbp+50h+String1]
0x180031eb6  mov     [rsp+150h+var_F0], rax
0x180031ebb  lea     rax, [rsp+150h+var_100]
0x180031ec0  mov     [rsp+150h+lpType], rax
0x180031ec5  lea     rax, [rsp+150h+var_F0]
0x180031eca  mov     [rsp+150h+phkResult], rax
0x180031ecf  lea     rdx, dword_1800419AC
0x180031ed6  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180031edb  jmp     short loc_180031F3F
0x180031edd  mov     rcx, cs:qword_18004A3C0
0x180031ee4  cmp     rcx, cs:qword_18004A3C8
0x180031eeb  jnz     short loc_180031F00
0x180031eed  lea     rcx, ?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x180031ef4  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180031ef9  mov     rcx, cs:qword_18004A3C0; void *
0x180031f00  mov     qword ptr [rcx+18h], 7
0x180031f08  mov     [rcx+10h], r13
0x180031f0c  mov     [rcx], r13w
0x180031f10  or      r9, 0FFFFFFFFFFFFFFFFh
0x180031f14  xor     r8d, r8d
0x180031f17  lea     rdx, [rbp+50h+String1]
0x180031f1b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180031f20  mov     rdx, cs:qword_18004A3C0
0x180031f27  add     rdx, 20h ; ' '
0x180031f2b  mov     cs:qword_18004A3C0, rdx
0x180031f32  add     rdx, 0FFFFFFFFFFFFFFE0h
0x180031f36  mov     rcx, r12
0x180031f39  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x180031f3e  nop
0x180031f3f  cmp     [rbp+50h+var_A8], 8
0x180031f44  jb      short loc_180031F56
0x180031f46  mov     rcx, [rbp+50h+String1]
0x180031f4a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180031f51  nop     dword ptr [rax+rax+00h]
0x180031f56  mov     word ptr [rbp+50h+String1], r13w
0x180031f5b  mov     [rbp+50h+var_B0], r13
0x180031f5f  mov     [rbp+50h+var_A8], 7
0x180031f67  mov     rcx, rsi
0x180031f6a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031f71  nop     dword ptr [rax+rax+00h]
0x180031f76  inc     r15d
0x180031f79  mov     edx, r15d; dwIndex
0x180031f7c  lea     rax, [rsp+150h+cbData]
0x180031f81  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180031f86  mov     [rsp+150h+lpData], r13; lpData
0x180031f8b  mov     [rsp+150h+lpType], r13; lpType
0x180031f90  mov     [rsp+150h+phkResult], r13; int
0x180031f95  mov     [rsp+150h+cchValueName], 0Fh
0x180031f9d  mov     [rsp+150h+cbData], r13d
0x180031fa2  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x180031fa7  lea     r8, [rbp+50h+ValueName]; lpValueName
0x180031fab  mov     rcx, [rsp+150h+hKey]; hKey
0x180031fb0  call    cs:__imp_RegEnumValueW
0x180031fb7  nop     dword ptr [rax+rax+00h]
0x180031fbc  cmp     eax, 103h
0x180031fc1  jnz     loc_180031B93
0x180031fc7  mov     rcx, [rsp+150h+hKey]; hKey
0x180031fcc  test    rcx, rcx
0x180031fcf  jz      short loc_180031FDE
0x180031fd1  call    cs:__imp_RegCloseKey
0x180031fd8  nop     dword ptr [rax+rax+00h]
0x180031fdd  nop
0x180031fde  mov     rcx, r14
0x180031fe1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180031fe6  mov     rcx, [rbp+50h+var_40]
0x180031fea  xor     rcx, rsp; StackCookie
0x180031fed  call    __security_check_cookie
0x180031ff2  mov     rbx, [rsp+150h+arg_10]
0x180031ffa  add     rsp, 120h
0x180032001  pop     r15
0x180032003  pop     r14
0x180032005  pop     r13
0x180032007  pop     r12
0x180032009  pop     rdi
0x18003200a  pop     rsi
0x18003200b  pop     rbp
0x18003200c  retn
0x18003200e  cmp     rbx, rdi
0x180032011  jz      short loc_180031FDE
0x180032013  mov     rdx, rbx
0x180032016  mov     rcx, r12
0x180032019  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x18003201e  add     rbx, 20h ; ' '
0x180032022  jmp     short loc_18003200E
  ... truncated ...
```
