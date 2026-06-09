# DusmStore::QueryBackgroundRestrictionFromStore(DusmConnection const &)

- ea: `0x18002886c`
- end: `0x1800289b7`
- name: `?QueryBackgroundRestrictionFromStore@DusmStore@@AEAA?AW4_DUSM_BACKGROUND_RESTRICTION@@AEBVDusmConnection@@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18002856c`

## callees

- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x18002886c`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800288a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800288a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002892e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002892e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002896a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002896a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DusmStore::QueryBackgroundRestrictionFromStore(__int64 a1, __int64 a2)
{
  LPCRITICAL_SECTION v3; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  LPCRITICAL_SECTION v9; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v10[32]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v11[32]; // [rsp+68h] [rbp-11h] BYREF
  unsigned int pvData; // [rsp+88h] [rbp+Fh] BYREF
  HKEY hkey; // [rsp+90h] [rbp+17h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+1Fh] BYREF
  _BYTE v15[32]; // [rsp+A0h] [rbp+27h] BYREF

  v3 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v9 = v3;
  v4 = 0;
  hkey = 0;
  v5 = std::wstring::wstring((__int64)v11, (__int64)qword_180068EC8);
  v6 = std::operator+<wchar_t>((__int64)v10, v5, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v15, v6, a2 + 144);
  std::wstring::_Tidy_deallocate(v10);
  std::wstring::_Tidy_deallocate(v11);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v15);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hkey) )
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"BackgroundTrafficRestriction", 0x18u, 0, &pvData, &pcbData) )
      v4 = pvData;
  }
  std::wstring::_Tidy_deallocate(v15);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
  return v4;
}

```

## disassembly

```asm
0x18002886c  mov     [rsp-8+arg_0], rbx
0x180028871  mov     [rsp-8+arg_10], rdi
0x180028876  push    rbp
0x180028877  lea     rbp, [rsp-57h]
0x18002887c  sub     rsp, 0D0h
0x180028883  mov     rax, cs:__security_cookie
0x18002888a  xor     rax, rsp
0x18002888d  mov     [rbp+57h+var_10], rax
0x180028891  mov     rdi, rdx
0x180028894  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002889b  add     rbx, 28h ; '('
0x18002889f  mov     rcx, rbx; lpCriticalSection
0x1800288a2  call    cs:__imp_EnterCriticalSection
0x1800288a8  mov     [rbp+57h+var_90], rbx
0x1800288ac  xor     ebx, ebx
0x1800288ae  mov     [rbp+57h+hkey], rbx
0x1800288b2  mov     rdx, cs:qword_180068EC8
0x1800288b9  lea     rcx, [rbp+57h+var_68]
0x1800288bd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800288c2  nop
0x1800288c3  lea     r8, asc_18004F678; "\\"
0x1800288ca  mov     rdx, rax
0x1800288cd  lea     rcx, [rbp+57h+var_88]
0x1800288d1  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800288d6  nop
0x1800288d7  lea     r8, [rdi+90h]
0x1800288de  mov     rdx, rax
0x1800288e1  lea     rcx, [rbp+57h+var_30]
0x1800288e5  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x1800288ea  nop
0x1800288eb  lea     rcx, [rbp+57h+var_88]
0x1800288ef  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800288f4  nop
0x1800288f5  lea     rcx, [rbp+57h+var_68]
0x1800288f9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800288fe  xor     edx, edx
0x180028900  lea     rcx, [rbp+57h+hkey]
0x180028904  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180028909  lea     rcx, [rbp+57h+var_30]
0x18002890d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028912  mov     rdx, rax; lpSubKey
0x180028915  lea     rax, [rbp+57h+hkey]
0x180028919  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002891e  mov     r9d, 20019h; samDesired
0x180028924  xor     r8d, r8d; ulOptions
0x180028927  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002892e  call    cs:__imp_RegOpenKeyExW
0x180028934  test    eax, eax
0x180028936  jnz     short loc_180028977
0x180028938  mov     [rbp+57h+var_48], ebx
0x18002893b  mov     [rbp+57h+var_38], 4
0x180028942  lea     rax, [rbp+57h+var_38]
0x180028946  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18002894b  lea     rax, [rbp+57h+var_48]
0x18002894f  mov     [rsp+0D0h+pvData], rax; pvData
0x180028954  mov     [rsp+0D0h+phkResult], rbx; pdwType
0x180028959  lea     r9d, [rbx+18h]; dwFlags
0x18002895d  lea     r8, aBackgroundtraf; "BackgroundTrafficRestriction"
0x180028964  xor     edx, edx; lpSubKey
0x180028966  mov     rcx, [rbp+57h+hkey]; hkey
0x18002896a  call    cs:__imp_RegGetValueW
0x180028970  test    eax, eax
0x180028972  jnz     short loc_180028977
0x180028974  mov     ebx, [rbp+57h+var_48]
0x180028977  lea     rcx, [rbp+57h+var_30]
0x18002897b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028980  nop
0x180028981  lea     rcx, [rbp+57h+hkey]
0x180028985  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002898a  nop
0x18002898b  lea     rcx, [rbp+57h+var_90]
0x18002898f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180028994  mov     eax, ebx
0x180028996  mov     rcx, [rbp+57h+var_10]
0x18002899a  xor     rcx, rsp; StackCookie
0x18002899d  call    __security_check_cookie
0x1800289a2  lea     r11, [rsp+0D0h+var_s0]
0x1800289aa  mov     rbx, [r11+10h]
0x1800289ae  mov     rdi, [r11+20h]
0x1800289b2  mov     rsp, r11
0x1800289b5  pop     rbp
0x1800289b6  retn
```
