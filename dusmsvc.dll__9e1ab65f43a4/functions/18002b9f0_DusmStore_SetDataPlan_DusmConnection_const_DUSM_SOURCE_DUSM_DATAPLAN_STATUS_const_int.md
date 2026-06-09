# DusmStore::SetDataPlan(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS const &,int)

- ea: `0x18002b9f0`
- end: `0x18002bdee`
- name: `?SetDataPlan@DusmStore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_DATAPLAN_STATUS@@H@Z`
- size: `1022`
- prototype: `__int64 __fastcall(__int64, unsigned int, const void *, int)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b688`
- `0x18001b708`
- `0x18001d524`

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
- `0x18002b9f0`
- `0x18002bdf4`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ba67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ba67`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002ba8f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002ba8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bb3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bb3f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002bbed`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002bbed`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002bbc7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002bbc7`

## string_xrefs

- `0x18002bd7a`: `DusmStore::SetDataPlan::RegCreateKeyExW`
- `0x18002bcd1`: `DusmStore::SetDataPlan::RegDeleteKeyValueW`
- `0x18002bda2`: `DusmStore::SetDataPlan::RegSetKeyValueW::dataPlan`

## pseudocode

```c
__int64 __fastcall DusmStore::SetDataPlan(__int64 a1, unsigned int a2, const void *a3, int a4)
{
  int v7; // esi
  LPCRITICAL_SECTION v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rax
  char v14; // bl
  const WCHAR *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  const char *samDesiredb; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v22; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v26[32]; // [rsp+C0h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v28[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v29[40]; // [rsp+108h] [rbp+8h] BYREF
  OLECHAR sz[40]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v7 = *(_DWORD *)(a1 + 16);
  if ( v7 == 3 )
  {
    if ( !*(_QWORD *)(a1 + 160) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x64F,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::SetDataPlan::iccid",
        samDesired);
    if ( a2 - 2 > 1 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x659,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::SetDataPlan::source::notUserOrOperator",
        samDesired);
    return DusmStore::SetDataPlanToStore(a1, a1, a2, a3, a4);
  }
  else
  {
    if ( v7 == 2 )
    {
      if ( !*(_QWORD *)(a1 + 64) )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x654,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::SetDataPlan::profileName",
          samDesired);
    }
    else if ( v7 != 1 )
    {
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x638,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::SetDataPlan::mediaType",
        samDesired);
    }
    if ( a2 != 2 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x65E,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::SetDataPlan::source::notUser",
        samDesired);
    v8 = DusmStore::s_pInstance;
    EnterCriticalSection(DusmStore::s_pInstance);
    v22 = v8;
    memset_0(sz, 0, sizeof(sz));
    if ( !StringFromGUID2((const GUID *const)(a1 + 32), sz, 40) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x66D,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0xE,
        (unsigned int)"DusmStore::SetDataPlan::StringFromGUID2",
        samDesired);
    hKey = 0;
    v9 = std::wstring::wstring(v24, qword_180068EC0);
    v10 = std::operator+<wchar_t>(v23, v9, L"\\");
    std::operator+<wchar_t>(v29, v10, sz);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::_Tidy_deallocate(v24);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v29);
    v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v12 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x678,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v12,
        (unsigned int)"DusmStore::SetDataPlan::RegCreateKeyExW",
        samDesireda);
    if ( v7 == 1 )
    {
      v13 = std::wstring::wstring(v26, L"*");
      v14 = 1;
    }
    else
    {
      v13 = std::wstring::wstring(v25, a1 + 48);
      v14 = 2;
    }
    std::wstring::wstring(v28, v13);
    if ( (v14 & 2) != 0 )
    {
      v14 &= ~2u;
      std::wstring::_Tidy_deallocate(v25);
    }
    if ( (v14 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v26);
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28);
    if ( a4 )
    {
      v16 = RegDeleteKeyValueW(hKey, v15, L"UserDataPlan");
      if ( (v16 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x683,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)v16,
          (unsigned int)"DusmStore::SetDataPlan::RegDeleteKeyValueW",
          samDesireda);
    }
    else
    {
      v17 = RegSetKeyValueW(hKey, v15, L"UserDataPlan", 3u, a3, 0x44u);
      if ( v17 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x68F,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)v17,
          (unsigned int)"DusmStore::SetDataPlan::RegSetKeyValueW::dataPlan",
          samDesiredb);
    }
    std::wstring::_Tidy_deallocate(v28);
    std::wstring::_Tidy_deallocate(v29);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
  }
}

```

## disassembly

```asm
0x18002b9f0  mov     [rsp-8+arg_8], rbx
0x18002b9f5  push    rbp
0x18002b9f6  push    rsi
0x18002b9f7  push    rdi
0x18002b9f8  push    r14
0x18002b9fa  push    r15
0x18002b9fc  lea     rbp, [rsp-90h]
0x18002ba04  sub     rsp, 190h
0x18002ba0b  mov     rax, cs:__security_cookie
0x18002ba12  xor     rax, rsp
0x18002ba15  mov     [rbp+0B0h+var_30], rax
0x18002ba1c  mov     r14d, r9d
0x18002ba1f  mov     r15, r8
0x18002ba22  mov     rdi, rcx
0x18002ba25  mov     [rsp+1B0h+var_160], 0
0x18002ba2d  mov     esi, [rcx+10h]
0x18002ba30  cmp     esi, 3
0x18002ba33  jz      loc_18002BC25
0x18002ba39  cmp     esi, 2
0x18002ba3c  jz      short loc_18002BA49
0x18002ba3e  cmp     esi, 1
0x18002ba41  jnz     loc_18002BC9F
0x18002ba47  jmp     short loc_18002BA54
0x18002ba49  cmp     qword ptr [rcx+40h], 0
0x18002ba4e  jz      loc_18002BCF2
0x18002ba54  cmp     edx, 2
0x18002ba57  jnz     loc_18002BD1D
0x18002ba5d  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002ba64  mov     rcx, rbx; lpCriticalSection
0x18002ba67  call    cs:__imp_EnterCriticalSection
0x18002ba6d  mov     [rsp+1B0h+var_158], rbx
0x18002ba72  xor     edx, edx; Val
0x18002ba74  lea     r8d, [rdx+50h]; Size
0x18002ba78  lea     rcx, [rbp+0B0h+sz]; void *
0x18002ba7c  call    memset_0
0x18002ba81  lea     rcx, [rdi+20h]; rguid
0x18002ba85  mov     r8d, 28h ; '('; cchMax
0x18002ba8b  lea     rdx, [rbp+0B0h+sz]; lpsz
0x18002ba8f  call    cs:__imp_StringFromGUID2
0x18002ba95  test    eax, eax
0x18002ba97  jz      loc_18002BD48
0x18002ba9d  mov     [rbp+0B0h+hKey], 0
0x18002baa5  mov     rdx, cs:qword_180068EC0
0x18002baac  lea     rcx, [rbp+0B0h+var_130]
0x18002bab0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002bab5  nop
0x18002bab6  lea     r8, asc_18004F678; "\\"
0x18002babd  mov     rdx, rax
0x18002bac0  lea     rcx, [rsp+1B0h+var_150]
0x18002bac5  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002baca  nop
0x18002bacb  lea     r8, [rbp+0B0h+sz]
0x18002bacf  mov     rdx, rax
0x18002bad2  lea     rcx, [rbp+0B0h+var_A8]
0x18002bad6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002badb  nop
0x18002badc  lea     rcx, [rsp+1B0h+var_150]
0x18002bae1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bae6  nop
0x18002bae7  lea     rcx, [rbp+0B0h+var_130]
0x18002baeb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002baf0  xor     edx, edx
0x18002baf2  lea     rcx, [rbp+0B0h+hKey]
0x18002baf6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002bafb  lea     rcx, [rbp+0B0h+var_A8]
0x18002baff  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bb04  mov     rdx, rax; lpSubKey
0x18002bb07  mov     [rsp+1B0h+lpdwDisposition], 0; lpdwDisposition
0x18002bb10  lea     rax, [rbp+0B0h+hKey]
0x18002bb14  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18002bb19  mov     [rsp+1B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002bb22  mov     dword ptr [rsp+1B0h+samDesired], 20006h; char *
0x18002bb2a  mov     [rsp+1B0h+dwOptions], 0; dwOptions
0x18002bb32  xor     r9d, r9d; lpClass
0x18002bb35  xor     r8d, r8d; Reserved
0x18002bb38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bb3f  call    cs:__imp_RegCreateKeyExW
0x18002bb45  test    eax, eax
0x18002bb47  jnz     loc_18002BD73
0x18002bb4d  cmp     esi, 1
0x18002bb50  jnz     short loc_18002BB67
0x18002bb52  lea     rdx, SubKey; "*"
0x18002bb59  lea     rcx, [rbp+0B0h+var_F0]
0x18002bb5d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002bb62  nop
0x18002bb63  mov     ebx, esi
0x18002bb65  jmp     short loc_18002BB7A
0x18002bb67  lea     rdx, [rdi+30h]
0x18002bb6b  lea     rcx, [rbp+0B0h+var_110]
0x18002bb6f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002bb74  nop
0x18002bb75  mov     ebx, 2
0x18002bb7a  mov     [rsp+1B0h+var_160], ebx
0x18002bb7e  mov     rdx, rax
0x18002bb81  lea     rcx, [rbp+0B0h+var_C8]
0x18002bb85  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002bb8a  nop
0x18002bb8b  test    bl, 2
0x18002bb8e  jz      short loc_18002BB9D
0x18002bb90  and     ebx, 0FFFFFFFDh
0x18002bb93  lea     rcx, [rbp+0B0h+var_110]
0x18002bb97  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bb9c  nop
0x18002bb9d  test    bl, 1
0x18002bba0  jz      short loc_18002BBAB
0x18002bba2  lea     rcx, [rbp+0B0h+var_F0]
0x18002bba6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bbab  lea     rcx, [rbp+0B0h+var_C8]
0x18002bbaf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002bbb4  lea     r8, aUserdataplan; "UserDataPlan"
0x18002bbbb  mov     rdx, rax; lpSubKey
0x18002bbbe  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18002bbc2  test    r14d, r14d
0x18002bbc5  jz      short loc_18002BBDA
0x18002bbc7  call    cs:__imp_RegDeleteKeyValueW
0x18002bbcd  test    eax, 0FFFFFFFDh
0x18002bbd2  jnz     loc_18002BCCA
0x18002bbd8  jmp     short loc_18002BBFB
0x18002bbda  mov     dword ptr [rsp+1B0h+samDesired], 44h ; 'D'; char *
0x18002bbe2  mov     qword ptr [rsp+1B0h+dwOptions], r15; lpData
0x18002bbe7  mov     r9d, 3; dwType
0x18002bbed  call    cs:__imp_RegSetKeyValueW
0x18002bbf3  test    eax, eax
0x18002bbf5  jnz     loc_18002BD9B
0x18002bbfb  lea     rcx, [rbp+0B0h+var_C8]
0x18002bbff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bc04  nop
0x18002bc05  lea     rcx, [rbp+0B0h+var_A8]
0x18002bc09  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bc0e  nop
0x18002bc0f  lea     rcx, [rbp+0B0h+hKey]
0x18002bc13  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002bc18  nop
0x18002bc19  lea     rcx, [rsp+1B0h+var_158]
0x18002bc1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002bc23  jmp     short loc_18002BC4E
0x18002bc25  cmp     qword ptr [rcx+0A0h], 0
0x18002bc2d  jz      loc_18002BDC3
0x18002bc33  lea     eax, [rdx-2]
0x18002bc36  cmp     eax, 1
0x18002bc39  ja      short loc_18002BC74
0x18002bc3b  mov     [rsp+1B0h+dwOptions], r14d
0x18002bc40  mov     r9, r15
0x18002bc43  mov     r8d, edx
0x18002bc46  mov     rdx, rdi
0x18002bc49  call    ?SetDataPlanToStore@DusmStore@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_DATAPLAN_STATUS@@H@Z; DusmStore::SetDataPlanToStore(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS const &,int)
0x18002bc4e  mov     rcx, [rbp+0B0h+var_30]
0x18002bc55  xor     rcx, rsp; StackCookie
0x18002bc58  call    __security_check_cookie
0x18002bc5d  mov     rbx, [rsp+1B0h+arg_8]
0x18002bc65  add     rsp, 190h
0x18002bc6c  pop     r15
0x18002bc6e  pop     r14
0x18002bc70  pop     rdi
0x18002bc71  pop     rsi
0x18002bc72  pop     rbp
0x18002bc73  retn
0x18002bc74  mov     rcx, [rbp+0B8h]; this
0x18002bc7b  lea     rax, aDusmstoreSetda_4; "DusmStore::SetDataPlan::source::notUser"...
0x18002bc82  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002bc87  mov     r9d, 57h ; 'W'; char *
0x18002bc8d  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bc94  mov     edx, 659h; void *
0x18002bc99  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bc9f  mov     rcx, [rbp+0B8h]; this
0x18002bca6  lea     rax, aDusmstoreSetda_5; "DusmStore::SetDataPlan::mediaType"
0x18002bcad  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002bcb2  mov     r9d, 57h ; 'W'; char *
0x18002bcb8  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bcbf  mov     edx, 638h; void *
0x18002bcc4  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bcca  mov     rcx, [rbp+0B8h]; this
0x18002bcd1  lea     rdx, aDusmstoreSetda_7; "DusmStore::SetDataPlan::RegDeleteKeyVal"...
0x18002bcd8  mov     qword ptr [rsp+1B0h+dwOptions], rdx; unsigned int
0x18002bcdd  mov     r9d, eax; char *
0x18002bce0  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bce7  mov     edx, 683h; void *
0x18002bcec  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bcf2  mov     rcx, [rbp+0B8h]; this
0x18002bcf9  lea     rax, aDusmstoreSetda; "DusmStore::SetDataPlan::profileName"
0x18002bd00  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002bd05  mov     r9d, 57h ; 'W'; char *
0x18002bd0b  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bd12  mov     edx, 654h; void *
0x18002bd17  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bd1d  mov     rcx, [rbp+0B8h]; this
0x18002bd24  lea     rax, aDusmstoreSetda_8; "DusmStore::SetDataPlan::source::notUser"
0x18002bd2b  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002bd30  mov     r9d, 57h ; 'W'; char *
0x18002bd36  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bd3d  mov     edx, 65Eh; void *
0x18002bd42  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bd48  mov     rcx, [rbp+0B8h]; this
0x18002bd4f  lea     rax, aDusmstoreSetda_10; "DusmStore::SetDataPlan::StringFromGUID2"
0x18002bd56  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002bd5b  mov     r9d, 0Eh; char *
0x18002bd61  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bd68  mov     edx, 66Dh; void *
0x18002bd6d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bd73  mov     rcx, [rbp+0B8h]; this
0x18002bd7a  lea     rdx, aDusmstoreSetda_3; "DusmStore::SetDataPlan::RegCreateKeyExW"
0x18002bd81  mov     qword ptr [rsp+1B0h+dwOptions], rdx; unsigned int
0x18002bd86  mov     r9d, eax; char *
0x18002bd89  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bd90  mov     edx, 678h; void *
0x18002bd95  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bd9b  mov     rcx, [rbp+0B8h]; this
0x18002bda2  lea     rdx, aDusmstoreSetda_1; "DusmStore::SetDataPlan::RegSetKeyValueW"...
0x18002bda9  mov     qword ptr [rsp+1B0h+dwOptions], rdx; unsigned int
0x18002bdae  mov     r9d, eax; char *
0x18002bdb1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bdb8  mov     edx, 68Fh; void *
0x18002bdbd  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002bdc3  mov     rcx, [rbp+0B8h]; this
0x18002bdca  lea     rax, aDusmstoreSetda_6; "DusmStore::SetDataPlan::iccid"
0x18002bdd1  mov     qword ptr [rsp+1B0h+dwOptions], rax; unsigned int
0x18002bdd6  mov     r9d, 57h ; 'W'; char *
0x18002bddc  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002bde3  mov     edx, 64Fh; void *
0x18002bde8  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
