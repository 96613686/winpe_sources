# DusmStore::SetEnableSetDataPlanToast(DusmConnection const &,int)

- ea: `0x18002c340`
- end: `0x18002c503`
- name: `?SetEnableSetDataPlanToast@DusmStore@@SAXAEBVDusmConnection@@H@Z`
- size: `451`
- prototype: `void __fastcall(const struct DusmConnection *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180019520`

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
- `0x18002c340`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c372`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c372`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c41b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c41b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c452`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c452`

## string_xrefs

- `0x18002c4e2`: `DusmStore::SetEnableSetDataPlanToast::RegCreateKeyExW`
- `0x18002c495`: `DusmStore::SetEnableSetDataPlanToast::RegSetKeyValueW`

## pseudocode

```c
void __fastcall DusmStore::SetEnableSetDataPlanToast(const struct DusmConnection *a1, int a2)
{
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  const char *samDesired; // [rsp+28h] [rbp-71h]
  const char *samDesireda; // [rsp+28h] [rbp-71h]
  const char *samDesiredb; // [rsp+28h] [rbp-71h]
  LPCRITICAL_SECTION v13; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v14[32]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v15[32]; // [rsp+78h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-1h] BYREF
  BOOL Data; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v18[32]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v4 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v13 = v4;
  if ( *((_DWORD *)a1 + 4) != 3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x7FC,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::SetEnableSetDataPlanToast::mediaType",
      samDesired);
  v5 = std::wstring::wstring((__int64)v15, (__int64)qword_180068EC8);
  v6 = std::operator+<wchar_t>((__int64)v14, v5, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v18, v6, (__int64)a1 + 144);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v15);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v18);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x805,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v8,
      (unsigned int)"DusmStore::SetEnableSetDataPlanToast::RegCreateKeyExW",
      samDesireda);
  Data = a2 != 0;
  v9 = RegSetKeyValueW(hKey, 0, L"EnableSetDataPlanToast", 4u, &Data, 4u);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x80E,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v9,
      (unsigned int)"DusmStore::SetEnableSetDataPlanToast::RegSetKeyValueW",
      samDesiredb);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
}

```

## disassembly

```asm
0x18002c340  push    rbp
0x18002c342  push    rbx
0x18002c343  push    rsi
0x18002c344  push    rdi
0x18002c345  lea     rbp, [rsp-3Fh]
0x18002c34a  sub     rsp, 0D8h
0x18002c351  mov     rax, cs:__security_cookie
0x18002c358  xor     rax, rsp
0x18002c35b  mov     [rbp+57h+var_28], rax
0x18002c35f  mov     esi, edx
0x18002c361  mov     rdi, rcx
0x18002c364  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002c36b  add     rbx, 28h ; '('
0x18002c36f  mov     rcx, rbx; lpCriticalSection
0x18002c372  call    cs:__imp_EnterCriticalSection
0x18002c378  mov     [rbp+57h+var_A0], rbx
0x18002c37c  cmp     dword ptr [rdi+10h], 3
0x18002c380  jnz     loc_18002C4B6
0x18002c386  mov     rdx, cs:qword_180068EC8
0x18002c38d  lea     rcx, [rbp+57h+var_78]
0x18002c391  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002c396  nop
0x18002c397  lea     r8, asc_18004F678; "\\"
0x18002c39e  mov     rdx, rax
0x18002c3a1  lea     rcx, [rbp+57h+var_98]
0x18002c3a5  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002c3aa  nop
0x18002c3ab  lea     r8, [rdi+90h]
0x18002c3b2  mov     rdx, rax
0x18002c3b5  lea     rcx, [rbp+57h+var_48]
0x18002c3b9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002c3be  nop
0x18002c3bf  lea     rcx, [rbp+57h+var_98]
0x18002c3c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c3c8  nop
0x18002c3c9  lea     rcx, [rbp+57h+var_78]
0x18002c3cd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c3d2  xor     ebx, ebx
0x18002c3d4  mov     [rbp+57h+hKey], rbx
0x18002c3d8  xor     edx, edx
0x18002c3da  lea     rcx, [rbp+57h+hKey]
0x18002c3de  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002c3e3  lea     rcx, [rbp+57h+var_48]
0x18002c3e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c3ec  mov     rdx, rax; lpSubKey
0x18002c3ef  mov     [rsp+0F0h+lpdwDisposition], rbx; lpdwDisposition
0x18002c3f4  lea     rax, [rbp+57h+hKey]
0x18002c3f8  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002c3fd  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18002c402  mov     dword ptr [rsp+0F0h+samDesired], 20006h; char *
0x18002c40a  mov     [rsp+0F0h+dwOptions], ebx; dwOptions
0x18002c40e  xor     r9d, r9d; lpClass
0x18002c411  xor     r8d, r8d; Reserved
0x18002c414  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c41b  call    cs:__imp_RegCreateKeyExW
0x18002c421  test    eax, eax
0x18002c423  jnz     loc_18002C4DE
0x18002c429  mov     eax, ebx
0x18002c42b  test    esi, esi
0x18002c42d  setnz   al
0x18002c430  mov     [rbp+57h+Data], eax
0x18002c433  lea     r9d, [rbx+4]; dwType
0x18002c437  mov     dword ptr [rsp+0F0h+samDesired], r9d; char *
0x18002c43c  lea     rax, [rbp+57h+Data]
0x18002c440  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18002c445  lea     r8, aEnablesetdatap; "EnableSetDataPlanToast"
0x18002c44c  xor     edx, edx; lpSubKey
0x18002c44e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c452  call    cs:__imp_RegSetKeyValueW
0x18002c458  test    eax, eax
0x18002c45a  jnz     short loc_18002C491
0x18002c45c  lea     rcx, [rbp+57h+hKey]
0x18002c460  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c465  nop
0x18002c466  lea     rcx, [rbp+57h+var_48]
0x18002c46a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c46f  nop
0x18002c470  lea     rcx, [rbp+57h+var_A0]
0x18002c474  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002c479  mov     rcx, [rbp+57h+var_28]
0x18002c47d  xor     rcx, rsp; StackCookie
0x18002c480  call    __security_check_cookie
0x18002c485  add     rsp, 0D8h
0x18002c48c  pop     rdi
0x18002c48d  pop     rsi
0x18002c48e  pop     rbx
0x18002c48f  pop     rbp
0x18002c490  retn
0x18002c491  mov     rcx, [rbp+5Fh]; this
0x18002c495  lea     rdx, aDusmstoreSeten; "DusmStore::SetEnableSetDataPlanToast::R"...
0x18002c49c  mov     qword ptr [rsp+0F0h+dwOptions], rdx; unsigned int
0x18002c4a1  mov     r9d, eax; char *
0x18002c4a4  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c4ab  mov     edx, 80Eh; void *
0x18002c4b0  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c4b6  mov     rcx, [rbp+5Fh]; this
0x18002c4ba  lea     rax, aDusmstoreSeten_2; "DusmStore::SetEnableSetDataPlanToast::m"...
0x18002c4c1  mov     qword ptr [rsp+0F0h+dwOptions], rax; unsigned int
0x18002c4c6  mov     r9d, 57h ; 'W'; char *
0x18002c4cc  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c4d3  mov     edx, 7FCh; void *
0x18002c4d8  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c4de  mov     rcx, [rbp+5Fh]; this
0x18002c4e2  lea     rdx, aDusmstoreSeten_1; "DusmStore::SetEnableSetDataPlanToast::R"...
0x18002c4e9  mov     qword ptr [rsp+0F0h+dwOptions], rdx; unsigned int
0x18002c4ee  mov     r9d, eax; char *
0x18002c4f1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c4f8  mov     edx, 805h; void *
0x18002c4fd  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
