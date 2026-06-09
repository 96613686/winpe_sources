# Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,Microsoft::Diagnostics::EndpointUnregistrationReason)

- ea: `0x1801defb8`
- end: `0x1801df676`
- name: `?UnregisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_NVEndpointUnregistrationReason@23@@Z`
- size: `1726`
- prototype: ``
- caller_count: `4`
- callee_count: `35`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18013a850`
- `0x1801deef8`
- `0x180262808`
- `0x1802ef7c0`

## callees

- `0x180002a28`
- `0x180002b90`
- `0x18000341c`
- `0x1800210a8`
- `0x18002110c`
- `0x180024558`
- `0x180027c28`
- `0x180027e50`
- `0x18002ac10`
- `0x18002b770`
- `0x18002b7c0`
- `0x18002df00`
- `0x18003c66c`
- `0x180049bec`
- `0x18004b6ac`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008e53c`
- `0x18008e578`
- `0x18008e828`
- `0x18008e898`
- `0x180097bc8`
- `0x18009c8c0`
- `0x1800b47f0`
- `0x1800f7eb8`
- `0x18010f8f4`
- `0x180128728`
- `0x180142fcc`
- `0x1801c38bc`
- `0x1801cd84c`
- `0x1801d1b14`
- `0x1801defb8`
- `0x18020aac0`
- `0x180265270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801df597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801df597`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801df3e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801df3e2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801df585`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801df585`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801df48f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1801df48f`

## string_xrefs

- `0x1801df54f`: `.json`
- `0x1801df3fa`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801df4a7`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801df5a2`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(
        __int64 a1,
        _QWORD *a2,
        char a3,
        int a4)
{
  __int64 v7; // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // r13
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r15
  __m128i v14; // xmm6
  __m128i v15; // xmm7
  __int64 v16; // rax
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // r9
  __int64 v21; // rcx
  unsigned __int64 v22; // r15
  __int64 v23; // rdx
  __int64 v24; // r14
  char v25; // bl
  _QWORD *v26; // rax
  const WCHAR *v27; // rdx
  unsigned int v28; // eax
  const WCHAR *v29; // rdx
  unsigned int v30; // eax
  wchar_t **v31; // rdx
  void *appended; // rax
  void *v33; // rax
  void *v34; // rax
  const WCHAR *v35; // rcx
  const char *v36; // r9
  __int64 v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  unsigned int v41; // [rsp+20h] [rbp-608h]
  unsigned int v42; // [rsp+20h] [rbp-608h]
  __m128i v44; // [rsp+50h] [rbp-5D8h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-5C8h] BYREF
  HKEY v46; // [rsp+70h] [rbp-5B8h] BYREF
  _QWORD v47[2]; // [rsp+78h] [rbp-5B0h] BYREF
  _BYTE v48[16]; // [rsp+88h] [rbp-5A0h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+98h] [rbp-590h] BYREF
  LPCWSTR lpValueName[4]; // [rsp+B8h] [rbp-570h] BYREF
  WCHAR Src[16]; // [rsp+D8h] [rbp-550h] BYREF
  LPCWSTR lpFileName[7]; // [rsp+F8h] [rbp-530h] BYREF
  int v53[282]; // [rsp+130h] [rbp-4F8h] BYREF
  int v54[14]; // [rsp+598h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+0h]

  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
  {
    v7 = _tlgWrapBinary<wchar_t,2>(&v44, *a2, *((unsigned int *)a2 + 2));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
      v8,
      (unsigned int)word_1803E73A2,
      v9,
      v10,
      v7);
  }
  std::wstring::wstring((__int64)lpSubKey, a2);
  v11 = a2[1];
  v12 = std::_Traits_find_ch<std::char_traits<wchar_t>>(*a2, v11, 0, 46);
  v13 = v12;
  if ( v12 - 1 > 0xFFFFFFFFFFFFFFFDuLL || v12 >= v11 - 1 )
  {
    if ( (unsigned int)dword_1804543B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
    {
      v37 = _tlgWrapBinary<wchar_t,2>(v48, *a2, (unsigned int)v11);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
        v38,
        (unsigned int)word_1803E7362,
        v39,
        v40,
        v37);
    }
    return std::wstring::_Tidy_deallocate(lpSubKey);
  }
  std::wstring_view::substr(a2, hKey, 0);
  v47[0] = v13 + 1;
  std::wstring_view::substr(a2, &v44, v13 + 1);
  v14 = v44;
  v15 = *(__m128i *)hKey;
  if ( !(unsigned __int8)Microsoft::Diagnostics::SettingsEndpoint::PartnerAndFeatureAreValid(hKey, &v44) )
  {
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 512) )
      {
        _tlgWrapBinary<wchar_t,2>(&v44, v14.m128i_i64[0], _mm_srli_si128(v14, 8).m128i_u32[0]);
        v16 = _tlgWrapBinary<wchar_t,2>(v47, v15.m128i_i64[0], _mm_srli_si128(v15, 8).m128i_u32[0]);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
          v17,
          (unsigned int)&word_1803E73E6,
          v18,
          v19,
          v16,
          v19);
      }
    }
    return std::wstring::_Tidy_deallocate(lpSubKey);
  }
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v44, a1 + 632);
  v22 = std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>::operator()<std::wstring>(
          v21,
          lpSubKey);
  v23 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>,0>>::_Find_last<std::wstring>(
                      a1 + 792,
                      hKey,
                      lpSubKey,
                      v22)
                  + 8);
  if ( v23 )
  {
    std::_Hash<std::_Umap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue,std::_Uhash_compare<Microsoft::Diagnostics::ScenarioDbLookupPair,std::hash<Microsoft::Diagnostics::ScenarioDbLookupPair>,Microsoft::Diagnostics::ScenarioDbLookupPairEqualsPred>,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue>>,0>>::_Erase_bucket(
      a1 + 792,
      v23,
      v22 & *(_QWORD *)(a1 + 840));
    std::list<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>::_Unchecked_erase(a1 + 800);
    v24 = 1;
  }
  else
  {
    v24 = 0;
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v44);
  if ( v24 && std::_Traits_find<std::char_traits<wchar_t>>(*a2, v11, 0, (unsigned int)L"P-", 2) != -1 )
  {
    hKey[0] = (HKEY)L"SettingsManager_TenantEndpointUnregistered_0";
    hKey[1] = (HKEY)44;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v53,
      (unsigned int)hKey,
      0x1000000,
      0,
      0,
      0,
      0);
    hKey[0] = (HKEY)L"Endpoint";
    hKey[1] = (HKEY)8;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((int)v53, (int)v54);
    LODWORD(hKey[0]) = a4;
    v44.m128i_i64[0] = (__int64)L"Reason";
    v44.m128i_i64[1] = 6;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v53, v54, &v44, hKey);
    v44 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(hKey, &v44);
    Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v53);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v53);
  }
  v25 = a3;
  if ( !a3 )
  {
    v26 = (_QWORD *)std::wstring_view::substr(a2, &v44, v47[0]);
    std::wstring::wstring((__int64)lpValueName, v26);
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v47, a1 + 232);
    v44 = *(__m128i *)std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Eqrange<std::wstring>(
                        a1 + 56,
                        v48,
                        lpValueName);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Erase(
      a1 + 56,
      &v44);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v47);
    hKey[0] = 0;
    v44 = *(__m128i *)&off_18036A690;
    if ( (int)Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0) >= 0 && hKey[0] )
    {
      v27 = (const WCHAR *)lpValueName;
      if ( lpValueName[3] > (LPCWSTR)7 )
        v27 = lpValueName[0];
      v28 = RegDeleteValueW(hKey[0], v27);
      if ( (v28 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0xF75,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)v28,
          v41);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    std::wstring::_Tidy_deallocate(lpValueName);
    v25 = a3;
  }
  v46 = 0;
  v44 = *(__m128i *)&off_18036A1A0;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0) >= 0 && v46 )
  {
    v29 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v29 = lpSubKey[0];
    v30 = RegDeleteKeyW(v46, v29);
    if ( (v30 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0xF82,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)v30,
        v42);
  }
  v31 = &off_1803703D8;
  if ( !v25 )
    v31 = &off_1803703E8;
  std::wstring::wstring((__int64)Src, v31);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)lpFileName);
  v44 = *(__m128i *)std::wstring::operator std::wstring_view(Src, v48);
  appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpFileName);
  v33 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  v44 = *(__m128i *)a2;
  v34 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v33);
  Microsoft::Diagnostics::WideStringStream::operator<<(v34);
  v35 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v35 = lpFileName[0];
  if ( !DeleteFileW(v35) && GetLastError() != 2 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xF8E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      v36);
  std::wstring::_Tidy_deallocate(lpFileName);
  std::wstring::_Tidy_deallocate(Src);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v46);
  return std::wstring::_Tidy_deallocate(lpSubKey);
}

```

## disassembly

```asm
0x1801defb8  mov     rax, rsp
0x1801defbb  mov     [rax+18h], rbx
0x1801defbf  push    rsi
0x1801defc0  push    r12
0x1801defc2  push    r13
0x1801defc4  push    r14
0x1801defc6  push    r15
0x1801defc8  sub     rsp, 600h
0x1801defcf  movaps  xmmword ptr [rax-38h], xmm6
0x1801defd3  movaps  xmmword ptr [rax-48h], xmm7
0x1801defd7  mov     rax, cs:__security_cookie
0x1801defde  xor     rax, rsp
0x1801defe1  mov     [rsp+628h+var_58], rax
0x1801defe9  mov     ebx, r9d
0x1801defec  mov     [rsp+628h+var_5E8], r8b
0x1801deff1  mov     rsi, rdx
0x1801deff4  mov     r12, rcx
0x1801deff7  mov     eax, cs:dword_1804543B0
0x1801deffd  mov     r14d, 200h
0x1801df003  cmp     eax, 4
0x1801df006  jbe     short loc_1801DF03D
0x1801df008  mov     edx, r14d
0x1801df00b  lea     rcx, dword_1804543B0
0x1801df012  call    _tlgKeywordOn
0x1801df017  test    al, al
0x1801df019  jz      short loc_1801DF03D
0x1801df01b  mov     r8d, [rsi+8]
0x1801df01f  mov     rdx, [rsi]
0x1801df022  lea     rcx, [rsp+628h+var_5D8]
0x1801df027  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1801df02c  mov     qword ptr [rsp+628h+var_608], rax
0x1801df031  lea     rdx, word_1803E73A2
0x1801df038  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x1801df03d  mov     rdx, rsi
0x1801df040  lea     rcx, [rsp+628h+lpSubKey]
0x1801df048  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1801df04d  nop
0x1801df04e  mov     r13, [rsi+8]
0x1801df052  mov     r9d, 2Eh ; '.'
0x1801df058  xor     r8d, r8d
0x1801df05b  mov     rdx, r13
0x1801df05e  mov     rcx, [rsi]
0x1801df061  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1801df066  mov     r15, rax
0x1801df069  lea     rcx, [rax-1]
0x1801df06d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801df071  ja      loc_1801DF61F
0x1801df077  lea     rcx, [r13-1]
0x1801df07b  cmp     rax, rcx
0x1801df07e  jnb     loc_1801DF61F
0x1801df084  mov     r9, rax
0x1801df087  xor     r8d, r8d
0x1801df08a  lea     rdx, [rsp+628h+hKey]
0x1801df08f  mov     rcx, rsi
0x1801df092  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801df097  lea     rax, [r15+1]
0x1801df09b  mov     [rsp+628h+var_5B0], rax
0x1801df0a0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801df0a4  mov     r8, rax
0x1801df0a7  lea     rdx, [rsp+628h+var_5D8]
0x1801df0ac  mov     rcx, rsi
0x1801df0af  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801df0b4  movaps  xmm6, [rsp+628h+var_5D8]
0x1801df0b9  movdqa  [rsp+628h+var_5D8], xmm6
0x1801df0bf  movaps  xmm7, xmmword ptr [rsp+628h+hKey]
0x1801df0c4  movdqa  xmmword ptr [rsp+628h+hKey], xmm7
0x1801df0ca  lea     rdx, [rsp+628h+var_5D8]
0x1801df0cf  lea     rcx, [rsp+628h+hKey]
0x1801df0d4  call    ?PartnerAndFeatureAreValid@SettingsEndpoint@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::SettingsEndpoint::PartnerAndFeatureAreValid(std::wstring_view,std::wstring_view)
0x1801df0d9  test    al, al
0x1801df0db  jnz     loc_1801DF16B
0x1801df0e1  mov     eax, cs:dword_1804543B0
0x1801df0e7  cmp     eax, 2
0x1801df0ea  jbe     short loc_1801DF159
0x1801df0ec  mov     rdx, r14
0x1801df0ef  lea     rcx, dword_1804543B0
0x1801df0f6  call    _tlgKeywordOn
0x1801df0fb  test    al, al
0x1801df0fd  jz      short loc_1801DF159
0x1801df0ff  movdqa  xmm0, xmm6
0x1801df103  psrldq  xmm0, 8
0x1801df108  movq    r8, xmm0
0x1801df10d  mov     r8d, r8d
0x1801df110  movq    rdx, xmm6
0x1801df115  lea     rcx, [rsp+628h+var_5D8]
0x1801df11a  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1801df11f  mov     r9, rax
0x1801df122  movdqa  xmm0, xmm7
0x1801df126  psrldq  xmm0, 8
0x1801df12b  movq    r8, xmm0
0x1801df130  mov     r8d, r8d
0x1801df133  movq    rdx, xmm7
0x1801df138  lea     rcx, [rsp+628h+var_5B0]
0x1801df13d  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1801df142  mov     qword ptr [rsp+628h+var_600], r9
0x1801df147  mov     qword ptr [rsp+628h+var_608], rax
0x1801df14c  lea     rdx, word_1803E73E6
0x1801df153  call    ??$Write@U?$_tlgWrapperArray@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x1801df158  nop
0x1801df159  lea     rcx, [rsp+628h+lpSubKey]
0x1801df161  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801df166  jmp     loc_1801DF5EC
0x1801df16b  lea     rdx, [r12+278h]
0x1801df173  lea     rcx, [rsp+628h+var_5D8]
0x1801df178  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801df17d  lea     r14, [r12+318h]
0x1801df185  lea     rdx, [rsp+628h+lpSubKey]
0x1801df18d  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHashPredicate@Hash@Utils@Diagnostics@Microsoft@@UCaseInsensitiveEqualToPredicate@String@567@@std@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>::operator()<std::wstring>(std::wstring const &)
0x1801df192  mov     r15, rax
0x1801df195  mov     r9, rax
0x1801df198  lea     r8, [rsp+628h+lpSubKey]
0x1801df1a0  lea     rdx, [rsp+628h+hKey]
0x1801df1a5  mov     rcx, r14
0x1801df1a8  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHashPredicate@Hash@Utils@Diagnostics@Microsoft@@UCaseInsensitiveEqualToPredicate@String@567@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>,std::_Uhash_compare<std::wstring,Microsoft::Diagnostics::Utils::Hash::CaseInsensitiveHashPredicate,Microsoft::Diagnostics::Utils::String::CaseInsensitiveEqualToPredicate>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1801df1ad  mov     rdx, [rax+8]
0x1801df1b1  test    rdx, rdx
0x1801df1b4  jz      short loc_1801DF1D6
0x1801df1b6  mov     r8, [r14+30h]
0x1801df1ba  and     r8, r15
0x1801df1bd  mov     rcx, r14
0x1801df1c0  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@UScenarioDbLookupPair@Diagnostics@Microsoft@@UScenarioObjectMapValue@ScenarioObjectCache@23@V?$_Uhash_compare@UScenarioDbLookupPair@Diagnostics@Microsoft@@U?$hash@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@UScenarioDbLookupPairEqualsPred@23@@std@@V?$allocator@U?$pair@$$CBUScenarioDbLookupPair@Diagnostics@Microsoft@@UScenarioObjectMapValue@ScenarioObjectCache@23@@std@@@7@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBUScenarioDbLookupPair@Diagnostics@Microsoft@@UScenarioObjectMapValue@ScenarioObjectCache@23@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue,std::_Uhash_compare<Microsoft::Diagnostics::ScenarioDbLookupPair,std::hash<Microsoft::Diagnostics::ScenarioDbLookupPair>,Microsoft::Diagnostics::ScenarioDbLookupPairEqualsPred>,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue>>,0>>::_Erase_bucket(std::_List_node<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,Microsoft::Diagnostics::ScenarioObjectCache::ScenarioObjectMapValue>,void *> *,unsigned __int64)
0x1801df1c5  lea     rcx, [r14+8]
0x1801df1c9  call    ?_Unchecked_erase@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VSettingsEndpoint@Diagnostics@Microsoft@@U?$default_delete@VSettingsEndpoint@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::SettingsEndpoint>>,void *> * const)
0x1801df1ce  mov     r14d, 1
0x1801df1d4  jmp     short loc_1801DF1D9
0x1801df1d6  xor     r14d, r14d
0x1801df1d9  lea     rcx, [rsp+628h+var_5D8]
0x1801df1de  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801df1e3  test    r14, r14
0x1801df1e6  jz      loc_1801DF2FA
0x1801df1ec  mov     qword ptr [rsp+628h+var_608], 2
0x1801df1f5  mov     r9, cs:off_1803845F0; "P-"
0x1801df1fc  xor     r8d, r8d
0x1801df1ff  mov     rdx, r13
0x1801df202  mov     rcx, [rsi]
0x1801df205  call    ??$_Traits_find@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K101@Z; std::_Traits_find<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1801df20a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801df20e  jz      loc_1801DF2FA
0x1801df214  lea     rax, aSettingsmanage_2; "SettingsManager_TenantEndpointUnregiste"...
0x1801df21b  mov     [rsp+628h+hKey], rax
0x1801df220  mov     [rsp+628h+hKey+8], 2Ch ; ','
0x1801df229  mov     r8d, 1000000h
0x1801df22f  mov     [rsp+628h+var_5F8], 0
0x1801df234  mov     byte ptr [rsp+628h+var_600], 0
0x1801df239  mov     byte ptr [rsp+628h+var_608], 0
0x1801df23e  mov     r9, 400000000000h
0x1801df248  lea     rdx, [rsp+628h+hKey]
0x1801df24d  lea     rcx, [rsp+628h+var_4F8]
0x1801df255  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x1801df25a  nop
0x1801df25b  lea     rax, aEndpoint_1; "Endpoint"
0x1801df262  mov     [rsp+628h+hKey], rax
0x1801df267  mov     [rsp+628h+hKey+8], 8
0x1801df270  mov     r9, rsi
0x1801df273  lea     r8, [rsp+628h+hKey]
0x1801df278  lea     rdx, [rsp+628h+var_90]; int
0x1801df280  lea     rcx, [rsp+628h+var_4F8]; int
0x1801df288  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x1801df28d  mov     dword ptr [rsp+628h+hKey], ebx
0x1801df291  lea     rax, aReason; "Reason"
0x1801df298  mov     qword ptr [rsp+628h+var_5D8], rax
0x1801df29d  mov     qword ptr [rsp+628h+var_5D8+8], 6
0x1801df2a6  lea     r9, [rsp+628h+hKey]
0x1801df2ab  lea     r8, [rsp+628h+var_5D8]
0x1801df2b0  lea     rdx, [rsp+628h+var_90]
0x1801df2b8  lea     rcx, [rsp+628h+var_4F8]
0x1801df2c0  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x1801df2c5  xorps   xmm0, xmm0
0x1801df2c8  movdqa  [rsp+628h+var_5D8], xmm0
0x1801df2ce  lea     rdx, [rsp+628h+var_5D8]
0x1801df2d3  lea     rcx, [rsp+628h+hKey]
0x1801df2d8  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x1801df2dd  mov     edx, [rax]
0x1801df2df  lea     rcx, [rsp+628h+var_4F8]; this
0x1801df2e7  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x1801df2ec  nop
0x1801df2ed  lea     rcx, [rsp+628h+var_4F8]; this
0x1801df2f5  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1801df2fa  mov     bl, [rsp+628h+var_5E8]
0x1801df2fe  test    bl, bl
0x1801df300  jnz     loc_1801DF428
0x1801df306  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801df30a  mov     r8, [rsp+628h+var_5B0]
0x1801df30f  lea     rdx, [rsp+628h+var_5D8]
0x1801df314  mov     rcx, rsi
0x1801df317  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801df31c  mov     rdx, rax
0x1801df31f  lea     rcx, [rsp+628h+lpValueName]
0x1801df327  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1801df32c  nop
0x1801df32d  lea     rdx, [r12+0E8h]
0x1801df335  lea     rcx, [rsp+628h+var_5B0]
0x1801df33a  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801df33f  lea     r8, [rsp+628h+lpValueName]
0x1801df347  lea     rdx, [rsp+628h+var_5A0]
0x1801df34f  lea     rcx, [r12+38h]
0x1801df354  call    ??$_Eqrange@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x1801df359  movups  xmm0, xmmword ptr [rax]
0x1801df35c  movdqu  [rsp+628h+var_5D8], xmm0
0x1801df362  lea     rdx, [rsp+628h+var_5D8]
0x1801df367  lea     rcx, [r12+38h]
0x1801df36c  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *> *,std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *> *>)
0x1801df371  lea     rcx, [rsp+628h+var_5B0]
0x1801df376  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801df37b  mov     [rsp+628h+hKey], 0
0x1801df384  movups  xmm0, xmmword ptr cs:off_18036A690; "%DiagtrackRegistryRoot%\\TelemetryNames"...
0x1801df38b  movdqu  [rsp+628h+var_5D8], xmm0
0x1801df391  mov     [rsp+628h+var_600], 0; DWORD
0x1801df399  mov     [rsp+628h+var_608], 0F003Fh; unsigned int
0x1801df3a1  xor     r9d, r9d
0x1801df3a4  lea     r8, [rsp+628h+hKey]
0x1801df3a9  lea     rdx, [rsp+628h+var_5D8]
0x1801df3ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801df3b5  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1801df3ba  test    eax, eax
0x1801df3bc  js      short loc_1801DF40C
0x1801df3be  mov     rcx, [rsp+628h+hKey]; hKey
0x1801df3c3  test    rcx, rcx
0x1801df3c6  jz      short loc_1801DF40C
0x1801df3c8  lea     rdx, [rsp+628h+lpValueName]
0x1801df3d0  cmp     [rsp+628h+var_558], 7
0x1801df3d9  cmova   rdx, [rsp+628h+lpValueName]; lpValueName
0x1801df3e2  call    cs:__imp_RegDeleteValueW
0x1801df3e8  test    eax, 0FFFFFFFDh
0x1801df3ed  jz      short loc_1801DF40C
0x1801df3ef  mov     rcx, [rsp+628h]; this
0x1801df3f7  mov     r9d, eax; char *
0x1801df3fa  lea     r8, aOnecoreBaseTel_83; "onecore\\base\\telemetry\\utc\\service"...
0x1801df401  mov     edx, 0F75h; void *
0x1801df406  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1801df40b  nop
0x1801df40c  lea     rcx, [rsp+628h+hKey]
0x1801df411  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801df416  nop
0x1801df417  lea     rcx, [rsp+628h+lpValueName]
0x1801df41f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801df424  mov     bl, [rsp+628h+var_5E8]
0x1801df428  mov     [rsp+628h+var_5B8], 0
0x1801df431  movups  xmm0, xmmword ptr cs:off_18036A1A0; "%DiagtrackRegistryRoot%\\SettingsReques"...
0x1801df438  movdqu  [rsp+628h+var_5D8], xmm0
0x1801df43e  mov     [rsp+628h+var_600], 0; DWORD
0x1801df446  mov     [rsp+628h+var_608], 0F003Fh; unsigned int
0x1801df44e  xor     r9d, r9d
0x1801df451  lea     r8, [rsp+628h+var_5B8]
0x1801df456  lea     rdx, [rsp+628h+var_5D8]
0x1801df45b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801df462  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1801df467  test    eax, eax
0x1801df469  js      short loc_1801DF4B8
0x1801df46b  mov     rcx, [rsp+628h+var_5B8]; hKey
0x1801df470  test    rcx, rcx
0x1801df473  jz      short loc_1801DF4B8
0x1801df475  lea     rdx, [rsp+628h+lpSubKey]
0x1801df47d  cmp     [rsp+628h+var_578], 7
0x1801df486  cmova   rdx, [rsp+628h+lpSubKey]; lpSubKey
0x1801df48f  call    cs:__imp_RegDeleteKeyW
0x1801df495  test    eax, 0FFFFFFFDh
0x1801df49a  jz      short loc_1801DF4B8
0x1801df49c  mov     rcx, [rsp+628h]; this
0x1801df4a4  mov     r9d, eax; char *
0x1801df4a7  lea     r8, aOnecoreBaseTel_83; "onecore\\base\\telemetry\\utc\\service"...
0x1801df4ae  mov     edx, 0F82h; void *
0x1801df4b3  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1801df4b8  lea     rax, off_1803703E8; "%DiagtrackStorageRoot%\\DownloadedSetti"...
0x1801df4bf  lea     rdx, off_1803703D8; "%DiagtrackStorageRoot%\\DownloadedScena"...
0x1801df4c6  test    bl, bl
0x1801df4c8  cmovz   rdx, rax
0x1801df4cc  lea     rcx, [rsp+628h+Src]
0x1801df4d4  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1801df4d9  nop
0x1801df4da  xor     r8d, r8d
0x1801df4dd  mov     dl, 1
0x1801df4df  lea     rcx, [rsp+628h+Src]; lpSrc
0x1801df4e7  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801df4ec  lea     rcx, [rsp+628h+lpFileName]; this
0x1801df4f4  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x1801df4f9  nop
0x1801df4fa  lea     rdx, [rsp+628h+var_5A0]
0x1801df502  lea     rcx, [rsp+628h+Src]
0x1801df50a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801df50f  movups  xmm0, xmmword ptr [rax]
0x1801df512  movdqu  [rsp+628h+var_5D8], xmm0
0x1801df518  lea     rdx, [rsp+628h+var_5D8]
0x1801df51d  lea     rcx, [rsp+628h+lpFileName]; Src
0x1801df525  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801df52a  lea     rdx, asc_18039BCF0; "\\"
0x1801df531  mov     rcx, rax; Src
0x1801df534  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801df539  movups  xmm0, xmmword ptr [rsi]
0x1801df53c  movdqu  [rsp+628h+var_5D8], xmm0
0x1801df542  lea     rdx, [rsp+628h+var_5D8]
0x1801df547  mov     rcx, rax; Src
0x1801df54a  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801df54f  lea     rcx, aJson_0; ".json"
0x1801df556  lea     rdx, aXml; ".xml"
0x1801df55d  test    bl, bl
0x1801df55f  cmovz   rdx, rcx
0x1801df563  mov     rcx, rax; Src
0x1801df566  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801df56b  lea     rcx, [rsp+628h+lpFileName]
  ... truncated ...
```
