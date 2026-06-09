# DusmStore::SetBackgroundRestrictionToStore(DusmConnection const &,_DUSM_BACKGROUND_RESTRICTION)

- ea: `0x18002b07c`
- end: `0x18002b214`
- name: `?SetBackgroundRestrictionToStore@DusmStore@@AEAAXAEBVDusmConnection@@W4_DUSM_BACKGROUND_RESTRICTION@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002ad1c`

## callees

- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x18002b07c`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b0b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b0b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b155`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b155`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b182`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b182`

## string_xrefs

- `0x18002b1f3`: `DusmStore::SetBackgroundRestrictionToStore::RegCreateKeyExW`
- `0x18002b1ce`: `DusmStore::SetBackgroundRestrictionToStore::RegSetKeyValueW`

## pseudocode

```c
__int64 __fastcall DusmStore::SetBackgroundRestrictionToStore(__int64 a1, __int64 a2, int a3)
{
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  const char *samDesired; // [rsp+28h] [rbp-51h]
  const char *samDesireda; // [rsp+28h] [rbp-51h]
  LPCRITICAL_SECTION v13; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v14[32]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+78h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+1Fh] BYREF
  int Data; // [rsp+A0h] [rbp+27h] BYREF
  _BYTE v18[32]; // [rsp+A8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  Data = a3;
  v4 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v13 = v4;
  hKey = 0;
  v5 = std::wstring::wstring(v15, qword_180068EC8);
  v6 = std::operator+<wchar_t>(v14, v5, L"\\");
  std::operator+<wchar_t>(v18, v6, a2 + 144);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v15);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v18);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v8,
      (unsigned int)"DusmStore::SetBackgroundRestrictionToStore::RegCreateKeyExW",
      samDesired);
  v9 = RegSetKeyValueW(hKey, 0, L"BackgroundTrafficRestriction", 4u, &Data, 4u);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x449,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v9,
      (unsigned int)"DusmStore::SetBackgroundRestrictionToStore::RegSetKeyValueW",
      samDesireda);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
}

```

## disassembly

```asm
0x18002b07c  mov     [rsp-8+arg_0], rbx
0x18002b081  mov     [rsp-8+arg_18], rdi
0x18002b086  push    rbp
0x18002b087  lea     rbp, [rsp-57h]
0x18002b08c  sub     rsp, 0D0h
0x18002b093  mov     rax, cs:__security_cookie
0x18002b09a  xor     rax, rsp
0x18002b09d  mov     [rbp+57h+var_8], rax
0x18002b0a1  mov     rdi, rdx
0x18002b0a4  mov     [rbp+57h+Data], r8d
0x18002b0a8  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002b0af  add     rbx, 28h ; '('
0x18002b0b3  mov     rcx, rbx; lpCriticalSection
0x18002b0b6  call    cs:__imp_EnterCriticalSection
0x18002b0bc  mov     [rbp+57h+var_80], rbx
0x18002b0c0  xor     ebx, ebx
0x18002b0c2  mov     [rbp+57h+hKey], rbx
0x18002b0c6  mov     rdx, cs:qword_180068EC8
0x18002b0cd  lea     rcx, [rbp+57h+var_58]
0x18002b0d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002b0d6  nop
0x18002b0d7  lea     r8, asc_18004F678; "\\"
0x18002b0de  mov     rdx, rax
0x18002b0e1  lea     rcx, [rbp+57h+var_78]
0x18002b0e5  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002b0ea  nop
0x18002b0eb  lea     r8, [rdi+90h]
0x18002b0f2  mov     rdx, rax
0x18002b0f5  lea     rcx, [rbp+57h+var_28]
0x18002b0f9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002b0fe  nop
0x18002b0ff  lea     rcx, [rbp+57h+var_78]
0x18002b103  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b108  nop
0x18002b109  lea     rcx, [rbp+57h+var_58]
0x18002b10d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b112  xor     edx, edx
0x18002b114  lea     rcx, [rbp+57h+hKey]
0x18002b118  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b11d  lea     rcx, [rbp+57h+var_28]
0x18002b121  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b126  mov     rdx, rax; lpSubKey
0x18002b129  mov     [rsp+0D0h+lpdwDisposition], rbx; lpdwDisposition
0x18002b12e  lea     rax, [rbp+57h+hKey]
0x18002b132  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002b137  mov     [rsp+0D0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18002b13c  mov     dword ptr [rsp+0D0h+samDesired], 20006h; char *
0x18002b144  mov     [rsp+0D0h+dwOptions], ebx; dwOptions
0x18002b148  xor     r9d, r9d; lpClass
0x18002b14b  xor     r8d, r8d; Reserved
0x18002b14e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b155  call    cs:__imp_RegCreateKeyExW
0x18002b15b  test    eax, eax
0x18002b15d  jnz     loc_18002B1EF
0x18002b163  lea     r9d, [rbx+4]; dwType
0x18002b167  mov     dword ptr [rsp+0D0h+samDesired], r9d; char *
0x18002b16c  lea     rax, [rbp+57h+Data]
0x18002b170  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18002b175  lea     r8, aBackgroundtraf; "BackgroundTrafficRestriction"
0x18002b17c  xor     edx, edx; lpSubKey
0x18002b17e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002b182  call    cs:__imp_RegSetKeyValueW
0x18002b188  test    eax, eax
0x18002b18a  jnz     short loc_18002B1CA
0x18002b18c  lea     rcx, [rbp+57h+var_28]
0x18002b190  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b195  nop
0x18002b196  lea     rcx, [rbp+57h+hKey]
0x18002b19a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b19f  nop
0x18002b1a0  lea     rcx, [rbp+57h+var_80]
0x18002b1a4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002b1a9  mov     rcx, [rbp+57h+var_8]
0x18002b1ad  xor     rcx, rsp; StackCookie
0x18002b1b0  call    __security_check_cookie
0x18002b1b5  lea     r11, [rsp+0D0h+var_s0]
0x18002b1bd  mov     rbx, [r11+10h]
0x18002b1c1  mov     rdi, [r11+28h]
0x18002b1c5  mov     rsp, r11
0x18002b1c8  pop     rbp
0x18002b1c9  retn
0x18002b1ca  mov     rcx, [rbp+5Fh]; this
0x18002b1ce  lea     rdx, aDusmstoreSetba; "DusmStore::SetBackgroundRestrictionToSt"...
0x18002b1d5  mov     qword ptr [rsp+0D0h+dwOptions], rdx; unsigned int
0x18002b1da  mov     r9d, eax; char *
0x18002b1dd  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002b1e4  mov     edx, 449h; void *
0x18002b1e9  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002b1ef  mov     rcx, [rbp+5Fh]; this
0x18002b1f3  lea     rdx, aDusmstoreSetba_7; "DusmStore::SetBackgroundRestrictionToSt"...
0x18002b1fa  mov     qword ptr [rsp+0D0h+dwOptions], rdx; unsigned int
0x18002b1ff  mov     r9d, eax; char *
0x18002b202  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002b209  mov     edx, 442h; void *
0x18002b20e  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
