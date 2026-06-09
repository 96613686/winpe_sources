# DusmStore::SetOperatorCycleData(DusmConnection const &,_DUSM_OPERATOR_CYCLE_DATA const &)

- ea: `0x18002c650`
- end: `0x18002c9c3`
- name: `?SetOperatorCycleData@DusmStore@@SAXAEBVDusmConnection@@AEBU_DUSM_OPERATOR_CYCLE_DATA@@@Z`
- size: `883`
- prototype: `void __fastcall(const struct DusmConnection *, const BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001d6a4`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x18002c650`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c68c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c68c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c71f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c7ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c71f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c7ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c812`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c83e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c812`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c83e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c7ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c7ad`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18002c75b`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18002c75b`

## string_xrefs

- `0x18002c900`: `DusmStore::SetOperatorCycleData::RegOpenKeyExW`
- `0x18002c97a`: `DusmStore::SetOperatorCycleData::RegOpenKeyEx::plan`
- `0x18002c952`: `DusmStore::SetOperatorCycleData::RegSetValueEx::daysInCycle`
- `0x18002c92a`: `DusmStore::SetOperatorCycleData::RegSetValueEx::daysIntoCycle`

## pseudocode

```c
void __fastcall DusmStore::SetOperatorCycleData(const struct DusmConnection *a1, const BYTE *a2)
{
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  DWORD v8; // ebx
  unsigned int v9; // eax
  unsigned int ValueW; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  const char *pvData; // [rsp+28h] [rbp-D8h]
  const char *pvDataa; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v16; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  char v21[4]; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcbData; // [rsp+9Ch] [rbp-64h] BYREF
  _BYTE v23[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v4 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v16 = v4;
  hKey = 0;
  v5 = std::wstring::wstring(v18, qword_180068EC8);
  v6 = std::operator+<wchar_t>(v17, v5, L"\\");
  std::operator+<wchar_t>(v23, v6, (char *)a1 + 144);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v23);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x490,
      (unsigned int)"DusmStore::SetOperatorCycleData::RegOpenKeyExW",
      pvData);
  memset_0(Name, 0, 0x208u);
  phkResult = 0;
  v8 = 0;
  while ( 1 )
  {
    v9 = RegEnumKeyW(hKey, v8, Name, 0x104u);
    if ( v9 == 259 )
      break;
    if ( v9 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x4BC,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v9,
        (unsigned int)"DusmStore::SetOperatorCycleData::RegEnumKey",
        pvData);
    *(_DWORD *)v21 = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, Name, L"DataPlanFlags", 0x10u, 0, v21, &pcbData);
    if ( ValueW )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x4C5,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)ValueW,
        (unsigned int)"DusmStore::SetOperatorCycleData::RegGetValue::flags",
        pvData);
    if ( (v21[0] & 1) != 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v11 = RegOpenKeyExW(hKey, Name, 0, 0x20006u, &phkResult);
      if ( v11 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x4D0,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)v11,
          (unsigned int)"DusmStore::SetOperatorCycleData::RegOpenKeyEx::plan",
          pvData);
      v12 = RegSetValueExW(phkResult, L"DaysInCycle", 0, 4u, a2, 4u);
      if ( v12 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x4D8,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)v12,
          (unsigned int)"DusmStore::SetOperatorCycleData::RegSetValueEx::daysInCycle",
          pvDataa);
      v13 = RegSetValueExW(phkResult, L"DaysIntoCycle", 0, 4u, a2 + 4, 4u);
      if ( v13 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x4E0,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)v13,
          (unsigned int)"DusmStore::SetOperatorCycleData::RegSetValueEx::daysIntoCycle",
          pvData);
    }
    if ( ++v8 >= 0x2710 )
      goto LABEL_13;
  }
  if ( !v8 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x4B8,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x490,
      (unsigned int)"DusmStore::SetOperatorCycleData::RegEnumKey",
      pvData);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  std::wstring::_Tidy_deallocate(v23);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v16);
}

```

## disassembly

```asm
0x18002c650  mov     [rsp-8+arg_10], rbx
0x18002c655  push    rbp
0x18002c656  push    rsi
0x18002c657  push    rdi
0x18002c658  lea     rbp, [rsp-1E0h]
0x18002c660  sub     rsp, 2E0h
0x18002c667  mov     rax, cs:__security_cookie
0x18002c66e  xor     rax, rsp
0x18002c671  mov     [rbp+1F0h+var_20], rax
0x18002c678  mov     rsi, rdx
0x18002c67b  mov     rdi, rcx
0x18002c67e  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002c685  add     rbx, 28h ; '('
0x18002c689  mov     rcx, rbx; lpCriticalSection
0x18002c68c  call    cs:__imp_EnterCriticalSection
0x18002c692  mov     [rsp+2F0h+var_2B0], rbx
0x18002c697  mov     [rbp+1F0h+hKey], 0
0x18002c69f  mov     rdx, cs:qword_180068EC8
0x18002c6a6  lea     rcx, [rsp+2F0h+var_288]
0x18002c6ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002c6b0  nop
0x18002c6b1  lea     r8, asc_18004F678; "\\"
0x18002c6b8  mov     rdx, rax
0x18002c6bb  lea     rcx, [rsp+2F0h+var_2A8]
0x18002c6c0  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002c6c5  nop
0x18002c6c6  lea     r8, [rdi+90h]
0x18002c6cd  mov     rdx, rax
0x18002c6d0  lea     rcx, [rbp+1F0h+var_250]
0x18002c6d4  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002c6d9  nop
0x18002c6da  lea     rcx, [rsp+2F0h+var_2A8]
0x18002c6df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c6e4  nop
0x18002c6e5  lea     rcx, [rsp+2F0h+var_288]
0x18002c6ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c6ef  xor     edx, edx
0x18002c6f1  lea     rcx, [rbp+1F0h+hKey]
0x18002c6f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002c6fa  lea     rcx, [rbp+1F0h+var_250]
0x18002c6fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c703  mov     rdx, rax; lpSubKey
0x18002c706  lea     rax, [rbp+1F0h+hKey]
0x18002c70a  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18002c70f  mov     r9d, 20019h; samDesired
0x18002c715  xor     r8d, r8d; ulOptions
0x18002c718  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c71f  call    cs:__imp_RegOpenKeyExW
0x18002c725  test    eax, eax
0x18002c727  jnz     loc_18002C8F9
0x18002c72d  xor     edx, edx; Val
0x18002c72f  mov     r8d, 208h; Size
0x18002c735  lea     rcx, [rbp+1F0h+Name]; void *
0x18002c739  call    memset_0
0x18002c73e  mov     [rbp+1F0h+var_260], 0
0x18002c746  xor     ebx, ebx
0x18002c748  lea     edi, [rbx+4]
0x18002c74b  mov     r9d, 104h; cchName
0x18002c751  lea     r8, [rbp+1F0h+Name]; lpName
0x18002c755  mov     edx, ebx; dwIndex
0x18002c757  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18002c75b  call    cs:__imp_RegEnumKeyW
0x18002c761  mov     r9d, eax; char *
0x18002c764  cmp     eax, 103h
0x18002c769  jz      loc_18002C85C
0x18002c76f  test    eax, eax
0x18002c771  jnz     loc_18002C8AA
0x18002c777  mov     dword ptr [rbp+1F0h+var_258], eax
0x18002c77a  mov     [rbp+1F0h+var_254], edi
0x18002c77d  lea     rax, [rbp+1F0h+var_254]
0x18002c781  mov     [rsp+2F0h+pcbData], rax; pcbData
0x18002c786  lea     rax, [rbp+1F0h+var_258]
0x18002c78a  mov     [rsp+2F0h+pvData], rax; char *
0x18002c78f  mov     [rsp+2F0h+phkResult], 0; pdwType
0x18002c798  mov     r9d, 10h; dwFlags
0x18002c79e  lea     r8, aDataplanflags; "DataPlanFlags"
0x18002c7a5  lea     rdx, [rbp+1F0h+Name]; lpSubKey
0x18002c7a9  mov     rcx, [rbp+1F0h+hKey]; hkey
0x18002c7ad  call    cs:__imp_RegGetValueW
0x18002c7b3  test    eax, eax
0x18002c7b5  jnz     loc_18002C99B
0x18002c7bb  test    [rbp+1F0h+var_258], 1
0x18002c7bf  jz      loc_18002C84C
0x18002c7c5  xor     edx, edx
0x18002c7c7  lea     rcx, [rbp+1F0h+var_260]
0x18002c7cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002c7d0  lea     rax, [rbp+1F0h+var_260]
0x18002c7d4  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18002c7d9  mov     r9d, 20006h; samDesired
0x18002c7df  xor     r8d, r8d; ulOptions
0x18002c7e2  lea     rdx, [rbp+1F0h+Name]; lpSubKey
0x18002c7e6  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18002c7ea  call    cs:__imp_RegOpenKeyExW
0x18002c7f0  test    eax, eax
0x18002c7f2  jnz     loc_18002C973
0x18002c7f8  mov     dword ptr [rsp+2F0h+pvData], edi; char *
0x18002c7fc  mov     [rsp+2F0h+phkResult], rsi; lpData
0x18002c801  mov     r9d, edi; dwType
0x18002c804  xor     r8d, r8d; Reserved
0x18002c807  lea     rdx, aDaysincycle; "DaysInCycle"
0x18002c80e  mov     rcx, [rbp+1F0h+var_260]; hKey
0x18002c812  call    cs:__imp_RegSetValueExW
0x18002c818  test    eax, eax
0x18002c81a  jnz     loc_18002C94B
0x18002c820  lea     rax, [rsi+4]
0x18002c824  mov     dword ptr [rsp+2F0h+pvData], edi; char *
0x18002c828  mov     [rsp+2F0h+phkResult], rax; lpData
0x18002c82d  mov     r9d, edi; dwType
0x18002c830  xor     r8d, r8d; Reserved
0x18002c833  lea     rdx, aDaysintocycle; "DaysIntoCycle"
0x18002c83a  mov     rcx, [rbp+1F0h+var_260]; hKey
0x18002c83e  call    cs:__imp_RegSetValueExW
0x18002c844  test    eax, eax
0x18002c846  jnz     loc_18002C923
0x18002c84c  inc     ebx
0x18002c84e  cmp     ebx, 2710h
0x18002c854  jb      loc_18002C74B
0x18002c85a  jmp     short loc_18002C860
0x18002c85c  test    ebx, ebx
0x18002c85e  jz      short loc_18002C8CF
0x18002c860  lea     rcx, [rbp+1F0h+var_260]
0x18002c864  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c869  nop
0x18002c86a  lea     rcx, [rbp+1F0h+var_250]
0x18002c86e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c873  nop
0x18002c874  lea     rcx, [rbp+1F0h+hKey]
0x18002c878  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c87d  nop
0x18002c87e  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c883  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002c888  mov     rcx, [rbp+1F0h+var_20]
0x18002c88f  xor     rcx, rsp; StackCookie
0x18002c892  call    __security_check_cookie
0x18002c897  mov     rbx, [rsp+2F0h+arg_10]
0x18002c89f  add     rsp, 2E0h
0x18002c8a6  pop     rdi
0x18002c8a7  pop     rsi
0x18002c8a8  pop     rbp
0x18002c8a9  retn
0x18002c8aa  mov     rcx, [rbp+1F8h]; this
0x18002c8b1  lea     rax, aDusmstoreSetop; "DusmStore::SetOperatorCycleData::RegEnu"...
0x18002c8b8  mov     [rsp+2F0h+phkResult], rax; unsigned int
0x18002c8bd  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c8c4  mov     edx, 4BCh; void *
0x18002c8c9  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c8cf  mov     rcx, [rbp+1F8h]; this
0x18002c8d6  lea     rax, aDusmstoreSetop; "DusmStore::SetOperatorCycleData::RegEnu"...
0x18002c8dd  mov     [rsp+2F0h+phkResult], rax; unsigned int
0x18002c8e2  mov     r9d, 490h; char *
0x18002c8e8  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c8ef  lea     edx, [r9+28h]; void *
0x18002c8f3  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c8f9  mov     rcx, [rbp+1F8h]; this
0x18002c900  lea     rax, aDusmstoreSetop_4; "DusmStore::SetOperatorCycleData::RegOpe"...
0x18002c907  mov     [rsp+2F0h+phkResult], rax; unsigned int
0x18002c90c  mov     r9d, 490h; char *
0x18002c912  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c919  lea     edx, [r9+15h]; void *
0x18002c91d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c923  mov     rcx, [rbp+1F8h]; this
0x18002c92a  lea     rdx, aDusmstoreSetop_0; "DusmStore::SetOperatorCycleData::RegSet"...
0x18002c931  mov     [rsp+2F0h+phkResult], rdx; unsigned int
0x18002c936  mov     r9d, eax; char *
0x18002c939  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c940  mov     edx, 4E0h; void *
0x18002c945  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c94b  mov     rcx, [rbp+1F8h]; this
0x18002c952  lea     rdx, aDusmstoreSetop_3; "DusmStore::SetOperatorCycleData::RegSet"...
0x18002c959  mov     [rsp+2F0h+phkResult], rdx; unsigned int
0x18002c95e  mov     r9d, eax; char *
0x18002c961  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c968  mov     edx, 4D8h; void *
0x18002c96d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c973  mov     rcx, [rbp+1F8h]; this
0x18002c97a  lea     rdx, aDusmstoreSetop_2; "DusmStore::SetOperatorCycleData::RegOpe"...
0x18002c981  mov     [rsp+2F0h+phkResult], rdx; unsigned int
0x18002c986  mov     r9d, eax; char *
0x18002c989  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c990  mov     edx, 4D0h; void *
0x18002c995  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002c99b  mov     rcx, [rbp+1F8h]; this
0x18002c9a2  lea     rdx, aDusmstoreSetop_1; "DusmStore::SetOperatorCycleData::RegGet"...
0x18002c9a9  mov     [rsp+2F0h+phkResult], rdx; unsigned int
0x18002c9ae  mov     r9d, eax; char *
0x18002c9b1  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002c9b8  mov     edx, 4C5h; void *
0x18002c9bd  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
