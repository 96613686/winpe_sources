# DusmStore::QueryEnableSetDataPlanToast(DusmConnection const &)

- ea: `0x18002999c`
- end: `0x180029b91`
- name: `?QueryEnableSetDataPlanToast@DusmStore@@SAHAEBVDusmConnection@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(const struct DusmConnection *)`
- caller_count: `1`
- callee_count: `12`
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
- `0x1800259f0`
- `0x180025a24`
- `0x180026fa0`
- `0x18002999c`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800299d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800299d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029a60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029a60`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029ae9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029ae9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall DusmStore::QueryEnableSetDataPlanToast(const struct DusmConnection *a1)
{
  LPCRITICAL_SECTION v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  LSTATUS ValueW; // edi
  BOOL v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rax
  __int16 *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 *pcbData; // [rsp+30h] [rbp-59h]
  __int64 v18; // [rsp+40h] [rbp-49h] BYREF
  HKEY v19; // [rsp+48h] [rbp-41h] BYREF
  __int64 v20; // [rsp+50h] [rbp-39h] BYREF
  LPCRITICAL_SECTION v21; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v23[32]; // [rsp+80h] [rbp-9h] BYREF
  HKEY hkey; // [rsp+A0h] [rbp+17h] BYREF
  int pvData; // [rsp+A8h] [rbp+1Fh] BYREF
  DWORD v26; // [rsp+ACh] [rbp+23h] BYREF
  _BYTE v27[32]; // [rsp+B0h] [rbp+27h] BYREF

  v2 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v21 = v2;
  v3 = std::wstring::wstring((__int64)v23, (__int64)qword_180068EC8);
  v4 = std::operator+<wchar_t>((__int64)v22, v3, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v27, v4, (__int64)a1 + 144);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v23);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hkey);
  v9 = 1;
  if ( ValueW )
  {
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v7, v6) + 8) > 5u )
    {
      v19 = hkey;
      v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
      pcbData = (__int64 *)&v19;
      v12 = &v20;
      v13 = (__int16 *)byte_180057D75;
LABEL_7:
      LODWORD(v18) = ValueW;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
        v10,
        (int)v13,
        v10,
        v11,
        (__int64)&v18,
        (const WCHAR **)v12,
        (__int64)pcbData);
    }
  }
  else
  {
    pvData = 1;
    v26 = 4;
    ValueW = RegGetValueW(hkey, 0, L"EnableSetDataPlanToast", 0x18u, 0, &pvData, &v26);
    if ( !ValueW )
    {
      v9 = pvData != 0;
      goto LABEL_9;
    }
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v15, v14) + 8) > 5u )
    {
      v20 = (__int64)hkey;
      v19 = (HKEY)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
      pcbData = &v20;
      v12 = (__int64 *)&v19;
      v13 = &word_180057D16;
      goto LABEL_7;
    }
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  std::wstring::_Tidy_deallocate(v27);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
  return v9;
}

```

## disassembly

```asm
0x18002999c  mov     [rsp-8+arg_8], rbx
0x1800299a1  mov     [rsp-8+arg_10], rdi
0x1800299a6  push    rbp
0x1800299a7  lea     rbp, [rsp-57h]
0x1800299ac  sub     rsp, 0E0h
0x1800299b3  mov     rax, cs:__security_cookie
0x1800299ba  xor     rax, rsp
0x1800299bd  mov     [rbp+57h+var_10], rax
0x1800299c1  mov     rdi, rcx
0x1800299c4  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x1800299cb  add     rbx, 28h ; '('
0x1800299cf  mov     rcx, rbx; lpCriticalSection
0x1800299d2  call    cs:__imp_EnterCriticalSection
0x1800299d8  mov     [rbp+57h+var_88], rbx
0x1800299dc  mov     rdx, cs:qword_180068EC8
0x1800299e3  lea     rcx, [rbp+57h+var_60]
0x1800299e7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800299ec  nop
0x1800299ed  lea     r8, asc_18004F678; "\\"
0x1800299f4  mov     rdx, rax
0x1800299f7  lea     rcx, [rbp+57h+var_80]
0x1800299fb  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180029a00  nop
0x180029a01  lea     r8, [rdi+90h]
0x180029a08  mov     rdx, rax
0x180029a0b  lea     rcx, [rbp+57h+var_30]
0x180029a0f  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x180029a14  nop
0x180029a15  lea     rcx, [rbp+57h+var_80]
0x180029a19  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a1e  nop
0x180029a1f  lea     rcx, [rbp+57h+var_60]
0x180029a23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a28  mov     [rbp+57h+hkey], 0
0x180029a30  xor     edx, edx
0x180029a32  lea     rcx, [rbp+57h+hkey]
0x180029a36  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029a3b  lea     rcx, [rbp+57h+var_30]
0x180029a3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029a44  mov     rdx, rax; lpSubKey
0x180029a47  lea     rax, [rbp+57h+hkey]
0x180029a4b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180029a50  mov     r9d, 20019h; samDesired
0x180029a56  xor     r8d, r8d; ulOptions
0x180029a59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029a60  call    cs:__imp_RegOpenKeyExW
0x180029a66  mov     edi, eax
0x180029a68  mov     ebx, 1
0x180029a6d  test    eax, eax
0x180029a6f  jz      short loc_180029AB1
0x180029a71  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180029a76  mov     r8, [rax+8]
0x180029a7a  mov     ecx, [r8]
0x180029a7d  cmp     ecx, 5
0x180029a80  jbe     loc_180029B52
0x180029a86  mov     rdx, [rbp+57h+hkey]
0x180029a8a  mov     [rbp+57h+var_98], rdx
0x180029a8e  lea     rcx, [rbp+57h+var_30]
0x180029a92  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029a97  mov     [rbp+57h+var_90], rax
0x180029a9b  lea     rax, [rbp+57h+var_98]
0x180029a9f  mov     [rsp+0E0h+pcbData], rax
0x180029aa4  lea     rax, [rbp+57h+var_90]
0x180029aa8  lea     rdx, byte_180057D75
0x180029aaf  jmp     short loc_180029B2F
0x180029ab1  mov     [rbp+57h+var_38], ebx
0x180029ab4  mov     [rbp+57h+var_34], 4
0x180029abb  lea     rax, [rbp+57h+var_34]
0x180029abf  mov     [rsp+0E0h+pcbData], rax; pcbData
0x180029ac4  lea     rax, [rbp+57h+var_38]
0x180029ac8  mov     [rsp+0E0h+pvData], rax; pvData
0x180029acd  mov     [rsp+0E0h+phkResult], 0; pdwType
0x180029ad6  mov     r9d, 18h; dwFlags
0x180029adc  lea     r8, aEnablesetdatap; "EnableSetDataPlanToast"
0x180029ae3  xor     edx, edx; lpSubKey
0x180029ae5  mov     rcx, [rbp+57h+hkey]; hkey
0x180029ae9  call    cs:__imp_RegGetValueW
0x180029aef  mov     edi, eax
0x180029af1  test    eax, eax
0x180029af3  jz      short loc_180029B4A
0x180029af5  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180029afa  mov     r8, [rax+8]
0x180029afe  mov     ecx, [r8]
0x180029b01  cmp     ecx, 5
0x180029b04  jbe     short loc_180029B52
0x180029b06  mov     rdx, [rbp+57h+hkey]
0x180029b0a  mov     [rbp+57h+var_90], rdx
0x180029b0e  lea     rcx, [rbp+57h+var_30]
0x180029b12  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029b17  mov     [rbp+57h+var_98], rax
0x180029b1b  lea     rax, [rbp+57h+var_90]
0x180029b1f  mov     [rsp+0E0h+pcbData], rax; __int64
0x180029b24  lea     rax, [rbp+57h+var_98]
0x180029b28  lea     rdx, word_180057D16
0x180029b2f  mov     [rsp+0E0h+pvData], rax; __int64
0x180029b34  lea     rax, [rbp+57h+var_A0]
0x180029b38  mov     [rsp+0E0h+phkResult], rax; __int64
0x180029b3d  mov     dword ptr [rbp+57h+var_A0], edi
0x180029b40  mov     rcx, r8; int
0x180029b43  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x180029b48  jmp     short loc_180029B52
0x180029b4a  xor     ebx, ebx
0x180029b4c  cmp     [rbp+57h+var_38], ebx
0x180029b4f  setnz   bl
0x180029b52  lea     rcx, [rbp+57h+hkey]
0x180029b56  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029b5b  lea     rcx, [rbp+57h+var_30]
0x180029b5f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029b64  nop
0x180029b65  lea     rcx, [rbp+57h+var_88]
0x180029b69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180029b6e  mov     eax, ebx
0x180029b70  mov     rcx, [rbp+57h+var_10]
0x180029b74  xor     rcx, rsp; StackCookie
0x180029b77  call    __security_check_cookie
0x180029b7c  lea     r11, [rsp+0E0h+var_s0]
0x180029b84  mov     rbx, [r11+18h]
0x180029b88  mov     rdi, [r11+20h]
0x180029b8c  mov     rsp, r11
0x180029b8f  pop     rbp
0x180029b90  retn
```
