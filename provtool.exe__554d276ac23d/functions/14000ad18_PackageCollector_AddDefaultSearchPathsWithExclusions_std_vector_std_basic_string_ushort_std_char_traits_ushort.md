# PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x14000ad18`
- end: `0x14000b248`
- name: `?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1328`
- prototype: `__int64 __fastcall(__int64, wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140006b70`

## callees

- `0x140001008`
- `0x14000124c`
- `0x140002288`
- `0x140003a0c`
- `0x140008b0c`
- `0x140008b88`
- `0x140008ba8`
- `0x140008cd8`
- `0x140008e50`
- `0x140009340`
- `0x14000ab6c`
- `0x14000ad18`
- `0x14000b250`
- `0x14000bd8c`
- `0x14000ded0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000b05e`
- `msvcrt!_wcsicmp` at `0x14000b05e`
- `msvcrt!_wcsnicmp` at `0x14000aee7`
- `msvcrt!_wcsnicmp` at `0x14000aee7`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000af08`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000af62`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b11e`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000af08`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000af62`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b11e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000ae73`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000aef6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000af50`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000b138`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000ae73`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000aef6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000af50`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000b138`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ad8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000ad8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b193`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b193`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000ae19`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000b178`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000ae19`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14000b178`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x14000b040`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x14000b040`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000af80`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000af80`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000b00f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000b00f`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions(__int64 a1, wchar_t *a2)
{
  __int64 v4; // rbx
  void *v5; // rdi
  unsigned int v6; // eax
  unsigned int v7; // r8d
  DWORD v8; // r15d
  DWORD i; // edx
  BYTE *lpData; // rsi
  const char *v11; // r9
  unsigned int v12; // eax
  unsigned int v13; // r8d
  _WORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rdi
  const unsigned __int16 *v18; // rdx
  size_t v19; // r8
  const wchar_t *v20; // rcx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  unsigned __int16 **v24; // rax
  const WCHAR *v25; // rcx
  DWORD FileAttributesW; // eax
  __int64 v27; // r8
  const wchar_t *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  const WCHAR *v31; // rcx
  LPWSTR FileNameW; // rbx
  const WCHAR *v33; // rcx
  HRESULT Extension; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  wchar_t **v38; // rax
  _QWORD *v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // r8d
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *v49; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR ppszExt; // [rsp+58h] [rbp-A8h] BYREF
  void *v51; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String2[3]; // [rsp+68h] [rbp-98h] BYREF
  void *v53; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v56; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v57[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v58; // [rsp+C8h] [rbp-38h]
  _BYTE v59[16]; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v60; // [rsp+E0h] [rbp-20h]
  int v61; // [rsp+E8h] [rbp-18h]
  int v62; // [rsp+ECh] [rbp-14h]
  WCHAR ValueName[16]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  String2[2] = a2;
  v4 = PackageCollector::s_registryCache;
  v5 = qword_140017A10;
  if ( (void *)PackageCollector::s_registryCache == qword_140017A10 )
  {
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\PackageLocations", 0, 0x20019u, &hKey);
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x3C, v7, (const char *)v6, phkResult);
    v8 = 0;
    for ( i = 0; ; i = v8 )
    {
      cchValueName = 15;
      cbData = 0;
      v40 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, &cbData);
      if ( v40 == 259 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        return std::vector<std::wstring>::_Tidy(a2);
      }
      if ( v40 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x51, v41, (const char *)v40, phkResultb);
      if ( cchValueName >= 0x10 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x8000FFFFLL,
          phkResultb);
      lpData = (BYTE *)operator new[](cbData);
      v51 = lpData;
      if ( !lpData )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          v11);
      cchValueName = 15;
      v12 = RegEnumValueW(hKey, v8, ValueName, &cchValueName, 0, 0, lpData, &cbData);
      if ( v12 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x61, v13, (const char *)v12, phkResulta);
      v14 = *(_WORD **)expanded_wstring::expanded_wstring((expanded_wstring *)&v53, (const unsigned __int16 *)lpData);
      v56 = 7;
      v55 = 0;
      LOWORD(String1[0]) = 0;
      if ( *v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
      }
      std::wstring::assign(String1, v14);
      operator delete[](v53);
      v16 = *(_QWORD *)a2;
      v17 = *((_QWORD *)a2 + 1);
      while ( v16 != v17 )
      {
        v58 = 7;
        v57[2] = 0;
        LOWORD(v57[0]) = 0;
        std::wstring::assign(v57);
        v18 = (const unsigned __int16 *)v57;
        if ( v58 >= 8 )
          v18 = v57[0];
        expanded_wstring::expanded_wstring((expanded_wstring *)String2, v18);
        v19 = -1;
        do
          ++v19;
        while ( String2[0][v19] );
        v20 = (const wchar_t *)String1;
        if ( v56 >= 8 )
          v20 = String1[0];
        if ( !_wcsnicmp(v20, String2[0], v19) )
        {
          if ( (unsigned int)dword_140017048 > 4 )
          {
            v24 = v57;
            if ( v58 >= 8 )
              v24 = (unsigned __int16 **)v57[0];
            v49 = v24;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              v21,
              (unsigned int)&word_140013646,
              v22,
              v23,
              (__int64)&v49);
          }
          operator delete[](String2[0]);
          if ( v58 >= 8 )
            operator delete(v57[0]);
          LOWORD(v57[0]) = 0;
          goto LABEL_57;
        }
        operator delete[](String2[0]);
        if ( v58 >= 8 )
          operator delete(v57[0]);
        v16 += 32;
      }
      v25 = (const WCHAR *)String1;
      if ( v56 >= 8 )
        v25 = String1[0];
      FileAttributesW = GetFileAttributesW(v25);
      if ( FileAttributesW == -1 )
      {
        if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          v28 = (const wchar_t *)String1;
          if ( v56 >= 8 )
            v28 = String1[0];
          if ( v28 )
          {
            v29 = -1;
            do
              ++v29;
            while ( v28[v29] );
            v30 = (unsigned int)(2 * v29 + 2);
          }
          else
          {
            v28 = L"NULL";
            v30 = 10;
          }
          v60 = v28;
          v61 = v30;
          v62 = 0;
          McGenEventWrite_EventWriteTransfer(v30, ProvisioningSearchPathNotExist, v27, 2, v59);
        }
        goto LABEL_57;
      }
      if ( (FileAttributesW & 0x10) != 0 )
        goto LABEL_54;
      v31 = (const WCHAR *)String1;
      if ( v56 >= 8 )
        v31 = String1[0];
      FileNameW = PathFindFileNameW(v31);
      if ( FileNameW )
        break;
LABEL_57:
      if ( v56 >= 8 )
        operator delete(String1[0]);
      LOWORD(String1[0]) = 0;
      v55 = 0;
      v56 = 7;
      operator delete[](lpData);
      ++v8;
    }
    ppszExt = 0;
    v33 = (const WCHAR *)String1;
    if ( v56 >= 8 )
      v33 = String1[0];
    Extension = PathCchFindExtension(v33, v55 + 1, &ppszExt);
    if ( Extension < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        (const char *)(unsigned int)Extension,
        phkResulta);
    if ( _wcsicmp(ppszExt, L".ppkg") )
    {
      if ( (unsigned int)dword_140017048 > 2 )
      {
        v49 = FileNameW;
        v38 = String1;
        if ( v56 >= 8 )
          v38 = (wchar_t **)String1[0];
        v51 = v38;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v35,
          (unsigned int)&dword_140013614,
          v36,
          v37,
          (__int64)&v51,
          (__int64)&v49);
      }
      goto LABEL_57;
    }
LABEL_54:
    v39 = qword_140017A10;
    if ( qword_140017A10 == (void *)qword_140017A18 )
    {
      std::vector<std::wstring>::_Reserve(&PackageCollector::s_registryCache);
      v39 = qword_140017A10;
    }
    v39[3] = 7;
    v39[2] = 0;
    *(_WORD *)v39 = 0;
    std::wstring::assign(v39);
    qword_140017A10 = (char *)qword_140017A10 + 32;
    PackageCollector::AddSearchPath(a1, (char *)qword_140017A10 - 32);
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
0x14000ad18  mov     [rsp-8+arg_10], rbx
0x14000ad1d  push    rbp
0x14000ad1e  push    rsi
0x14000ad1f  push    rdi
0x14000ad20  push    r12
0x14000ad22  push    r13
0x14000ad24  push    r14
0x14000ad26  push    r15
0x14000ad28  lea     rbp, [rsp-20h]
0x14000ad2d  sub     rsp, 120h
0x14000ad34  mov     rax, cs:__security_cookie
0x14000ad3b  xor     rax, rsp
0x14000ad3e  mov     [rbp+50h+var_40], rax
0x14000ad42  mov     r14, rdx
0x14000ad45  mov     r12, rcx
0x14000ad48  mov     [rsp+150h+var_D8], rdx
0x14000ad4d  mov     rbx, cs:?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x14000ad54  mov     rdi, cs:qword_140017A10
0x14000ad5b  cmp     rbx, rdi
0x14000ad5e  jnz     loc_14000B1CE
0x14000ad64  xor     r13d, r13d
0x14000ad67  mov     [rsp+150h+hKey], r13
0x14000ad6c  lea     rax, [rsp+150h+hKey]
0x14000ad71  mov     [rsp+150h+phkResult], rax; unsigned int
0x14000ad76  mov     r9d, 20019h; samDesired
0x14000ad7c  xor     r8d, r8d; ulOptions
0x14000ad7f  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x14000ad86  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ad8d  call    cs:__imp_RegOpenKeyExW
0x14000ad93  mov     rcx, [rbp+58h]; this
0x14000ad97  test    eax, eax
0x14000ad99  jnz     loc_14000B1ED
0x14000ad9f  mov     r15d, r13d
0x14000ada2  xor     edx, edx
0x14000ada4  jmp     loc_14000B144
0x14000ada9  mov     rcx, [rbp+58h]; this
0x14000adad  test    eax, eax
0x14000adaf  jnz     loc_14000B1DF
0x14000adb5  cmp     [rsp+150h+cchValueName], 10h
0x14000adba  setb    al
0x14000adbd  mov     rcx, [rbp+58h]; this
0x14000adc1  test    al, al
0x14000adc3  jz      loc_14000B230
0x14000adc9  mov     ecx, [rsp+150h+cbData]; unsigned __int64
0x14000adcd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000add2  mov     rsi, rax
0x14000add5  mov     [rsp+150h+var_F0], rax
0x14000adda  mov     rcx, [rbp+58h]; this
0x14000adde  test    rax, rax
0x14000ade1  jz      loc_14000B21E
0x14000ade7  mov     [rsp+150h+cchValueName], 0Fh
0x14000adef  lea     rax, [rsp+150h+cbData]
0x14000adf4  mov     [rsp+150h+lpcbData], rax; lpcbData
0x14000adf9  mov     [rsp+150h+lpData], rsi; lpData
0x14000adfe  mov     [rsp+150h+lpType], r13; lpType
0x14000ae03  mov     [rsp+150h+phkResult], r13; unsigned int
0x14000ae08  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x14000ae0d  lea     r8, [rbp+50h+ValueName]; lpValueName
0x14000ae11  mov     edx, r15d; dwIndex
0x14000ae14  mov     rcx, [rsp+150h+hKey]; hKey
0x14000ae19  call    cs:__imp_RegEnumValueW
0x14000ae1f  mov     rcx, [rbp+58h]; this
0x14000ae23  test    eax, eax
0x14000ae25  jnz     loc_14000B210
0x14000ae2b  mov     rdx, rsi; unsigned __int16 *
0x14000ae2e  lea     rcx, [rbp+50h+var_D0]; this
0x14000ae32  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x14000ae37  nop
0x14000ae38  mov     rdx, [rax]; Src
0x14000ae3b  mov     [rbp+50h+var_A8], 7
0x14000ae43  mov     [rbp+50h+var_B0], r13
0x14000ae47  mov     word ptr [rbp+50h+String1], r13w
0x14000ae4c  cmp     [rdx], r13w
0x14000ae50  jnz     short loc_14000AE57
0x14000ae52  mov     r8, r13
0x14000ae55  jmp     short loc_14000AE65
0x14000ae57  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000ae5b  inc     r8
0x14000ae5e  cmp     [rdx+r8*2], r13w
0x14000ae63  jnz     short loc_14000AE5B
0x14000ae65  lea     rcx, [rbp+50h+String1]; void *
0x14000ae69  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000ae6e  nop
0x14000ae6f  mov     rcx, [rbp+50h+var_D0]
0x14000ae73  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000ae79  mov     rbx, [r14]
0x14000ae7c  mov     rdi, [r14+8]
0x14000ae80  cmp     rbx, rdi
0x14000ae83  jz      loc_14000AF72
0x14000ae89  mov     [rbp+50h+var_88], 7
0x14000ae91  mov     [rbp+50h+var_90], r13
0x14000ae95  mov     word ptr [rbp+50h+var_A0], r13w
0x14000ae9a  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000ae9e  xor     r8d, r8d
0x14000aea1  mov     rdx, rbx
0x14000aea4  lea     rcx, [rbp+50h+var_A0]; void *
0x14000aea8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000aead  nop
0x14000aeae  lea     rdx, [rbp+50h+var_A0]
0x14000aeb2  cmp     [rbp+50h+var_88], 8
0x14000aeb7  cmovnb  rdx, [rbp+50h+var_A0]; unsigned __int16 *
0x14000aebc  lea     rcx, [rsp+150h+String2]; this
0x14000aec1  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x14000aec6  mov     rdx, [rsp+150h+String2]; String2
0x14000aecb  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000aecf  inc     r8; MaxCount
0x14000aed2  cmp     [rdx+r8*2], r13w
0x14000aed7  jnz     short loc_14000AECF
0x14000aed9  lea     rcx, [rbp+50h+String1]
0x14000aedd  cmp     [rbp+50h+var_A8], 8
0x14000aee2  cmovnb  rcx, [rbp+50h+String1]; String1
0x14000aee7  call    cs:__imp__wcsnicmp
0x14000aeed  test    eax, eax
0x14000aeef  jz      short loc_14000AF17
0x14000aef1  mov     rcx, [rsp+150h+String2]
0x14000aef6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000aefc  nop
0x14000aefd  cmp     [rbp+50h+var_88], 8
0x14000af02  jb      short loc_14000AF0E
0x14000af04  mov     rcx, [rbp+50h+var_A0]
0x14000af08  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000af0e  add     rbx, 20h ; ' '
0x14000af12  jmp     loc_14000AE80
0x14000af17  mov     eax, cs:dword_140017048
0x14000af1d  cmp     eax, 4
0x14000af20  jbe     short loc_14000AF4B
0x14000af22  lea     rax, [rbp+50h+var_A0]
0x14000af26  cmp     [rbp+50h+var_88], 8
0x14000af2b  cmovnb  rax, [rbp+50h+var_A0]
0x14000af30  mov     [rsp+150h+var_100], rax
0x14000af35  lea     rax, [rsp+150h+var_100]
0x14000af3a  mov     [rsp+150h+phkResult], rax
0x14000af3f  lea     rdx, word_140013646
0x14000af46  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000af4b  mov     rcx, [rsp+150h+String2]
0x14000af50  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000af56  nop
0x14000af57  cmp     [rbp+50h+var_88], 8
0x14000af5c  jb      short loc_14000AF68
0x14000af5e  mov     rcx, [rbp+50h+var_A0]
0x14000af62  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000af68  mov     word ptr [rbp+50h+var_A0], r13w
0x14000af6d  jmp     loc_14000B113
0x14000af72  lea     rcx, [rbp+50h+String1]
0x14000af76  cmp     [rbp+50h+var_A8], 8
0x14000af7b  cmovnb  rcx, [rbp+50h+String1]; lpFileName
0x14000af80  call    cs:__imp_GetFileAttributesW
0x14000af86  cmp     eax, 0FFFFFFFFh
0x14000af89  jnz     short loc_14000AFF9
0x14000af8b  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 4
0x14000af92  jz      loc_14000B113
0x14000af98  lea     rax, [rbp+50h+String1]
0x14000af9c  cmp     [rbp+50h+var_A8], 8
0x14000afa1  cmovnb  rax, [rbp+50h+String1]
0x14000afa6  test    rax, rax
0x14000afa9  jz      short loc_14000AFC2
0x14000afab  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000afaf  inc     rcx
0x14000afb2  cmp     [rax+rcx*2], r13w
0x14000afb7  jnz     short loc_14000AFAF
0x14000afb9  lea     ecx, ds:2[rcx*2]
0x14000afc0  jmp     short loc_14000AFCE
0x14000afc2  lea     rax, aNull; "NULL"
0x14000afc9  mov     ecx, 0Ah
0x14000afce  mov     [rbp+50h+var_70], rax
0x14000afd2  mov     [rbp+50h+var_68], ecx
0x14000afd5  mov     [rbp+50h+var_64], r13d
0x14000afd9  lea     rax, [rbp+50h+var_80]
0x14000afdd  mov     [rsp+150h+phkResult], rax
0x14000afe2  mov     r9d, 2
0x14000afe8  lea     rdx, ProvisioningSearchPathNotExist
0x14000afef  call    McGenEventWrite_EventWriteTransfer
0x14000aff4  jmp     loc_14000B113
0x14000aff9  test    al, 10h
0x14000affb  jnz     loc_14000B0B1
0x14000b001  lea     rcx, [rbp+50h+String1]
0x14000b005  cmp     [rbp+50h+var_A8], 8
0x14000b00a  cmovnb  rcx, [rbp+50h+String1]; pszPath
0x14000b00f  call    cs:__imp_PathFindFileNameW
0x14000b015  mov     rbx, rax
0x14000b018  test    rax, rax
0x14000b01b  jz      loc_14000B113
0x14000b021  mov     [rsp+150h+ppszExt], r13
0x14000b026  mov     rdx, [rbp+50h+var_B0]
0x14000b02a  lea     rcx, [rbp+50h+String1]
0x14000b02e  cmp     [rbp+50h+var_A8], 8
0x14000b033  cmovnb  rcx, [rbp+50h+String1]; pszPath
0x14000b038  inc     rdx; cchPath
0x14000b03b  lea     r8, [rsp+150h+ppszExt]; ppszExt
0x14000b040  call    cs:__imp_PathCchFindExtension
0x14000b046  mov     rcx, [rbp+58h]; this
0x14000b04a  test    eax, eax
0x14000b04c  js      loc_14000B1FB
0x14000b052  lea     rdx, aPpkg_0; ".ppkg"
0x14000b059  mov     rcx, [rsp+150h+ppszExt]; String1
0x14000b05e  call    cs:__imp__wcsicmp
0x14000b064  test    eax, eax
0x14000b066  jz      short loc_14000B0B1
0x14000b068  mov     eax, cs:dword_140017048
0x14000b06e  cmp     eax, 2
0x14000b071  jbe     loc_14000B113
0x14000b077  mov     [rsp+150h+var_100], rbx
0x14000b07c  lea     rax, [rbp+50h+String1]
0x14000b080  cmp     [rbp+50h+var_A8], 8
0x14000b085  cmovnb  rax, [rbp+50h+String1]
0x14000b08a  mov     [rsp+150h+var_F0], rax
0x14000b08f  lea     rax, [rsp+150h+var_100]
0x14000b094  mov     [rsp+150h+lpType], rax
0x14000b099  lea     rax, [rsp+150h+var_F0]
0x14000b09e  mov     [rsp+150h+phkResult], rax
0x14000b0a3  lea     rdx, dword_140013614
0x14000b0aa  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000b0af  jmp     short loc_14000B113
0x14000b0b1  mov     rcx, cs:qword_140017A10
0x14000b0b8  cmp     rcx, cs:qword_140017A18
0x14000b0bf  jnz     short loc_14000B0D4
0x14000b0c1  lea     rcx, ?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x14000b0c8  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x14000b0cd  mov     rcx, cs:qword_140017A10; void *
0x14000b0d4  mov     qword ptr [rcx+18h], 7
0x14000b0dc  mov     [rcx+10h], r13
0x14000b0e0  mov     [rcx], r13w
0x14000b0e4  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000b0e8  xor     r8d, r8d
0x14000b0eb  lea     rdx, [rbp+50h+String1]
0x14000b0ef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000b0f4  mov     rdx, cs:qword_140017A10
0x14000b0fb  add     rdx, 20h ; ' '
0x14000b0ff  mov     cs:qword_140017A10, rdx
0x14000b106  add     rdx, 0FFFFFFFFFFFFFFE0h
0x14000b10a  mov     rcx, r12
0x14000b10d  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x14000b112  nop
0x14000b113  cmp     [rbp+50h+var_A8], 8
0x14000b118  jb      short loc_14000B124
0x14000b11a  mov     rcx, [rbp+50h+String1]
0x14000b11e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000b124  mov     word ptr [rbp+50h+String1], r13w
0x14000b129  mov     [rbp+50h+var_B0], r13
0x14000b12d  mov     [rbp+50h+var_A8], 7
0x14000b135  mov     rcx, rsi
0x14000b138  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000b13e  inc     r15d
0x14000b141  mov     edx, r15d; dwIndex
0x14000b144  lea     rax, [rsp+150h+cbData]
0x14000b149  mov     [rsp+150h+lpcbData], rax; lpcbData
0x14000b14e  mov     [rsp+150h+lpData], r13; lpData
0x14000b153  mov     [rsp+150h+lpType], r13; lpType
0x14000b158  mov     [rsp+150h+phkResult], r13; int
0x14000b15d  mov     [rsp+150h+cchValueName], 0Fh
0x14000b165  mov     [rsp+150h+cbData], r13d
0x14000b16a  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x14000b16f  lea     r8, [rbp+50h+ValueName]; lpValueName
0x14000b173  mov     rcx, [rsp+150h+hKey]; hKey
0x14000b178  call    cs:__imp_RegEnumValueW
0x14000b17e  cmp     eax, 103h
0x14000b183  jnz     loc_14000ADA9
0x14000b189  mov     rcx, [rsp+150h+hKey]; hKey
0x14000b18e  test    rcx, rcx
0x14000b191  jz      short loc_14000B19A
0x14000b193  call    cs:__imp_RegCloseKey
0x14000b199  nop
0x14000b19a  mov     rcx, r14
0x14000b19d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x14000b1a2  mov     rcx, [rbp+50h+var_40]
0x14000b1a6  xor     rcx, rsp; StackCookie
0x14000b1a9  call    __security_check_cookie
0x14000b1ae  mov     rbx, [rsp+150h+arg_10]
0x14000b1b6  add     rsp, 120h
0x14000b1bd  pop     r15
0x14000b1bf  pop     r14
0x14000b1c1  pop     r13
0x14000b1c3  pop     r12
0x14000b1c5  pop     rdi
0x14000b1c6  pop     rsi
0x14000b1c7  pop     rbp
0x14000b1c8  retn
0x14000b1c9  cmp     rbx, rdi
0x14000b1cc  jz      short loc_14000B19A
0x14000b1ce  mov     rdx, rbx
0x14000b1d1  mov     rcx, r12
0x14000b1d4  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x14000b1d9  add     rbx, 20h ; ' '
0x14000b1dd  jmp     short loc_14000B1C9
0x14000b1df  mov     r9d, eax; char *
0x14000b1e2  mov     edx, 51h ; 'Q'; void *
0x14000b1e7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000b1ed  mov     r9d, eax; char *
0x14000b1f0  mov     edx, 3Ch ; '<'; void *
0x14000b1f5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000b1fb  mov     r9d, eax; char *
0x14000b1fe  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x14000b205  mov     edx, 93h; void *
0x14000b20a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b210  mov     r9d, eax; char *
0x14000b213  mov     edx, 61h ; 'a'; void *
0x14000b218  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000b21e  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x14000b225  mov     edx, 56h ; 'V'; void *
0x14000b22a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
  ... truncated ...
```
