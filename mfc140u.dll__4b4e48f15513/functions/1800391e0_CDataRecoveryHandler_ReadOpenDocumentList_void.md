# CDataRecoveryHandler::ReadOpenDocumentList(void)

- ea: `0x1800391e0`
- end: `0x1800394c3`
- name: `?ReadOpenDocumentList@CDataRecoveryHandler@@UEAAHXZ`
- size: `739`
- prototype: `int __fastcall(CDataRecoveryHandler *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180002e40`
- `0x1800391e0`
- `0x18003b2f8`
- `0x18003c714`
- `0x180139860`
- `0x1801d8090`
- `0x1802c4640`
- `0x1802c56e6`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800393b7`
- `ADVAPI32!RegCloseKey` at `0x18003947d`
- `ADVAPI32!RegCloseKey` at `0x18003948e`
- `ADVAPI32!RegCloseKey` at `0x1800393b7`
- `ADVAPI32!RegCloseKey` at `0x18003947d`
- `ADVAPI32!RegCloseKey` at `0x18003948e`
- `ADVAPI32!RegOpenKeyExW` at `0x180039281`
- `ADVAPI32!RegOpenKeyExW` at `0x180039281`
- `ADVAPI32!RegEnumValueW` at `0x18003939d`
- `ADVAPI32!RegEnumValueW` at `0x18003939d`
- `ADVAPI32!RegDeleteKeyW` at `0x180039445`
- `ADVAPI32!RegDeleteKeyW` at `0x180039445`
- `KERNEL32!GetProcAddress` at `0x180039404`
- `KERNEL32!GetProcAddress` at `0x180039404`
- `KERNEL32!GetModuleHandleW` at `0x1800393ef`
- `KERNEL32!GetModuleHandleW` at `0x1800393ef`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003935b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003935b`

## string_xrefs

- `0x1800393fa`: `RegDeleteKeyExW`
- `0x1800393e8`: `Advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDataRecoveryHandler::ReadOpenDocumentList(CDataRecoveryHandler *this)
{
  unsigned int v2; // r15d
  AFX_MODULE_STATE *ModuleState; // rax
  HKEY AppRegistryKey; // rbx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *v5; // rax
  LSTATUS v6; // eax
  LSTATUS v7; // ebx
  HKEY__ *v8; // rdx
  DWORD v9; // esi
  DWORD i; // edx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *v11; // rbx
  int v12; // eax
  wchar_t *m_pszData; // rbx
  HMODULE ModuleHandleW; // rax
  int (__fastcall *ProcAddress)(HKEY__ *, const wchar_t *, unsigned int, unsigned int); // rax
  HKEY__ *v16; // rdx
  HKEY__ *cchValueName; // [rsp+48h] [rbp-C0h] BYREF
  ATL::CRegKey keyRestart; // [rsp+50h] [rbp-B8h] BYREF
  ATL::CRegKey keyApp; // [rsp+68h] [rbp-A0h]
  wchar_t szValueName[260]; // [rsp+80h] [rbp-88h] BYREF
  wchar_t szValue[268]; // [rsp+290h] [rbp+188h] BYREF

  v2 = 0;
  ModuleState = AfxGetModuleState();
  AppRegistryKey = CWinApp::GetAppRegistryKey(ModuleState->m_pCurrentWinApp, 0);
  *(_QWORD *)&keyApp.m_samWOW64 = AppRegistryKey;
  LODWORD(keyApp.m_pTM) = 0;
  *(_QWORD *)szValueName = 0;
  *(_QWORD *)&keyRestart.m_samWOW64 = 0;
  LODWORD(keyRestart.m_pTM) = 0;
  keyApp.m_hKey = 0;
  v5 = this->GetRestartIdentifier(this, &keyRestart);
  cchValueName = 0;
  v6 = RegOpenKeyExW(AppRegistryKey, v5->m_pszData, 0, 0x2001Fu, &cchValueName);
  if ( !v6 )
  {
    *(_QWORD *)&keyRestart.m_samWOW64 = cchValueName;
    LODWORD(keyRestart.m_pTM) = 0;
  }
  v7 = v6 != 0 ? v6 : 0;
  v8 = keyRestart.m_hKey - 6;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)keyRestart.m_hKey - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  if ( !v7 )
  {
    v9 = 0;
    szValueName[4] = 0;
    memset_0(&szValueName[5], 0, 0x206u);
    LODWORD(keyRestart.m_hKey) = 260;
    for ( i = 0;
          !RegEnumValueW(*(HKEY *)&keyRestart.m_samWOW64, i, &szValueName[4], (LPDWORD)&keyRestart, 0, 0, 0, 0);
          i = v9 )
    {
      ++v9;
      LODWORD(keyRestart.m_hKey) = 260;
      szValue[4] = 0;
      memset_0(&szValue[5], 0, 0x206u);
      LODWORD(cchValueName) = 260;
      if ( !ATL::CRegKey::QueryStringValue(
              (ATL::CRegKey *)&keyRestart.m_samWOW64,
              &szValueName[4],
              &szValue[4],
              (unsigned int *)&cchValueName) )
      {
        v11 = CMap<ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,wchar_t const *,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,wchar_t const *>::operator[](
                &this->m_mapDocNameToAutosaveName,
                &szValueName[4]);
        v12 = wcslen(&szValue[4]);
        ATL::CSimpleStringT<wchar_t,1>::SetString(v11, &szValue[4], v12);
        v2 = 1;
      }
    }
    if ( *(_QWORD *)&keyRestart.m_samWOW64 )
    {
      RegCloseKey(*(HKEY *)&keyRestart.m_samWOW64);
      *(_QWORD *)&keyRestart.m_samWOW64 = 0;
    }
    LODWORD(keyRestart.m_pTM) = 0;
    m_pszData = this->GetRestartIdentifier(this, &cchValueName)->m_pszData;
    if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
    {
      ProcAddress = `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
    }
    else
    {
      ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
      if ( ModuleHandleW )
      {
        ProcAddress = (int (__fastcall *)(HKEY__ *, const wchar_t *, unsigned int, unsigned int))GetProcAddress(
                                                                                                   ModuleHandleW,
                                                                                                   "RegDeleteKeyExW");
        `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = ProcAddress;
      }
      else
      {
        ProcAddress = `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
      }
      `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
    }
    if ( ProcAddress )
      ProcAddress(*(HKEY__ **)&keyApp.m_samWOW64, m_pszData, 0, 0);
    else
      RegDeleteKeyW(*(HKEY *)&keyApp.m_samWOW64, m_pszData);
    v16 = cchValueName - 6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)cchValueName - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
  }
  if ( *(_QWORD *)&keyRestart.m_samWOW64 )
    RegCloseKey(*(HKEY *)&keyRestart.m_samWOW64);
  if ( *(_QWORD *)&keyApp.m_samWOW64 )
    RegCloseKey(*(HKEY *)&keyApp.m_samWOW64);
  return v2;
}

```

## disassembly

```asm
0x1800391e0  mov     rax, rsp
0x1800391e3  mov     [rax+10h], rbx
0x1800391e7  mov     [rax+18h], rsi
0x1800391eb  mov     [rax+20h], r12
0x1800391ef  push    rbp
0x1800391f0  push    r14
0x1800391f2  push    r15
0x1800391f4  lea     rbp, [rax-3C8h]
0x1800391fb  sub     rsp, 4B0h
0x180039202  mov     rax, cs:__security_cookie
0x180039209  xor     rax, rsp
0x18003920c  mov     [rbp+3C0h+var_20], rax
0x180039213  mov     r14, this
0x180039216  xor     r12d, r12d
0x180039219  mov     r15d, r12d
0x18003921c  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180039221  xor     edx, edx; pTM
0x180039223  mov     this, [rax+8]; this
0x180039227  call    ?GetAppRegistryKey@CWinApp@@QEAAPEAUHKEY__@@PEAVCAtlTransactionManager@ATL@@@Z; CWinApp::GetAppRegistryKey(ATL::CAtlTransactionManager *)
0x18003922c  mov     rbx, rax
0x18003922f  mov     qword ptr [rsp+4C0h+keyApp.m_samWOW64], rax
0x180039234  mov     dword ptr [rsp+4C0h+keyApp.m_pTM], r12d
0x180039239  mov     qword ptr [rsp+4C0h+szValueName], r12
0x18003923e  mov     qword ptr [rsp+4C0h+keyRestart.m_samWOW64], r12
0x180039243  mov     dword ptr [rsp+4C0h+keyRestart.m_pTM], r12d
0x180039248  mov     [rsp+4C0h+keyApp.m_hKey], r12
0x18003924d  mov     this, [r14]
0x180039250  mov     rax, [this+50h]
0x180039254  lea     rdx, [rsp+4C0h+keyRestart]
0x180039259  mov     this, r14
0x18003925c  call    cs:__guard_dispatch_icall_fptr
0x180039262  nop
0x180039263  mov     [rsp+4C0h+cchValueName], r12
0x180039268  lea     this, [rsp+4C0h+cchValueName]
0x18003926d  mov     [rsp+4C0h+phkResult], this; phkResult
0x180039272  mov     r9d, 2001Fh; samDesired
0x180039278  xor     r8d, r8d; ulOptions
0x18003927b  mov     rdx, [rax]; lpSubKey
0x18003927e  mov     this, rbx; hKey
0x180039281  call    cs:__imp_RegOpenKeyExW
0x180039287  test    eax, eax
0x180039289  jnz     short loc_18003929A
0x18003928b  mov     this, [rsp+4C0h+cchValueName]
0x180039290  mov     qword ptr [rsp+4C0h+keyRestart.m_samWOW64], this
0x180039295  mov     dword ptr [rsp+4C0h+keyRestart.m_pTM], r12d
0x18003929a  mov     ecx, eax
0x18003929c  neg     ecx
0x18003929e  sbb     ebx, ebx
0x1800392a0  and     ebx, eax
0x1800392a2  mov     rdx, [rsp+4C0h+keyRestart.m_hKey]
0x1800392a7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800392ab  or      eax, 0FFFFFFFFh
0x1800392ae  lock xadd [rdx+10h], eax
0x1800392b3  sub     eax, 1
0x1800392b6  jg      short loc_1800392C8
0x1800392b8  mov     this, [rdx]
0x1800392bb  mov     rax, [this]
0x1800392be  mov     rax, [rax+8]
0x1800392c2  call    cs:__guard_dispatch_icall_fptr
0x1800392c8  test    ebx, ebx
0x1800392ca  jnz     loc_180039473
0x1800392d0  mov     esi, r12d
0x1800392d3  mov     [rbp+3C0h+szValueName+8], r12w
0x1800392d8  xor     edx, edx; Val
0x1800392da  mov     r8d, 206h; Size
0x1800392e0  lea     this, [rbp+3C0h+szValueName+0Ah]; void *
0x1800392e4  call    memset_0
0x1800392e9  mov     dword ptr [rsp+4C0h+keyRestart.m_hKey], 104h
0x1800392f1  xor     edx, edx
0x1800392f3  jmp     loc_18003937B
0x1800392f8  inc     esi
0x1800392fa  mov     dword ptr [rsp+4C0h+keyRestart.m_hKey], 104h
0x180039302  mov     [rbp+3C0h+szValue+8], r12w
0x18003930a  xor     edx, edx; Val
0x18003930c  mov     r8d, 206h; Size
0x180039312  lea     this, [rbp+3C0h+szValue+0Ah]; void *
0x180039319  call    memset_0
0x18003931e  mov     dword ptr [rsp+4C0h+cchValueName], 104h
0x180039326  lea     r9, [rsp+4C0h+cchValueName]; pnChars
0x18003932b  lea     r8, [rbp+3C0h+szValue+8]; pszValue
0x180039332  lea     rdx, [rbp+3C0h+szValueName+8]; pszValueName
0x180039336  lea     this, [rsp+4C0h+keyRestart.m_samWOW64]; this
0x18003933b  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEB_WPEA_WPEAK@Z; ATL::CRegKey::QueryStringValue(wchar_t const *,wchar_t *,ulong *)
0x180039340  test    eax, eax
0x180039342  jnz     short loc_180039379
0x180039344  lea     this, [r14+8]; this
0x180039348  lea     rdx, [rbp+3C0h+szValueName+8]; key
0x18003934c  call    ??A?$CMap@V?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@PEB_WV12@PEB_W@@QEAAAEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@PEB_W@Z; CMap<ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,wchar_t const *,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,wchar_t const *>::operator[](wchar_t const *)
0x180039351  mov     rbx, rax
0x180039354  lea     this, [rbp+3C0h+szValue+8]; String
0x18003935b  call    cs:__imp_wcslen
0x180039361  mov     r8d, eax; nLength
0x180039364  lea     rdx, [rbp+3C0h+szValue+8]; pszSrc
0x18003936b  mov     this, rbx; this
0x18003936e  call    ?SetString@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::SetString(wchar_t const *,int)
0x180039373  mov     r15d, 1
0x180039379  mov     edx, esi; dwIndex
0x18003937b  mov     [rsp+4C0h+cchValue], r12; lpcbData
0x180039380  mov     [rsp+4C0h+lpData], r12; lpData
0x180039385  mov     [rsp+4C0h+lpType], r12; lpType
0x18003938a  mov     [rsp+4C0h+phkResult], r12; lpReserved
0x18003938f  lea     r9, [rsp+4C0h+keyRestart]; lpcchValueName
0x180039394  lea     r8, [rbp+3C0h+szValueName+8]; lpValueName
0x180039398  mov     this, qword ptr [rsp+4C0h+keyRestart.m_samWOW64]; hKey
0x18003939d  call    cs:__imp_RegEnumValueW
0x1800393a3  test    eax, eax
0x1800393a5  jz      loc_1800392F8
0x1800393ab  cmp     qword ptr [rsp+4C0h+keyRestart.m_samWOW64], r12
0x1800393b0  jz      short loc_1800393C2
0x1800393b2  mov     this, qword ptr [rsp+4C0h+keyRestart.m_samWOW64]; hKey
0x1800393b7  call    cs:__imp_RegCloseKey
0x1800393bd  mov     qword ptr [rsp+4C0h+keyRestart.m_samWOW64], r12
0x1800393c2  mov     dword ptr [rsp+4C0h+keyRestart.m_pTM], r12d
0x1800393c7  mov     rax, [r14]
0x1800393ca  lea     rdx, [rsp+4C0h+cchValueName]
0x1800393cf  mov     this, r14
0x1800393d2  mov     rax, [rax+50h]
0x1800393d6  call    cs:__guard_dispatch_icall_fptr
0x1800393dc  mov     rbx, [rax]
0x1800393df  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4_NA, r12b; bool `ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::bInitialized
0x1800393e6  jnz     short loc_180039423
0x1800393e8  lea     this, aAdvapi32Dll_0; "Advapi32.dll"
0x1800393ef  call    cs:__imp_GetModuleHandleW
0x1800393f5  test    rax, rax
0x1800393f8  jz      short loc_180039413
0x1800393fa  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180039401  mov     this, rax; hModule
0x180039404  call    cs:__imp_GetProcAddress
0x18003940a  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x180039411  jmp     short loc_18003941A
0x180039413  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x18003941a  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4_NA, 1; bool `ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::bInitialized
0x180039421  jmp     short loc_18003942A
0x180039423  mov     rax, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x18003942a  mov     rdx, rbx; lpSubKey
0x18003942d  mov     this, qword ptr [rsp+4C0h+keyApp.m_samWOW64]; hKey
0x180039432  test    rax, rax
0x180039435  jz      short loc_180039445
0x180039437  xor     r9d, r9d
0x18003943a  xor     r8d, r8d
0x18003943d  call    cs:__guard_dispatch_icall_fptr
0x180039443  jmp     short loc_18003944C
0x180039445  call    cs:__imp_RegDeleteKeyW
0x18003944b  nop
0x18003944c  mov     rdx, [rsp+4C0h+cchValueName]
0x180039451  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180039455  or      eax, 0FFFFFFFFh
0x180039458  lock xadd [rdx+10h], eax
0x18003945d  sub     eax, 1
0x180039460  jg      short loc_180039473
0x180039462  mov     this, [rdx]
0x180039465  mov     rax, [this]
0x180039468  mov     rax, [rax+8]
0x18003946c  call    cs:__guard_dispatch_icall_fptr
0x180039472  nop
0x180039473  mov     this, qword ptr [rsp+4C0h+keyRestart.m_samWOW64]; hKey
0x180039478  test    this, this
0x18003947b  jz      short loc_180039484
0x18003947d  call    cs:__imp_RegCloseKey
0x180039483  nop
0x180039484  mov     this, qword ptr [rsp+4C0h+keyApp.m_samWOW64]; hKey
0x180039489  test    this, this
0x18003948c  jz      short loc_180039494
0x18003948e  call    cs:__imp_RegCloseKey
0x180039494  mov     eax, r15d
0x180039497  mov     this, [rbp+3C0h+var_20]
0x18003949e  xor     this, rsp; StackCookie
0x1800394a1  call    __security_check_cookie
0x1800394a6  lea     r11, [rsp+4C0h+var_10]
0x1800394ae  mov     rbx, [r11+28h]
0x1800394b2  mov     rsi, [r11+30h]
0x1800394b6  mov     r12, [r11+38h]
0x1800394ba  mov     rsp, r11
0x1800394bd  pop     r15
0x1800394bf  pop     r14
0x1800394c1  pop     rbp
0x1800394c2  retn
```
