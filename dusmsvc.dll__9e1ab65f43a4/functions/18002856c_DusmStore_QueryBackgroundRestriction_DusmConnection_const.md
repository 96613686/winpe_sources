# DusmStore::QueryBackgroundRestriction(DusmConnection const &)

- ea: `0x18002856c`
- end: `0x180028866`
- name: `?QueryBackgroundRestriction@DusmStore@@SA?AW4_DUSM_BACKGROUND_RESTRICTION@@AEBVDusmConnection@@@Z`
- size: `762`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800148b0`
- `0x18001f54c`
- `0x1800203f4`
- `0x18002051c`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000e7e0`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x18001d87c`
- `0x180025a24`
- `0x180026fa0`
- `0x18002856c`
- `0x18002886c`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800285c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800285c7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800285ef`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800285ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028682`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028682`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028759`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028759`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DusmStore::QueryBackgroundRestriction(__int64 a1)
{
  int v2; // esi
  LPCRITICAL_SECTION v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  const WCHAR *v6; // rax
  __int64 v8; // rax
  char v9; // bl
  const WCHAR *v10; // rax
  unsigned int v11; // ebx
  const char *pvData; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v13; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v17; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcbData; // [rsp+9Ch] [rbp-64h] BYREF
  _BYTE v19[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v20[32]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[40]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v2 = *(_DWORD *)(a1 + 16);
  if ( v2 == 3 )
  {
    if ( !*(_QWORD *)(a1 + 160) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x6AB,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryBackgroundRestriction::iccid",
        pvData);
    return DusmStore::QueryBackgroundRestrictionFromStore(a1, a1);
  }
  else
  {
    if ( v2 == 2 )
    {
      if ( !*(_QWORD *)(a1 + 64) )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x6B0,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::QueryBackgroundRestriction::profileName",
          pvData);
    }
    else if ( v2 != 1 )
    {
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x699,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryBackgroundRestriction::mediaType",
        pvData);
    }
    v3 = DusmStore::s_pInstance;
    EnterCriticalSection(DusmStore::s_pInstance);
    v13 = v3;
    memset_0(sz, 0, sizeof(sz));
    if ( !StringFromGUID2((const GUID *const)(a1 + 32), sz, 40) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x6BD,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0xE,
        (unsigned int)"DusmStore::QueryBackgroundRestriction::StringFromGUID2",
        pvData);
    v4 = std::wstring::wstring((__int64)v15, (__int64)qword_180068EC0);
    v5 = std::operator+<wchar_t>((__int64)v14, v4, (__int64)L"\\");
    std::operator+<wchar_t>((__int64)v19, v5, (__int64)sz);
    std::wstring::_Tidy_deallocate(v14);
    std::wstring::_Tidy_deallocate(v15);
    hkey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v19);
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hkey) )
      goto LABEL_8;
    if ( v2 == 1 )
    {
      v8 = std::wstring::wstring((__int64)v14, (__int64)L"*");
      v9 = 1;
    }
    else
    {
      v8 = std::wstring::wstring((__int64)v15, a1 + 48);
      v9 = 2;
    }
    std::wstring::wstring((__int64)v20, v8);
    if ( (v9 & 2) != 0 )
    {
      v9 &= ~2u;
      std::wstring::_Tidy_deallocate(v15);
    }
    if ( (v9 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v14);
    v17 = 0;
    pcbData = 4;
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20);
    if ( RegGetValueW(hkey, v10, L"BackgroundRestriction", 0x10u, 0, &v17, &pcbData) )
    {
      std::wstring::_Tidy_deallocate(v20);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      std::wstring::_Tidy_deallocate(v19);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
      return 0;
    }
    v11 = v17;
    std::wstring::_Tidy_deallocate(v20);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    std::wstring::_Tidy_deallocate(v19);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
    return v11;
  }
}

```

## disassembly

```asm
0x18002856c  push    rbp
0x18002856e  push    rbx
0x18002856f  push    rsi
0x180028570  push    rdi
0x180028571  lea     rbp, [rsp-48h]
0x180028576  sub     rsp, 148h
0x18002857d  mov     rax, cs:__security_cookie
0x180028584  xor     rax, rsp
0x180028587  mov     [rbp+60h+var_30], rax
0x18002858b  mov     rdi, rcx
0x18002858e  mov     [rsp+160h+var_120], 0
0x180028596  mov     esi, [rcx+10h]
0x180028599  cmp     esi, 3
0x18002859c  jz      loc_18002879C
0x1800285a2  cmp     esi, 2
0x1800285a5  jz      short loc_1800285B2
0x1800285a7  cmp     esi, 1
0x1800285aa  jnz     loc_1800287EE
0x1800285b0  jmp     short loc_1800285BD
0x1800285b2  cmp     qword ptr [rcx+40h], 0
0x1800285b7  jz      loc_180028816
0x1800285bd  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x1800285c4  mov     rcx, rbx; lpCriticalSection
0x1800285c7  call    cs:__imp_EnterCriticalSection
0x1800285cd  mov     [rsp+160h+var_118], rbx
0x1800285d2  xor     edx, edx; Val
0x1800285d4  lea     r8d, [rdx+50h]; Size
0x1800285d8  lea     rcx, [rbp+60h+sz]; void *
0x1800285dc  call    memset_0
0x1800285e1  lea     rcx, [rdi+20h]; rguid
0x1800285e5  mov     r8d, 28h ; '('; cchMax
0x1800285eb  lea     rdx, [rbp+60h+sz]; lpsz
0x1800285ef  call    cs:__imp_StringFromGUID2
0x1800285f5  test    eax, eax
0x1800285f7  jz      loc_18002883E
0x1800285fd  mov     rdx, cs:qword_180068EC0
0x180028604  lea     rcx, [rsp+160h+var_F0]
0x180028609  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002860e  nop
0x18002860f  lea     r8, asc_18004F678; "\\"
0x180028616  mov     rdx, rax
0x180028619  lea     rcx, [rsp+160h+var_110]
0x18002861e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180028623  nop
0x180028624  lea     r8, [rbp+60h+sz]
0x180028628  mov     rdx, rax
0x18002862b  lea     rcx, [rbp+60h+var_C0]
0x18002862f  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180028634  nop
0x180028635  lea     rcx, [rsp+160h+var_110]
0x18002863a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002863f  nop
0x180028640  lea     rcx, [rsp+160h+var_F0]
0x180028645  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002864a  mov     [rbp+60h+hkey], 0
0x180028652  xor     edx, edx
0x180028654  lea     rcx, [rbp+60h+hkey]
0x180028658  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002865d  lea     rcx, [rbp+60h+var_C0]
0x180028661  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028666  mov     rdx, rax; lpSubKey
0x180028669  lea     rax, [rbp+60h+hkey]
0x18002866d  mov     [rsp+160h+phkResult], rax; phkResult
0x180028672  mov     r9d, 20019h; samDesired
0x180028678  xor     r8d, r8d; ulOptions
0x18002867b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028682  call    cs:__imp_RegOpenKeyExW
0x180028688  test    eax, eax
0x18002868a  jz      short loc_1800286B1
0x18002868c  lea     rcx, [rbp+60h+hkey]
0x180028690  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028695  nop
0x180028696  lea     rcx, [rbp+60h+var_C0]
0x18002869a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002869f  nop
0x1800286a0  lea     rcx, [rsp+160h+var_118]
0x1800286a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800286aa  xor     eax, eax
0x1800286ac  jmp     loc_1800287AE
0x1800286b1  cmp     esi, 1
0x1800286b4  jnz     short loc_1800286CC
0x1800286b6  lea     rdx, SubKey; "*"
0x1800286bd  lea     rcx, [rsp+160h+var_110]
0x1800286c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800286c7  nop
0x1800286c8  mov     ebx, esi
0x1800286ca  jmp     short loc_1800286E0
0x1800286cc  lea     rdx, [rdi+30h]
0x1800286d0  lea     rcx, [rsp+160h+var_F0]
0x1800286d5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800286da  nop
0x1800286db  mov     ebx, 2
0x1800286e0  mov     [rsp+160h+var_120], ebx
0x1800286e4  mov     rdx, rax
0x1800286e7  lea     rcx, [rbp+60h+var_A0]
0x1800286eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800286f0  nop
0x1800286f1  test    bl, 2
0x1800286f4  jz      short loc_180028704
0x1800286f6  and     ebx, 0FFFFFFFDh
0x1800286f9  lea     rcx, [rsp+160h+var_F0]
0x1800286fe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028703  nop
0x180028704  test    bl, 1
0x180028707  jz      short loc_180028713
0x180028709  lea     rcx, [rsp+160h+var_110]
0x18002870e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028713  mov     [rbp+60h+var_C8], 0
0x18002871a  mov     [rbp+60h+var_C4], 4
0x180028721  lea     rcx, [rbp+60h+var_A0]
0x180028725  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002872a  mov     rdx, rax; lpSubKey
0x18002872d  lea     rax, [rbp+60h+var_C4]
0x180028731  mov     [rsp+160h+pcbData], rax; pcbData
0x180028736  lea     rax, [rbp+60h+var_C8]
0x18002873a  mov     [rsp+160h+pvData], rax; pvData
0x18002873f  mov     [rsp+160h+phkResult], 0; pdwType
0x180028748  mov     r9d, 10h; dwFlags
0x18002874e  lea     r8, Value; "BackgroundRestriction"
0x180028755  mov     rcx, [rbp+60h+hkey]; hkey
0x180028759  call    cs:__imp_RegGetValueW
0x18002875f  lea     rcx, [rbp+60h+var_A0]
0x180028763  test    eax, eax
0x180028765  jz      short loc_180028771
0x180028767  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002876c  jmp     loc_18002868C
0x180028771  mov     ebx, [rbp+60h+var_C8]
0x180028774  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028779  nop
0x18002877a  lea     rcx, [rbp+60h+hkey]
0x18002877e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028783  nop
0x180028784  lea     rcx, [rbp+60h+var_C0]
0x180028788  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002878d  nop
0x18002878e  lea     rcx, [rsp+160h+var_118]
0x180028793  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180028798  mov     eax, ebx
0x18002879a  jmp     short loc_1800287AE
0x18002879c  cmp     qword ptr [rcx+0A0h], 0
0x1800287a4  jz      short loc_1800287C6
0x1800287a6  mov     rdx, rdi
0x1800287a9  call    ?QueryBackgroundRestrictionFromStore@DusmStore@@AEAA?AW4_DUSM_BACKGROUND_RESTRICTION@@AEBVDusmConnection@@@Z; DusmStore::QueryBackgroundRestrictionFromStore(DusmConnection const &)
0x1800287ae  mov     rcx, [rbp+60h+var_30]
0x1800287b2  xor     rcx, rsp; StackCookie
0x1800287b5  call    __security_check_cookie
0x1800287ba  add     rsp, 148h
0x1800287c1  pop     rdi
0x1800287c2  pop     rsi
0x1800287c3  pop     rbx
0x1800287c4  pop     rbp
0x1800287c5  retn
0x1800287c6  mov     rcx, [rbp+68h]; this
0x1800287ca  lea     rax, aDusmstoreQuery_23; "DusmStore::QueryBackgroundRestriction::"...
0x1800287d1  mov     [rsp+160h+phkResult], rax; unsigned int
0x1800287d6  mov     r9d, 57h ; 'W'; char *
0x1800287dc  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x1800287e3  mov     edx, 6ABh; void *
0x1800287e8  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800287ee  mov     rcx, [rbp+68h]; this
0x1800287f2  lea     rax, aDusmstoreQuery_0; "DusmStore::QueryBackgroundRestriction::"...
0x1800287f9  mov     [rsp+160h+phkResult], rax; unsigned int
0x1800287fe  mov     r9d, 57h ; 'W'; char *
0x180028804  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002880b  mov     edx, 699h; void *
0x180028810  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180028816  mov     rcx, [rbp+68h]; this
0x18002881a  lea     rax, aDusmstoreQuery_22; "DusmStore::QueryBackgroundRestriction::"...
0x180028821  mov     [rsp+160h+phkResult], rax; unsigned int
0x180028826  mov     r9d, 57h ; 'W'; char *
0x18002882c  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180028833  mov     edx, 6B0h; void *
0x180028838  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002883e  mov     rcx, [rbp+68h]; this
0x180028842  lea     rax, aDusmstoreQuery_18; "DusmStore::QueryBackgroundRestriction::"...
0x180028849  mov     [rsp+160h+phkResult], rax; unsigned int
0x18002884e  mov     r9d, 0Eh; char *
0x180028854  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002885b  mov     edx, 6BDh; void *
0x180028860  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
