# DusmStore::SetBackgroundRestriction(DusmConnection const &,_DUSM_BACKGROUND_RESTRICTION)

- ea: `0x18002ad1c`
- end: `0x18002b075`
- name: `?SetBackgroundRestriction@DusmStore@@SAXAEBVDusmConnection@@W4_DUSM_BACKGROUND_RESTRICTION@@@Z`
- size: `857`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015980`

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
- `0x18002ad1c`
- `0x18002b07c`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ad86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ad86`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002adae`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002adae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ae5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ae5e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002aef7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002aef7`

## string_xrefs

- `0x18002b02f`: `DusmStore::SetBackgroundRestriction::RegCreateKeyExW`
- `0x18002b054`: `DusmStore::SetBackgroundRestriction::RegSetKeyValueW`

## pseudocode

```c
__int64 __fastcall DusmStore::SetBackgroundRestriction(__int64 a1, unsigned int a2)
{
  int v3; // esi
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rax
  char v10; // bl
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  const char *samDesiredb; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v17; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int Data; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v22[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v23[32]; // [rsp+D0h] [rbp-30h] BYREF
  OLECHAR sz[40]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  Data = a2;
  if ( a2 > 6 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x6DD,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::SetBackgroundRestriction::restriction",
      samDesired);
  v3 = *(_DWORD *)(a1 + 16);
  if ( v3 == 3 )
  {
    if ( !*(_QWORD *)(a1 + 160) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x6F6,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::SetBackgroundRestriction::iccid",
        samDesired);
    return DusmStore::SetBackgroundRestrictionToStore(a1, a1, a2);
  }
  else
  {
    if ( v3 == 2 )
    {
      if ( !*(_QWORD *)(a1 + 64) )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x6FB,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::SetBackgroundRestriction::profileName",
          samDesired);
    }
    else if ( v3 != 1 )
    {
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x6E4,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::SetBackgroundRestriction::mediaType",
        samDesired);
    }
    v4 = DusmStore::s_pInstance;
    EnterCriticalSection(DusmStore::s_pInstance);
    v17 = v4;
    memset_0(sz, 0, sizeof(sz));
    if ( !StringFromGUID2((const GUID *const)(a1 + 32), sz, 40) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x70A,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0xE,
        (unsigned int)"DusmStore::SetBackgroundRestriction::StringFromGUID2",
        samDesired);
    v5 = std::wstring::wstring(v19, qword_180068EC0);
    v6 = std::operator+<wchar_t>(v18, v5, L"\\");
    std::operator+<wchar_t>(v23, v6, sz);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v19);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v23);
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x715,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v8,
        (unsigned int)"DusmStore::SetBackgroundRestriction::RegCreateKeyExW",
        samDesireda);
    if ( v3 == 1 )
    {
      v9 = std::wstring::wstring(v18, L"*");
      v10 = 1;
    }
    else
    {
      v9 = std::wstring::wstring(v19, a1 + 48);
      v10 = 2;
    }
    std::wstring::wstring(v22, v9);
    if ( (v10 & 2) != 0 )
    {
      v10 &= ~2u;
      std::wstring::_Tidy_deallocate(v19);
    }
    if ( (v10 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v18);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v22);
    v12 = RegSetKeyValueW(hKey, v11, L"BackgroundRestriction", 4u, &Data, 4u);
    if ( v12 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x71F,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v12,
        (unsigned int)"DusmStore::SetBackgroundRestriction::RegSetKeyValueW",
        samDesiredb);
    std::wstring::_Tidy_deallocate(v22);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v23);
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  }
}

```

## disassembly

```asm
0x18002ad1c  mov     [rsp-8+arg_10], rbx
0x18002ad21  push    rbp
0x18002ad22  push    rsi
0x18002ad23  push    rdi
0x18002ad24  lea     rbp, [rsp-50h]
0x18002ad29  sub     rsp, 150h
0x18002ad30  mov     rax, cs:__security_cookie
0x18002ad37  xor     rax, rsp
0x18002ad3a  mov     [rbp+60h+var_20], rax
0x18002ad3e  mov     rdi, rcx
0x18002ad41  mov     [rbp+60h+Data], edx
0x18002ad44  mov     [rsp+160h+var_110], 0
0x18002ad4c  cmp     edx, 6
0x18002ad4f  ja      loc_18002AFB3
0x18002ad55  mov     esi, [rcx+10h]
0x18002ad58  cmp     esi, 3
0x18002ad5b  jz      loc_18002AF4C
0x18002ad61  cmp     esi, 2
0x18002ad64  jz      short loc_18002AD71
0x18002ad66  cmp     esi, 1
0x18002ad69  jnz     loc_18002AF8B
0x18002ad6f  jmp     short loc_18002AD7C
0x18002ad71  cmp     qword ptr [rcx+40h], 0
0x18002ad76  jz      loc_18002AFDB
0x18002ad7c  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002ad83  mov     rcx, rbx; lpCriticalSection
0x18002ad86  call    cs:__imp_EnterCriticalSection
0x18002ad8c  mov     [rsp+160h+var_108], rbx
0x18002ad91  xor     edx, edx; Val
0x18002ad93  lea     r8d, [rdx+50h]; Size
0x18002ad97  lea     rcx, [rbp+60h+sz]; void *
0x18002ad9b  call    memset_0
0x18002ada0  lea     rcx, [rdi+20h]; rguid
0x18002ada4  mov     r8d, 28h ; '('; cchMax
0x18002adaa  lea     rdx, [rbp+60h+sz]; lpsz
0x18002adae  call    cs:__imp_StringFromGUID2
0x18002adb4  test    eax, eax
0x18002adb6  jz      loc_18002B003
0x18002adbc  mov     rdx, cs:qword_180068EC0
0x18002adc3  lea     rcx, [rbp+60h+var_E0]
0x18002adc7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002adcc  nop
0x18002adcd  lea     r8, asc_18004F678; "\\"
0x18002add4  mov     rdx, rax
0x18002add7  lea     rcx, [rsp+160h+var_100]
0x18002addc  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002ade1  nop
0x18002ade2  lea     r8, [rbp+60h+sz]
0x18002ade6  mov     rdx, rax
0x18002ade9  lea     rcx, [rbp+60h+var_90]
0x18002aded  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002adf2  nop
0x18002adf3  lea     rcx, [rsp+160h+var_100]
0x18002adf8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002adfd  nop
0x18002adfe  lea     rcx, [rbp+60h+var_E0]
0x18002ae02  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae07  mov     [rbp+60h+hKey], 0
0x18002ae0f  xor     edx, edx
0x18002ae11  lea     rcx, [rbp+60h+hKey]
0x18002ae15  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002ae1a  lea     rcx, [rbp+60h+var_90]
0x18002ae1e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002ae23  mov     rdx, rax; lpSubKey
0x18002ae26  mov     [rsp+160h+lpdwDisposition], 0; lpdwDisposition
0x18002ae2f  lea     rax, [rbp+60h+hKey]
0x18002ae33  mov     [rsp+160h+phkResult], rax; phkResult
0x18002ae38  mov     [rsp+160h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002ae41  mov     dword ptr [rsp+160h+samDesired], 20006h; char *
0x18002ae49  mov     [rsp+160h+dwOptions], 0; dwOptions
0x18002ae51  xor     r9d, r9d; lpClass
0x18002ae54  xor     r8d, r8d; Reserved
0x18002ae57  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ae5e  call    cs:__imp_RegCreateKeyExW
0x18002ae64  test    eax, eax
0x18002ae66  jnz     loc_18002B02B
0x18002ae6c  cmp     esi, 1
0x18002ae6f  jnz     short loc_18002AE87
0x18002ae71  lea     rdx, SubKey; "*"
0x18002ae78  lea     rcx, [rsp+160h+var_100]
0x18002ae7d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002ae82  nop
0x18002ae83  mov     ebx, esi
0x18002ae85  jmp     short loc_18002AE9A
0x18002ae87  lea     rdx, [rdi+30h]
0x18002ae8b  lea     rcx, [rbp+60h+var_E0]
0x18002ae8f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ae94  nop
0x18002ae95  mov     ebx, 2
0x18002ae9a  mov     [rsp+160h+var_110], ebx
0x18002ae9e  mov     rdx, rax
0x18002aea1  lea     rcx, [rbp+60h+var_B0]
0x18002aea5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002aeaa  nop
0x18002aeab  test    bl, 2
0x18002aeae  jz      short loc_18002AEBD
0x18002aeb0  and     ebx, 0FFFFFFFDh
0x18002aeb3  lea     rcx, [rbp+60h+var_E0]
0x18002aeb7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aebc  nop
0x18002aebd  test    bl, 1
0x18002aec0  jz      short loc_18002AECC
0x18002aec2  lea     rcx, [rsp+160h+var_100]
0x18002aec7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aecc  lea     rcx, [rbp+60h+var_B0]
0x18002aed0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002aed5  mov     rdx, rax; lpSubKey
0x18002aed8  mov     r9d, 4; dwType
0x18002aede  mov     dword ptr [rsp+160h+samDesired], r9d; char *
0x18002aee3  lea     rax, [rbp+60h+Data]
0x18002aee7  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x18002aeec  lea     r8, Value; "BackgroundRestriction"
0x18002aef3  mov     rcx, [rbp+60h+hKey]; hKey
0x18002aef7  call    cs:__imp_RegSetKeyValueW
0x18002aefd  test    eax, eax
0x18002aeff  jnz     loc_18002B050
0x18002af05  lea     rcx, [rbp+60h+var_B0]
0x18002af09  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002af0e  nop
0x18002af0f  lea     rcx, [rbp+60h+hKey]
0x18002af13  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002af18  nop
0x18002af19  lea     rcx, [rbp+60h+var_90]
0x18002af1d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002af22  nop
0x18002af23  lea     rcx, [rsp+160h+var_108]
0x18002af28  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002af2d  mov     rcx, [rbp+60h+var_20]
0x18002af31  xor     rcx, rsp; StackCookie
0x18002af34  call    __security_check_cookie
0x18002af39  mov     rbx, [rsp+160h+arg_10]
0x18002af41  add     rsp, 150h
0x18002af48  pop     rdi
0x18002af49  pop     rsi
0x18002af4a  pop     rbp
0x18002af4b  retn
0x18002af4c  cmp     qword ptr [rcx+0A0h], 0
0x18002af54  jz      short loc_18002AF63
0x18002af56  mov     r8d, edx
0x18002af59  mov     rdx, rdi
0x18002af5c  call    ?SetBackgroundRestrictionToStore@DusmStore@@AEAAXAEBVDusmConnection@@W4_DUSM_BACKGROUND_RESTRICTION@@@Z; DusmStore::SetBackgroundRestrictionToStore(DusmConnection const &,_DUSM_BACKGROUND_RESTRICTION)
0x18002af61  jmp     short loc_18002AF2D
0x18002af63  mov     rcx, [rbp+68h]; this
0x18002af67  lea     rax, aDusmstoreSetba_2; "DusmStore::SetBackgroundRestriction::ic"...
0x18002af6e  mov     qword ptr [rsp+160h+dwOptions], rax; unsigned int
0x18002af73  mov     r9d, 57h ; 'W'; char *
0x18002af79  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002af80  mov     edx, 6F6h; void *
0x18002af85  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002af8b  mov     rcx, [rbp+68h]; this
0x18002af8f  lea     rax, aDusmstoreSetba_5; "DusmStore::SetBackgroundRestriction::me"...
0x18002af96  mov     qword ptr [rsp+160h+dwOptions], rax; unsigned int
0x18002af9b  mov     r9d, 57h ; 'W'; char *
0x18002afa1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002afa8  mov     edx, 6E4h; void *
0x18002afad  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002afb3  mov     rcx, [rbp+68h]; this
0x18002afb7  lea     rax, aDusmstoreSetba_0; "DusmStore::SetBackgroundRestriction::re"...
0x18002afbe  mov     qword ptr [rsp+160h+dwOptions], rax; unsigned int
0x18002afc3  mov     r9d, 57h ; 'W'; char *
0x18002afc9  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002afd0  mov     edx, 6DDh; void *
0x18002afd5  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002afdb  mov     rcx, [rbp+68h]; this
0x18002afdf  lea     rax, aDusmstoreSetba_3; "DusmStore::SetBackgroundRestriction::pr"...
0x18002afe6  mov     qword ptr [rsp+160h+dwOptions], rax; unsigned int
0x18002afeb  mov     r9d, 57h ; 'W'; char *
0x18002aff1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002aff8  mov     edx, 6FBh; void *
0x18002affd  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002b003  mov     rcx, [rbp+68h]; this
0x18002b007  lea     rax, aDusmstoreSetba_6; "DusmStore::SetBackgroundRestriction::St"...
0x18002b00e  mov     qword ptr [rsp+160h+dwOptions], rax; unsigned int
0x18002b013  mov     r9d, 0Eh; char *
0x18002b019  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002b020  mov     edx, 70Ah; void *
0x18002b025  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002b02b  mov     rcx, [rbp+68h]; this
0x18002b02f  lea     rdx, aDusmstoreSetba_1; "DusmStore::SetBackgroundRestriction::Re"...
0x18002b036  mov     qword ptr [rsp+160h+dwOptions], rdx; unsigned int
0x18002b03b  mov     r9d, eax; char *
0x18002b03e  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002b045  mov     edx, 715h; void *
0x18002b04a  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002b050  mov     rcx, [rbp+68h]; this
0x18002b054  lea     rdx, aDusmstoreSetba_4; "DusmStore::SetBackgroundRestriction::Re"...
0x18002b05b  mov     qword ptr [rsp+160h+dwOptions], rdx; unsigned int
0x18002b060  mov     r9d, eax; char *
0x18002b063  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002b06a  mov     edx, 71Fh; void *
0x18002b06f  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
