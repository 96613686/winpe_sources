# AfxOleUnregisterTypeLib(_GUID const &,ushort,ushort,ulong)

- ea: `0x1801fd6e0`
- end: `0x1801fdac1`
- name: `?AfxOleUnregisterTypeLib@@YAHAEBU_GUID@@GGK@Z`
- size: `993`
- prototype: `int __fastcall(const _GUID *tlid, unsigned __int16 wVerMajor, unsigned __int16 wVerMinor, unsigned int lcid)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000df50`
- `0x1801d8c48`
- `0x1801fd228`
- `0x1801fd27c`
- `0x1801fd6e0`
- `0x1801fe650`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1801fd8fe`
- `ADVAPI32!RegCloseKey` at `0x1801fd91f`
- `ADVAPI32!RegCloseKey` at `0x1801fd94b`
- `ADVAPI32!RegCloseKey` at `0x1801fd963`
- `ADVAPI32!RegCloseKey` at `0x1801fd9d2`
- `ADVAPI32!RegCloseKey` at `0x1801fd8fe`
- `ADVAPI32!RegCloseKey` at `0x1801fd91f`
- `ADVAPI32!RegCloseKey` at `0x1801fd94b`
- `ADVAPI32!RegCloseKey` at `0x1801fd963`
- `ADVAPI32!RegCloseKey` at `0x1801fd9d2`
- `ADVAPI32!RegOpenKeyExW` at `0x1801fd82d`
- `ADVAPI32!RegOpenKeyExW` at `0x1801fd8c6`
- `ADVAPI32!RegOpenKeyExW` at `0x1801fd8ef`
- `ADVAPI32!RegOpenKeyExW` at `0x1801fd82d`
- `ADVAPI32!RegOpenKeyExW` at `0x1801fd8c6`
- `ADVAPI32!RegOpenKeyExW` at `0x1801fd8ef`
- `ADVAPI32!RegEnumKeyW` at `0x1801fd7f7`
- `ADVAPI32!RegEnumKeyW` at `0x1801fd938`
- `ADVAPI32!RegEnumKeyW` at `0x1801fd9b9`
- `ADVAPI32!RegEnumKeyW` at `0x1801fd7f7`
- `ADVAPI32!RegEnumKeyW` at `0x1801fd938`
- `ADVAPI32!RegEnumKeyW` at `0x1801fd9b9`
- `KERNEL32!CompareStringW` at `0x1801fd865`
- `KERNEL32!CompareStringW` at `0x1801fd895`
- `KERNEL32!CompareStringW` at `0x1801fd865`
- `KERNEL32!CompareStringW` at `0x1801fd895`
- `ole32!StringFromGUID2` at `0x1801fd759`
- `ole32!StringFromGUID2` at `0x1801fd759`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1801fd73d`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1801fda2c`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1801fd73d`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1801fda2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AfxOleUnregisterTypeLib(const _GUID *tlid, WORD wVerMajor, WORD wVerMinor, LCID lcid)
{
  WORD v4; // r15
  DWORD v7; // r14d
  int v9; // esi
  int v10; // edi
  unsigned int v11; // ebx
  int v12; // r15d
  DWORD v13; // esi
  DWORD i; // edx
  wchar_t *v15; // rdx
  int v16; // [rsp+30h] [rbp-D0h]
  ITypeLib *pDummy; // [rsp+38h] [rbp-C8h] BYREF
  WORD v18; // [rsp+40h] [rbp-C0h]
  HKEY__ *hKeyVersion; // [rsp+48h] [rbp-B8h] BYREF
  HKEY__ *hKeyTypeLib; // [rsp+50h] [rbp-B0h] BYREF
  ITypeLib *pTypeLib; // [rsp+58h] [rbp-A8h] BYREF
  LCID v22; // [rsp+60h] [rbp-A0h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strTypeLibID; // [rsp+68h] [rbp-98h] BYREF
  HKEY__ *hkey; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szTypeLibID[40]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t szLocale[264]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t szVersion[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wchar_t szKeyTypeLib[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v22 = lcid;
  v4 = wVerMinor;
  v18 = wVerMinor;
  v7 = 0;
  pTypeLib = 0;
  if ( wVerMajor && LoadRegTypeLib(tlid, wVerMajor, wVerMinor, lcid, &pTypeLib) < 0 )
    pTypeLib = 0;
  if ( StringFromGUID2(tlid, szTypeLibID, 39) != 39 )
    return 0;
  v9 = 0;
  v16 = 0;
  v10 = 0;
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strTypeLibID,
    szTypeLibID);
  if ( swprintf_s(szKeyTypeLib, 0x104u, L"TYPELIB\\%Ts", strTypeLibID.m_pszData) == -1 )
  {
LABEL_40:
    v11 = 0;
    goto LABEL_41;
  }
  v11 = 1;
  if ( AfxRegOpenKeyEx((HKEY__ *)0xFFFFFFFF80000000LL, szKeyTypeLib, 0, 0x30019u, &hKeyTypeLib, 0) )
    goto LABEL_30;
  if ( RegEnumKeyW(hKeyTypeLib, 0, szVersion, 0x104u) )
    goto LABEL_29;
  do
  {
    hKeyVersion = 0;
    v12 = 0;
    if ( RegOpenKeyExW(hKeyTypeLib, szVersion, 0, 0x30019u, &hKeyVersion) )
      goto LABEL_25;
    v13 = 0;
    for ( i = 0; !RegEnumKeyW(hKeyVersion, i, szLocale, 0x104u); i = v13 )
    {
      if ( CompareStringW(0x7Fu, 1u, szLocale, -1, L"HELPDIR", -1) == 2 )
        goto LABEL_16;
      if ( CompareStringW(0x7Fu, 1u, szLocale, -1, L"FLAGS", -1) == 2 )
        goto LABEL_16;
      pDummy = 0;
      if ( RegOpenKeyExW(hKeyVersion, szLocale, 0, 0x30019u, (PHKEY)&pDummy) )
        goto LABEL_16;
      if ( !RegOpenKeyExW((HKEY)pDummy, L"win32", 0, 0x20000u, &hkey) )
      {
        RegCloseKey(hkey);
        v10 = _AfxRecursiveRegDeleteKey((HKEY__ *)pDummy, (wchar_t *)L"win64");
        v12 = 1;
        RegCloseKey((HKEY)pDummy);
LABEL_16:
        ++v13;
        continue;
      }
      RegCloseKey((HKEY)pDummy);
      if ( _AfxRecursiveRegDeleteKey(hKeyVersion, szLocale) )
        goto LABEL_16;
      v13 = 0;
    }
    RegCloseKey(hKeyVersion);
    if ( v12 )
    {
      v9 = 1;
      v16 = 1;
      goto LABEL_26;
    }
    if ( !_AfxRecursiveRegDeleteKey(hKeyTypeLib, szVersion) )
    {
      v7 = 0;
      v9 = v16;
      continue;
    }
LABEL_25:
    v9 = v16;
LABEL_26:
    ++v7;
  }
  while ( !RegEnumKeyW(hKeyTypeLib, v7, szVersion, 0x104u) );
  v4 = v18;
LABEL_29:
  RegCloseKey(hKeyTypeLib);
  if ( !v9 )
LABEL_30:
    v10 = _AfxRecursiveRegDeleteKey((HKEY__ *)0xFFFFFFFF80000000LL, szKeyTypeLib);
  if ( v10 && v10 != 1010 && v10 != 2 )
    goto LABEL_40;
  if ( pTypeLib )
  {
    pDummy = 0;
    if ( LoadRegTypeLib(tlid, wVerMajor, v4, v22, &pDummy) >= 0 )
      pDummy->Release(pDummy);
    else
      _AfxUnregisterInterfaces(pTypeLib);
    pTypeLib->Release(pTypeLib);
  }
LABEL_41:
  v15 = strTypeLibID.m_pszData - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)strTypeLibID.m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
  return v11;
}

```

## disassembly

```asm
0x1801fd6e0  push    rbp
0x1801fd6e2  push    rbx
0x1801fd6e3  push    rsi
0x1801fd6e4  push    rdi
0x1801fd6e5  push    r12
0x1801fd6e7  push    r13
0x1801fd6e9  push    r14
0x1801fd6eb  push    r15
0x1801fd6ed  lea     rbp, [rsp-618h]
0x1801fd6f5  sub     rsp, 718h
0x1801fd6fc  mov     rax, cs:__security_cookie
0x1801fd703  xor     rax, rsp
0x1801fd706  mov     [rbp+650h+var_50], rax
0x1801fd70d  mov     [rsp+750h+var_6F0], lcid
0x1801fd712  movzx   r15d, wVerMinor
0x1801fd716  mov     [rsp+750h+var_710], wVerMinor
0x1801fd71c  movzx   r13d, wVerMajor
0x1801fd720  mov     r12, tlid
0x1801fd723  xor     r14d, r14d
0x1801fd726  mov     [rsp+750h+pTypeLib], r14
0x1801fd72b  test    wVerMajor, wVerMajor
0x1801fd72e  jz      short loc_1801FD74C
0x1801fd730  lea     tlid, [rsp+750h+pTypeLib]
0x1801fd735  mov     [rsp+750h+pptlib], tlid; pptlib
0x1801fd73a  mov     tlid, r12; rguid
0x1801fd73d  call    cs:__imp_LoadRegTypeLib
0x1801fd743  test    eax, eax
0x1801fd745  jns     short loc_1801FD74C
0x1801fd747  mov     [rsp+750h+pTypeLib], r14
0x1801fd74c  mov     r8d, 27h ; '''; cchMax
0x1801fd752  lea     rdx, [rbp+650h+szTypeLibID]; lpsz
0x1801fd756  mov     tlid, r12; rguid
0x1801fd759  call    cs:__imp_StringFromGUID2
0x1801fd75f  cmp     eax, 27h ; '''
0x1801fd762  jz      short loc_1801FD76B
0x1801fd764  xor     eax, eax
0x1801fd766  jmp     loc_1801FDA9E
0x1801fd76b  mov     esi, r14d
0x1801fd76e  mov     [rsp+750h+var_720], r14d
0x1801fd773  mov     edi, r14d
0x1801fd776  lea     rdx, [rbp+650h+szTypeLibID]; pszSrc
0x1801fd77a  lea     tlid, [rsp+750h+strTypeLibID]; this
0x1801fd77f  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x1801fd784  nop
0x1801fd785  mov     r9, [rsp+750h+strTypeLibID.m_pszData]
0x1801fd78a  lea     r8, aTypelibTs; "TYPELIB\\%Ts"
0x1801fd791  mov     edx, 104h; _BufferCount
0x1801fd796  lea     tlid, [rbp+650h+szKeyTypeLib]; _Buffer
0x1801fd79d  call    swprintf_s
0x1801fd7a2  cmp     eax, 0FFFFFFFFh
0x1801fd7a5  jz      loc_1801FDA73
0x1801fd7ab  mov     [rsp+750h+pTM], r14; pTM
0x1801fd7b0  lea     rax, [rsp+750h+hKeyTypeLib]
0x1801fd7b5  mov     [rsp+750h+pptlib], rax; phkResult
0x1801fd7ba  mov     lcid, 30019h; samDesired
0x1801fd7c0  xor     r8d, r8d; ulOptions
0x1801fd7c3  lea     rdx, [rbp+650h+szKeyTypeLib]; lpSubKey
0x1801fd7ca  mov     tlid, 0FFFFFFFF80000000h; hKey
0x1801fd7d1  call    ?AfxRegOpenKeyEx@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@PEAVCAtlTransactionManager@ATL@@@Z; AfxRegOpenKeyEx(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *,ATL::CAtlTransactionManager *)
0x1801fd7d6  mov     ebx, 1
0x1801fd7db  test    eax, eax
0x1801fd7dd  jnz     loc_1801FD9DF
0x1801fd7e3  mov     lcid, 104h; cchName
0x1801fd7e9  lea     r8, [rbp+650h+szVersion]; lpName
0x1801fd7f0  xor     edx, edx; dwIndex
0x1801fd7f2  mov     tlid, [rsp+750h+hKeyTypeLib]; hKey
0x1801fd7f7  call    cs:__imp_RegEnumKeyW
0x1801fd7fd  test    eax, eax
0x1801fd7ff  jnz     loc_1801FD9CD
0x1801fd805  and     [rsp+750h+hKeyVersion], 0
0x1801fd80b  xor     r15d, r15d
0x1801fd80e  lea     rax, [rsp+750h+hKeyVersion]
0x1801fd813  mov     [rsp+750h+pptlib], rax; phkResult
0x1801fd818  mov     lcid, 30019h; samDesired
0x1801fd81e  xor     r8d, r8d; ulOptions
0x1801fd821  lea     rdx, [rbp+650h+szVersion]; lpSubKey
0x1801fd828  mov     tlid, [rsp+750h+hKeyTypeLib]; hKey
0x1801fd82d  call    cs:__imp_RegOpenKeyExW
0x1801fd833  test    eax, eax
0x1801fd835  jnz     loc_1801FD99D
0x1801fd83b  xor     esi, esi
0x1801fd83d  xor     edx, edx
0x1801fd83f  jmp     loc_1801FD929
0x1801fd844  or      ecx, 0FFFFFFFFh
0x1801fd847  mov     dword ptr [rsp+750h+pTM], ecx; cchCount2
0x1801fd84b  lea     rax, aHelpdir; "HELPDIR"
0x1801fd852  mov     [rsp+750h+pptlib], rax; lpString2
0x1801fd857  mov     lcid, ecx; cchCount1
0x1801fd85a  lea     r8, [rbp+650h+szLocale]; lpString1
0x1801fd85e  mov     edx, ebx; dwCmpFlags
0x1801fd860  mov     ecx, 7Fh; Locale
0x1801fd865  call    cs:__imp_CompareStringW
0x1801fd86b  cmp     eax, 2
0x1801fd86e  jz      loc_1801FD925
0x1801fd874  or      ecx, 0FFFFFFFFh
0x1801fd877  mov     dword ptr [rsp+750h+pTM], ecx; cchCount2
0x1801fd87b  lea     rax, aFlags; "FLAGS"
0x1801fd882  mov     [rsp+750h+pptlib], rax; lpString2
0x1801fd887  mov     lcid, ecx; cchCount1
0x1801fd88a  lea     r8, [rbp+650h+szLocale]; lpString1
0x1801fd88e  mov     edx, ebx; dwCmpFlags
0x1801fd890  mov     ecx, 7Fh; Locale
0x1801fd895  call    cs:__imp_CompareStringW
0x1801fd89b  cmp     eax, 2
0x1801fd89e  jz      loc_1801FD925
0x1801fd8a4  and     [rsp+750h+pDummy], 0
0x1801fd8aa  lea     rax, [rsp+750h+pDummy]
0x1801fd8af  mov     [rsp+750h+pptlib], rax; phkResult
0x1801fd8b4  mov     lcid, 30019h; samDesired
0x1801fd8ba  xor     r8d, r8d; ulOptions
0x1801fd8bd  lea     rdx, [rbp+650h+szLocale]; lpSubKey
0x1801fd8c1  mov     tlid, [rsp+750h+hKeyVersion]; hKey
0x1801fd8c6  call    cs:__imp_RegOpenKeyExW
0x1801fd8cc  test    eax, eax
0x1801fd8ce  jnz     short loc_1801FD925
0x1801fd8d0  lea     rax, [rsp+750h+hkey]
0x1801fd8d5  mov     [rsp+750h+pptlib], rax; phkResult
0x1801fd8da  mov     lcid, 20000h; samDesired
0x1801fd8e0  xor     r8d, r8d; ulOptions
0x1801fd8e3  lea     rdx, aWin32; "win32"
0x1801fd8ea  mov     tlid, [rsp+750h+pDummy]; hKey
0x1801fd8ef  call    cs:__imp_RegOpenKeyExW
0x1801fd8f5  test    eax, eax
0x1801fd8f7  jnz     short loc_1801FD95E
0x1801fd8f9  mov     tlid, [rsp+750h+hkey]; hKey
0x1801fd8fe  call    cs:__imp_RegCloseKey
0x1801fd904  lea     rdx, aWin64; "win64"
0x1801fd90b  mov     tlid, [rsp+750h+pDummy]; hParentKey
0x1801fd910  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEA_W@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,wchar_t *)
0x1801fd915  mov     edi, eax
0x1801fd917  mov     r15d, ebx
0x1801fd91a  mov     tlid, [rsp+750h+pDummy]; hKey
0x1801fd91f  call    cs:__imp_RegCloseKey
0x1801fd925  add     esi, ebx
0x1801fd927  mov     edx, esi; dwIndex
0x1801fd929  mov     lcid, 104h; cchName
0x1801fd92f  lea     r8, [rbp+650h+szLocale]; lpName
0x1801fd933  mov     tlid, [rsp+750h+hKeyVersion]; hKey
0x1801fd938  call    cs:__imp_RegEnumKeyW
0x1801fd93e  test    eax, eax
0x1801fd940  jz      loc_1801FD844
0x1801fd946  mov     tlid, [rsp+750h+hKeyVersion]; hKey
0x1801fd94b  call    cs:__imp_RegCloseKey
0x1801fd951  test    r15d, r15d
0x1801fd954  jz      short loc_1801FD97F
0x1801fd956  mov     esi, ebx
0x1801fd958  mov     [rsp+750h+var_720], ebx
0x1801fd95c  jmp     short loc_1801FD9A1
0x1801fd95e  mov     tlid, [rsp+750h+pDummy]; hKey
0x1801fd963  call    cs:__imp_RegCloseKey
0x1801fd969  lea     rdx, [rbp+650h+szLocale]; szKeyName
0x1801fd96d  mov     tlid, [rsp+750h+hKeyVersion]; hParentKey
0x1801fd972  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEA_W@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,wchar_t *)
0x1801fd977  test    eax, eax
0x1801fd979  jnz     short loc_1801FD925
0x1801fd97b  xor     esi, esi
0x1801fd97d  jmp     short loc_1801FD927
0x1801fd97f  lea     rdx, [rbp+650h+szVersion]; szKeyName
0x1801fd986  mov     tlid, [rsp+750h+hKeyTypeLib]; hParentKey
0x1801fd98b  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEA_W@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,wchar_t *)
0x1801fd990  test    eax, eax
0x1801fd992  jnz     short loc_1801FD99D
0x1801fd994  xor     r14d, r14d
0x1801fd997  mov     esi, [rsp+750h+var_720]
0x1801fd99b  jmp     short loc_1801FD9A4
0x1801fd99d  mov     esi, [rsp+750h+var_720]
0x1801fd9a1  add     r14d, ebx
0x1801fd9a4  mov     lcid, 104h; cchName
0x1801fd9aa  lea     r8, [rbp+650h+szVersion]; lpName
0x1801fd9b1  mov     edx, r14d; dwIndex
0x1801fd9b4  mov     tlid, [rsp+750h+hKeyTypeLib]; hKey
0x1801fd9b9  call    cs:__imp_RegEnumKeyW
0x1801fd9bf  test    eax, eax
0x1801fd9c1  jz      loc_1801FD805
0x1801fd9c7  movzx   r15d, [rsp+750h+var_710]
0x1801fd9cd  mov     tlid, [rsp+750h+hKeyTypeLib]; hKey
0x1801fd9d2  call    cs:__imp_RegCloseKey
0x1801fd9d8  xor     r14d, r14d
0x1801fd9db  test    esi, esi
0x1801fd9dd  jnz     short loc_1801FD9F4
0x1801fd9df  lea     rdx, [rbp+650h+szKeyTypeLib]; szKeyName
0x1801fd9e6  mov     tlid, 0FFFFFFFF80000000h; hParentKey
0x1801fd9ed  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEA_W@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,wchar_t *)
0x1801fd9f2  mov     edi, eax
0x1801fd9f4  mov     esi, 3F2h
0x1801fd9f9  test    edi, edi
0x1801fd9fb  jz      short loc_1801FDA06
0x1801fd9fd  cmp     edi, esi
0x1801fd9ff  jz      short loc_1801FDA06
0x1801fda01  cmp     edi, 2
0x1801fda04  jnz     short loc_1801FDA73
0x1801fda06  cmp     [rsp+750h+pTypeLib], r14
0x1801fda0b  jz      short loc_1801FDA66
0x1801fda0d  mov     [rsp+750h+pDummy], r14
0x1801fda12  lea     rax, [rsp+750h+pDummy]
0x1801fda17  mov     [rsp+750h+pptlib], rax; pptlib
0x1801fda1c  mov     lcid, [rsp+750h+var_6F0]; lcid
0x1801fda21  movzx   r8d, r15w; wVerMinor
0x1801fda25  movzx   edx, r13w; wVerMajor
0x1801fda29  mov     tlid, r12; rguid
0x1801fda2c  call    cs:__imp_LoadRegTypeLib
0x1801fda32  test    eax, eax
0x1801fda34  jns     short loc_1801FDA42
0x1801fda36  mov     tlid, [rsp+750h+pTypeLib]; pTypeLib
0x1801fda3b  call    ?_AfxUnregisterInterfaces@@YAXPEAUITypeLib@@@Z; _AfxUnregisterInterfaces(ITypeLib *)
0x1801fda40  jmp     short loc_1801FDA54
0x1801fda42  mov     tlid, [rsp+750h+pDummy]
0x1801fda47  mov     rax, [tlid]
0x1801fda4a  mov     rax, [rax+10h]
0x1801fda4e  call    cs:__guard_dispatch_icall_fptr
0x1801fda54  mov     tlid, [rsp+750h+pTypeLib]
0x1801fda59  mov     rax, [tlid]
0x1801fda5c  mov     rax, [rax+10h]
0x1801fda60  call    cs:__guard_dispatch_icall_fptr
0x1801fda66  test    edi, edi
0x1801fda68  jz      short loc_1801FDA76
0x1801fda6a  cmp     edi, esi
0x1801fda6c  jz      short loc_1801FDA76
0x1801fda6e  cmp     edi, 2
0x1801fda71  jz      short loc_1801FDA76
0x1801fda73  mov     ebx, r14d
0x1801fda76  mov     rdx, [rsp+750h+strTypeLibID.m_pszData]
0x1801fda7b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1801fda7f  or      ecx, 0FFFFFFFFh
0x1801fda82  lock xadd [rdx+10h], ecx
0x1801fda87  sub     ecx, 1
0x1801fda8a  jg      short loc_1801FDA9C
0x1801fda8c  mov     tlid, [rdx]
0x1801fda8f  mov     r8, [tlid]
0x1801fda92  mov     rax, [r8+8]
0x1801fda96  call    cs:__guard_dispatch_icall_fptr
0x1801fda9c  mov     eax, ebx
0x1801fda9e  mov     tlid, [rbp+650h+var_50]
0x1801fdaa5  xor     tlid, rsp; StackCookie
0x1801fdaa8  call    __security_check_cookie
0x1801fdaad  add     rsp, 718h
0x1801fdab4  pop     r15
0x1801fdab6  pop     r14
0x1801fdab8  pop     r13
0x1801fdaba  pop     r12
0x1801fdabc  pop     rdi
0x1801fdabd  pop     rsi
0x1801fdabe  pop     rbx
0x1801fdabf  pop     rbp
0x1801fdac0  retn
```
