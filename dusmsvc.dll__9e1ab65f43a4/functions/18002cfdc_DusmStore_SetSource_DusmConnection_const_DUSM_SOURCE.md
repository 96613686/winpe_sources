# DusmStore::SetSource(DusmConnection const &,_DUSM_SOURCE)

- ea: `0x18002cfdc`
- end: `0x18002d1c3`
- name: `?SetSource@DusmStore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001b708`
- `0x18001d7c4`
- `0x18003a1e4`

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
- `0x18002cfdc`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d01d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d01d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002d0dd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002d0dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d0bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d0bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002d10b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002d10b`

## string_xrefs

- `0x18002d1a2`: `DusmStore::SetSource::RegCreateKeyExW`
- `0x18002d155`: `DusmStore::SetSource::RegSetKeyValueW`

## pseudocode

```c
__int64 __fastcall DusmStore::SetSource(__int64 a1, int a2)
{
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  const char *samDesired; // [rsp+28h] [rbp-61h]
  const char *samDesireda; // [rsp+28h] [rbp-61h]
  const char *samDesiredb; // [rsp+28h] [rbp-61h]
  LPCRITICAL_SECTION v14; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v16[32]; // [rsp+78h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+Fh] BYREF
  int Data; // [rsp+A0h] [rbp+17h] BYREF
  _BYTE v19[32]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( (unsigned int)(a2 - 2) > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::SetSource::source",
      samDesired);
  v4 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v14 = v4;
  hKey = 0;
  Data = a2;
  v5 = std::wstring::wstring(v16, qword_180068EC8);
  v6 = std::operator+<wchar_t>(v15, v5, L"\\");
  std::operator+<wchar_t>(v19, v6, a1 + 144);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v16);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v19);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x403,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v8,
      (unsigned int)"DusmStore::SetSource::RegCreateKeyExW",
      samDesireda);
  if ( a2 != 2 || (RegDeleteValueW(hKey, L"UseOperator") & 0xFFFFFFFD) != 0 )
  {
    v9 = RegSetKeyValueW(hKey, 0, L"UseOperator", 4u, &Data, 4u);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x416,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v9,
        (unsigned int)"DusmStore::SetSource::RegSetKeyValueW",
        samDesiredb);
  }
  std::wstring::_Tidy_deallocate(v19);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v14);
}

```

## disassembly

```asm
0x18002cfdc  mov     [rsp-8+arg_10], rbx
0x18002cfe1  push    rbp
0x18002cfe2  push    rsi
0x18002cfe3  push    rdi
0x18002cfe4  lea     rbp, [rsp-47h]
0x18002cfe9  sub     rsp, 0D0h
0x18002cff0  mov     rax, cs:__security_cookie
0x18002cff7  xor     rax, rsp
0x18002cffa  mov     [rbp+57h+var_18], rax
0x18002cffe  mov     edi, edx
0x18002d000  mov     rsi, rcx
0x18002d003  lea     eax, [rdx-2]
0x18002d006  cmp     eax, 1
0x18002d009  ja      loc_18002D176
0x18002d00f  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002d016  add     rbx, 28h ; '('
0x18002d01a  mov     rcx, rbx; lpCriticalSection
0x18002d01d  call    cs:__imp_EnterCriticalSection
0x18002d023  mov     [rbp+57h+var_90], rbx
0x18002d027  xor     ebx, ebx
0x18002d029  mov     [rbp+57h+hKey], rbx
0x18002d02d  mov     [rbp+57h+Data], edi
0x18002d030  mov     rdx, cs:qword_180068EC8
0x18002d037  lea     rcx, [rbp+57h+var_68]
0x18002d03b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002d040  nop
0x18002d041  lea     r8, asc_18004F678; "\\"
0x18002d048  mov     rdx, rax
0x18002d04b  lea     rcx, [rbp+57h+var_88]
0x18002d04f  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002d054  nop
0x18002d055  lea     r8, [rsi+90h]
0x18002d05c  mov     rdx, rax
0x18002d05f  lea     rcx, [rbp+57h+var_38]
0x18002d063  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002d068  nop
0x18002d069  lea     rcx, [rbp+57h+var_88]
0x18002d06d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d072  nop
0x18002d073  lea     rcx, [rbp+57h+var_68]
0x18002d077  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d07c  xor     edx, edx
0x18002d07e  lea     rcx, [rbp+57h+hKey]
0x18002d082  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d087  lea     rcx, [rbp+57h+var_38]
0x18002d08b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d090  mov     rdx, rax; lpSubKey
0x18002d093  mov     [rsp+0E0h+lpdwDisposition], rbx; lpdwDisposition
0x18002d098  lea     rax, [rbp+57h+hKey]
0x18002d09c  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002d0a1  mov     [rsp+0E0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18002d0a6  mov     dword ptr [rsp+0E0h+samDesired], 20006h; char *
0x18002d0ae  mov     [rsp+0E0h+dwOptions], ebx; dwOptions
0x18002d0b2  xor     r9d, r9d; lpClass
0x18002d0b5  xor     r8d, r8d; Reserved
0x18002d0b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d0bf  call    cs:__imp_RegCreateKeyExW
0x18002d0c5  test    eax, eax
0x18002d0c7  jnz     loc_18002D19E
0x18002d0cd  cmp     edi, 2
0x18002d0d0  jnz     short loc_18002D0EA
0x18002d0d2  lea     rdx, ValueName; "UseOperator"
0x18002d0d9  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d0dd  call    cs:__imp_RegDeleteValueW
0x18002d0e3  test    eax, 0FFFFFFFDh
0x18002d0e8  jz      short loc_18002D115
0x18002d0ea  mov     r9d, 4; dwType
0x18002d0f0  mov     dword ptr [rsp+0E0h+samDesired], r9d; char *
0x18002d0f5  lea     rax, [rbp+57h+Data]
0x18002d0f9  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002d0fe  lea     r8, ValueName; "UseOperator"
0x18002d105  xor     edx, edx; lpSubKey
0x18002d107  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d10b  call    cs:__imp_RegSetKeyValueW
0x18002d111  test    eax, eax
0x18002d113  jnz     short loc_18002D151
0x18002d115  lea     rcx, [rbp+57h+var_38]
0x18002d119  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d11e  nop
0x18002d11f  lea     rcx, [rbp+57h+hKey]
0x18002d123  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d128  nop
0x18002d129  lea     rcx, [rbp+57h+var_90]
0x18002d12d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002d132  mov     rcx, [rbp+57h+var_18]
0x18002d136  xor     rcx, rsp; StackCookie
0x18002d139  call    __security_check_cookie
0x18002d13e  mov     rbx, [rsp+0E0h+arg_10]
0x18002d146  add     rsp, 0D0h
0x18002d14d  pop     rdi
0x18002d14e  pop     rsi
0x18002d14f  pop     rbp
0x18002d150  retn
0x18002d151  mov     rcx, [rbp+5Fh]; this
0x18002d155  lea     rdx, aDusmstoreSetso_0; "DusmStore::SetSource::RegSetKeyValueW"
0x18002d15c  mov     qword ptr [rsp+0E0h+dwOptions], rdx; unsigned int
0x18002d161  mov     r9d, eax; char *
0x18002d164  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002d16b  mov     edx, 416h; void *
0x18002d170  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002d176  mov     rcx, [rbp+5Fh]; this
0x18002d17a  lea     rax, aDusmstoreSetso_1; "DusmStore::SetSource::source"
0x18002d181  mov     qword ptr [rsp+0E0h+dwOptions], rax; unsigned int
0x18002d186  mov     r9d, 57h ; 'W'; char *
0x18002d18c  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002d193  mov     edx, 3F5h; void *
0x18002d198  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002d19e  mov     rcx, [rbp+5Fh]; this
0x18002d1a2  lea     rdx, aDusmstoreSetso; "DusmStore::SetSource::RegCreateKeyExW"
0x18002d1a9  mov     qword ptr [rsp+0E0h+dwOptions], rdx; unsigned int
0x18002d1ae  mov     r9d, eax; char *
0x18002d1b1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002d1b8  mov     edx, 403h; void *
0x18002d1bd  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
