# DusmStore::SetCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)

- ea: `0x18002b21c`
- end: `0x18002b9e7`
- name: `?SetCost@DusmStore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z`
- size: `1995`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, int)`
- caller_count: `6`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800359dc`
- `0x180036d88`
- `0x180037e38`
- `0x180038550`
- `0x18003a5ec`
- `0x18003b33c`

## callees

- `0x180001f90`
- `0x1800020fc`
- `0x1800021e4`
- `0x18000541c`
- `0x180005620`
- `0x1800057a8`
- `0x180007c90`
- `0x180008704`
- `0x18000e828`
- `0x18000f094`
- `0x180010e28`
- `0x180012fcc`
- `0x180013114`
- `0x1800132f4`
- `0x180013444`
- `0x18001742c`
- `0x180017464`
- `0x180018a50`
- `0x180018a60`
- `0x18001d87c`
- `0x180026fa0`
- `0x18002b21c`
- `0x18002da30`
- `0x18002da58`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b29b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b29b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b2c2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b2c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002b4bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002b4bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b36f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b3dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b45c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b36f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b3dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b45c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b604`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b604`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b63c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b63c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002b4df`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002b4df`

## string_xrefs

- `0x18002b8d8`: `DusmStore::SetCost::RegCreateKeyExW`
- `0x18002b91a`: `DusmStore::SetCost::RegDelete%ws`
- `0x18002b788`: `DusmStore::SetCost::RegSet%ws`

## pseudocode

```c
__int64 __fastcall DusmStore::SetCost(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  unsigned int v7; // edi
  LPCRITICAL_SECTION v8; // rbx
  const WCHAR *v9; // rax
  unsigned int v10; // ebx
  const WCHAR *v11; // rax
  _BYTE *v12; // rcx
  const WCHAR *v13; // rax
  HKEY v14; // r10
  const WCHAR *v15; // r15
  const wchar_t *v16; // rsi
  LSTATUS v17; // eax
  const WCHAR *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // r8d
  const wchar_t *v24; // rsi
  LSTATUS v25; // eax
  const WCHAR *v26; // rax
  unsigned int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  int v31; // r8d
  const char *v33; // rax
  __int64 v34; // rax
  const struct _tlgProvider_t *v35; // rax
  int v36; // esi
  __int64 Imsi; // rax
  __int64 v38; // rax
  __int64 Iccid; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // r10
  __int64 v50; // r11
  const char *v51; // rax
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  __int64 v54; // [rsp+70h] [rbp-90h] BYREF
  __int64 v55; // [rsp+78h] [rbp-88h] BYREF
  __int64 v56; // [rsp+80h] [rbp-80h] BYREF
  __int64 v57; // [rsp+88h] [rbp-78h] BYREF
  __int64 v58; // [rsp+90h] [rbp-70h] BYREF
  __int64 v59; // [rsp+98h] [rbp-68h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v63; // [rsp+B8h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+C0h] [rbp-40h] BYREF
  BYTE Data[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v66[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v67[32]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR sz[40]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v55 = a3;
  v7 = *(_DWORD *)(a1 + 16);
  if ( v7 != 3 )
  {
    if ( v7 != 2 )
    {
      if ( v7 != 1 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x273,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::SetCost::mediaType",
          samDesired);
      if ( a2 != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x298,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::SetCost::source::notUser",
          samDesired);
      goto LABEL_8;
    }
    if ( !*(_QWORD *)(a1 + 64) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::SetCost::profileName",
        samDesired);
  }
  if ( a2 - 2 > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x291,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::SetCost::source::notUserOrOperator",
      samDesired);
LABEL_8:
  v8 = DusmStore::s_pInstance;
  EnterCriticalSection(DusmStore::s_pInstance);
  v63 = v8;
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2((const GUID *const)(a1 + 32), sz, 40) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0xE,
      (unsigned int)"DusmStore::SetCost::StringFromGUID2",
      samDesired);
  phkResult = 0;
  if ( v7 == 1 || v7 == 2 )
  {
    std::wstring::wstring(v67, qword_180068EC0);
    std::wstring::append(v67, L"\\");
    std::wstring::append(v67, sz);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v67);
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    v12 = v67;
  }
  else
  {
    std::wstring::wstring(v66, qword_180068EC8);
    std::wstring::append(v66, L"\\");
    std::wstring::append(v66, a1 + 144);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v66);
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    if ( v10 )
    {
      v34 = wil::details::static_lazy<DusmTraceLoggingProvider>::get();
      if ( **(_DWORD **)(v34 + 8) > 5u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          *(_QWORD *)(v34 + 8),
          word_18005842A);
      std::wstring::_Tidy_deallocate(v66);
LABEL_55:
      v35 = DusmTraceLoggingProvider::Provider();
      v36 = (int)v35;
      if ( *(_DWORD *)v35 > 5u && (unsigned __int8)tlgKeywordOn(v35, 0) )
      {
        wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v62, sz);
        Imsi = DusmConnection::GetImsi(a1);
        v38 = std::wstring::c_str(Imsi);
        wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v59, v38);
        Iccid = DusmConnection::GetIccid(a1);
        v40 = std::wstring::c_str(Iccid);
        v41 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v58, v40);
        v44 = DusmSourceToSz(a2, v42, v43, v41);
        wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v57, v44);
        v45 = DusmMediaTypeToSz(v7);
        v46 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v56, v45);
        LODWORD(v54) = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
          v36,
          (int)&word_1800583C2,
          (__int64)&v54,
          v46,
          v47,
          v48,
          v49,
          v50);
      }
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x2CE,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v10,
        (unsigned int)"DusmStore::SetCost::RegCreateKeyExW",
        samDesireda);
    }
    std::wstring::append(v66, L"\\");
    std::wstring::append(v66, a1 + 112);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v66);
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
    v12 = v66;
  }
  std::wstring::_Tidy_deallocate(v12);
  if ( v10 )
    goto LABEL_55;
  v14 = phkResult;
  v15 = L"OperatorCost";
  if ( a2 != 3 )
    v15 = L"UserCost";
  if ( a4 )
  {
    v16 = L"*";
    if ( v7 == 1 || v7 == 2 )
    {
      if ( v7 == 1 )
        v18 = L"*";
      else
        v18 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      v17 = RegDeleteKeyValueW(v14, v18, v15);
    }
    else
    {
      v17 = RegDeleteValueW(phkResult, v15);
    }
    v19 = v17;
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
    {
      if ( v7 == 3 )
      {
        v16 = L"n/a";
      }
      else if ( v7 != 1 )
      {
        v16 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      }
      v55 = (__int64)v16;
      v60 = (__int64)sz;
      v61 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 112);
      v56 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 144);
      v57 = (__int64)v15;
      v58 = DusmSourceToSz(a2, v20, v21, v22);
      v59 = DusmMediaTypeToSz(v7);
      LODWORD(v54) = v19;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v23,
        (int)&byte_180058317,
        (__int64)&v54,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v61,
        (__int64)&v60,
        (__int64)&v55);
    }
    if ( (v19 & 0xFFFFFFFD) != 0 )
    {
      v51 = (const char *)L"Value";
      if ( v7 != 3 )
        v51 = L"KeyValueW";
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x2F4,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v19,
        (unsigned int)"DusmStore::SetCost::RegDelete%ws",
        v51);
    }
  }
  else
  {
    *(_DWORD *)Data = *(_DWORD *)v55;
    v24 = L"*";
    if ( v7 == 1 || v7 == 2 )
    {
      if ( v7 == 1 )
        v26 = L"*";
      else
        v26 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      v25 = RegSetKeyValueW(v14, v26, v15, 4u, Data, 4u);
    }
    else
    {
      v25 = RegSetValueExW(phkResult, v15, 0, 4u, Data, 4u);
    }
    v27 = v25;
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
    {
      if ( v7 == 3 )
      {
        v24 = L"n/a";
      }
      else if ( v7 != 1 )
      {
        v24 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
      }
      v59 = (__int64)v24;
      v58 = (__int64)sz;
      v57 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 112);
      v56 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 144);
      LODWORD(v54) = *(_DWORD *)Data;
      v61 = (__int64)v15;
      v60 = DusmSourceToSz(a2, v28, v29, v30);
      v62 = DusmMediaTypeToSz(v7);
      LODWORD(v55) = v27;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v31,
        (int)&word_18005826A,
        (__int64)&v55,
        (__int64)&v62,
        (__int64)&v60,
        (__int64)&v61,
        (__int64)&v54,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v58,
        (__int64)&v59);
    }
    if ( v27 )
    {
      v33 = (const char *)L"ValueEx";
      if ( v7 != 3 )
        v33 = L"KeyValueW";
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x320,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v27,
        (unsigned int)"DusmStore::SetCost::RegSet%ws",
        v33);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v63);
}

```

## disassembly

```asm
0x18002b21c  mov     [rsp-8+arg_18], rbx
0x18002b221  push    rbp
0x18002b222  push    rsi
0x18002b223  push    rdi
0x18002b224  push    r12
0x18002b226  push    r13
0x18002b228  push    r14
0x18002b22a  push    r15
0x18002b22c  lea     rbp, [rsp-70h]
0x18002b231  sub     rsp, 170h
0x18002b238  mov     rax, cs:__security_cookie
0x18002b23f  xor     rax, rsp
0x18002b242  mov     [rbp+0A0h+var_40], rax
0x18002b246  mov     r12d, r9d
0x18002b249  mov     rsi, r8
0x18002b24c  mov     [rsp+1A0h+var_128], r8
0x18002b251  mov     r13d, edx
0x18002b254  mov     r14, rcx
0x18002b257  mov     edi, [rcx+10h]
0x18002b25a  xor     r15d, r15d
0x18002b25d  cmp     edi, 3
0x18002b260  jz      short loc_18002B285
0x18002b262  cmp     edi, 2
0x18002b265  jz      short loc_18002B27B
0x18002b267  cmp     edi, 1
0x18002b26a  jnz     loc_18002B93B
0x18002b270  cmp     edx, 2
0x18002b273  jnz     loc_18002B7A9
0x18002b279  jmp     short loc_18002B291
0x18002b27b  cmp     [rcx+40h], r15
0x18002b27f  jz      loc_18002B966
0x18002b285  lea     eax, [rdx-2]
0x18002b288  cmp     eax, 1
0x18002b28b  ja      loc_18002B991
0x18002b291  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002b298  mov     rcx, rbx; lpCriticalSection
0x18002b29b  call    cs:__imp_EnterCriticalSection
0x18002b2a1  mov     [rbp+0A0h+var_E8], rbx
0x18002b2a5  xor     edx, edx; Val
0x18002b2a7  lea     r8d, [rdx+50h]; Size
0x18002b2ab  lea     rcx, [rbp+0A0h+sz]; void *
0x18002b2af  call    memset_0
0x18002b2b4  lea     rcx, [r14+20h]; rguid
0x18002b2b8  mov     r8d, 28h ; '('; cchMax
0x18002b2be  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18002b2c2  call    cs:__imp_StringFromGUID2
0x18002b2c8  test    eax, eax
0x18002b2ca  jz      loc_18002B9BC
0x18002b2d0  mov     ebx, r15d
0x18002b2d3  mov     r10, r15
0x18002b2d6  mov     [rbp+0A0h+var_E0], r15
0x18002b2da  mov     ecx, edi
0x18002b2dc  sub     ecx, 1
0x18002b2df  jz      loc_18002B3EA
0x18002b2e5  sub     ecx, 1
0x18002b2e8  jz      loc_18002B3EA
0x18002b2ee  cmp     ecx, 1
0x18002b2f1  jnz     loc_18002B47E
0x18002b2f7  mov     rdx, cs:qword_180068EC8
0x18002b2fe  lea     rcx, [rbp+0A0h+var_D0]
0x18002b302  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002b307  nop
0x18002b308  lea     rdx, asc_18004F678; "\\"
0x18002b30f  lea     rcx, [rbp+0A0h+var_D0]
0x18002b313  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18002b318  lea     rdx, [r14+90h]
0x18002b31f  lea     rcx, [rbp+0A0h+var_D0]
0x18002b323  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002b328  xor     edx, edx
0x18002b32a  lea     rcx, [rbp+0A0h+var_E0]
0x18002b32e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b333  lea     rcx, [rbp+0A0h+var_D0]
0x18002b337  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b33c  mov     rdx, rax; lpSubKey
0x18002b33f  mov     [rsp+1A0h+lpdwDisposition], r15; lpdwDisposition
0x18002b344  lea     rax, [rbp+0A0h+var_E0]
0x18002b348  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18002b34d  mov     [rsp+1A0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002b352  mov     [rsp+1A0h+samDesired], 20006h; samDesired
0x18002b35a  mov     [rsp+1A0h+dwOptions], r15d; dwOptions
0x18002b35f  xor     r9d, r9d; lpClass
0x18002b362  xor     r8d, r8d; Reserved
0x18002b365  mov     rsi, 0FFFFFFFF80000002h
0x18002b36c  mov     rcx, rsi; hKey
0x18002b36f  call    cs:__imp_RegCreateKeyExW
0x18002b375  mov     ebx, eax
0x18002b377  test    eax, eax
0x18002b379  jnz     loc_18002B7D4
0x18002b37f  lea     rdx, asc_18004F678; "\\"
0x18002b386  lea     rcx, [rbp+0A0h+var_D0]
0x18002b38a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18002b38f  lea     rdx, [r14+70h]
0x18002b393  lea     rcx, [rbp+0A0h+var_D0]
0x18002b397  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002b39c  xor     edx, edx
0x18002b39e  lea     rcx, [rbp+0A0h+var_E0]
0x18002b3a2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b3a7  lea     rcx, [rbp+0A0h+var_D0]
0x18002b3ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b3b0  mov     rdx, rax; lpSubKey
0x18002b3b3  mov     [rsp+1A0h+lpdwDisposition], r15; lpdwDisposition
0x18002b3b8  lea     rax, [rbp+0A0h+var_E0]
0x18002b3bc  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18002b3c1  mov     [rsp+1A0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002b3c6  mov     [rsp+1A0h+samDesired], 20006h; samDesired
0x18002b3ce  mov     [rsp+1A0h+dwOptions], r15d; dwOptions
0x18002b3d3  xor     r9d, r9d; lpClass
0x18002b3d6  xor     r8d, r8d; Reserved
0x18002b3d9  mov     rcx, rsi; hKey
0x18002b3dc  call    cs:__imp_RegCreateKeyExW
0x18002b3e2  mov     ebx, eax
0x18002b3e4  lea     rcx, [rbp+0A0h+var_D0]
0x18002b3e8  jmp     short loc_18002B468
0x18002b3ea  mov     rdx, cs:qword_180068EC0
0x18002b3f1  lea     rcx, [rbp+0A0h+var_B0]
0x18002b3f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002b3fa  nop
0x18002b3fb  lea     rdx, asc_18004F678; "\\"
0x18002b402  lea     rcx, [rbp+0A0h+var_B0]
0x18002b406  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18002b40b  lea     rdx, [rbp+0A0h+sz]
0x18002b40f  lea     rcx, [rbp+0A0h+var_B0]
0x18002b413  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18002b418  xor     edx, edx
0x18002b41a  lea     rcx, [rbp+0A0h+var_E0]
0x18002b41e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002b423  lea     rcx, [rbp+0A0h+var_B0]
0x18002b427  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b42c  mov     rdx, rax; lpSubKey
0x18002b42f  mov     [rsp+1A0h+lpdwDisposition], r15; lpdwDisposition
0x18002b434  lea     rax, [rbp+0A0h+var_E0]
0x18002b438  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18002b43d  mov     [rsp+1A0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002b442  mov     [rsp+1A0h+samDesired], 20006h; samDesired
0x18002b44a  mov     [rsp+1A0h+dwOptions], r15d; dwOptions
0x18002b44f  xor     r9d, r9d; lpClass
0x18002b452  xor     r8d, r8d; Reserved
0x18002b455  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b45c  call    cs:__imp_RegCreateKeyExW
0x18002b462  mov     ebx, eax
0x18002b464  lea     rcx, [rbp+0A0h+var_B0]
0x18002b468  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b46d  test    ebx, ebx
0x18002b46f  jnz     loc_18002B7FE
0x18002b475  mov     r10, [rbp+0A0h+var_E0]
0x18002b479  mov     rsi, [rsp+1A0h+var_128]
0x18002b47e  lea     rax, aUsercost; "UserCost"
0x18002b485  lea     r15, aOperatorcost; "OperatorCost"
0x18002b48c  cmp     r13d, 3
0x18002b490  cmovnz  r15, rax
0x18002b494  mov     ecx, edi
0x18002b496  test    r12d, r12d
0x18002b499  jz      loc_18002B5CE
0x18002b49f  lea     rsi, SubKey; "*"
0x18002b4a6  sub     ecx, 1
0x18002b4a9  jz      short loc_18002B4C3
0x18002b4ab  sub     ecx, 1
0x18002b4ae  jz      short loc_18002B4C3
0x18002b4b0  cmp     ecx, 1
0x18002b4b3  jnz     short loc_18002B4E7
0x18002b4b5  mov     rdx, r15; lpValueName
0x18002b4b8  mov     rcx, r10; hKey
0x18002b4bb  call    cs:__imp_RegDeleteValueW
0x18002b4c1  jmp     short loc_18002B4E5
0x18002b4c3  cmp     edi, 1
0x18002b4c6  jnz     short loc_18002B4CD
0x18002b4c8  mov     rax, rsi
0x18002b4cb  jmp     short loc_18002B4D6
0x18002b4cd  lea     rcx, [r14+30h]
0x18002b4d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b4d6  mov     r8, r15; lpValueName
0x18002b4d9  mov     rdx, rax; lpSubKey
0x18002b4dc  mov     rcx, r10; hKey
0x18002b4df  call    cs:__imp_RegDeleteKeyValueW
0x18002b4e5  mov     ebx, eax
0x18002b4e7  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002b4ec  mov     r8, [rax+8]
0x18002b4f0  mov     eax, [r8]
0x18002b4f3  cmp     eax, 5
0x18002b4f6  jbe     loc_18002B5BD
0x18002b4fc  cmp     edi, 3
0x18002b4ff  jnz     short loc_18002B50A
0x18002b501  lea     rsi, aNA; "n/a"
0x18002b508  jmp     short loc_18002B51B
0x18002b50a  cmp     edi, 1
0x18002b50d  jz      short loc_18002B51B
0x18002b50f  lea     rcx, [r14+30h]
0x18002b513  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b518  mov     rsi, rax
0x18002b51b  mov     [rsp+1A0h+var_128], rsi
0x18002b520  lea     rax, [rbp+0A0h+sz]
0x18002b524  mov     [rbp+0A0h+var_100], rax
0x18002b528  lea     rcx, [r14+70h]
0x18002b52c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b531  mov     [rbp+0A0h+var_F8], rax
0x18002b535  lea     rcx, [r14+90h]
0x18002b53c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b541  mov     [rbp+0A0h+var_120], rax
0x18002b545  mov     [rbp+0A0h+var_118], r15
0x18002b549  mov     ecx, r13d
0x18002b54c  call    ?DusmSourceToSz@@YAPEB_WW4_DUSM_SOURCE@@@Z; DusmSourceToSz(_DUSM_SOURCE)
0x18002b551  mov     [rbp+0A0h+var_110], rax
0x18002b555  mov     ecx, edi
0x18002b557  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18002b55c  mov     [rbp+0A0h+var_108], rax
0x18002b560  mov     dword ptr [rsp+1A0h+var_130], ebx
0x18002b564  lea     rax, [rsp+1A0h+var_128]
0x18002b569  mov     [rsp+1A0h+var_148], rax; __int64
0x18002b56e  lea     rax, [rbp+0A0h+var_100]
0x18002b572  mov     [rsp+1A0h+var_150], rax; __int64
0x18002b577  lea     rax, [rbp+0A0h+var_F8]
0x18002b57b  mov     [rsp+1A0h+var_158], rax; __int64
0x18002b580  lea     rax, [rbp+0A0h+var_120]
0x18002b584  mov     [rsp+1A0h+lpdwDisposition], rax; __int64
0x18002b589  lea     rax, [rbp+0A0h+var_118]
0x18002b58d  mov     [rsp+1A0h+phkResult], rax; __int64
0x18002b592  lea     rax, [rbp+0A0h+var_110]
0x18002b596  mov     [rsp+1A0h+lpSecurityAttributes], rax; __int64
0x18002b59b  lea     rax, [rbp+0A0h+var_108]
0x18002b59f  mov     qword ptr [rsp+1A0h+samDesired], rax; __int64
0x18002b5a4  lea     rax, [rsp+1A0h+var_130]
0x18002b5a9  mov     qword ptr [rsp+1A0h+dwOptions], rax; __int64
0x18002b5ae  lea     rdx, byte_180058317; int
0x18002b5b5  mov     rcx, r8; int
0x18002b5b8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18002b5bd  test    ebx, 0FFFFFFFDh
0x18002b5c3  jnz     loc_18002B8F9
0x18002b5c9  jmp     loc_18002B72D
0x18002b5ce  mov     eax, [rsi]
0x18002b5d0  mov     dword ptr [rbp+0A0h+Data], eax
0x18002b5d3  lea     rsi, SubKey; "*"
0x18002b5da  sub     ecx, 1
0x18002b5dd  jz      short loc_18002B60C
0x18002b5df  sub     ecx, 1
0x18002b5e2  jz      short loc_18002B60C
0x18002b5e4  cmp     ecx, 1
0x18002b5e7  jnz     short loc_18002B644
0x18002b5e9  lea     r9d, [rcx+3]; dwType
0x18002b5ed  mov     [rsp+1A0h+samDesired], r9d; cbData
0x18002b5f2  lea     rax, [rbp+0A0h+Data]
0x18002b5f6  mov     qword ptr [rsp+1A0h+dwOptions], rax; lpData
0x18002b5fb  xor     r8d, r8d; Reserved
0x18002b5fe  mov     rdx, r15; lpValueName
0x18002b601  mov     rcx, r10; hKey
0x18002b604  call    cs:__imp_RegSetValueExW
0x18002b60a  jmp     short loc_18002B642
0x18002b60c  cmp     edi, 1
0x18002b60f  jnz     short loc_18002B616
0x18002b611  mov     rax, rsi
0x18002b614  jmp     short loc_18002B61F
0x18002b616  lea     rcx, [r14+30h]
0x18002b61a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b61f  mov     r9d, 4; dwType
0x18002b625  mov     [rsp+1A0h+samDesired], r9d; cbData
0x18002b62a  lea     rcx, [rbp+0A0h+Data]
0x18002b62e  mov     qword ptr [rsp+1A0h+dwOptions], rcx; lpData
0x18002b633  mov     r8, r15; lpValueName
0x18002b636  mov     rdx, rax; lpSubKey
0x18002b639  mov     rcx, r10; hKey
0x18002b63c  call    cs:__imp_RegSetKeyValueW
0x18002b642  mov     ebx, eax
0x18002b644  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002b649  mov     r8, [rax+8]
0x18002b64d  mov     eax, [r8]
0x18002b650  cmp     eax, 5
0x18002b653  jbe     loc_18002B729
0x18002b659  cmp     edi, 3
0x18002b65c  jnz     short loc_18002B667
0x18002b65e  lea     rsi, aNA; "n/a"
0x18002b665  jmp     short loc_18002B678
0x18002b667  cmp     edi, 1
0x18002b66a  jz      short loc_18002B678
0x18002b66c  lea     rcx, [r14+30h]
0x18002b670  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b675  mov     rsi, rax
0x18002b678  mov     [rbp+0A0h+var_108], rsi
0x18002b67c  lea     rax, [rbp+0A0h+sz]
0x18002b680  mov     [rbp+0A0h+var_110], rax
0x18002b684  lea     rcx, [r14+70h]
0x18002b688  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b68d  mov     [rbp+0A0h+var_118], rax
0x18002b691  lea     rcx, [r14+90h]
0x18002b698  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002b69d  mov     [rbp+0A0h+var_120], rax
0x18002b6a1  mov     eax, dword ptr [rbp+0A0h+Data]
0x18002b6a4  mov     dword ptr [rsp+1A0h+var_130], eax
0x18002b6a8  mov     [rbp+0A0h+var_F8], r15
0x18002b6ac  mov     ecx, r13d
0x18002b6af  call    ?DusmSourceToSz@@YAPEB_WW4_DUSM_SOURCE@@@Z; DusmSourceToSz(_DUSM_SOURCE)
0x18002b6b4  mov     [rbp+0A0h+var_100], rax
0x18002b6b8  mov     ecx, edi
0x18002b6ba  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18002b6bf  mov     [rbp+0A0h+var_F0], rax
0x18002b6c3  mov     dword ptr [rsp+1A0h+var_128], ebx
0x18002b6c7  lea     rax, [rbp+0A0h+var_108]
0x18002b6cb  mov     [rsp+1A0h+var_140], rax; __int64
0x18002b6d0  lea     rax, [rbp+0A0h+var_110]
0x18002b6d4  mov     [rsp+1A0h+var_148], rax; __int64
0x18002b6d9  lea     rax, [rbp+0A0h+var_118]
0x18002b6dd  mov     [rsp+1A0h+var_150], rax; __int64
  ... truncated ...
```
