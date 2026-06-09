# DusmStore::SetEnableOperatorToast(DusmConnection const &,int)

- ea: `0x18002c174`
- end: `0x18002c337`
- name: `?SetEnableOperatorToast@DusmStore@@SAXAEBVDusmConnection@@H@Z`
- size: `451`
- prototype: `void __fastcall(const struct DusmConnection *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001d5e4`

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
- `0x18002c174`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c1a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c1a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c24f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c24f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c286`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002c286`

## string_xrefs

- `0x18002c316`: `DusmStore::SetEnableOperatorToast::RegCreateKeyExW`
- `0x18002c2c9`: `DusmStore::SetEnableOperatorToast::RegSetKeyValueW`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall DusmStore::SetEnableOperatorToast(const struct DusmConnection *a1, int a2)
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
      (void *)0x7E0,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::SetEnableOperatorToast::mediaType",
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
      (void *)0x7E9,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v8,
      (unsigned int)"DusmStore::SetEnableOperatorToast::RegCreateKeyExW",
      samDesireda);
  Data = a2 != 0;
  v9 = RegSetKeyValueW(hKey, 0, L"EnableOperatorToast", 4u, &Data, 4u);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x7F2,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)v9,
      (unsigned int)"DusmStore::SetEnableOperatorToast::RegSetKeyValueW",
      samDesiredb);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
}

```

## disassembly

```asm
0x18002c174  push    rbp
0x18002c176  push    rbx
0x18002c177  push    rsi
0x18002c178  push    rdi
0x18002c179  lea     rbp, [rsp-3Fh]
0x18002c17e  sub     rsp, 0D8h
0x18002c185  mov     rax, cs:__security_cookie
0x18002c18c  xor     rax, rsp
0x18002c18f  mov     [rbp+57h+var_28], rax
0x18002c193  mov     esi, edx
0x18002c195  mov     rdi, rcx
0x18002c198  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002c19f  add     rbx, 28h ; '('
0x18002c1a3  mov     rcx, rbx; lpCriticalSection
0x18002c1a6  call    cs:__imp_EnterCriticalSection
0x18002c1ac  mov     [rbp+57h+var_A0], rbx
0x18002c1b0  cmp     dword ptr [rdi+10h], 3
0x18002c1b4  jnz     loc_18002C2EA
0x18002c1ba  mov     rdx, cs:qword_180068EC8
0x18002c1c1  lea     rcx, [rbp+57h+var_78]
0x18002c1c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002c1ca  nop
0x18002c1cb  lea     r8, asc_18004F678; "\\"
0x18002c1d2  mov     rdx, rax
0x18002c1d5  lea     rcx, [rbp+57h+var_98]
0x18002c1d9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002c1de  nop
0x18002c1df  lea     r8, [rdi+90h]
0x18002c1e6  mov     rdx, rax
0x18002c1e9  lea     rcx, [rbp+57h+var_48]
0x18002c1ed  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002c1f2  nop
0x18002c1f3  lea     rcx, [rbp+57h+var_98]
0x18002c1f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c1fc  nop
0x18002c1fd  lea     rcx, [rbp+57h+var_78]
0x18002c201  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c206  xor     ebx, ebx
0x18002c208  mov     [rbp+57h+hKey], rbx
0x18002c20c  xor     edx, edx
0x18002c20e  lea     rcx, [rbp+57h+hKey]
0x18002c212  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002c217  lea     rcx, [rbp+57h+var_48]
0x18002c21b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c220  mov     rdx, rax; lpSubKey
0x18002c223  mov     [rsp+0F0h+lpdwDisposition], rbx; lpdwDisposition
0x18002c228  lea     rax, [rbp+57h+hKey]
0x18002c22c  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002c231  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18002c236  mov     dword ptr [rsp+0F0h+samDesired], 20006h; char *
0x18002c23e  mov     [rsp+0F0h+dwOptions], ebx; dwOptions
0x18002c242  xor     r9d, r9d; lpClass
0x18002c245  xor     r8d, r8d; Reserved
0x18002c248  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c24f  call    cs:__imp_RegCreateKeyExW
0x18002c255  test    eax, eax
0x18002c257  jnz     loc_18002C312
0x18002c25d  mov     eax, ebx
0x18002c25f  test    esi, esi
0x18002c261  setnz   al
0x18002c264  mov     [rbp+57h+Data], eax
0x18002c267  lea     r9d, [rbx+4]; dwType
0x18002c26b  mov     dword ptr [rsp+0F0h+samDesired], r9d; char *
0x18002c270  lea     rax, [rbp+57h+Data]
0x18002c274  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18002c279  lea     r8, aEnableoperator; "EnableOperatorToast"
0x18002c280  xor     edx, edx; lpSubKey
0x18002c282  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c286  call    cs:__imp_RegSetKeyValueW
0x18002c28c  test    eax, eax
0x18002c28e  jnz     short loc_18002C2C5
0x18002c290  lea     rcx, [rbp+57h+hKey]
0x18002c294  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c299  nop
0x18002c29a  lea     rcx, [rbp+57h+var_48]
0x18002c29e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c2a3  nop
0x18002c2a4  lea     rcx, [rbp+57h+var_A0]
0x18002c2a8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002c2ad  mov     rcx, [rbp+57h+var_28]
0x18002c2b1  xor     rcx, rsp; StackCookie
0x18002c2b4  call    __security_check_cookie
0x18002c2b9  add     rsp, 0D8h
0x18002c2c0  pop     rdi
0x18002c2c1  pop     rsi
0x18002c2c2  pop     rbx
0x18002c2c3  pop     rbp
0x18002c2c4  retn
0x18002c2c5  mov     rcx, [rbp+5Fh]; this
0x18002c2c9  lea     rdx, aDusmstoreSeten_4; "DusmStore::SetEnableOperatorToast::RegS"...
0x18002c2d0  mov     qword ptr [rsp+0F0h+dwOptions], rdx; unsigned int
0x18002c2d5  mov     r9d, eax; char *
0x18002c2d8  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c2df  mov     edx, 7F2h; void *
0x18002c2e4  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c2ea  mov     rcx, [rbp+5Fh]; this
0x18002c2ee  lea     rax, aDusmstoreSeten_3; "DusmStore::SetEnableOperatorToast::medi"...
0x18002c2f5  mov     qword ptr [rsp+0F0h+dwOptions], rax; unsigned int
0x18002c2fa  mov     r9d, 57h ; 'W'; char *
0x18002c300  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c307  mov     edx, 7E0h; void *
0x18002c30c  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c312  mov     rcx, [rbp+5Fh]; this
0x18002c316  lea     rdx, aDusmstoreSeten_0; "DusmStore::SetEnableOperatorToast::RegC"...
0x18002c31d  mov     qword ptr [rsp+0F0h+dwOptions], rdx; unsigned int
0x18002c322  mov     r9d, eax; char *
0x18002c325  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c32c  mov     edx, 7E9h; void *
0x18002c331  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
