# DusmStore::QueryCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)

- ea: `0x1800289c0`
- end: `0x180028f3f`
- name: `?QueryCost@DusmStore@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z`
- size: `1407`
- prototype: ``
- caller_count: `5`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034d24`
- `0x180037984`
- `0x1800381b8`
- `0x18003a1e4`
- `0x18003aa18`

## callees

- `0x1800021e4`
- `0x18000541c`
- `0x180005620`
- `0x180007c90`
- `0x180008704`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x180013444`
- `0x18001742c`
- `0x180017464`
- `0x18001d87c`
- `0x180026fa0`
- `0x1800289c0`
- `0x18002da30`
- `0x18002da58`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028a3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028a3a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180028a61`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180028a61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028afa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028beb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028afa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028b7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028beb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028d17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180028d17`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DusmStore::QueryCost(__int64 a1, unsigned int a2, _DWORD *a3)
{
  unsigned int v5; // edi
  LPCRITICAL_SECTION v6; // rbx
  __int64 v7; // r15
  const WCHAR *v8; // rax
  LSTATUS v9; // ebx
  _DWORD *v10; // rcx
  const WCHAR *v11; // rax
  const WCHAR *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r9
  HKEY v18; // r10
  const WCHAR *v19; // r15
  const WCHAR *v20; // r12
  int v21; // ebx
  LSTATUS ValueW; // r13d
  const wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // r9
  _DWORD *v30; // rax
  const char *pvData; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h] BYREF
  LPCRITICAL_SECTION v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v40; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v41; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v42; // [rsp+C0h] [rbp-40h]
  HKEY phkResult; // [rsp+C8h] [rbp-38h] BYREF
  int v44; // [rsp+D0h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+D4h] [rbp-2Ch] BYREF
  _BYTE v46[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v47[40]; // [rsp+F8h] [rbp-8h] BYREF
  OLECHAR sz[40]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v42 = a3;
  v5 = *(_DWORD *)(a1 + 16);
  if ( v5 != 3 )
  {
    if ( v5 != 2 )
    {
      if ( v5 != 1 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x1F0,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::QueryCost::mediaType",
          pvData);
      if ( a2 != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x215,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::QueryCost::source::notUser",
          pvData);
      goto LABEL_8;
    }
    if ( !*(_QWORD *)(a1 + 64) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x206,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryCost::profileName",
        pvData);
  }
  if ( a2 - 2 > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::QueryCost::source::notUserOrOperator",
      pvData);
LABEL_8:
  v6 = DusmStore::s_pInstance;
  EnterCriticalSection(DusmStore::s_pInstance);
  v38 = v6;
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2((const GUID *const)(a1 + 32), sz, 40) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0xE,
      (unsigned int)"DusmStore::QueryCost::StringFromGUID2",
      pvData);
  phkResult = 0;
  if ( v5 == 1 || v5 == 2 )
  {
    std::wstring::wstring((__int64)v47, (__int64)qword_180068EC0);
    std::wstring::append(v47, L"\\");
    std::wstring::append(v47, sz);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x20019u, &phkResult);
    std::wstring::_Tidy_deallocate(v47);
    v7 = a1 + 144;
  }
  else
  {
    std::wstring::wstring((__int64)v46, (__int64)qword_180068EC8);
    std::wstring::append(v46, L"\\");
    v7 = a1 + 144;
    std::wstring::append(v46, a1 + 144);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v46);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &phkResult);
    if ( v9 )
    {
      v10 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
      if ( *v10 > 5u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (int)v10,
          (int)byte_180058559);
      std::wstring::_Tidy_deallocate(v46);
      goto LABEL_18;
    }
    std::wstring::append(v46, L"\\");
    std::wstring::append(v46, a1 + 112);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v46);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &phkResult);
    std::wstring::_Tidy_deallocate(v46);
  }
  if ( v9 )
  {
LABEL_18:
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
    {
      v33 = (__int64)sz;
      v34 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 112);
      v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7);
      v36 = DusmSourceToSz(a2, v13, v14, v15);
      v37 = DusmMediaTypeToSz(v5);
      LODWORD(v32) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v16,
        (int)&byte_1800584F1,
        v16,
        v17,
        (__int64)&v32,
        (const WCHAR **)&v37,
        (const WCHAR **)&v36,
        (const WCHAR **)&v35,
        (const WCHAR **)&v34,
        (const WCHAR **)&v33);
    }
LABEL_32:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v38);
    return 0;
  }
  v18 = phkResult;
  if ( v5 == 3 )
  {
    v19 = 0;
  }
  else if ( v5 == 1 )
  {
    v19 = L"*";
  }
  else
  {
    v19 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
  }
  v20 = L"OperatorCost";
  if ( a2 != 3 )
    v20 = L"UserCost";
  v44 = 0;
  v21 = 4;
  pcbData = 4;
  ValueW = RegGetValueW(v18, v19, v20, 0x10u, 0, &v44, &pcbData);
  if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
  {
    v23 = L"n/a";
    if ( v5 != 3 )
      v23 = v19;
    v37 = (__int64)v23;
    v36 = (__int64)sz;
    v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 112);
    v34 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 144);
    LODWORD(v32) = v44;
    v39 = (__int64)v20;
    v40 = DusmSourceToSz(a2, v24, v25, v26);
    v41 = DusmMediaTypeToSz(v5);
    LODWORD(v33) = ValueW;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      v27,
      (int)&byte_18005846D,
      v27,
      v28,
      (__int64)&v33,
      (const WCHAR **)&v41,
      (const WCHAR **)&v40,
      (const WCHAR **)&v39,
      (__int64)&v32,
      (const WCHAR **)&v34,
      (const WCHAR **)&v35,
      (const WCHAR **)&v36,
      (const WCHAR **)&v37);
  }
  if ( ValueW )
    goto LABEL_32;
  v30 = v42;
  *v42 = v44;
  if ( a2 != 3 )
    v21 = 2;
  v30[1] = v21;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v38);
  return 1;
}

```

## disassembly

```asm
0x1800289c0  mov     [rsp-8+arg_8], rbx
0x1800289c5  push    rbp
0x1800289c6  push    rsi
0x1800289c7  push    rdi
0x1800289c8  push    r12
0x1800289ca  push    r13
0x1800289cc  push    r14
0x1800289ce  push    r15
0x1800289d0  lea     rbp, [rsp-80h]
0x1800289d5  sub     rsp, 180h
0x1800289dc  mov     rax, cs:__security_cookie
0x1800289e3  xor     rax, rsp
0x1800289e6  mov     [rbp+0B0h+var_40], rax
0x1800289ea  mov     [rbp+0B0h+var_F0], r8
0x1800289ee  mov     r14d, edx
0x1800289f1  mov     rsi, rcx
0x1800289f4  mov     edi, [rcx+10h]
0x1800289f7  xor     r13d, r13d
0x1800289fa  lea     eax, [r13+2]
0x1800289fe  cmp     edi, 3
0x180028a01  jz      short loc_180028A24
0x180028a03  cmp     edi, eax
0x180028a05  jz      short loc_180028A1A
0x180028a07  cmp     edi, 1
0x180028a0a  jnz     loc_180028EBE
0x180028a10  cmp     edx, eax
0x180028a12  jnz     loc_180028E93
0x180028a18  jmp     short loc_180028A30
0x180028a1a  cmp     [rcx+40h], r13
0x180028a1e  jz      loc_180028EE9
0x180028a24  lea     eax, [rdx-2]
0x180028a27  cmp     eax, 1
0x180028a2a  ja      loc_180028F14
0x180028a30  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x180028a37  mov     rcx, rbx; lpCriticalSection
0x180028a3a  call    cs:__imp_EnterCriticalSection
0x180028a40  mov     [rbp+0B0h+var_110], rbx
0x180028a44  xor     edx, edx; Val
0x180028a46  lea     r8d, [rdx+50h]; Size
0x180028a4a  lea     rcx, [rbp+0B0h+sz]; void *
0x180028a4e  call    memset_0
0x180028a53  lea     rcx, [rsi+20h]; rguid
0x180028a57  mov     r8d, 28h ; '('; cchMax
0x180028a5d  lea     rdx, [rbp+0B0h+sz]; lpsz
0x180028a61  call    cs:__imp_StringFromGUID2
0x180028a67  test    eax, eax
0x180028a69  jz      loc_180028E68
0x180028a6f  mov     r10, r13
0x180028a72  mov     [rbp+0B0h+var_E8], r13
0x180028a76  mov     ecx, edi
0x180028a78  sub     ecx, 1
0x180028a7b  jz      loc_180028B8D
0x180028a81  sub     ecx, 1
0x180028a84  jz      loc_180028B8D
0x180028a8a  cmp     ecx, 1
0x180028a8d  jnz     loc_180028CAD
0x180028a93  mov     rdx, cs:qword_180068EC8
0x180028a9a  lea     rcx, [rbp+0B0h+var_D8]
0x180028a9e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180028aa3  nop
0x180028aa4  lea     rdx, asc_18004F678; "\\"
0x180028aab  lea     rcx, [rbp+0B0h+var_D8]
0x180028aaf  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180028ab4  lea     r15, [rsi+90h]
0x180028abb  mov     rdx, r15
0x180028abe  lea     rcx, [rbp+0B0h+var_D8]
0x180028ac2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180028ac7  xor     edx, edx
0x180028ac9  lea     rcx, [rbp+0B0h+var_E8]
0x180028acd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180028ad2  lea     rcx, [rbp+0B0h+var_D8]
0x180028ad6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028adb  mov     rdx, rax; lpSubKey
0x180028ade  lea     rax, [rbp+0B0h+var_E8]
0x180028ae2  mov     [rsp+1B0h+phkResult], rax; phkResult
0x180028ae7  mov     r9d, 20019h; samDesired
0x180028aed  xor     r8d, r8d; ulOptions
0x180028af0  mov     r12, 0FFFFFFFF80000002h
0x180028af7  mov     rcx, r12; hKey
0x180028afa  call    cs:__imp_RegOpenKeyExW
0x180028b00  mov     ebx, eax
0x180028b02  test    eax, eax
0x180028b04  jz      short loc_180028B31
0x180028b06  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180028b0b  mov     rcx, [rax+8]
0x180028b0f  mov     edx, [rcx]
0x180028b11  cmp     edx, 5
0x180028b14  jbe     short loc_180028B23
0x180028b16  lea     rdx, byte_180058559
0x180028b1d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180028b22  nop
0x180028b23  lea     rcx, [rbp+0B0h+var_D8]
0x180028b27  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028b2c  jmp     loc_180028C0B
0x180028b31  lea     rdx, asc_18004F678; "\\"
0x180028b38  lea     rcx, [rbp+0B0h+var_D8]
0x180028b3c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180028b41  lea     rdx, [rsi+70h]
0x180028b45  lea     rcx, [rbp+0B0h+var_D8]
0x180028b49  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180028b4e  xor     edx, edx
0x180028b50  lea     rcx, [rbp+0B0h+var_E8]
0x180028b54  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180028b59  lea     rcx, [rbp+0B0h+var_D8]
0x180028b5d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028b62  mov     rdx, rax; lpSubKey
0x180028b65  lea     rax, [rbp+0B0h+var_E8]
0x180028b69  mov     [rsp+1B0h+phkResult], rax; phkResult
0x180028b6e  mov     r9d, 20019h; samDesired
0x180028b74  xor     r8d, r8d; ulOptions
0x180028b77  mov     rcx, r12; hKey
0x180028b7a  call    cs:__imp_RegOpenKeyExW
0x180028b80  mov     ebx, eax
0x180028b82  lea     rcx, [rbp+0B0h+var_D8]
0x180028b86  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028b8b  jmp     short loc_180028C03
0x180028b8d  mov     rdx, cs:qword_180068EC0
0x180028b94  lea     rcx, [rbp+0B0h+var_B8]
0x180028b98  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180028b9d  nop
0x180028b9e  lea     rdx, asc_18004F678; "\\"
0x180028ba5  lea     rcx, [rbp+0B0h+var_B8]
0x180028ba9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180028bae  lea     rdx, [rbp+0B0h+sz]
0x180028bb2  lea     rcx, [rbp+0B0h+var_B8]
0x180028bb6  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180028bbb  xor     edx, edx
0x180028bbd  lea     rcx, [rbp+0B0h+var_E8]
0x180028bc1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180028bc6  lea     rcx, [rbp+0B0h+var_B8]
0x180028bca  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028bcf  mov     rdx, rax; lpSubKey
0x180028bd2  lea     rax, [rbp+0B0h+var_E8]
0x180028bd6  mov     [rsp+1B0h+phkResult], rax; phkResult
0x180028bdb  mov     r9d, 20019h; samDesired
0x180028be1  xor     r8d, r8d; ulOptions
0x180028be4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028beb  call    cs:__imp_RegOpenKeyExW
0x180028bf1  mov     ebx, eax
0x180028bf3  lea     rcx, [rbp+0B0h+var_B8]
0x180028bf7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028bfc  lea     r15, [rsi+90h]
0x180028c03  test    ebx, ebx
0x180028c05  jz      loc_180028CA9
0x180028c0b  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180028c10  mov     r8, [rax+8]
0x180028c14  mov     eax, [r8]
0x180028c17  cmp     eax, 5
0x180028c1a  jbe     loc_180028DFA
0x180028c20  lea     rax, [rbp+0B0h+sz]
0x180028c24  mov     [rsp+1B0h+var_138], rax
0x180028c29  lea     rcx, [rsi+70h]
0x180028c2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028c32  mov     [rbp+0B0h+var_130], rax
0x180028c36  mov     rcx, r15
0x180028c39  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028c3e  mov     [rbp+0B0h+var_128], rax
0x180028c42  mov     ecx, r14d
0x180028c45  call    ?DusmSourceToSz@@YAPEB_WW4_DUSM_SOURCE@@@Z; DusmSourceToSz(_DUSM_SOURCE)
0x180028c4a  mov     [rbp+0B0h+var_120], rax
0x180028c4e  mov     ecx, edi
0x180028c50  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x180028c55  mov     [rbp+0B0h+var_118], rax
0x180028c59  mov     dword ptr [rsp+1B0h+var_140], ebx
0x180028c5d  lea     rax, [rsp+1B0h+var_138]
0x180028c62  mov     [rsp+1B0h+var_168], rax; __int64
0x180028c67  lea     rax, [rbp+0B0h+var_130]
0x180028c6b  mov     [rsp+1B0h+var_170], rax; __int64
0x180028c70  lea     rax, [rbp+0B0h+var_128]
0x180028c74  mov     [rsp+1B0h+var_178], rax; __int64
0x180028c79  lea     rax, [rbp+0B0h+var_120]
0x180028c7d  mov     [rsp+1B0h+pcbData], rax; __int64
0x180028c82  lea     rax, [rbp+0B0h+var_118]
0x180028c86  mov     [rsp+1B0h+pvData], rax; __int64
0x180028c8b  lea     rax, [rsp+1B0h+var_140]
0x180028c90  mov     [rsp+1B0h+phkResult], rax; __int64
0x180028c95  lea     rdx, byte_1800584F1; int
0x180028c9c  mov     rcx, r8; int
0x180028c9f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180028ca4  jmp     loc_180028DFA
0x180028ca9  mov     r10, [rbp+0B0h+var_E8]
0x180028cad  cmp     edi, 3
0x180028cb0  jnz     short loc_180028CB7
0x180028cb2  mov     r15, r13
0x180028cb5  jmp     short loc_180028CD1
0x180028cb7  cmp     edi, 1
0x180028cba  jnz     short loc_180028CC5
0x180028cbc  lea     r15, SubKey; "*"
0x180028cc3  jmp     short loc_180028CD1
0x180028cc5  lea     rcx, [rsi+30h]
0x180028cc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028cce  mov     r15, rax
0x180028cd1  lea     rax, aUsercost; "UserCost"
0x180028cd8  lea     r12, aOperatorcost; "OperatorCost"
0x180028cdf  cmp     r14d, 3
0x180028ce3  cmovnz  r12, rax
0x180028ce7  mov     [rbp+0B0h+var_E0], r13d
0x180028ceb  mov     ebx, 4
0x180028cf0  mov     [rbp+0B0h+var_DC], ebx
0x180028cf3  lea     rax, [rbp+0B0h+var_DC]
0x180028cf7  mov     [rsp+1B0h+pcbData], rax; pcbData
0x180028cfc  lea     rax, [rbp+0B0h+var_E0]
0x180028d00  mov     [rsp+1B0h+pvData], rax; pvData
0x180028d05  mov     [rsp+1B0h+phkResult], r13; pdwType
0x180028d0a  lea     r9d, [rbx+0Ch]; dwFlags
0x180028d0e  mov     r8, r12; lpValue
0x180028d11  mov     rdx, r15; lpSubKey
0x180028d14  mov     rcx, r10; hkey
0x180028d17  call    cs:__imp_RegGetValueW
0x180028d1d  mov     r13d, eax
0x180028d20  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180028d25  mov     r8, [rax+8]
0x180028d29  mov     ecx, [r8]
0x180028d2c  cmp     ecx, 5
0x180028d2f  jbe     loc_180028DF5
0x180028d35  lea     rcx, aNA; "n/a"
0x180028d3c  cmp     edi, 3
0x180028d3f  cmovnz  rcx, r15
0x180028d43  mov     [rbp+0B0h+var_118], rcx
0x180028d47  lea     rax, [rbp+0B0h+sz]
0x180028d4b  mov     [rbp+0B0h+var_120], rax
0x180028d4f  lea     rcx, [rsi+70h]
0x180028d53  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028d58  mov     [rbp+0B0h+var_128], rax
0x180028d5c  lea     rcx, [rsi+90h]
0x180028d63  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028d68  mov     [rbp+0B0h+var_130], rax
0x180028d6c  mov     eax, [rbp+0B0h+var_E0]
0x180028d6f  mov     dword ptr [rsp+1B0h+var_140], eax
0x180028d73  mov     [rbp+0B0h+var_108], r12
0x180028d77  mov     ecx, r14d
0x180028d7a  call    ?DusmSourceToSz@@YAPEB_WW4_DUSM_SOURCE@@@Z; DusmSourceToSz(_DUSM_SOURCE)
0x180028d7f  mov     [rbp+0B0h+var_100], rax
0x180028d83  mov     ecx, edi
0x180028d85  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x180028d8a  mov     [rbp+0B0h+var_F8], rax
0x180028d8e  mov     dword ptr [rsp+1B0h+var_138], r13d
0x180028d93  lea     rax, [rbp+0B0h+var_118]
0x180028d97  mov     [rsp+1B0h+var_150], rax; __int64
0x180028d9c  lea     rax, [rbp+0B0h+var_120]
0x180028da0  mov     [rsp+1B0h+var_158], rax; __int64
0x180028da5  lea     rax, [rbp+0B0h+var_128]
0x180028da9  mov     [rsp+1B0h+var_160], rax; __int64
0x180028dae  lea     rax, [rbp+0B0h+var_130]
0x180028db2  mov     [rsp+1B0h+var_168], rax; __int64
0x180028db7  lea     rax, [rsp+1B0h+var_140]
0x180028dbc  mov     [rsp+1B0h+var_170], rax; __int64
0x180028dc1  lea     rax, [rbp+0B0h+var_108]
0x180028dc5  mov     [rsp+1B0h+var_178], rax; __int64
0x180028dca  lea     rax, [rbp+0B0h+var_100]
0x180028dce  mov     [rsp+1B0h+pcbData], rax; __int64
0x180028dd3  lea     rax, [rbp+0B0h+var_F8]
0x180028dd7  mov     [rsp+1B0h+pvData], rax; __int64
0x180028ddc  lea     rax, [rsp+1B0h+var_138]
0x180028de1  mov     [rsp+1B0h+phkResult], rax; __int64
0x180028de6  lea     rdx, byte_18005846D; int
0x180028ded  mov     rcx, r8; int
0x180028df0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@U2@U1@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@4434444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180028df5  test    r13d, r13d
0x180028df8  jz      short loc_180028E11
0x180028dfa  lea     rcx, [rbp+0B0h+var_E8]
0x180028dfe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028e03  nop
0x180028e04  lea     rcx, [rbp+0B0h+var_110]
0x180028e08  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180028e0d  xor     eax, eax
0x180028e0f  jmp     short loc_180028E41
0x180028e11  mov     ecx, [rbp+0B0h+var_E0]
0x180028e14  mov     rax, [rbp+0B0h+var_F0]
0x180028e18  mov     [rax], ecx
0x180028e1a  cmp     r14d, 3
0x180028e1e  mov     ecx, 2
0x180028e23  cmovnz  ebx, ecx
0x180028e26  mov     [rax+4], ebx
0x180028e29  lea     rcx, [rbp+0B0h+var_E8]
0x180028e2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028e32  nop
0x180028e33  lea     rcx, [rbp+0B0h+var_110]
0x180028e37  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180028e3c  mov     eax, 1
0x180028e41  mov     rcx, [rbp+0B0h+var_40]
0x180028e45  xor     rcx, rsp; StackCookie
0x180028e48  call    __security_check_cookie
0x180028e4d  mov     rbx, [rsp+1B0h+arg_8]
0x180028e55  add     rsp, 180h
0x180028e5c  pop     r15
0x180028e5e  pop     r14
0x180028e60  pop     r13
0x180028e62  pop     r12
0x180028e64  pop     rdi
0x180028e65  pop     rsi
0x180028e66  pop     rbp
0x180028e67  retn
0x180028e68  mov     rcx, [rbp+0B8h]; this
0x180028e6f  lea     rax, aDusmstoreQuery_8; "DusmStore::QueryCost::StringFromGUID2"
0x180028e76  mov     [rsp+1B0h+phkResult], rax; unsigned int
0x180028e7b  mov     r9d, 0Eh; char *
0x180028e81  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180028e88  mov     edx, 21Eh; void *
0x180028e8d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
  ... truncated ...
```
