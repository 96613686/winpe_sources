# DusmStore::QueryOperatorCycleData(DusmConnection const &)

- ea: `0x180029df8`
- end: `0x18002a1be`
- name: `?QueryOperatorCycleData@DusmStore@@SA?AU_DUSM_OPERATOR_CYCLE_DATA@@AEBVDusmConnection@@@Z`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001fe44`

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
- `0x180029df8`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029e34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029e34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029ec7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029ec7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029f5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a009`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a044`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029f5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a009`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a044`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180029f0c`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180029f0c`

## string_xrefs

- `0x18002a123`: `DusmStore::QueryOperatorCycleData::RegOpenKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DusmStore::QueryOperatorCycleData(__int64 a1)
{
  LPCRITICAL_SECTION v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  DWORD v6; // ebx
  unsigned int v7; // eax
  unsigned int ValueW; // eax
  __int64 v9; // rbx
  unsigned int v11; // eax
  unsigned int v12; // eax
  const char *pvData; // [rsp+28h] [rbp-D8h]
  const char *pvDataa; // [rsp+28h] [rbp-D8h]
  const char *pvDatab; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION v17; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[32]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  char v21[4]; // [rsp+98h] [rbp-68h] BYREF
  DWORD v22[3]; // [rsp+9Ch] [rbp-64h] BYREF
  char v23[8]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD pcbData; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v25[40]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR Name[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v2 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v17 = v2;
  hKey = 0;
  v3 = std::wstring::wstring((__int64)v19, (__int64)qword_180068EC8);
  v4 = std::operator+<wchar_t>((__int64)v18, v3, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v25, v4, a1 + 144);
  std::wstring::_Tidy_deallocate(v18);
  std::wstring::_Tidy_deallocate(v19);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x458,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x490,
      (unsigned int)"DusmStore::QueryOperatorCycleData::RegOpenKeyExW",
      pvData);
  memset_0(Name, 0, 0x208u);
  v16 = 0;
  *(_QWORD *)v23 = 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = RegEnumKeyW(hKey, v6, Name, 0x104u);
    if ( v7 == 259 )
      break;
    if ( v7 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x470,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v7,
        (unsigned int)"DusmStore::QueryOperatorCycleData::RegEnumKey",
        pvData);
    *(_DWORD *)v21 = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, Name, L"DataPlanFlags", 0x10u, 0, v21, &pcbData);
    if ( ValueW )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x479,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)ValueW,
        (unsigned int)"DusmStore::QueryOperatorCycleData::RegGetValue::flags",
        pvData);
    if ( (v21[0] & 1) != 0 )
    {
      v22[0] = 4;
      v11 = RegGetValueW(hKey, Name, L"DaysInCycle", 0x10u, 0, v23, v22);
      if ( v11 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x486,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)v11,
          (unsigned int)"DusmStore::QueryOperatorCycleData::RegGetValue::daysInCycle",
          pvDataa);
      v12 = RegGetValueW(hKey, Name, L"DaysIntoCycle", 0x10u, 0, &v23[4], v22);
      if ( v12 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x48E,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)v12,
          (unsigned int)"DusmStore::QueryOperatorCycleData::RegGetValue::daysIntoCycle",
          pvDatab);
      v9 = *(_QWORD *)v23;
      if ( *(_DWORD *)&v23[4] > *(_DWORD *)v23 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x492,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0xD,
          (unsigned int)"DusmStore::QueryOperatorCycleData::RegGetValue::daysIntoCycle",
          pvDatab);
      goto LABEL_9;
    }
    if ( ++v6 >= 0x2710 )
    {
      v9 = *(_QWORD *)v23;
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
      std::wstring::_Tidy_deallocate(v25);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
      return v9;
    }
  }
  if ( !v6 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x490,
      (unsigned int)"DusmStore::QueryOperatorCycleData::RegEnumKey",
      pvData);
  *(_QWORD *)v22 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
  std::wstring::_Tidy_deallocate(v25);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  return *(_QWORD *)v22;
}

```

## disassembly

```asm
0x180029df8  mov     [rsp-8+arg_8], rbx
0x180029dfd  mov     [rsp-8+arg_10], rdi
0x180029e02  push    rbp
0x180029e03  lea     rbp, [rsp-200h]
0x180029e0b  sub     rsp, 300h
0x180029e12  mov     rax, cs:__security_cookie
0x180029e19  xor     rax, rsp
0x180029e1c  mov     [rbp+200h+var_10], rax
0x180029e23  mov     rdi, rcx
0x180029e26  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x180029e2d  add     rbx, 28h ; '('
0x180029e31  mov     rcx, rbx; lpCriticalSection
0x180029e34  call    cs:__imp_EnterCriticalSection
0x180029e3a  mov     [rsp+300h+var_2B8], rbx
0x180029e3f  mov     [rbp+200h+hKey], 0
0x180029e47  mov     rdx, cs:qword_180068EC8
0x180029e4e  lea     rcx, [rsp+300h+var_290]
0x180029e53  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180029e58  nop
0x180029e59  lea     r8, asc_18004F678; "\\"
0x180029e60  mov     rdx, rax
0x180029e63  lea     rcx, [rsp+300h+var_2B0]
0x180029e68  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180029e6d  nop
0x180029e6e  lea     r8, [rdi+90h]
0x180029e75  mov     rdx, rax
0x180029e78  lea     rcx, [rbp+200h+var_248]
0x180029e7c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x180029e81  nop
0x180029e82  lea     rcx, [rsp+300h+var_2B0]
0x180029e87  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029e8c  nop
0x180029e8d  lea     rcx, [rsp+300h+var_290]
0x180029e92  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029e97  xor     edx, edx
0x180029e99  lea     rcx, [rbp+200h+hKey]
0x180029e9d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029ea2  lea     rcx, [rbp+200h+var_248]
0x180029ea6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029eab  mov     rdx, rax; lpSubKey
0x180029eae  lea     rax, [rbp+200h+hKey]
0x180029eb2  mov     [rsp+300h+phkResult], rax; phkResult
0x180029eb7  mov     r9d, 20019h; samDesired
0x180029ebd  xor     r8d, r8d; ulOptions
0x180029ec0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029ec7  call    cs:__imp_RegOpenKeyExW
0x180029ecd  test    eax, eax
0x180029ecf  jnz     loc_18002A11C
0x180029ed5  xor     edx, edx; Val
0x180029ed7  mov     r8d, 208h; Size
0x180029edd  lea     rcx, [rbp+200h+Name]; void *
0x180029ee1  call    memset_0
0x180029ee6  mov     [rsp+300h+var_2C0], 0
0x180029eef  mov     qword ptr [rbp+200h+var_258], 0
0x180029ef7  xor     ebx, ebx
0x180029ef9  lea     edi, [rbx+10h]
0x180029efc  mov     r9d, 104h; cchName
0x180029f02  lea     r8, [rbp+200h+Name]; lpName
0x180029f06  mov     edx, ebx; dwIndex
0x180029f08  mov     rcx, [rbp+200h+hKey]; hKey
0x180029f0c  call    cs:__imp_RegEnumKeyW
0x180029f12  mov     r9d, eax; char *
0x180029f15  cmp     eax, 103h
0x180029f1a  jz      loc_18002A060
0x180029f20  test    eax, eax
0x180029f22  jnz     loc_18002A0A2
0x180029f28  mov     dword ptr [rbp+200h+var_268], eax
0x180029f2b  mov     [rbp+200h+var_250], 4
0x180029f32  lea     rax, [rbp+200h+var_250]
0x180029f36  mov     [rsp+300h+pcbData], rax; pcbData
0x180029f3b  lea     rax, [rbp+200h+var_268]
0x180029f3f  mov     [rsp+300h+pvData], rax; char *
0x180029f44  mov     [rsp+300h+phkResult], 0; pdwType
0x180029f4d  mov     r9d, edi; dwFlags
0x180029f50  lea     r8, aDataplanflags; "DataPlanFlags"
0x180029f57  lea     rdx, [rbp+200h+Name]; lpSubKey
0x180029f5b  mov     rcx, [rbp+200h+hKey]; hkey
0x180029f5f  call    cs:__imp_RegGetValueW
0x180029f65  test    eax, eax
0x180029f67  jnz     loc_18002A196
0x180029f6d  test    [rbp+200h+var_268], 1
0x180029f71  jnz     short loc_180029FD5
0x180029f73  inc     ebx
0x180029f75  cmp     ebx, 2710h
0x180029f7b  jb      loc_180029EFC
0x180029f81  mov     rbx, qword ptr [rbp+200h+var_258]
0x180029f85  lea     rcx, [rsp+300h+var_2C0]
0x180029f8a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029f8f  nop
0x180029f90  lea     rcx, [rbp+200h+var_248]
0x180029f94  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029f99  nop
0x180029f9a  lea     rcx, [rbp+200h+hKey]
0x180029f9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029fa3  nop
0x180029fa4  lea     rcx, [rsp+300h+var_2B8]
0x180029fa9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180029fae  mov     rax, rbx
0x180029fb1  mov     rcx, [rbp+200h+var_10]
0x180029fb8  xor     rcx, rsp; StackCookie
0x180029fbb  call    __security_check_cookie
0x180029fc0  lea     r11, [rsp+300h+var_s0]
0x180029fc8  mov     rbx, [r11+18h]
0x180029fcc  mov     rdi, [r11+20h]
0x180029fd0  mov     rsp, r11
0x180029fd3  pop     rbp
0x180029fd4  retn
0x180029fd5  mov     [rbp+200h+var_264], 4
0x180029fdc  lea     rax, [rbp+200h+var_264]
0x180029fe0  mov     [rsp+300h+pcbData], rax; pcbData
0x180029fe5  lea     rax, [rbp+200h+var_258]
0x180029fe9  mov     [rsp+300h+pvData], rax; char *
0x180029fee  mov     [rsp+300h+phkResult], 0; pdwType
0x180029ff7  mov     r9d, edi; dwFlags
0x180029ffa  lea     r8, aDaysincycle; "DaysInCycle"
0x18002a001  lea     rdx, [rbp+200h+Name]; lpSubKey
0x18002a005  mov     rcx, [rbp+200h+hKey]; hkey
0x18002a009  call    cs:__imp_RegGetValueW
0x18002a00f  test    eax, eax
0x18002a011  jnz     loc_18002A146
0x18002a017  lea     rax, [rbp+200h+var_264]
0x18002a01b  mov     [rsp+300h+pcbData], rax; pcbData
0x18002a020  lea     rax, [rbp+200h+var_258+4]
0x18002a024  mov     [rsp+300h+pvData], rax; char *
0x18002a029  mov     [rsp+300h+phkResult], 0; pdwType
0x18002a032  mov     r9d, edi; dwFlags
0x18002a035  lea     r8, aDaysintocycle; "DaysIntoCycle"
0x18002a03c  lea     rdx, [rbp+200h+Name]; lpSubKey
0x18002a040  mov     rcx, [rbp+200h+hKey]; hkey
0x18002a044  call    cs:__imp_RegGetValueW
0x18002a04a  test    eax, eax
0x18002a04c  jnz     loc_18002A16E
0x18002a052  mov     rbx, qword ptr [rbp+200h+var_258]
0x18002a056  cmp     dword ptr [rbp+200h+var_258+4], ebx
0x18002a059  ja      short loc_18002A0C7
0x18002a05b  jmp     loc_180029F85
0x18002a060  test    ebx, ebx
0x18002a062  jz      loc_18002A0F2
0x18002a068  mov     qword ptr [rbp+200h+var_264], 0
0x18002a070  lea     rcx, [rsp+300h+var_2C0]
0x18002a075  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a07a  nop
0x18002a07b  lea     rcx, [rbp+200h+var_248]
0x18002a07f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a084  nop
0x18002a085  lea     rcx, [rbp+200h+hKey]
0x18002a089  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a08e  nop
0x18002a08f  lea     rcx, [rsp+300h+var_2B8]
0x18002a094  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002a099  mov     rax, qword ptr [rbp+200h+var_264]
0x18002a09d  jmp     loc_180029FB1
0x18002a0a2  mov     rcx, [rbp+208h]; this
0x18002a0a9  lea     rax, aDusmstoreQuery_11; "DusmStore::QueryOperatorCycleData::RegE"...
0x18002a0b0  mov     [rsp+300h+phkResult], rax; unsigned int
0x18002a0b5  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002a0bc  mov     edx, 470h; void *
0x18002a0c1  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002a0c7  mov     rcx, [rbp+208h]; this
0x18002a0ce  lea     rdx, aDusmstoreQuery_20; "DusmStore::QueryOperatorCycleData::RegG"...
0x18002a0d5  mov     [rsp+300h+phkResult], rdx; unsigned int
0x18002a0da  mov     r9d, 0Dh; char *
0x18002a0e0  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002a0e7  mov     edx, 492h; void *
0x18002a0ec  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002a0f2  mov     rcx, [rbp+208h]; this
0x18002a0f9  lea     rax, aDusmstoreQuery_11; "DusmStore::QueryOperatorCycleData::RegE"...
0x18002a100  mov     [rsp+300h+phkResult], rax; unsigned int
0x18002a105  mov     r9d, 490h; char *
0x18002a10b  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002a112  lea     edx, [r9-24h]; void *
0x18002a116  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002a11c  mov     rcx, [rbp+208h]; this
0x18002a123  lea     rax, aDusmstoreQuery_10; "DusmStore::QueryOperatorCycleData::RegO"...
0x18002a12a  mov     [rsp+300h+phkResult], rax; unsigned int
0x18002a12f  mov     r9d, 490h; char *
0x18002a135  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002a13c  lea     edx, [r9-38h]; void *
0x18002a140  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002a146  mov     rcx, [rbp+208h]; this
0x18002a14d  lea     rdx, aDusmstoreQuery_16; "DusmStore::QueryOperatorCycleData::RegG"...
0x18002a154  mov     [rsp+300h+phkResult], rdx; unsigned int
0x18002a159  mov     r9d, eax; char *
0x18002a15c  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002a163  mov     edx, 486h; void *
0x18002a168  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002a16e  mov     rcx, [rbp+208h]; this
0x18002a175  lea     rdx, aDusmstoreQuery_20; "DusmStore::QueryOperatorCycleData::RegG"...
0x18002a17c  mov     [rsp+300h+phkResult], rdx; unsigned int
0x18002a181  mov     r9d, eax; char *
0x18002a184  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002a18b  mov     edx, 48Eh; void *
0x18002a190  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002a196  mov     rcx, [rbp+208h]; this
0x18002a19d  lea     rdx, aDusmstoreQuery_26; "DusmStore::QueryOperatorCycleData::RegG"...
0x18002a1a4  mov     [rsp+300h+phkResult], rdx; unsigned int
0x18002a1a9  mov     r9d, eax; char *
0x18002a1ac  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002a1b3  mov     edx, 479h; void *
0x18002a1b8  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
