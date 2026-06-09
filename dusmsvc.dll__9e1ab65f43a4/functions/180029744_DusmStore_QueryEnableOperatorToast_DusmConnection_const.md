# DusmStore::QueryEnableOperatorToast(DusmConnection const &)

- ea: `0x180029744`
- end: `0x180029996`
- name: `?QueryEnableOperatorToast@DusmStore@@SAHAEBVDusmConnection@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(const struct DusmConnection *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18002051c`

## callees

- `0x180005998`
- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x180013444`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x180029744`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002977a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002977a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029810`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029810`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800298a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800298a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall DusmStore::QueryEnableOperatorToast(const struct DusmConnection *a1)
{
  LPCRITICAL_SECTION v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  LSTATUS ValueW; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  BOOL v15; // ebx
  const char *pvData; // [rsp+28h] [rbp-61h]
  __int64 *pvDataa; // [rsp+28h] [rbp-61h]
  __int64 *pcbData; // [rsp+30h] [rbp-59h]
  __int64 v19; // [rsp+40h] [rbp-49h] BYREF
  __int64 v20; // [rsp+48h] [rbp-41h] BYREF
  __int64 v21; // [rsp+50h] [rbp-39h] BYREF
  LPCRITICAL_SECTION v22; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v23[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v24[32]; // [rsp+80h] [rbp-9h] BYREF
  HKEY hkey; // [rsp+A0h] [rbp+17h] BYREF
  int v26; // [rsp+A8h] [rbp+1Fh] BYREF
  DWORD v27; // [rsp+ACh] [rbp+23h] BYREF
  _BYTE v28[32]; // [rsp+B0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v22 = v2;
  if ( *((_DWORD *)a1 + 4) != 3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x7B3,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
      (const char *)0x57,
      (unsigned int)"DusmStore::QueryEnableOperatorToast::mediaType",
      pvData);
  v3 = std::wstring::wstring((__int64)v24, (__int64)qword_180068EC8);
  v4 = std::operator+<wchar_t>((__int64)v23, v3, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v28, v4, (__int64)a1 + 144);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v24);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hkey);
  if ( ValueW )
  {
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v7, v6) + 8) > 5u )
    {
      v20 = (__int64)hkey;
      v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28);
      pcbData = &v20;
      pvDataa = &v21;
      v11 = byte_180057E31;
LABEL_8:
      LODWORD(v19) = ValueW;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
        v9,
        (int)v11,
        v9,
        v10,
        (__int64)&v19,
        (const WCHAR **)pvDataa,
        (__int64)pcbData);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  v26 = 1;
  v27 = 4;
  ValueW = RegGetValueW(hkey, 0, L"EnableOperatorToast", 0x18u, 0, &v26, &v27);
  if ( ValueW )
  {
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8) > 5u )
    {
      v21 = (__int64)hkey;
      v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28);
      pcbData = &v21;
      pvDataa = &v20;
      v11 = byte_180057DD5;
      goto LABEL_8;
    }
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    std::wstring::_Tidy_deallocate(v28);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
    return 1;
  }
  v15 = v26 != 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  std::wstring::_Tidy_deallocate(v28);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
  return v15;
}

```

## disassembly

```asm
0x180029744  mov     [rsp-8+arg_8], rbx
0x180029749  mov     [rsp-8+arg_10], rdi
0x18002974e  push    rbp
0x18002974f  lea     rbp, [rsp-57h]
0x180029754  sub     rsp, 0E0h
0x18002975b  mov     rax, cs:__security_cookie
0x180029762  xor     rax, rsp
0x180029765  mov     [rbp+57h+var_10], rax
0x180029769  mov     rdi, rcx
0x18002976c  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x180029773  add     rbx, 28h ; '('
0x180029777  mov     rcx, rbx; lpCriticalSection
0x18002977a  call    cs:__imp_EnterCriticalSection
0x180029780  mov     [rbp+57h+var_88], rbx
0x180029784  cmp     dword ptr [rdi+10h], 3
0x180029788  jnz     loc_18002996E
0x18002978e  mov     rdx, cs:qword_180068EC8
0x180029795  lea     rcx, [rbp+57h+var_60]
0x180029799  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002979e  nop
0x18002979f  lea     r8, asc_18004F678; "\\"
0x1800297a6  mov     rdx, rax
0x1800297a9  lea     rcx, [rbp+57h+var_80]
0x1800297ad  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1800297b2  nop
0x1800297b3  lea     r8, [rdi+90h]
0x1800297ba  mov     rdx, rax
0x1800297bd  lea     rcx, [rbp+57h+var_30]
0x1800297c1  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x1800297c6  nop
0x1800297c7  lea     rcx, [rbp+57h+var_80]
0x1800297cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800297d0  nop
0x1800297d1  lea     rcx, [rbp+57h+var_60]
0x1800297d5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800297da  xor     edi, edi
0x1800297dc  mov     [rbp+57h+hkey], rdi
0x1800297e0  xor     edx, edx
0x1800297e2  lea     rcx, [rbp+57h+hkey]
0x1800297e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800297eb  lea     rcx, [rbp+57h+var_30]
0x1800297ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800297f4  mov     rdx, rax; lpSubKey
0x1800297f7  lea     rax, [rbp+57h+hkey]
0x1800297fb  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180029800  mov     r9d, 20019h; samDesired
0x180029806  xor     r8d, r8d; ulOptions
0x180029809  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029810  call    cs:__imp_RegOpenKeyExW
0x180029816  mov     ebx, eax
0x180029818  test    eax, eax
0x18002981a  jz      short loc_18002986D
0x18002981c  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180029821  mov     r8, [rax+8]
0x180029825  mov     ecx, [r8]
0x180029828  cmp     ecx, 5
0x18002982b  jbe     loc_180029904
0x180029831  mov     rdx, [rbp+57h+hkey]
0x180029835  mov     [rbp+57h+var_98], rdx
0x180029839  lea     rcx, [rbp+57h+var_30]
0x18002983d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029842  mov     [rbp+57h+var_90], rax
0x180029846  lea     rax, [rbp+57h+var_98]
0x18002984a  mov     [rsp+0E0h+pcbData], rax
0x18002984f  lea     rax, [rbp+57h+var_90]
0x180029853  mov     [rsp+0E0h+pvData], rax
0x180029858  lea     rax, [rbp+57h+var_A0]
0x18002985c  mov     [rsp+0E0h+phkResult], rax
0x180029861  lea     rdx, byte_180057E31
0x180029868  jmp     loc_1800298F9
0x18002986d  mov     [rbp+57h+var_38], 1
0x180029874  mov     [rbp+57h+var_34], 4
0x18002987b  lea     rax, [rbp+57h+var_34]
0x18002987f  mov     [rsp+0E0h+pcbData], rax; pcbData
0x180029884  lea     rax, [rbp+57h+var_38]
0x180029888  mov     [rsp+0E0h+pvData], rax; pvData
0x18002988d  mov     [rsp+0E0h+phkResult], rdi; pdwType
0x180029892  mov     r9d, 18h; dwFlags
0x180029898  lea     r8, aEnableoperator; "EnableOperatorToast"
0x18002989f  xor     edx, edx; lpSubKey
0x1800298a1  mov     rcx, [rbp+57h+hkey]; hkey
0x1800298a5  call    cs:__imp_RegGetValueW
0x1800298ab  mov     ebx, eax
0x1800298ad  test    eax, eax
0x1800298af  jz      short loc_180029927
0x1800298b1  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x1800298b6  mov     r8, [rax+8]
0x1800298ba  mov     ecx, [r8]
0x1800298bd  cmp     ecx, 5
0x1800298c0  jbe     short loc_180029904
0x1800298c2  mov     rdx, [rbp+57h+hkey]
0x1800298c6  mov     [rbp+57h+var_90], rdx
0x1800298ca  lea     rcx, [rbp+57h+var_30]
0x1800298ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800298d3  mov     [rbp+57h+var_98], rax
0x1800298d7  lea     rax, [rbp+57h+var_90]
0x1800298db  mov     [rsp+0E0h+pcbData], rax; __int64
0x1800298e0  lea     rax, [rbp+57h+var_98]
0x1800298e4  mov     [rsp+0E0h+pvData], rax; __int64
0x1800298e9  lea     rcx, [rbp+57h+var_A0]
0x1800298ed  mov     [rsp+0E0h+phkResult], rcx; __int64
0x1800298f2  lea     rdx, byte_180057DD5
0x1800298f9  mov     dword ptr [rbp+57h+var_A0], ebx
0x1800298fc  mov     rcx, r8; int
0x1800298ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x180029904  lea     rcx, [rbp+57h+hkey]
0x180029908  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002990d  lea     rcx, [rbp+57h+var_30]
0x180029911  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029916  nop
0x180029917  lea     rcx, [rbp+57h+var_88]
0x18002991b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180029920  mov     eax, 1
0x180029925  jmp     short loc_18002994D
0x180029927  mov     ebx, edi
0x180029929  cmp     [rbp+57h+var_38], edi
0x18002992c  setnz   bl
0x18002992f  lea     rcx, [rbp+57h+hkey]
0x180029933  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029938  lea     rcx, [rbp+57h+var_30]
0x18002993c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029941  nop
0x180029942  lea     rcx, [rbp+57h+var_88]
0x180029946  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002994b  mov     eax, ebx
0x18002994d  mov     rcx, [rbp+57h+var_10]
0x180029951  xor     rcx, rsp; StackCookie
0x180029954  call    __security_check_cookie
0x180029959  lea     r11, [rsp+0E0h+var_s0]
0x180029961  mov     rbx, [r11+18h]
0x180029965  mov     rdi, [r11+20h]
0x180029969  mov     rsp, r11
0x18002996c  pop     rbp
0x18002996d  retn
0x18002996e  mov     rcx, [rbp+5Fh]; this
0x180029972  lea     rax, aDusmstoreQuery_15; "DusmStore::QueryEnableOperatorToast::me"...
0x180029979  mov     [rsp+0E0h+phkResult], rax; unsigned int
0x18002997e  mov     r9d, 57h ; 'W'; char *
0x180029984  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002998b  mov     edx, 7B3h; void *
0x180029990  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
