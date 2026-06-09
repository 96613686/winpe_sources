# DusmStore::SetProfileIndexList(DusmConnection const &)

- ea: `0x18002c9cc`
- end: `0x18002cd35`
- name: `?SetProfileIndexList@DusmStore@@SAXAEBVDusmConnection@@@Z`
- size: `873`
- prototype: `void __fastcall(const struct DusmConnection *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ec44`
- `0x18002051c`

## callees

- `0x18000522c`
- `0x180007c90`
- `0x180008704`
- `0x18000e828`
- `0x18000ee34`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x180013444`
- `0x180018bdc`
- `0x18001d87c`
- `0x1800259f0`
- `0x180025a24`
- `0x180026224`
- `0x1800267f4`
- `0x180026fa0`
- `0x180027eb8`
- `0x18002c9cc`
- `0x18002d23c`
- `0x18002d9e8`
- `0x18002de88`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ca0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ca0d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cae5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cae5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cb29`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cb8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cb29`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cb8d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cc22`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cc22`

## string_xrefs

- `0x18002cd14`: `DusmStore::SetProfileIndexList::RegCreateKeyExW`
- `0x18002ccef`: `DusmStore::SetProfileIndexList::RegSetKeyValueW`

## pseudocode

```c
void __fastcall DusmStore::SetProfileIndexList(const struct DusmConnection *a1)
{
  LPCRITICAL_SECTION v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rcx
  const void *v9; // rax
  DWORD v10; // edx
  unsigned int v11; // eax
  int v12; // r8d
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  LPCRITICAL_SECTION v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  PVOID pvData[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+90h] [rbp-70h]
  _BYTE v23[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+D0h] [rbp-30h]
  _BYTE v26[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v27; // [rsp+110h] [rbp+10h]
  _BYTE v28[32]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( *((_DWORD *)a1 + 4) != 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  v2 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v15 = v2;
  memset_0(v26, 0, 0x40u);
  DusmConnection::GetProfileIndexList(a1, v26);
  if ( v27 )
  {
    v3 = std::wstring::wstring(v24, qword_180068EC8);
    v4 = std::operator+<wchar_t>(pvData, v3, L"\\");
    std::operator+<wchar_t>(v28, v4, (char *)a1 + 144);
    std::wstring::_Tidy_deallocate(pvData);
    std::wstring::_Tidy_deallocate(v24);
    hkey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28);
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x2001Fu, 0, &hkey, 0);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x594,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v6,
        (unsigned int)"DusmStore::SetProfileIndexList::RegCreateKeyExW",
        samDesired);
    pcbData = 0;
    if ( !RegGetValueW(hkey, 0, L"ProfileIndexList", 2u, 0, 0, &pcbData) && pcbData )
    {
      *(_OWORD *)pvData = 0;
      v22 = 0;
      std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(pvData, pcbData);
      if ( !RegGetValueW(hkey, 0, L"ProfileIndexList", 2u, 0, pvData[0], &pcbData) )
      {
        memset_0(v24, 0, 0x40u);
        SzToProfileIndexList(v24, pvData[0]);
        v7 = v25;
        std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::merge<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>(
          v26,
          v24);
        if ( v25 != v7 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v8);
        std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>(v24);
      }
      std::vector<wchar_t>::_Tidy(pvData);
    }
    ProfileIndexListToStr(v23, v26);
    v9 = (const void *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v23);
    v11 = RegSetKeyValueW(hkey, 0, L"ProfileIndexList", 1u, v9, v10);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x5B8,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmstore.cpp",
        (const char *)v11,
        (unsigned int)"DusmStore::SetProfileIndexList::RegSetKeyValueW",
        samDesireda);
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
    {
      v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v23);
      v17 = v27;
      v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a1 + 144);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
        v12,
        (int)&word_180057FEA,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v16);
    }
    std::wstring::_Tidy_deallocate(v23);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    std::wstring::_Tidy_deallocate(v28);
  }
  std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>(v26);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
}

```

## disassembly

```asm
0x18002c9cc  mov     [rsp-8+arg_8], rbx
0x18002c9d1  mov     [rsp-8+arg_10], rdi
0x18002c9d6  push    rbp
0x18002c9d7  lea     rbp, [rsp-70h]
0x18002c9dc  sub     rsp, 170h
0x18002c9e3  mov     rax, cs:__security_cookie
0x18002c9ea  xor     rax, rsp
0x18002c9ed  mov     [rbp+70h+var_10], rax
0x18002c9f1  mov     rdi, rcx
0x18002c9f4  cmp     dword ptr [rcx+10h], 3
0x18002c9f8  jz      short loc_18002C9FF
0x18002c9fa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c9ff  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002ca06  add     rbx, 28h ; '('
0x18002ca0a  mov     rcx, rbx; lpCriticalSection
0x18002ca0d  call    cs:__imp_EnterCriticalSection
0x18002ca13  mov     [rsp+170h+var_120], rbx
0x18002ca18  xor     edx, edx; Val
0x18002ca1a  lea     r8d, [rdx+40h]; Size
0x18002ca1e  lea     rcx, [rbp+70h+var_70]; void *
0x18002ca22  call    memset_0
0x18002ca27  lea     rdx, [rbp+70h+var_70]
0x18002ca2b  mov     rcx, rdi
0x18002ca2e  call    ?GetProfileIndexList@DusmConnection@@QEBA?AV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@XZ; DusmConnection::GetProfileIndexList(void)
0x18002ca33  nop
0x18002ca34  cmp     [rbp+70h+var_60], 0
0x18002ca39  jz      loc_18002CCB6
0x18002ca3f  mov     rdx, cs:qword_180068EC8
0x18002ca46  lea     rcx, [rbp+70h+var_B0]
0x18002ca4a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002ca4f  nop
0x18002ca50  lea     r8, asc_18004F678; "\\"
0x18002ca57  mov     rdx, rax
0x18002ca5a  lea     rcx, [rbp+70h+pvData]
0x18002ca5e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002ca63  nop
0x18002ca64  lea     r8, [rdi+90h]
0x18002ca6b  mov     rdx, rax
0x18002ca6e  lea     rcx, [rbp+70h+var_30]
0x18002ca72  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002ca77  nop
0x18002ca78  lea     rcx, [rbp+70h+pvData]
0x18002ca7c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ca81  nop
0x18002ca82  lea     rcx, [rbp+70h+var_B0]
0x18002ca86  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ca8b  mov     [rsp+170h+hkey], 0
0x18002ca94  xor     edx, edx
0x18002ca96  lea     rcx, [rsp+170h+hkey]
0x18002ca9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002caa0  lea     rcx, [rbp+70h+var_30]
0x18002caa4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002caa9  mov     rdx, rax; lpSubKey
0x18002caac  mov     [rsp+170h+lpdwDisposition], 0; lpdwDisposition
0x18002cab5  lea     rax, [rsp+170h+hkey]
0x18002caba  mov     [rsp+170h+phkResult], rax; phkResult
0x18002cabf  mov     [rsp+170h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002cac8  mov     [rsp+170h+samDesired], 2001Fh; char *
0x18002cad0  mov     [rsp+170h+dwOptions], 0; dwOptions
0x18002cad8  xor     r9d, r9d; lpClass
0x18002cadb  xor     r8d, r8d; Reserved
0x18002cade  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002cae5  call    cs:__imp_RegCreateKeyExW
0x18002caeb  test    eax, eax
0x18002caed  jnz     loc_18002CD10
0x18002caf3  mov     [rsp+170h+pcbData], eax
0x18002caf7  lea     rax, [rsp+170h+pcbData]
0x18002cafc  mov     [rsp+170h+lpSecurityAttributes], rax; pcbData
0x18002cb01  mov     qword ptr [rsp+170h+samDesired], 0; pvData
0x18002cb0a  mov     qword ptr [rsp+170h+dwOptions], 0; pdwType
0x18002cb13  mov     ebx, 2
0x18002cb18  mov     r9d, ebx; dwFlags
0x18002cb1b  lea     r8, aProfileindexli; "ProfileIndexList"
0x18002cb22  xor     edx, edx; lpSubKey
0x18002cb24  mov     rcx, [rsp+170h+hkey]; hkey
0x18002cb29  call    cs:__imp_RegGetValueW
0x18002cb2f  test    eax, eax
0x18002cb31  jnz     loc_18002CBE4
0x18002cb37  mov     eax, [rsp+170h+pcbData]
0x18002cb3b  test    eax, eax
0x18002cb3d  jz      loc_18002CBE4
0x18002cb43  xor     ecx, ecx
0x18002cb45  xorps   xmm1, xmm1
0x18002cb48  movdqu  xmmword ptr [rbp+70h+pvData], xmm1
0x18002cb4d  mov     [rbp+70h+var_E0], rcx
0x18002cb51  mov     edx, eax
0x18002cb53  test    eax, eax
0x18002cb55  jz      short loc_18002CB60
0x18002cb57  lea     rcx, [rbp+70h+pvData]
0x18002cb5b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002cb60  mov     rax, [rbp+70h+pvData]
0x18002cb64  lea     rcx, [rsp+170h+pcbData]
0x18002cb69  mov     [rsp+170h+lpSecurityAttributes], rcx; pcbData
0x18002cb6e  mov     qword ptr [rsp+170h+samDesired], rax; pvData
0x18002cb73  mov     qword ptr [rsp+170h+dwOptions], 0; pdwType
0x18002cb7c  mov     r9d, ebx; dwFlags
0x18002cb7f  lea     r8, aProfileindexli; "ProfileIndexList"
0x18002cb86  xor     edx, edx; lpSubKey
0x18002cb88  mov     rcx, [rsp+170h+hkey]; hkey
0x18002cb8d  call    cs:__imp_RegGetValueW
0x18002cb93  test    eax, eax
0x18002cb95  jnz     short loc_18002CBDB
0x18002cb97  xor     edx, edx; Val
0x18002cb99  lea     r8d, [rax+40h]; Size
0x18002cb9d  lea     rcx, [rbp+70h+var_B0]; void *
0x18002cba1  call    memset_0
0x18002cba6  mov     rdx, [rbp+70h+pvData]
0x18002cbaa  lea     rcx, [rbp+70h+var_B0]
0x18002cbae  call    SzToProfileIndexList
0x18002cbb3  nop
0x18002cbb4  mov     rbx, [rbp+70h+var_A0]
0x18002cbb8  lea     rdx, [rbp+70h+var_B0]
0x18002cbbc  lea     rcx, [rbp+70h+var_70]
0x18002cbc0  call    ??$merge@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAAXAEAV01@@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::merge<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>> &)
0x18002cbc5  cmp     [rbp+70h+var_A0], rbx
0x18002cbc9  jz      short loc_18002CBD1
0x18002cbcb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002cbd0  nop
0x18002cbd1  lea     rcx, [rbp+70h+var_B0]
0x18002cbd5  call    ??1?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::~_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(void)
0x18002cbda  nop
0x18002cbdb  lea     rcx, [rbp+70h+pvData]
0x18002cbdf  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18002cbe4  lea     rdx, [rbp+70h+var_70]
0x18002cbe8  lea     rcx, [rbp+70h+var_D0]
0x18002cbec  call    ProfileIndexListToStr
0x18002cbf1  nop
0x18002cbf2  mov     eax, [rbp+70h+var_C0]
0x18002cbf5  lea     edx, ds:2[rax*2]
0x18002cbfc  lea     rcx, [rbp+70h+var_D0]
0x18002cc00  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cc05  mov     [rsp+170h+samDesired], edx; char *
0x18002cc09  mov     qword ptr [rsp+170h+dwOptions], rax; lpData
0x18002cc0e  mov     r9d, 1; dwType
0x18002cc14  lea     r8, aProfileindexli; "ProfileIndexList"
0x18002cc1b  xor     edx, edx; lpSubKey
0x18002cc1d  mov     rcx, [rsp+170h+hkey]; hKey
0x18002cc22  call    cs:__imp_RegSetKeyValueW
0x18002cc28  test    eax, eax
0x18002cc2a  jnz     loc_18002CCEB
0x18002cc30  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002cc35  mov     r8, [rax+8]
0x18002cc39  mov     eax, [r8]
0x18002cc3c  cmp     eax, 5
0x18002cc3f  jbe     short loc_18002CC97
0x18002cc41  lea     rcx, [rbp+70h+var_D0]
0x18002cc45  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cc4a  mov     [rsp+170h+var_118], rax
0x18002cc4f  mov     rax, [rbp+70h+var_60]
0x18002cc53  mov     [rsp+170h+var_110], rax
0x18002cc58  lea     rcx, [rdi+90h]
0x18002cc5f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cc64  mov     [rsp+170h+var_108], rax
0x18002cc69  lea     rax, [rsp+170h+var_118]
0x18002cc6e  mov     [rsp+170h+lpSecurityAttributes], rax; __int64
0x18002cc73  lea     rax, [rsp+170h+var_110]
0x18002cc78  mov     qword ptr [rsp+170h+samDesired], rax; __int64
0x18002cc7d  lea     rax, [rsp+170h+var_108]
0x18002cc82  mov     qword ptr [rsp+170h+dwOptions], rax; __int64
0x18002cc87  lea     rdx, word_180057FEA; int
0x18002cc8e  mov     rcx, r8; int
0x18002cc91  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &)
0x18002cc96  nop
0x18002cc97  lea     rcx, [rbp+70h+var_D0]
0x18002cc9b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cca0  nop
0x18002cca1  lea     rcx, [rsp+170h+hkey]
0x18002cca6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002ccab  nop
0x18002ccac  lea     rcx, [rbp+70h+var_30]
0x18002ccb0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ccb5  nop
0x18002ccb6  lea     rcx, [rbp+70h+var_70]
0x18002ccba  call    ??1?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::~_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(void)
0x18002ccbf  nop
0x18002ccc0  lea     rcx, [rsp+170h+var_120]
0x18002ccc5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002ccca  mov     rcx, [rbp+70h+var_10]
0x18002ccce  xor     rcx, rsp; StackCookie
0x18002ccd1  call    __security_check_cookie
0x18002ccd6  lea     r11, [rsp+170h+var_s0]
0x18002ccde  mov     rbx, [r11+18h]
0x18002cce2  mov     rdi, [r11+20h]
0x18002cce6  mov     rsp, r11
0x18002cce9  pop     rbp
0x18002ccea  retn
0x18002cceb  mov     rcx, [rbp+78h]; this
0x18002ccef  lea     rdx, aDusmstoreSetpr_0; "DusmStore::SetProfileIndexList::RegSetK"...
0x18002ccf6  mov     qword ptr [rsp+170h+dwOptions], rdx; unsigned int
0x18002ccfb  mov     r9d, eax; char *
0x18002ccfe  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002cd05  mov     edx, 5B8h; void *
0x18002cd0a  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002cd10  mov     rcx, [rbp+78h]; this
0x18002cd14  lea     rdx, aDusmstoreSetpr; "DusmStore::SetProfileIndexList::RegCrea"...
0x18002cd1b  mov     qword ptr [rsp+170h+dwOptions], rdx; unsigned int
0x18002cd20  mov     r9d, eax; char *
0x18002cd23  lea     r8, aOnecoreuapNetD_14; "onecoreuap\\net\\dusm\\lib\\dusmstore.c"...
0x18002cd2a  mov     edx, 594h; void *
0x18002cd2f  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
