# PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x180028f74`
- end: `0x180029478`
- name: `?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1284`
- prototype: `__int64 __fastcall(_QWORD *, wchar_t *, __int64, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028f28`

## callees

- `0x1800017ec`
- `0x180002300`
- `0x180003e6c`
- `0x18000de00`
- `0x18001b388`
- `0x18001b3a8`
- `0x18002066c`
- `0x18002072c`
- `0x180020fe0`
- `0x1800210f0`
- `0x180022784`
- `0x1800245fc`
- `0x180028f74`
- `0x180029480`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002915f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800291be`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029339`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002915f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800291be`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029339`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800290cd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002914d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800291ac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029353`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800290cd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002914d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800291ac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029353`
- `msvcrt!_wcsicmp` at `0x180029278`
- `msvcrt!_wcsicmp` at `0x180029278`
- `msvcrt!_wcsnicmp` at `0x18002913f`
- `msvcrt!_wcsnicmp` at `0x18002913f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800291dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800291dc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180029073`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180029393`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180029073`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180029393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800293ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800293ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028fe8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028fe8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180029229`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180029229`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18002925a`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18002925a`

## pseudocode

```c
__int64 __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions(_QWORD *a1, wchar_t *a2, __int64 a3, int a4)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rdi
  unsigned int v8; // eax
  DWORD v9; // r15d
  DWORD i; // edx
  BYTE *lpData; // rdi
  const char *v12; // r9
  unsigned int v13; // eax
  _WORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rsi
  const unsigned __int16 *v18; // rdx
  size_t v19; // r8
  const wchar_t *v20; // rcx
  int v21; // r9d
  unsigned __int16 **v22; // rax
  const WCHAR *v23; // rcx
  DWORD FileAttributesW; // eax
  __int64 v25; // rcx
  wchar_t **v26; // r8
  const WCHAR *v27; // rcx
  LPWSTR FileNameW; // rbx
  const WCHAR *v29; // rcx
  HRESULT Extension; // eax
  int v31; // r8d
  int v32; // r9d
  wchar_t **v33; // rax
  _QWORD *v34; // rcx
  __int64 v35; // r8
  int v36; // r9d
  unsigned int v37; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-B9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-B9h]
  unsigned int phkResultb; // [rsp+20h] [rbp-B9h]
  DWORD cchValueName; // [rsp+40h] [rbp-99h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-95h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-91h] BYREF
  void *v45; // [rsp+50h] [rbp-89h] BYREF
  PCWSTR ppszExt; // [rsp+58h] [rbp-81h] BYREF
  void *v47; // [rsp+60h] [rbp-79h] BYREF
  wchar_t *String2[3]; // [rsp+68h] [rbp-71h] BYREF
  void *v49; // [rsp+80h] [rbp-59h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-49h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-39h]
  unsigned __int64 v52; // [rsp+A8h] [rbp-31h]
  unsigned __int16 *v53[3]; // [rsp+B0h] [rbp-29h] BYREF
  unsigned __int64 v54; // [rsp+C8h] [rbp-11h]
  WCHAR ValueName[16]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  String2[2] = a2;
  v6 = (_QWORD *)PackageCollector::s_registryCache;
  v7 = qword_18004AEC0;
  if ( (void *)PackageCollector::s_registryCache == qword_18004AEC0 )
  {
    hKey = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\PackageLocations", 0, 0x20019u, &hKey);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        (const char *)v8,
        phkResult);
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      cchValueName = 15;
      cbData = 0;
      v37 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, &cbData);
      if ( v37 == 259 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return std::vector<std::wstring>::_Tidy(a2);
      }
      if ( v37 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v37,
          phkResultb);
      if ( cchValueName >= 0x10 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x8000FFFFLL,
          phkResultb);
      lpData = (BYTE *)operator new[](cbData);
      v47 = lpData;
      if ( !lpData )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          v12);
      cchValueName = 15;
      v13 = RegEnumValueW(hKey, v9, ValueName, &cchValueName, 0, 0, lpData, &cbData);
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v13,
          phkResulta);
      v14 = *(_WORD **)expanded_wstring::expanded_wstring((expanded_wstring *)&v49, (const unsigned __int16 *)lpData);
      v52 = 7;
      v51 = 0;
      LOWORD(String1[0]) = 0;
      if ( *v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
      }
      std::wstring::assign(String1, v14);
      operator delete[](v49);
      v16 = *(_QWORD *)a2;
      v17 = *((_QWORD *)a2 + 1);
      while ( v16 != v17 )
      {
        v54 = 7;
        v53[2] = 0;
        LOWORD(v53[0]) = 0;
        std::wstring::assign(v53);
        v18 = (const unsigned __int16 *)v53;
        if ( v54 >= 8 )
          v18 = v53[0];
        expanded_wstring::expanded_wstring((expanded_wstring *)String2, v18);
        v19 = -1;
        do
          ++v19;
        while ( String2[0][v19] );
        v20 = (const wchar_t *)String1;
        if ( v52 >= 8 )
          v20 = String1[0];
        if ( !_wcsnicmp(v20, String2[0], v19) )
        {
          if ( *(_DWORD *)g_hProvTraceProvider > 4u )
          {
            v22 = v53;
            if ( v54 >= 8 )
              v22 = (unsigned __int16 **)v53[0];
            v45 = v22;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              g_hProvTraceProvider,
              (unsigned int)byte_1800413DB,
              0,
              v21,
              (__int64)&v45);
          }
          operator delete[](String2[0]);
          if ( v54 >= 8 )
            operator delete(v53[0]);
          LOWORD(v53[0]) = 0;
          goto LABEL_52;
        }
        operator delete[](String2[0]);
        if ( v54 >= 8 )
          operator delete(v53[0]);
        v16 += 32;
      }
      v23 = (const WCHAR *)String1;
      if ( v52 >= 8 )
        v23 = String1[0];
      FileAttributesW = GetFileAttributesW(v23);
      if ( FileAttributesW == -1 )
      {
        if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          v26 = String1;
          if ( v52 >= 8 )
            v26 = (wchar_t **)String1[0];
          McTemplateU0z_EventWriteTransfer(v25, ProvisioningSearchPathNotExist, v26);
        }
        goto LABEL_52;
      }
      if ( (FileAttributesW & 0x10) != 0 )
        goto LABEL_49;
      v27 = (const WCHAR *)String1;
      if ( v52 >= 8 )
        v27 = String1[0];
      FileNameW = PathFindFileNameW(v27);
      if ( FileNameW )
        break;
LABEL_52:
      if ( v52 >= 8 )
        operator delete(String1[0]);
      LOWORD(String1[0]) = 0;
      v51 = 0;
      v52 = 7;
      operator delete[](lpData);
      ++v9;
    }
    ppszExt = 0;
    v29 = (const WCHAR *)String1;
    if ( v52 >= 8 )
      v29 = String1[0];
    Extension = PathCchFindExtension(v29, v51 + 1, &ppszExt);
    if ( Extension < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        (const char *)(unsigned int)Extension,
        phkResulta);
    if ( _wcsicmp(ppszExt, L".ppkg") )
    {
      if ( *(_DWORD *)g_hProvTraceProvider > 2u )
      {
        v45 = FileNameW;
        v33 = String1;
        if ( v52 >= 8 )
          v33 = (wchar_t **)String1[0];
        v47 = v33;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          g_hProvTraceProvider,
          (unsigned int)byte_1800413A9,
          v31,
          v32,
          (__int64)&v47,
          (__int64)&v45);
      }
      goto LABEL_52;
    }
LABEL_49:
    v34 = qword_18004AEC0;
    if ( qword_18004AEC0 == (void *)qword_18004AEC8 )
    {
      std::vector<std::wstring>::_Reserve(&PackageCollector::s_registryCache);
      v34 = qword_18004AEC0;
    }
    v34[3] = 7;
    v34[2] = 0;
    *(_WORD *)v34 = 0;
    std::wstring::assign(v34);
    qword_18004AEC0 = (char *)qword_18004AEC0 + 32;
    PackageCollector::AddSearchPath(a1, (_QWORD *)qword_18004AEC0 - 4, v35, v36);
    goto LABEL_52;
  }
  do
  {
    PackageCollector::AddSearchPath(a1, v6, a3, a4);
    v6 += 4;
  }
  while ( v6 != v7 );
  return std::vector<std::wstring>::_Tidy(a2);
}

```

## disassembly

```asm
0x180028f74  mov     [rsp-8+arg_10], rbx
0x180028f79  push    rbp
0x180028f7a  push    rsi
0x180028f7b  push    rdi
0x180028f7c  push    r12
0x180028f7e  push    r13
0x180028f80  push    r14
0x180028f82  push    r15
0x180028f84  lea     rbp, [rsp-27h]
0x180028f89  sub     rsp, 100h
0x180028f90  mov     rax, cs:__security_cookie
0x180028f97  xor     rax, rsp
0x180028f9a  mov     [rbp+57h+var_40], rax
0x180028f9e  mov     r14, rdx
0x180028fa1  mov     r12, rcx
0x180028fa4  mov     [rbp+57h+var_B8], rdx
0x180028fa8  mov     rbx, cs:?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x180028faf  mov     rdi, cs:qword_18004AEC0
0x180028fb6  cmp     rbx, rdi
0x180028fb9  jnz     loc_1800293E9
0x180028fbf  xor     r13d, r13d
0x180028fc2  mov     [rsp+130h+hKey], r13
0x180028fc7  lea     rax, [rsp+130h+hKey]
0x180028fcc  mov     [rsp+130h+phkResult], rax; unsigned int
0x180028fd1  mov     r9d, 20019h; samDesired
0x180028fd7  xor     r8d, r8d; ulOptions
0x180028fda  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x180028fe1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028fe8  call    cs:__imp_RegOpenKeyExW
0x180028fee  mov     rcx, [rbp+5Fh]; this
0x180028ff2  test    eax, eax
0x180028ff4  jnz     loc_18002940F
0x180028ffa  mov     r15d, r13d
0x180028ffd  xor     edx, edx
0x180028fff  jmp     loc_18002935F
0x180029004  mov     rcx, [rbp+5Fh]; this
0x180029008  test    eax, eax
0x18002900a  jnz     loc_1800293FA
0x180029010  cmp     [rsp+130h+cchValueName], 10h
0x180029015  setb    al
0x180029018  mov     rcx, [rbp+5Fh]; this
0x18002901c  test    al, al
0x18002901e  jz      loc_180029460
0x180029024  mov     ecx, [rsp+130h+cbData]; unsigned __int64
0x180029028  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002902d  mov     rdi, rax
0x180029030  mov     [rbp+57h+var_D0], rax
0x180029034  mov     rcx, [rbp+5Fh]; this
0x180029038  test    rax, rax
0x18002903b  jz      loc_18002944E
0x180029041  mov     [rsp+130h+cchValueName], 0Fh
0x180029049  lea     rax, [rsp+130h+cbData]
0x18002904e  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180029053  mov     [rsp+130h+lpData], rdi; lpData
0x180029058  mov     [rsp+130h+lpType], r13; lpType
0x18002905d  mov     [rsp+130h+phkResult], r13; unsigned int
0x180029062  lea     r9, [rsp+130h+cchValueName]; lpcchValueName
0x180029067  lea     r8, [rbp+57h+ValueName]; lpValueName
0x18002906b  mov     edx, r15d; dwIndex
0x18002906e  mov     rcx, [rsp+130h+hKey]; hKey
0x180029073  call    cs:__imp_RegEnumValueW
0x180029079  mov     rcx, [rbp+5Fh]; this
0x18002907d  test    eax, eax
0x18002907f  jnz     loc_180029439
0x180029085  mov     rdx, rdi; unsigned __int16 *
0x180029088  lea     rcx, [rbp+57h+var_B0]; this
0x18002908c  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180029091  nop
0x180029092  mov     rdx, [rax]; Src
0x180029095  mov     [rbp+57h+var_88], 7
0x18002909d  mov     [rbp+57h+var_90], r13
0x1800290a1  mov     word ptr [rbp+57h+String1], r13w
0x1800290a6  cmp     [rdx], r13w
0x1800290aa  jnz     short loc_1800290B1
0x1800290ac  mov     r8, r13
0x1800290af  jmp     short loc_1800290BF
0x1800290b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800290b5  inc     r8
0x1800290b8  cmp     [rdx+r8*2], r13w
0x1800290bd  jnz     short loc_1800290B5
0x1800290bf  lea     rcx, [rbp+57h+String1]; void *
0x1800290c3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800290c8  nop
0x1800290c9  mov     rcx, [rbp+57h+var_B0]
0x1800290cd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800290d3  mov     rbx, [r14]
0x1800290d6  mov     rsi, [r14+8]
0x1800290da  cmp     rbx, rsi
0x1800290dd  jz      loc_1800291CE
0x1800290e3  mov     [rbp+57h+var_68], 7
0x1800290eb  mov     [rbp+57h+var_70], r13
0x1800290ef  mov     word ptr [rbp+57h+var_80], r13w
0x1800290f4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800290f8  xor     r8d, r8d
0x1800290fb  mov     rdx, rbx
0x1800290fe  lea     rcx, [rbp+57h+var_80]; void *
0x180029102  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180029107  nop
0x180029108  lea     rdx, [rbp+57h+var_80]
0x18002910c  cmp     [rbp+57h+var_68], 8
0x180029111  cmovnb  rdx, [rbp+57h+var_80]; unsigned __int16 *
0x180029116  lea     rcx, [rbp+57h+String2]; this
0x18002911a  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x18002911f  mov     rdx, [rbp+57h+String2]; String2
0x180029123  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029127  inc     r8; MaxCount
0x18002912a  cmp     [rdx+r8*2], r13w
0x18002912f  jnz     short loc_180029127
0x180029131  lea     rcx, [rbp+57h+String1]
0x180029135  cmp     [rbp+57h+var_88], 8
0x18002913a  cmovnb  rcx, [rbp+57h+String1]; String1
0x18002913f  call    cs:__imp__wcsnicmp
0x180029145  test    eax, eax
0x180029147  jz      short loc_18002916E
0x180029149  mov     rcx, [rbp+57h+String2]
0x18002914d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029153  nop
0x180029154  cmp     [rbp+57h+var_68], 8
0x180029159  jb      short loc_180029165
0x18002915b  mov     rcx, [rbp+57h+var_80]
0x18002915f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029165  add     rbx, 20h ; ' '
0x180029169  jmp     loc_1800290DA
0x18002916e  mov     rcx, cs:g_hProvTraceProvider
0x180029175  mov     eax, [rcx]
0x180029177  cmp     eax, 4
0x18002917a  jbe     short loc_1800291A8
0x18002917c  lea     rax, [rbp+57h+var_80]
0x180029180  cmp     [rbp+57h+var_68], 8
0x180029185  cmovnb  rax, [rbp+57h+var_80]
0x18002918a  mov     [rsp+130h+var_E0], rax
0x18002918f  lea     rax, [rsp+130h+var_E0]
0x180029194  mov     [rsp+130h+phkResult], rax
0x180029199  xor     r8d, r8d
0x18002919c  lea     rdx, byte_1800413DB
0x1800291a3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800291a8  mov     rcx, [rbp+57h+String2]
0x1800291ac  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800291b2  nop
0x1800291b3  cmp     [rbp+57h+var_68], 8
0x1800291b8  jb      short loc_1800291C4
0x1800291ba  mov     rcx, [rbp+57h+var_80]
0x1800291be  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800291c4  mov     word ptr [rbp+57h+var_80], r13w
0x1800291c9  jmp     loc_18002932E
0x1800291ce  lea     rcx, [rbp+57h+String1]
0x1800291d2  cmp     [rbp+57h+var_88], 8
0x1800291d7  cmovnb  rcx, [rbp+57h+String1]; lpFileName
0x1800291dc  call    cs:__imp_GetFileAttributesW
0x1800291e2  cmp     eax, 0FFFFFFFFh
0x1800291e5  jnz     short loc_180029213
0x1800291e7  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 4
0x1800291ee  jz      loc_18002932E
0x1800291f4  lea     r8, [rbp+57h+String1]
0x1800291f8  cmp     [rbp+57h+var_88], 8
0x1800291fd  cmovnb  r8, [rbp+57h+String1]
0x180029202  lea     rdx, ProvisioningSearchPathNotExist
0x180029209  call    McTemplateU0z_EventWriteTransfer
0x18002920e  jmp     loc_18002932E
0x180029213  test    al, 10h
0x180029215  jnz     loc_1800292CC
0x18002921b  lea     rcx, [rbp+57h+String1]
0x18002921f  cmp     [rbp+57h+var_88], 8
0x180029224  cmovnb  rcx, [rbp+57h+String1]; pszPath
0x180029229  call    cs:__imp_PathFindFileNameW
0x18002922f  mov     rbx, rax
0x180029232  test    rax, rax
0x180029235  jz      loc_18002932E
0x18002923b  mov     [rsp+130h+ppszExt], r13
0x180029240  mov     rdx, [rbp+57h+var_90]
0x180029244  lea     rcx, [rbp+57h+String1]
0x180029248  cmp     [rbp+57h+var_88], 8
0x18002924d  cmovnb  rcx, [rbp+57h+String1]; pszPath
0x180029252  inc     rdx; cchPath
0x180029255  lea     r8, [rsp+130h+ppszExt]; ppszExt
0x18002925a  call    cs:__imp_PathCchFindExtension
0x180029260  mov     rcx, [rbp+5Fh]; this
0x180029264  test    eax, eax
0x180029266  js      loc_180029424
0x18002926c  lea     rdx, aPpkg_0; ".ppkg"
0x180029273  mov     rcx, [rsp+130h+ppszExt]; String1
0x180029278  call    cs:__imp__wcsicmp
0x18002927e  test    eax, eax
0x180029280  jz      short loc_1800292CC
0x180029282  mov     rcx, cs:g_hProvTraceProvider
0x180029289  mov     eax, [rcx]
0x18002928b  cmp     eax, 2
0x18002928e  jbe     loc_18002932E
0x180029294  mov     [rsp+130h+var_E0], rbx
0x180029299  lea     rax, [rbp+57h+String1]
0x18002929d  cmp     [rbp+57h+var_88], 8
0x1800292a2  cmovnb  rax, [rbp+57h+String1]
0x1800292a7  mov     [rbp+57h+var_D0], rax
0x1800292ab  lea     rax, [rsp+130h+var_E0]
0x1800292b0  mov     [rsp+130h+lpType], rax
0x1800292b5  lea     rax, [rbp+57h+var_D0]
0x1800292b9  mov     [rsp+130h+phkResult], rax
0x1800292be  lea     rdx, byte_1800413A9
0x1800292c5  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800292ca  jmp     short loc_18002932E
0x1800292cc  mov     rcx, cs:qword_18004AEC0
0x1800292d3  cmp     rcx, cs:qword_18004AEC8
0x1800292da  jnz     short loc_1800292EF
0x1800292dc  lea     rcx, ?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x1800292e3  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800292e8  mov     rcx, cs:qword_18004AEC0; void *
0x1800292ef  mov     qword ptr [rcx+18h], 7
0x1800292f7  mov     [rcx+10h], r13
0x1800292fb  mov     [rcx], r13w
0x1800292ff  or      r9, 0FFFFFFFFFFFFFFFFh
0x180029303  xor     r8d, r8d
0x180029306  lea     rdx, [rbp+57h+String1]
0x18002930a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002930f  mov     rdx, cs:qword_18004AEC0
0x180029316  add     rdx, 20h ; ' '
0x18002931a  mov     cs:qword_18004AEC0, rdx
0x180029321  add     rdx, 0FFFFFFFFFFFFFFE0h
0x180029325  mov     rcx, r12
0x180029328  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x18002932d  nop
0x18002932e  cmp     [rbp+57h+var_88], 8
0x180029333  jb      short loc_18002933F
0x180029335  mov     rcx, [rbp+57h+String1]
0x180029339  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002933f  mov     word ptr [rbp+57h+String1], r13w
0x180029344  mov     [rbp+57h+var_90], r13
0x180029348  mov     [rbp+57h+var_88], 7
0x180029350  mov     rcx, rdi
0x180029353  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029359  inc     r15d
0x18002935c  mov     edx, r15d; dwIndex
0x18002935f  lea     rax, [rsp+130h+cbData]
0x180029364  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180029369  mov     [rsp+130h+lpData], r13; lpData
0x18002936e  mov     [rsp+130h+lpType], r13; lpType
0x180029373  mov     [rsp+130h+phkResult], r13; int
0x180029378  mov     [rsp+130h+cchValueName], 0Fh
0x180029380  mov     [rsp+130h+cbData], r13d
0x180029385  lea     r9, [rsp+130h+cchValueName]; lpcchValueName
0x18002938a  lea     r8, [rbp+57h+ValueName]; lpValueName
0x18002938e  mov     rcx, [rsp+130h+hKey]; hKey
0x180029393  call    cs:__imp_RegEnumValueW
0x180029399  cmp     eax, 103h
0x18002939e  jnz     loc_180029004
0x1800293a4  mov     rcx, [rsp+130h+hKey]; hKey
0x1800293a9  test    rcx, rcx
0x1800293ac  jz      short loc_1800293B5
0x1800293ae  call    cs:__imp_RegCloseKey
0x1800293b4  nop
0x1800293b5  mov     rcx, r14
0x1800293b8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800293bd  mov     rcx, [rbp+57h+var_40]
0x1800293c1  xor     rcx, rsp; StackCookie
0x1800293c4  call    __security_check_cookie
0x1800293c9  mov     rbx, [rsp+130h+arg_10]
0x1800293d1  add     rsp, 100h
0x1800293d8  pop     r15
0x1800293da  pop     r14
0x1800293dc  pop     r13
0x1800293de  pop     r12
0x1800293e0  pop     rdi
0x1800293e1  pop     rsi
0x1800293e2  pop     rbp
0x1800293e3  retn
0x1800293e4  cmp     rbx, rdi
0x1800293e7  jz      short loc_1800293B5
0x1800293e9  mov     rdx, rbx
0x1800293ec  mov     rcx, r12
0x1800293ef  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x1800293f4  add     rbx, 20h ; ' '
0x1800293f8  jmp     short loc_1800293E4
0x1800293fa  mov     r9d, eax; char *
0x1800293fd  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x180029404  mov     edx, 51h ; 'Q'; void *
0x180029409  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002940f  mov     r9d, eax; char *
0x180029412  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x180029419  mov     edx, 3Ch ; '<'; void *
0x18002941e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180029424  mov     r9d, eax; char *
0x180029427  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002942e  mov     edx, 93h; void *
0x180029433  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029439  mov     r9d, eax; char *
0x18002943c  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x180029443  mov     edx, 61h ; 'a'; void *
0x180029448  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002944e  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x180029455  mov     edx, 56h ; 'V'; void *
0x18002945a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180029460  mov     r9d, 8000FFFFh; char *
0x180029466  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002946d  mov     edx, 52h ; 'R'; void *
0x180029472  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
