# DusmStore::QueryDataPlan(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS &)

- ea: `0x180028f48`
- end: `0x18002933e`
- name: `?QueryDataPlan@DusmStore@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@AEAU_DUSM_DATAPLAN_STATUS@@@Z`
- size: `1014`
- prototype: `static int __high(const struct DusmConnection *, enum _DUSM_SOURCE, struct _DUSM_DATAPLAN_STATUS *)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bbc8`
- `0x18001cc38`
- `0x18001fe44`

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
- `0x180028f48`
- `0x180029344`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002901f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002901f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180029047`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180029047`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800290d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800290d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800291a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800291a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DusmStore::QueryDataPlan(__int64 a1, unsigned int a2, void *a3)
{
  int v5; // esi
  unsigned int DataPlanFromStore; // ebx
  LPCRITICAL_SECTION v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rax
  __int64 v12; // rax
  char v13; // bl
  const WCHAR *v14; // rax
  const char *pvData; // [rsp+28h] [rbp-D8h]
  const char *pvDataa; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v17; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[32]; // [rsp+90h] [rbp-70h] BYREF
  HKEY hkey; // [rsp+B0h] [rbp-50h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v23[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v25[32]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz[40]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v5 = *(_DWORD *)(a1 + 16);
  if ( v5 == 3 )
  {
    if ( !*(_QWORD *)(a1 + 160) )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x5F3,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryDataPlan::iccid",
        pvData);
    if ( a2 - 2 > 1 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x5FD,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryDataPlan::source::notUserOrOperator",
        pvData);
  }
  else
  {
    if ( v5 == 2 )
    {
      if ( !*(_QWORD *)(a1 + 64) )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x5F8,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
          (const char *)0x57,
          (unsigned int)"DusmStore::QueryDataPlan::profileName",
          pvData);
    }
    else if ( v5 != 1 )
    {
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x5DC,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryDataPlan::mediaType",
        pvData);
    }
    if ( a2 != 2 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x602,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)0x57,
        (unsigned int)"DusmStore::QueryDataPlan::source::notUser",
        pvData);
  }
  if ( v5 == 3 )
  {
    v23[0] = 0;
    v23[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v23[0]) = 0;
    DataPlanFromStore = DusmStore::QueryDataPlanFromStore(DusmStore::s_pInstance, a1, a2, a3, v23);
    std::wstring::_Tidy_deallocate(v23);
    return DataPlanFromStore;
  }
  v8 = DusmStore::s_pInstance;
  EnterCriticalSection(DusmStore::s_pInstance);
  v17 = v8;
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2((const GUID *const)(a1 + 32), sz, 40) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x611,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0xE,
      (unsigned int)"DusmStore::QueryDataPlan::StringFromGUID2",
      pvData);
  hkey = 0;
  v9 = std::wstring::wstring((__int64)v18, (__int64)qword_180068EC0);
  v10 = std::operator+<wchar_t>((__int64)v23, v9, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v24, v10, (__int64)sz);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &hkey) )
    goto LABEL_14;
  if ( v5 == 1 )
  {
    v12 = std::wstring::wstring((__int64)v20, (__int64)L"*");
    v13 = 1;
  }
  else
  {
    v12 = std::wstring::wstring((__int64)v19, a1 + 48);
    v13 = 2;
  }
  std::wstring::wstring((__int64)v25, v12);
  if ( (v13 & 2) != 0 )
  {
    v13 &= ~2u;
    std::wstring::_Tidy_deallocate(v19);
  }
  if ( (v13 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v20);
  pcbData = 68;
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
  if ( RegGetValueW(hkey, v14, L"UserDataPlan", 8u, 0, a3, &pcbData) )
  {
    std::wstring::_Tidy_deallocate(v25);
LABEL_14:
    std::wstring::_Tidy_deallocate(v24);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
    return 0;
  }
  if ( pcbData != 68 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x62B,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0xD,
      (unsigned int)"DusmStore::QueryDataPlan::RegGetValueW::cbData",
      pvDataa);
  std::wstring::_Tidy_deallocate(v25);
  std::wstring::_Tidy_deallocate(v24);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  return 1;
}

```

## disassembly

```asm
0x180028f48  mov     [rsp-8+arg_8], rbx
0x180028f4d  mov     [rsp-8+arg_18], rsi
0x180028f52  push    rbp
0x180028f53  push    rdi
0x180028f54  push    r14
0x180028f56  lea     rbp, [rsp-80h]
0x180028f5b  sub     rsp, 180h
0x180028f62  mov     rax, cs:__security_cookie
0x180028f69  xor     rax, rsp
0x180028f6c  mov     [rbp+90h+var_20], rax
0x180028f70  mov     r14, r8
0x180028f73  mov     rdi, rcx
0x180028f76  mov     [rsp+190h+var_150], 0
0x180028f7e  mov     esi, [rcx+10h]
0x180028f81  cmp     esi, 3
0x180028f84  jz      short loc_180028FAC
0x180028f86  cmp     esi, 2
0x180028f89  jz      short loc_180028F96
0x180028f8b  cmp     esi, 1
0x180028f8e  jnz     loc_18002923C
0x180028f94  jmp     short loc_180028FA1
0x180028f96  cmp     qword ptr [rcx+40h], 0
0x180028f9b  jz      loc_180029292
0x180028fa1  cmp     edx, 2
0x180028fa4  jnz     loc_180029267
0x180028faa  jmp     short loc_180028FC6
0x180028fac  cmp     qword ptr [rcx+0A0h], 0
0x180028fb4  jz      loc_1800292BD
0x180028fba  lea     eax, [rdx-2]
0x180028fbd  cmp     eax, 1
0x180028fc0  ja      loc_1800292E8
0x180028fc6  cmp     esi, 3
0x180028fc9  jnz     short loc_180029015
0x180028fcb  xorps   xmm0, xmm0
0x180028fce  movups  [rbp+90h+var_D0], xmm0
0x180028fd2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180028fda  movdqu  [rbp+90h+var_C0], xmm1
0x180028fdf  xor     eax, eax
0x180028fe1  mov     word ptr [rbp+90h+var_D0], ax
0x180028fe5  lea     rax, [rbp+90h+var_D0]
0x180028fe9  mov     [rsp+190h+phkResult], rax
0x180028fee  mov     r9, r14
0x180028ff1  mov     r8d, edx
0x180028ff4  mov     rdx, rdi
0x180028ff7  mov     rcx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x180028ffe  call    ?QueryDataPlanFromStore@DusmStore@@AEAAHAEBVDusmConnection@@W4_DUSM_SOURCE@@AEAU_DUSM_DATAPLAN_STATUS@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; DusmStore::QueryDataPlanFromStore(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS &,std::wstring &)
0x180029003  mov     ebx, eax
0x180029005  lea     rcx, [rbp+90h+var_D0]
0x180029009  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002900e  mov     eax, ebx
0x180029010  jmp     loc_1800291ED
0x180029015  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002901c  mov     rcx, rbx; lpCriticalSection
0x18002901f  call    cs:__imp_EnterCriticalSection
0x180029025  mov     [rsp+190h+var_148], rbx
0x18002902a  xor     edx, edx; Val
0x18002902c  lea     r8d, [rdx+50h]; Size
0x180029030  lea     rcx, [rbp+90h+sz]; void *
0x180029034  call    memset_0
0x180029039  lea     rcx, [rdi+20h]; rguid
0x18002903d  mov     r8d, 28h ; '('; cchMax
0x180029043  lea     rdx, [rbp+90h+sz]; lpsz
0x180029047  call    cs:__imp_StringFromGUID2
0x18002904d  test    eax, eax
0x18002904f  jz      loc_180029313
0x180029055  mov     [rbp+90h+hkey], 0
0x18002905d  mov     rdx, cs:qword_180068EC0
0x180029064  lea     rcx, [rsp+190h+var_140]
0x180029069  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002906e  nop
0x18002906f  lea     r8, asc_18004F678; "\\"
0x180029076  mov     rdx, rax
0x180029079  lea     rcx, [rbp+90h+var_D0]
0x18002907d  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180029082  nop
0x180029083  lea     r8, [rbp+90h+sz]
0x180029087  mov     rdx, rax
0x18002908a  lea     rcx, [rbp+90h+var_B0]
0x18002908e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180029093  nop
0x180029094  lea     rcx, [rbp+90h+var_D0]
0x180029098  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002909d  nop
0x18002909e  lea     rcx, [rsp+190h+var_140]
0x1800290a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800290a8  xor     edx, edx
0x1800290aa  lea     rcx, [rbp+90h+hkey]
0x1800290ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800290b3  lea     rcx, [rbp+90h+var_B0]
0x1800290b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800290bc  mov     rdx, rax; lpSubKey
0x1800290bf  lea     rax, [rbp+90h+hkey]
0x1800290c3  mov     [rsp+190h+phkResult], rax; phkResult
0x1800290c8  mov     r9d, 20019h; samDesired
0x1800290ce  xor     r8d, r8d; ulOptions
0x1800290d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800290d8  call    cs:__imp_RegOpenKeyExW
0x1800290de  test    eax, eax
0x1800290e0  jz      short loc_180029107
0x1800290e2  lea     rcx, [rbp+90h+var_B0]
0x1800290e6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800290eb  nop
0x1800290ec  lea     rcx, [rbp+90h+hkey]
0x1800290f0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800290f5  nop
0x1800290f6  lea     rcx, [rsp+190h+var_148]
0x1800290fb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180029100  xor     eax, eax
0x180029102  jmp     loc_1800291ED
0x180029107  cmp     esi, 1
0x18002910a  jnz     short loc_180029121
0x18002910c  lea     rdx, SubKey; "*"
0x180029113  lea     rcx, [rbp+90h+var_100]
0x180029117  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002911c  nop
0x18002911d  mov     ebx, esi
0x18002911f  jmp     short loc_180029135
0x180029121  lea     rdx, [rdi+30h]
0x180029125  lea     rcx, [rsp+190h+var_120]
0x18002912a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002912f  nop
0x180029130  mov     ebx, 2
0x180029135  mov     [rsp+190h+var_150], ebx
0x180029139  mov     rdx, rax
0x18002913c  lea     rcx, [rbp+90h+var_90]
0x180029140  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180029145  nop
0x180029146  test    bl, 2
0x180029149  jz      short loc_180029159
0x18002914b  and     ebx, 0FFFFFFFDh
0x18002914e  lea     rcx, [rsp+190h+var_120]
0x180029153  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029158  nop
0x180029159  test    bl, 1
0x18002915c  jz      short loc_180029167
0x18002915e  lea     rcx, [rbp+90h+var_100]
0x180029162  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029167  mov     [rbp+90h+var_D8], 44h ; 'D'
0x18002916e  lea     rcx, [rbp+90h+var_90]
0x180029172  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029177  mov     rdx, rax; lpSubKey
0x18002917a  lea     rax, [rbp+90h+var_D8]
0x18002917e  mov     [rsp+190h+pcbData], rax; pcbData
0x180029183  mov     [rsp+190h+pvData], r14; char *
0x180029188  mov     [rsp+190h+phkResult], 0; pdwType
0x180029191  mov     r9d, 8; dwFlags
0x180029197  lea     r8, aUserdataplan; "UserDataPlan"
0x18002919e  mov     rcx, [rbp+90h+hkey]; hkey
0x1800291a2  call    cs:__imp_RegGetValueW
0x1800291a8  test    eax, eax
0x1800291aa  jz      short loc_1800291BA
0x1800291ac  lea     rcx, [rbp+90h+var_90]
0x1800291b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800291b5  jmp     loc_1800290E2
0x1800291ba  cmp     [rbp+90h+var_D8], 44h ; 'D'
0x1800291be  jnz     short loc_180029211
0x1800291c0  lea     rcx, [rbp+90h+var_90]
0x1800291c4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800291c9  nop
0x1800291ca  lea     rcx, [rbp+90h+var_B0]
0x1800291ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800291d3  nop
0x1800291d4  lea     rcx, [rbp+90h+hkey]
0x1800291d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800291dd  nop
0x1800291de  lea     rcx, [rsp+190h+var_148]
0x1800291e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800291e8  mov     eax, 1
0x1800291ed  mov     rcx, [rbp+90h+var_20]
0x1800291f1  xor     rcx, rsp; StackCookie
0x1800291f4  call    __security_check_cookie
0x1800291f9  lea     r11, [rsp+190h+var_10]
0x180029201  mov     rbx, [r11+28h]
0x180029205  mov     rsi, [r11+38h]
0x180029209  mov     rsp, r11
0x18002920c  pop     r14
0x18002920e  pop     rdi
0x18002920f  pop     rbp
0x180029210  retn
0x180029211  mov     rcx, [rbp+98h]; this
0x180029218  lea     rax, aDusmstoreQuery_3; "DusmStore::QueryDataPlan::RegGetValueW:"...
0x18002921f  mov     [rsp+190h+phkResult], rax; unsigned int
0x180029224  mov     r9d, 0Dh; char *
0x18002922a  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180029231  mov     edx, 62Bh; void *
0x180029236  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002923c  mov     rcx, [rbp+98h]; this
0x180029243  lea     rax, aDusmstoreQuery_19; "DusmStore::QueryDataPlan::mediaType"
0x18002924a  mov     [rsp+190h+phkResult], rax; unsigned int
0x18002924f  mov     r9d, 57h ; 'W'; char *
0x180029255  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002925c  mov     edx, 5DCh; void *
0x180029261  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180029267  mov     rcx, [rbp+98h]; this
0x18002926e  lea     rax, aDusmstoreQuery_1; "DusmStore::QueryDataPlan::source::notUs"...
0x180029275  mov     [rsp+190h+phkResult], rax; unsigned int
0x18002927a  mov     r9d, 57h ; 'W'; char *
0x180029280  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180029287  mov     edx, 602h; void *
0x18002928c  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180029292  mov     rcx, [rbp+98h]; this
0x180029299  lea     rax, aDusmstoreQuery_27; "DusmStore::QueryDataPlan::profileName"
0x1800292a0  mov     [rsp+190h+phkResult], rax; unsigned int
0x1800292a5  mov     r9d, 57h ; 'W'; char *
0x1800292ab  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x1800292b2  mov     edx, 5F8h; void *
0x1800292b7  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800292bd  mov     rcx, [rbp+98h]; this
0x1800292c4  lea     rax, aDusmstoreQuery_5; "DusmStore::QueryDataPlan::iccid"
0x1800292cb  mov     [rsp+190h+phkResult], rax; unsigned int
0x1800292d0  mov     r9d, 57h ; 'W'; char *
0x1800292d6  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x1800292dd  mov     edx, 5F3h; void *
0x1800292e2  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800292e8  mov     rcx, [rbp+98h]; this
0x1800292ef  lea     rax, aDusmstoreQuery; "DusmStore::QueryDataPlan::source::notUs"...
0x1800292f6  mov     [rsp+190h+phkResult], rax; unsigned int
0x1800292fb  mov     r9d, 57h ; 'W'; char *
0x180029301  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180029308  mov     edx, 5FDh; void *
0x18002930d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180029313  mov     rcx, [rbp+98h]; this
0x18002931a  lea     rax, aDusmstoreQuery_21; "DusmStore::QueryDataPlan::StringFromGUI"...
0x180029321  mov     [rsp+190h+phkResult], rax; unsigned int
0x180029326  mov     r9d, 0Eh; char *
0x18002932c  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x180029333  mov     edx, 611h; void *
0x180029338  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
