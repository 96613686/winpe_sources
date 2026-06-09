# PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x180039828`
- end: `0x180039d77`
- name: `?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1359`
- prototype: `__int64 __fastcall(__int64, wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800141f0`

## callees

- `0x1800011ac`
- `0x180001a14`
- `0x180002e70`
- `0x18000af20`
- `0x18000b030`
- `0x18000fcc4`
- `0x180010ad8`
- `0x180021c5c`
- `0x180021cf4`
- `0x180021d14`
- `0x180022d84`
- `0x18002f9bc`
- `0x180039828`
- `0x180039d80`
- `0x180043750`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800399f7`
- `msvcrt!_wcsnicmp` at `0x1800399f7`
- `msvcrt!_wcsicmp` at `0x180039b78`
- `msvcrt!_wcsicmp` at `0x180039b78`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a18`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039c38`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a18`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a7c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039c38`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039983`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039a06`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039a6a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039c52`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039983`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039a06`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039a6a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180039c52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003989d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003989d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180039929`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180039c92`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180039929`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180039c92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039cad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039cad`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039a9a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039a9a`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180039b5a`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180039b5a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180039b29`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180039b29`

## pseudocode

```c
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
  int v19; // r9d
  unsigned __int16 **v20; // rax
  const WCHAR *v21; // rcx
  DWORD FileAttributesW; // eax
  __int64 v23; // r8
  const wchar_t *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  const WCHAR *v27; // rcx
  LPWSTR FileNameW; // rbx
  const WCHAR *v29; // rcx
  HRESULT Extension; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  wchar_t **v34; // rax
  _QWORD *v35; // rcx
  unsigned int v36; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *v44; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR ppszExt; // [rsp+58h] [rbp-A8h] BYREF
  void *v46; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String2[3]; // [rsp+68h] [rbp-98h] BYREF
  void *v48; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v51; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v52[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v53; // [rsp+C8h] [rbp-38h]
  _BYTE v54[16]; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v55; // [rsp+E0h] [rbp-20h]
  int v56; // [rsp+E8h] [rbp-18h]
  int v57; // [rsp+ECh] [rbp-14h]
  WCHAR ValueName[16]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  String2[2] = a2;
  v4 = PackageCollector::s_registryCache;
  v5 = qword_18005ADD8;
  if ( (void *)PackageCollector::s_registryCache == qword_18005ADD8 )
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
      v36 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, &cbData);
      if ( v36 == 259 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return std::vector<std::wstring>::_Tidy(a2);
      }
      if ( v36 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v36,
          phkResultb);
      if ( cchValueName >= 0x10 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x8000FFFFLL,
          phkResultb);
      lpData = (BYTE *)operator new[](cbData);
      v46 = lpData;
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
      v12 = *(_WORD **)expanded_wstring::expanded_wstring((expanded_wstring *)&v48, (const unsigned __int16 *)lpData);
      v51 = 7;
      v50 = 0;
      LOWORD(String1[0]) = 0;
      if ( *v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
      }
      std::wstring::assign(String1, v12);
      operator delete[](v48);
      v14 = *(_QWORD *)a2;
      v15 = *((_QWORD *)a2 + 1);
      while ( v14 != v15 )
      {
        v53 = 7;
        v52[2] = 0;
        LOWORD(v52[0]) = 0;
        std::wstring::assign(v52);
        v16 = (const unsigned __int16 *)v52;
        if ( v53 >= 8 )
          v16 = v52[0];
        expanded_wstring::expanded_wstring((expanded_wstring *)String2, v16);
        v17 = -1;
        do
          ++v17;
        while ( String2[0][v17] );
        v18 = (const wchar_t *)String1;
        if ( v51 >= 8 )
          v18 = String1[0];
        if ( !_wcsnicmp(v18, String2[0], v17) )
        {
          if ( (unsigned int)dword_18005A000 > 4 )
          {
            v20 = v52;
            if ( v53 >= 8 )
              v20 = (unsigned __int16 **)v52[0];
            v44 = v20;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (unsigned int)&dword_18005A000,
              (unsigned int)&byte_1800502D7,
              0,
              v19,
              (__int64)&v44);
          }
          operator delete[](String2[0]);
          if ( v53 >= 8 )
            operator delete(v52[0]);
          LOWORD(v52[0]) = 0;
          goto LABEL_57;
        }
        operator delete[](String2[0]);
        if ( v53 >= 8 )
          operator delete(v52[0]);
        v14 += 32;
      }
      v21 = (const WCHAR *)String1;
      if ( v51 >= 8 )
        v21 = String1[0];
      FileAttributesW = GetFileAttributesW(v21);
      if ( FileAttributesW == -1 )
      {
        if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          v24 = (const wchar_t *)String1;
          if ( v51 >= 8 )
            v24 = String1[0];
          if ( v24 )
          {
            v25 = -1;
            do
              ++v25;
            while ( v24[v25] );
            v26 = (unsigned int)(2 * v25 + 2);
          }
          else
          {
            v24 = L"NULL";
            v26 = 10;
          }
          v55 = v24;
          v56 = v26;
          v57 = 0;
          McGenEventWrite_EventWriteTransfer(v26, "(", v23, 2, v54);
        }
        goto LABEL_57;
      }
      if ( (FileAttributesW & 0x10) != 0 )
        goto LABEL_54;
      v27 = (const WCHAR *)String1;
      if ( v51 >= 8 )
        v27 = String1[0];
      FileNameW = PathFindFileNameW(v27);
      if ( FileNameW )
        break;
LABEL_57:
      if ( v51 >= 8 )
        operator delete(String1[0]);
      LOWORD(String1[0]) = 0;
      v50 = 0;
      v51 = 7;
      operator delete[](lpData);
      ++v7;
    }
    ppszExt = 0;
    v29 = (const WCHAR *)String1;
    if ( v51 >= 8 )
      v29 = String1[0];
    Extension = PathCchFindExtension(v29, v50 + 1, &ppszExt);
    if ( Extension < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        (const char *)(unsigned int)Extension,
        phkResulta);
    if ( _wcsicmp(ppszExt, L".ppkg") )
    {
      if ( (unsigned int)dword_18005A000 > 2 )
      {
        v44 = FileNameW;
        v34 = String1;
        if ( v51 >= 8 )
          v34 = (wchar_t **)String1[0];
        v46 = v34;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v31,
          (unsigned int)&dword_180050284,
          v32,
          v33,
          (__int64)&v46,
          (__int64)&v44);
      }
      goto LABEL_57;
    }
LABEL_54:
    v35 = qword_18005ADD8;
    if ( qword_18005ADD8 == (void *)qword_18005ADE0 )
    {
      std::vector<std::wstring>::_Reserve(&PackageCollector::s_registryCache);
      v35 = qword_18005ADD8;
    }
    v35[3] = 7;
    v35[2] = 0;
    *(_WORD *)v35 = 0;
    std::wstring::assign(v35);
    qword_18005ADD8 = (char *)qword_18005ADD8 + 32;
    PackageCollector::AddSearchPath(a1, (char *)qword_18005ADD8 - 32);
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
0x180039828  mov     [rsp-8+arg_10], rbx
0x18003982d  push    rbp
0x18003982e  push    rsi
0x18003982f  push    rdi
0x180039830  push    r12
0x180039832  push    r13
0x180039834  push    r14
0x180039836  push    r15
0x180039838  lea     rbp, [rsp-20h]
0x18003983d  sub     rsp, 120h
0x180039844  mov     rax, cs:__security_cookie
0x18003984b  xor     rax, rsp
0x18003984e  mov     [rbp+50h+var_40], rax
0x180039852  mov     r14, rdx
0x180039855  mov     r12, rcx
0x180039858  mov     [rsp+150h+var_D8], rdx
0x18003985d  mov     rbx, cs:?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x180039864  mov     rdi, cs:qword_18005ADD8
0x18003986b  cmp     rbx, rdi
0x18003986e  jnz     loc_180039CE8
0x180039874  xor     r13d, r13d
0x180039877  mov     [rsp+150h+hKey], r13
0x18003987c  lea     rax, [rsp+150h+hKey]
0x180039881  mov     [rsp+150h+phkResult], rax; unsigned int
0x180039886  mov     r9d, 20019h; samDesired
0x18003988c  xor     r8d, r8d; ulOptions
0x18003988f  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x180039896  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003989d  call    cs:__imp_RegOpenKeyExW
0x1800398a3  mov     rcx, [rbp+58h]; this
0x1800398a7  test    eax, eax
0x1800398a9  jnz     loc_180039D0E
0x1800398af  mov     r15d, r13d
0x1800398b2  xor     edx, edx
0x1800398b4  jmp     loc_180039C5E
0x1800398b9  mov     rcx, [rbp+58h]; this
0x1800398bd  test    eax, eax
0x1800398bf  jnz     loc_180039CF9
0x1800398c5  cmp     [rsp+150h+cchValueName], 10h
0x1800398ca  setb    al
0x1800398cd  mov     rcx, [rbp+58h]; this
0x1800398d1  test    al, al
0x1800398d3  jz      loc_180039D5F
0x1800398d9  mov     ecx, [rsp+150h+cbData]; unsigned __int64
0x1800398dd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800398e2  mov     rsi, rax
0x1800398e5  mov     [rsp+150h+var_F0], rax
0x1800398ea  mov     rcx, [rbp+58h]; this
0x1800398ee  test    rax, rax
0x1800398f1  jz      loc_180039D4D
0x1800398f7  mov     [rsp+150h+cchValueName], 0Fh
0x1800398ff  lea     rax, [rsp+150h+cbData]
0x180039904  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180039909  mov     [rsp+150h+lpData], rsi; lpData
0x18003990e  mov     [rsp+150h+lpType], r13; lpType
0x180039913  mov     [rsp+150h+phkResult], r13; unsigned int
0x180039918  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x18003991d  lea     r8, [rbp+50h+ValueName]; lpValueName
0x180039921  mov     edx, r15d; dwIndex
0x180039924  mov     rcx, [rsp+150h+hKey]; hKey
0x180039929  call    cs:__imp_RegEnumValueW
0x18003992f  mov     rcx, [rbp+58h]; this
0x180039933  test    eax, eax
0x180039935  jnz     loc_180039D38
0x18003993b  mov     rdx, rsi; unsigned __int16 *
0x18003993e  lea     rcx, [rbp+50h+var_D0]; this
0x180039942  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180039947  nop
0x180039948  mov     rdx, [rax]; Src
0x18003994b  mov     [rbp+50h+var_A8], 7
0x180039953  mov     [rbp+50h+var_B0], r13
0x180039957  mov     word ptr [rbp+50h+String1], r13w
0x18003995c  cmp     [rdx], r13w
0x180039960  jnz     short loc_180039967
0x180039962  mov     r8, r13
0x180039965  jmp     short loc_180039975
0x180039967  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003996b  inc     r8
0x18003996e  cmp     [rdx+r8*2], r13w
0x180039973  jnz     short loc_18003996B
0x180039975  lea     rcx, [rbp+50h+String1]; void *
0x180039979  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003997e  nop
0x18003997f  mov     rcx, [rbp+50h+var_D0]
0x180039983  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180039989  mov     rbx, [r14]
0x18003998c  mov     rdi, [r14+8]
0x180039990  cmp     rbx, rdi
0x180039993  jz      loc_180039A8C
0x180039999  mov     [rbp+50h+var_88], 7
0x1800399a1  mov     [rbp+50h+var_90], r13
0x1800399a5  mov     word ptr [rbp+50h+var_A0], r13w
0x1800399aa  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800399ae  xor     r8d, r8d
0x1800399b1  mov     rdx, rbx
0x1800399b4  lea     rcx, [rbp+50h+var_A0]; void *
0x1800399b8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800399bd  nop
0x1800399be  lea     rdx, [rbp+50h+var_A0]
0x1800399c2  cmp     [rbp+50h+var_88], 8
0x1800399c7  cmovnb  rdx, [rbp+50h+var_A0]; unsigned __int16 *
0x1800399cc  lea     rcx, [rsp+150h+String2]; this
0x1800399d1  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x1800399d6  mov     rdx, [rsp+150h+String2]; String2
0x1800399db  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800399df  inc     r8; MaxCount
0x1800399e2  cmp     [rdx+r8*2], r13w
0x1800399e7  jnz     short loc_1800399DF
0x1800399e9  lea     rcx, [rbp+50h+String1]
0x1800399ed  cmp     [rbp+50h+var_A8], 8
0x1800399f2  cmovnb  rcx, [rbp+50h+String1]; String1
0x1800399f7  call    cs:__imp__wcsnicmp
0x1800399fd  test    eax, eax
0x1800399ff  jz      short loc_180039A27
0x180039a01  mov     rcx, [rsp+150h+String2]
0x180039a06  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180039a0c  nop
0x180039a0d  cmp     [rbp+50h+var_88], 8
0x180039a12  jb      short loc_180039A1E
0x180039a14  mov     rcx, [rbp+50h+var_A0]
0x180039a18  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039a1e  add     rbx, 20h ; ' '
0x180039a22  jmp     loc_180039990
0x180039a27  mov     eax, cs:dword_18005A000
0x180039a2d  cmp     eax, 4
0x180039a30  jbe     short loc_180039A65
0x180039a32  lea     rax, [rbp+50h+var_A0]
0x180039a36  cmp     [rbp+50h+var_88], 8
0x180039a3b  cmovnb  rax, [rbp+50h+var_A0]
0x180039a40  mov     [rsp+150h+var_100], rax
0x180039a45  lea     rax, [rsp+150h+var_100]
0x180039a4a  mov     [rsp+150h+phkResult], rax
0x180039a4f  xor     r8d, r8d
0x180039a52  lea     rdx, byte_1800502D7
0x180039a59  lea     rcx, dword_18005A000
0x180039a60  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180039a65  mov     rcx, [rsp+150h+String2]
0x180039a6a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180039a70  nop
0x180039a71  cmp     [rbp+50h+var_88], 8
0x180039a76  jb      short loc_180039A82
0x180039a78  mov     rcx, [rbp+50h+var_A0]
0x180039a7c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039a82  mov     word ptr [rbp+50h+var_A0], r13w
0x180039a87  jmp     loc_180039C2D
0x180039a8c  lea     rcx, [rbp+50h+String1]
0x180039a90  cmp     [rbp+50h+var_A8], 8
0x180039a95  cmovnb  rcx, [rbp+50h+String1]; lpFileName
0x180039a9a  call    cs:__imp_GetFileAttributesW
0x180039aa0  cmp     eax, 0FFFFFFFFh
0x180039aa3  jnz     short loc_180039B13
0x180039aa5  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 4
0x180039aac  jz      loc_180039C2D
0x180039ab2  lea     rax, [rbp+50h+String1]
0x180039ab6  cmp     [rbp+50h+var_A8], 8
0x180039abb  cmovnb  rax, [rbp+50h+String1]
0x180039ac0  test    rax, rax
0x180039ac3  jz      short loc_180039ADC
0x180039ac5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180039ac9  inc     rcx
0x180039acc  cmp     [rax+rcx*2], r13w
0x180039ad1  jnz     short loc_180039AC9
0x180039ad3  lea     ecx, ds:2[rcx*2]
0x180039ada  jmp     short loc_180039AE8
0x180039adc  lea     rax, aNull; "NULL"
0x180039ae3  mov     ecx, 0Ah
0x180039ae8  mov     [rbp+50h+var_70], rax
0x180039aec  mov     [rbp+50h+var_68], ecx
0x180039aef  mov     [rbp+50h+var_64], r13d
0x180039af3  lea     rax, [rbp+50h+var_80]
0x180039af7  mov     [rsp+150h+phkResult], rax
0x180039afc  mov     r9d, 2
0x180039b02  lea     rdx, ProvisioningSearchPathNotExist; "("
0x180039b09  call    McGenEventWrite_EventWriteTransfer
0x180039b0e  jmp     loc_180039C2D
0x180039b13  test    al, 10h
0x180039b15  jnz     loc_180039BCB
0x180039b1b  lea     rcx, [rbp+50h+String1]
0x180039b1f  cmp     [rbp+50h+var_A8], 8
0x180039b24  cmovnb  rcx, [rbp+50h+String1]; pszPath
0x180039b29  call    cs:__imp_PathFindFileNameW
0x180039b2f  mov     rbx, rax
0x180039b32  test    rax, rax
0x180039b35  jz      loc_180039C2D
0x180039b3b  mov     [rsp+150h+ppszExt], r13
0x180039b40  mov     rdx, [rbp+50h+var_B0]
0x180039b44  lea     rcx, [rbp+50h+String1]
0x180039b48  cmp     [rbp+50h+var_A8], 8
0x180039b4d  cmovnb  rcx, [rbp+50h+String1]; pszPath
0x180039b52  inc     rdx; cchPath
0x180039b55  lea     r8, [rsp+150h+ppszExt]; ppszExt
0x180039b5a  call    cs:__imp_PathCchFindExtension
0x180039b60  mov     rcx, [rbp+58h]; this
0x180039b64  test    eax, eax
0x180039b66  js      loc_180039D23
0x180039b6c  lea     rdx, aPpkg_0; ".ppkg"
0x180039b73  mov     rcx, [rsp+150h+ppszExt]; String1
0x180039b78  call    cs:__imp__wcsicmp
0x180039b7e  test    eax, eax
0x180039b80  jz      short loc_180039BCB
0x180039b82  mov     eax, cs:dword_18005A000
0x180039b88  cmp     eax, 2
0x180039b8b  jbe     loc_180039C2D
0x180039b91  mov     [rsp+150h+var_100], rbx
0x180039b96  lea     rax, [rbp+50h+String1]
0x180039b9a  cmp     [rbp+50h+var_A8], 8
0x180039b9f  cmovnb  rax, [rbp+50h+String1]
0x180039ba4  mov     [rsp+150h+var_F0], rax
0x180039ba9  lea     rax, [rsp+150h+var_100]
0x180039bae  mov     [rsp+150h+lpType], rax
0x180039bb3  lea     rax, [rsp+150h+var_F0]
0x180039bb8  mov     [rsp+150h+phkResult], rax
0x180039bbd  lea     rdx, dword_180050284
0x180039bc4  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180039bc9  jmp     short loc_180039C2D
0x180039bcb  mov     rcx, cs:qword_18005ADD8
0x180039bd2  cmp     rcx, cs:qword_18005ADE0
0x180039bd9  jnz     short loc_180039BEE
0x180039bdb  lea     rcx, ?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x180039be2  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x180039be7  mov     rcx, cs:qword_18005ADD8; void *
0x180039bee  mov     qword ptr [rcx+18h], 7
0x180039bf6  mov     [rcx+10h], r13
0x180039bfa  mov     [rcx], r13w
0x180039bfe  or      r9, 0FFFFFFFFFFFFFFFFh
0x180039c02  xor     r8d, r8d
0x180039c05  lea     rdx, [rbp+50h+String1]
0x180039c09  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180039c0e  mov     rdx, cs:qword_18005ADD8
0x180039c15  add     rdx, 20h ; ' '
0x180039c19  mov     cs:qword_18005ADD8, rdx
0x180039c20  add     rdx, 0FFFFFFFFFFFFFFE0h
0x180039c24  mov     rcx, r12
0x180039c27  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x180039c2c  nop
0x180039c2d  cmp     [rbp+50h+var_A8], 8
0x180039c32  jb      short loc_180039C3E
0x180039c34  mov     rcx, [rbp+50h+String1]
0x180039c38  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039c3e  mov     word ptr [rbp+50h+String1], r13w
0x180039c43  mov     [rbp+50h+var_B0], r13
0x180039c47  mov     [rbp+50h+var_A8], 7
0x180039c4f  mov     rcx, rsi
0x180039c52  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180039c58  inc     r15d
0x180039c5b  mov     edx, r15d; dwIndex
0x180039c5e  lea     rax, [rsp+150h+cbData]
0x180039c63  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180039c68  mov     [rsp+150h+lpData], r13; lpData
0x180039c6d  mov     [rsp+150h+lpType], r13; lpType
0x180039c72  mov     [rsp+150h+phkResult], r13; int
0x180039c77  mov     [rsp+150h+cchValueName], 0Fh
0x180039c7f  mov     [rsp+150h+cbData], r13d
0x180039c84  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x180039c89  lea     r8, [rbp+50h+ValueName]; lpValueName
0x180039c8d  mov     rcx, [rsp+150h+hKey]; hKey
0x180039c92  call    cs:__imp_RegEnumValueW
0x180039c98  cmp     eax, 103h
0x180039c9d  jnz     loc_1800398B9
0x180039ca3  mov     rcx, [rsp+150h+hKey]; hKey
0x180039ca8  test    rcx, rcx
0x180039cab  jz      short loc_180039CB4
0x180039cad  call    cs:__imp_RegCloseKey
0x180039cb3  nop
0x180039cb4  mov     rcx, r14
0x180039cb7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180039cbc  mov     rcx, [rbp+50h+var_40]
0x180039cc0  xor     rcx, rsp; StackCookie
0x180039cc3  call    __security_check_cookie
0x180039cc8  mov     rbx, [rsp+150h+arg_10]
0x180039cd0  add     rsp, 120h
0x180039cd7  pop     r15
0x180039cd9  pop     r14
0x180039cdb  pop     r13
0x180039cdd  pop     r12
0x180039cdf  pop     rdi
0x180039ce0  pop     rsi
0x180039ce1  pop     rbp
0x180039ce2  retn
0x180039ce3  cmp     rbx, rdi
0x180039ce6  jz      short loc_180039CB4
0x180039ce8  mov     rdx, rbx
0x180039ceb  mov     rcx, r12
0x180039cee  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x180039cf3  add     rbx, 20h ; ' '
0x180039cf7  jmp     short loc_180039CE3
0x180039cf9  mov     r9d, eax; char *
0x180039cfc  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x180039d03  mov     edx, 51h ; 'Q'; void *
0x180039d08  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180039d0e  mov     r9d, eax; char *
0x180039d11  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x180039d18  mov     edx, 3Ch ; '<'; void *
0x180039d1d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180039d23  mov     r9d, eax; char *
0x180039d26  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x180039d2d  mov     edx, 93h; void *
0x180039d32  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039d38  mov     r9d, eax; char *
0x180039d3b  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\packageco"...
  ... truncated ...
```
