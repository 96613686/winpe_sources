# DusmStore::QueryProfileIndexList(DusmConnection const &)

- ea: `0x18002a1c4`
- end: `0x18002a52c`
- name: `?QueryProfileIndexList@DusmStore@@SA?AV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@AEBVDusmConnection@@@Z`
- size: `872`
- prototype: ``
- caller_count: `6`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ea28`
- `0x18002051c`
- `0x180022d90`
- `0x1800235e4`
- `0x180023b48`
- `0x180024074`

## callees

- `0x180001234`
- `0x180001294`
- `0x18000522c`
- `0x180007c90`
- `0x180008704`
- `0x18000e6e4`
- `0x18000e828`
- `0x18000ee34`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x180013444`
- `0x180018050`
- `0x1800259f0`
- `0x180025a24`
- `0x180026224`
- `0x180026fa0`
- `0x18002a1c4`
- `0x18002d23c`
- `0x18002d9e8`
- `0x18002de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a205`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a205`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a296`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a296`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a318`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a3b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a318`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a3b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DusmStore::QueryProfileIndexList(__int64 a1, __int64 a2)
{
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  LSTATUS v10; // ebx
  _DWORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  LSTATUS ValueW; // ebx
  char *v17; // rdi
  unsigned __int64 v18; // rcx
  char *v19; // rax
  size_t v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  LSTATUS v23; // ebx
  _DWORD *v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  _DWORD *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  LPCRITICAL_SECTION v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v38[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v39[32]; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp-48h] BYREF
  HKEY hkey; // [rsp+C0h] [rbp-40h] BYREF
  PVOID pvData[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-28h]
  _BYTE v44[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v45[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v46; // [rsp+110h] [rbp+10h]

  v37 = a1;
  v4 = DusmStore::s_pInstance + 1;
  EnterCriticalSection(DusmStore::s_pInstance + 1);
  v36[0] = v4;
  v5 = std::wstring::wstring((__int64)v39, (__int64)qword_180068EC8);
  v6 = std::operator+<wchar_t>((__int64)v38, v5, (__int64)L"\\");
  std::operator+<wchar_t>((__int64)v44, v6, a2 + 144);
  std::wstring::_Tidy_deallocate(v38);
  std::wstring::_Tidy_deallocate(v39);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v44);
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hkey);
  if ( !v10 )
  {
    *(_OWORD *)pvData = 0;
    v43 = 0;
    pcbData = 0;
    ValueW = RegGetValueW(hkey, 0, L"ProfileIndexList", 2u, 0, 0, &pcbData);
    if ( ValueW || (v15 = pcbData) == 0 )
    {
      v30 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v15, v14) + 8);
      if ( *v30 > 5u )
      {
        LODWORD(v35) = pcbData;
        LODWORD(v34) = ValueW;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v30,
          (int)byte_1800580F9,
          v31,
          v32,
          (__int64)&v34,
          (__int64)&v35);
      }
      goto LABEL_22;
    }
    v17 = (char *)pvData[1];
    v18 = ((char *)pvData[1] - (char *)pvData[0]) >> 1;
    if ( pcbData < v18 )
    {
      v19 = (char *)pvData[0] + 2 * pcbData;
LABEL_13:
      pvData[1] = v19;
      goto LABEL_14;
    }
    if ( pcbData > v18 )
    {
      if ( pcbData <= (unsigned __int64)((signed __int64)(v43 - (unsigned __int64)pvData[0]) >> 1) )
      {
        v20 = 2 * (pcbData - v18);
        memset_0(pvData[1], 0, v20);
        v19 = &v17[v20];
        goto LABEL_13;
      }
      std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(pvData, pcbData);
    }
LABEL_14:
    v23 = RegGetValueW(hkey, 0, L"ProfileIndexList", 2u, 0, pvData[0], &pcbData);
    if ( !v23 )
    {
      memset_0(v45, 0, 0x40u);
      SzToProfileIndexList(v45, pvData[0]);
      if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v27, v26) + 8) > 5u )
      {
        v35 = (__int64)pvData[0];
        v34 = v46;
        v37 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2 + 144);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
          v28,
          (int)&word_180058042,
          v28,
          v29,
          (const WCHAR **)&v37,
          (__int64)&v34,
          (const WCHAR **)&v35);
      }
      std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>(
        a1,
        (__int64)v45);
      std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>((__int64)v45);
      goto LABEL_23;
    }
    v24 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v22, v21) + 8);
    if ( *v24 > 5u )
    {
      LODWORD(v34) = pcbData;
      LODWORD(v35) = v23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (int)v24,
        (int)&word_18005809E,
        (__int64)v24,
        v25,
        (__int64)&v35,
        (__int64)&v34);
    }
LABEL_22:
    std::unordered_set<unsigned long>::unordered_set<unsigned long>(a1);
LABEL_23:
    std::vector<wchar_t>::_Tidy(pvData);
    goto LABEL_24;
  }
  v11 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v9, v8) + 8);
  if ( *v11 > 5u )
  {
    LODWORD(v34) = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)v11,
      (int)&dword_180058154,
      v12,
      v13,
      (__int64)&v34);
  }
  std::unordered_set<unsigned long>::unordered_set<unsigned long>(a1);
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  std::wstring::_Tidy_deallocate(v44);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v36);
  return a1;
}

```

## disassembly

```asm
0x18002a1c4  mov     [rsp-8+arg_10], rbx
0x18002a1c9  mov     [rsp-8+arg_18], rsi
0x18002a1ce  push    rbp
0x18002a1cf  push    rdi
0x18002a1d0  push    r14
0x18002a1d2  lea     rbp, [rsp-50h]
0x18002a1d7  sub     rsp, 150h
0x18002a1de  mov     rax, cs:__security_cookie
0x18002a1e5  xor     rax, rsp
0x18002a1e8  mov     [rbp+60h+var_20], rax
0x18002a1ec  mov     r14, rdx
0x18002a1ef  mov     rsi, rcx
0x18002a1f2  mov     [rsp+160h+var_100], rcx
0x18002a1f7  mov     rbx, cs:?s_pInstance@DusmStore@@0PEAV1@EA; DusmStore * DusmStore::s_pInstance
0x18002a1fe  add     rbx, 28h ; '('
0x18002a202  mov     rcx, rbx; lpCriticalSection
0x18002a205  call    cs:__imp_EnterCriticalSection
0x18002a20b  mov     [rsp+160h+var_110], rbx
0x18002a210  mov     rdx, cs:qword_180068EC8
0x18002a217  lea     rcx, [rbp+60h+var_C8]
0x18002a21b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18002a220  nop
0x18002a221  lea     r8, asc_18004F678; "\\"
0x18002a228  mov     rdx, rax
0x18002a22b  lea     rcx, [rsp+160h+var_E8]
0x18002a230  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18002a235  nop
0x18002a236  lea     r8, [r14+90h]
0x18002a23d  mov     rdx, rax
0x18002a240  lea     rcx, [rbp+60h+var_80]
0x18002a244  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18002a249  nop
0x18002a24a  lea     rcx, [rsp+160h+var_E8]
0x18002a24f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a254  nop
0x18002a255  lea     rcx, [rbp+60h+var_C8]
0x18002a259  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a25e  mov     [rbp+60h+hkey], 0
0x18002a266  xor     edx, edx
0x18002a268  lea     rcx, [rbp+60h+hkey]
0x18002a26c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a271  lea     rcx, [rbp+60h+var_80]
0x18002a275  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a27a  mov     rdx, rax; lpSubKey
0x18002a27d  lea     rax, [rbp+60h+hkey]
0x18002a281  mov     [rsp+160h+phkResult], rax; phkResult
0x18002a286  mov     r9d, 20019h; samDesired
0x18002a28c  xor     r8d, r8d; ulOptions
0x18002a28f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a296  call    cs:__imp_RegOpenKeyExW
0x18002a29c  mov     ebx, eax
0x18002a29e  test    eax, eax
0x18002a2a0  jz      short loc_18002A2D9
0x18002a2a2  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002a2a7  mov     rcx, [rax+8]
0x18002a2ab  mov     eax, [rcx]
0x18002a2ad  cmp     eax, 5
0x18002a2b0  jbe     short loc_18002A2CC
0x18002a2b2  mov     dword ptr [rsp+160h+var_120], ebx
0x18002a2b6  lea     rax, [rsp+160h+var_120]
0x18002a2bb  mov     [rsp+160h+phkResult], rax
0x18002a2c0  lea     rdx, dword_180058154
0x18002a2c7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002a2cc  mov     rcx, rsi
0x18002a2cf  call    ??0?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@QEAA@XZ; std::unordered_set<ulong>::unordered_set<ulong>(void)
0x18002a2d4  jmp     loc_18002A4E7
0x18002a2d9  xor     eax, eax
0x18002a2db  xorps   xmm1, xmm1
0x18002a2de  movdqu  xmmword ptr [rbp+60h+var_98], xmm1
0x18002a2e3  mov     [rbp+60h+var_88], rax
0x18002a2e7  mov     [rbp+60h+var_A8], eax
0x18002a2ea  lea     rax, [rbp+60h+var_A8]
0x18002a2ee  mov     [rsp+160h+pcbData], rax; pcbData
0x18002a2f3  mov     [rsp+160h+pvData], 0; pvData
0x18002a2fc  mov     [rsp+160h+phkResult], 0; pdwType
0x18002a305  mov     r9d, 2; dwFlags
0x18002a30b  lea     r8, aProfileindexli; "ProfileIndexList"
0x18002a312  xor     edx, edx; lpSubKey
0x18002a314  mov     rcx, [rbp+60h+hkey]; hkey
0x18002a318  call    cs:__imp_RegGetValueW
0x18002a31e  mov     ebx, eax
0x18002a320  test    eax, eax
0x18002a322  jnz     loc_18002A499
0x18002a328  mov     ecx, [rbp+60h+var_A8]
0x18002a32b  test    ecx, ecx
0x18002a32d  jz      loc_18002A499
0x18002a333  mov     ebx, ecx
0x18002a335  mov     rdx, [rbp+60h+var_98]
0x18002a339  mov     rdi, [rbp+60h+var_98+8]
0x18002a33d  mov     rcx, rdi
0x18002a340  sub     rcx, rdx
0x18002a343  sar     rcx, 1
0x18002a346  cmp     rbx, rcx
0x18002a349  jnb     short loc_18002A351
0x18002a34b  lea     rax, [rdx+rbx*2]
0x18002a34f  jmp     short loc_18002A387
0x18002a351  jbe     short loc_18002A38B
0x18002a353  mov     rax, [rbp+60h+var_88]
0x18002a357  sub     rax, rdx
0x18002a35a  sar     rax, 1
0x18002a35d  cmp     rbx, rax
0x18002a360  jbe     short loc_18002A370
0x18002a362  mov     rdx, rbx
0x18002a365  lea     rcx, [rbp+60h+var_98]
0x18002a369  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002a36e  jmp     short loc_18002A38B
0x18002a370  sub     rbx, rcx
0x18002a373  add     rbx, rbx
0x18002a376  mov     r8, rbx; Size
0x18002a379  xor     edx, edx; Val
0x18002a37b  mov     rcx, rdi; void *
0x18002a37e  call    memset_0
0x18002a383  lea     rax, [rbx+rdi]
0x18002a387  mov     [rbp+60h+var_98+8], rax
0x18002a38b  mov     rax, [rbp+60h+var_98]
0x18002a38f  lea     rcx, [rbp+60h+var_A8]
0x18002a393  mov     [rsp+160h+pcbData], rcx; pcbData
0x18002a398  mov     [rsp+160h+pvData], rax; pvData
0x18002a39d  mov     [rsp+160h+phkResult], 0; pdwType
0x18002a3a6  mov     r9d, 2; dwFlags
0x18002a3ac  lea     r8, aProfileindexli; "ProfileIndexList"
0x18002a3b3  xor     edx, edx; lpSubKey
0x18002a3b5  mov     rcx, [rbp+60h+hkey]; hkey
0x18002a3b9  call    cs:__imp_RegGetValueW
0x18002a3bf  mov     ebx, eax
0x18002a3c1  test    eax, eax
0x18002a3c3  jz      short loc_18002A403
0x18002a3c5  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002a3ca  mov     r8, [rax+8]
0x18002a3ce  mov     ecx, [r8]
0x18002a3d1  cmp     ecx, 5
0x18002a3d4  jbe     loc_18002A4D4
0x18002a3da  mov     ecx, [rbp+60h+var_A8]
0x18002a3dd  mov     dword ptr [rsp+160h+var_120], ecx
0x18002a3e1  mov     dword ptr [rsp+160h+var_118], ebx
0x18002a3e5  lea     rax, [rsp+160h+var_120]
0x18002a3ea  mov     [rsp+160h+pvData], rax
0x18002a3ef  lea     rax, [rsp+160h+var_118]
0x18002a3f4  lea     rdx, word_18005809E
0x18002a3fb  mov     rcx, r8
0x18002a3fe  jmp     loc_18002A4CA
0x18002a403  xor     edx, edx; Val
0x18002a405  lea     r8d, [rdx+40h]; Size
0x18002a409  lea     rcx, [rbp+60h+var_60]; void *
0x18002a40d  call    memset_0
0x18002a412  mov     rdx, [rbp+60h+var_98]
0x18002a416  lea     rcx, [rbp+60h+var_60]
0x18002a41a  call    SzToProfileIndexList
0x18002a41f  nop
0x18002a420  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002a425  mov     r8, [rax+8]
0x18002a429  mov     eax, [r8]
0x18002a42c  cmp     eax, 5
0x18002a42f  jbe     short loc_18002A481
0x18002a431  mov     rax, [rbp+60h+var_98]
0x18002a435  mov     [rsp+160h+var_118], rax
0x18002a43a  mov     rax, [rbp+60h+var_50]
0x18002a43e  mov     [rsp+160h+var_120], rax
0x18002a443  lea     rcx, [r14+90h]
0x18002a44a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002a44f  mov     [rsp+160h+var_100], rax
0x18002a454  lea     rax, [rsp+160h+var_118]
0x18002a459  mov     [rsp+160h+pcbData], rax; __int64
0x18002a45e  lea     rax, [rsp+160h+var_120]
0x18002a463  mov     [rsp+160h+pvData], rax; __int64
0x18002a468  lea     rax, [rsp+160h+var_100]
0x18002a46d  mov     [rsp+160h+phkResult], rax; __int64
0x18002a472  lea     rdx, word_180058042; int
0x18002a479  mov     rcx, r8; int
0x18002a47c  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &)
0x18002a481  lea     rdx, [rbp+60h+var_60]
0x18002a485  mov     rcx, rsi
0x18002a488  call    ??0?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>> &&)
0x18002a48d  nop
0x18002a48e  lea     rcx, [rbp+60h+var_60]
0x18002a492  call    ??1?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::~_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(void)
0x18002a497  jmp     short loc_18002A4DD
0x18002a499  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18002a49e  mov     rcx, [rax+8]
0x18002a4a2  mov     eax, [rcx]
0x18002a4a4  cmp     eax, 5
0x18002a4a7  jbe     short loc_18002A4D4
0x18002a4a9  mov     eax, [rbp+60h+var_A8]
0x18002a4ac  mov     dword ptr [rsp+160h+var_118], eax
0x18002a4b0  mov     dword ptr [rsp+160h+var_120], ebx
0x18002a4b4  lea     rax, [rsp+160h+var_118]
0x18002a4b9  mov     [rsp+160h+pvData], rax
0x18002a4be  lea     rax, [rsp+160h+var_120]
0x18002a4c3  lea     rdx, byte_1800580F9
0x18002a4ca  mov     [rsp+160h+phkResult], rax
0x18002a4cf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002a4d4  mov     rcx, rsi
0x18002a4d7  call    ??0?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@QEAA@XZ; std::unordered_set<ulong>::unordered_set<ulong>(void)
0x18002a4dc  nop
0x18002a4dd  lea     rcx, [rbp+60h+var_98]
0x18002a4e1  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18002a4e6  nop
0x18002a4e7  lea     rcx, [rbp+60h+hkey]
0x18002a4eb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a4f0  nop
0x18002a4f1  lea     rcx, [rbp+60h+var_80]
0x18002a4f5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a4fa  nop
0x18002a4fb  lea     rcx, [rsp+160h+var_110]
0x18002a500  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002a505  mov     rax, rsi
0x18002a508  mov     rcx, [rbp+60h+var_20]
0x18002a50c  xor     rcx, rsp; StackCookie
0x18002a50f  call    __security_check_cookie
0x18002a514  lea     r11, [rsp+160h+var_10]
0x18002a51c  mov     rbx, [r11+30h]
0x18002a520  mov     rsi, [r11+38h]
0x18002a524  mov     rsp, r11
0x18002a527  pop     r14
0x18002a529  pop     rdi
0x18002a52a  pop     rbp
0x18002a52b  retn
```
