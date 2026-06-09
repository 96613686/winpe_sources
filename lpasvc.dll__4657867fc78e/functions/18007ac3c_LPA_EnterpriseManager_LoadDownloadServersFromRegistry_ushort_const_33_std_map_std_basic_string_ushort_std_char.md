# LPA::EnterpriseManager::LoadDownloadServersFromRegistry(ushort const (*)[33],std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer,std::default_delete<LPA::EnterpriseManager::ConfiguredDownloadServer>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer,std::default_delete<LPA::EnterpriseManager::ConfiguredDownloadServer>>>>> &)

- ea: `0x18007ac3c`
- end: `0x18007b43e`
- name: `?LoadDownloadServersFromRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@@Z`
- size: `2050`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `4`
- callee_count: `25`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078930`
- `0x180078f20`
- `0x180079620`
- `0x18007a670`

## callees

- `0x1800017c8`
- `0x18000199c`
- `0x18000df90`
- `0x18000e46c`
- `0x180071344`
- `0x180071650`
- `0x180074270`
- `0x18007430c`
- `0x1800743c4`
- `0x1800753a0`
- `0x180075ad0`
- `0x180076200`
- `0x180076a3c`
- `0x180076a90`
- `0x180079550`
- `0x180079b84`
- `0x18007a320`
- `0x18007a4d8`
- `0x18007a878`
- `0x18007ac3c`
- `0x180080dc0`
- `0x180080dfc`
- `0x180080f38`
- `0x180081104`
- `0x180081154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007b08b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007b08b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007aeda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007aeda`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007af58`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007af58`

## string_xrefs

- `0x18007afa5`: `LpaServiceEnterpriseManager`
- `0x18007b001`: `LpaServiceEnterpriseManager`
- `0x18007af99`: `LPA::EnterpriseManager::LoadDownloadServersFromRegistry`
- `0x18007affa`: `LPA::EnterpriseManager::LoadDownloadServersFromRegistry`
- `0x18007b1ea`: `DownloadsAttempted`
- `0x18007b1ca`: `MaximumAttempts`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall LPA::EnterpriseManager::LoadDownloadServersFromRegistry(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // edi
  int v5; // ebx
  __int64 *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rbx
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  signed int StringFromRegistry; // ebx
  char IsEnabled; // al
  HKEY v13; // rcx
  LSTATUS v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  DWORD i; // r14d
  WCHAR *v19; // rax
  HKEY v20; // rcx
  LSTATUS v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rax
  const WCHAR *v26; // rax
  unsigned int *v27; // r9
  const WCHAR *v28; // rax
  unsigned int *v29; // r9
  const WCHAR *v30; // rbx
  unsigned int *v31; // r9
  unsigned int *v32; // r9
  const unsigned __int16 *v33; // rdx
  unsigned __int64 *v34; // r9
  unsigned int *v35; // r9
  int v36; // esi
  const WCHAR *v37; // rax
  unsigned int *v38; // r9
  const WCHAR *v39; // rax
  bool v40; // r15
  int v41; // r8d
  __int64 v42; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-1B8h]
  int v45; // [rsp+60h] [rbp-178h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-174h] BYREF
  BYTE v47[4]; // [rsp+68h] [rbp-170h] BYREF
  BYTE v48[4]; // [rsp+6Ch] [rbp-16Ch] BYREF
  BYTE v49[8]; // [rsp+70h] [rbp-168h] BYREF
  const char *v50; // [rsp+78h] [rbp-160h] BYREF
  BYTE v51[4]; // [rsp+80h] [rbp-158h] BYREF
  DWORD cSubKeys; // [rsp+84h] [rbp-154h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+88h] [rbp-150h] BYREF
  BYTE v54[4]; // [rsp+8Ch] [rbp-14Ch] BYREF
  unsigned __int16 v55[4]; // [rsp+90h] [rbp-148h] BYREF
  BYTE Data[4]; // [rsp+98h] [rbp-140h] BYREF
  int v57; // [rsp+9Ch] [rbp-13Ch]
  HKEY v58; // [rsp+A0h] [rbp-138h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-130h] BYREF
  const char *v60; // [rsp+B0h] [rbp-128h] BYREF
  __int64 v61; // [rsp+B8h] [rbp-120h]
  _BYTE v62[16]; // [rsp+C0h] [rbp-118h] BYREF
  int v63[4]; // [rsp+D0h] [rbp-108h] BYREF
  __int64 v64; // [rsp+E0h] [rbp-F8h]
  __int64 v65; // [rsp+E8h] [rbp-F0h]
  __int64 v66[2]; // [rsp+F0h] [rbp-E8h] BYREF
  __int64 v67; // [rsp+100h] [rbp-D8h]
  __int64 v68; // [rsp+108h] [rbp-D0h]
  __int64 v69[2]; // [rsp+110h] [rbp-C8h] BYREF
  __int64 v70; // [rsp+120h] [rbp-B8h]
  __int64 v71; // [rsp+128h] [rbp-B0h]
  __int128 v72; // [rsp+130h] [rbp-A8h] BYREF
  __int64 v73; // [rsp+140h] [rbp-98h]
  __int64 v74; // [rsp+148h] [rbp-90h]
  _BYTE v75[32]; // [rsp+150h] [rbp-88h] BYREF
  _QWORD v76[4]; // [rsp+170h] [rbp-68h] BYREF

  v61 = a3;
  v4 = a2;
  v5 = a1;
  v57 = 0;
  hKey = 0;
  v58 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v72 = 0;
  v73 = 0;
  v74 = 7;
  LOWORD(v72) = 0;
  *(_DWORD *)Data = 0;
  LOBYTE(v45) = 0;
  *(_OWORD *)v63 = 0;
  v64 = 0;
  v65 = 7;
  LOWORD(v63[0]) = 0;
  *(_DWORD *)v47 = 0;
  *(_DWORD *)v51 = 0;
  *(_DWORD *)v49 = 0;
  *(_DWORD *)v48 = 0;
  *(_QWORD *)v55 = 0;
  *(_OWORD *)v66 = 0;
  v67 = 0;
  v68 = 7;
  LOWORD(v66[0]) = 0;
  cchName = 0;
  *(_OWORD *)v69 = 0;
  v70 = 0;
  v71 = 7;
  LOWORD(v69[0]) = 0;
  LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(a1, a2, &v72);
  if ( (int)LPA::EnterpriseManager::LoadDownloadServerFromRegistry(
              v5,
              v4,
              (int)v63,
              (int)&v45,
              (__int64)v47,
              v51,
              v49,
              v48,
              v55,
              (__int64)v66,
              (__int64)&cchName,
              (__int64)v69) >= 0 )
  {
    v6 = (__int64 *)std::make_unique<LPA::EnterpriseManager::ConfiguredDownloadServer,std::wstring &,bool &,enum LPAENTERPRISEDISCOVERYSTATE &,unsigned long &,unsigned long &,unsigned long &,unsigned __int64 &,std::wstring &,enum LPAERROR &,std::wstring &,0>(
                      (unsigned int)&v50,
                      (unsigned int)v63,
                      (unsigned int)&v45,
                      (unsigned int)v47,
                      (__int64)v51,
                      (__int64)v49,
                      (__int64)v48,
                      (__int64)v55,
                      (__int64)v66,
                      (__int64)&cchName,
                      (__int64)v69);
    v7 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>::_Try_emplace<std::wstring const &,>(
           a3,
           v76,
           v63);
    std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>::operator=<std::default_delete<LPA::EnterpriseManager::ConfiguredDownloadServer>,0>(
      (__int64 *)(*(_QWORD *)v7 + 64LL),
      v6);
    std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>::~unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>(&v50);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::GetImpl'::`2'::impl) )
  {
    v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v58);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v72);
    phkResult = (PHKEY)v8;
  }
  else
  {
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v72);
    phkResult = &hKey;
  }
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, phkResult);
  StringFromRegistry = v10;
  if ( v10 > 0 )
    StringFromRegistry = (unsigned __int16)v10 | 0x80070000;
  if ( StringFromRegistry >= 0 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::GetImpl'::`2'::impl);
    v13 = v58;
    if ( !IsEnabled )
      v13 = hKey;
    v14 = RegQueryInfoKeyW(v13, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    StringFromRegistry = v14;
    if ( v14 > 0 )
      StringFromRegistry = (unsigned __int16)v14 | 0x80070000;
    if ( StringFromRegistry >= 0 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        *(_DWORD *)v54 = StringFromRegistry;
        *(_DWORD *)v47 = cSubKeys;
        cchName = cbMaxSubKeyLen;
        v50 = "LPA::EnterpriseManager::LoadDownloadServersFromRegistry";
        v60 = "LpaServiceEnterpriseManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v15,
          (unsigned int)byte_18012B9B3,
          v16,
          v17,
          (__int64)&v60,
          (__int64)&v50,
          (__int64)&cchName,
          (__int64)v47,
          (__int64)v54);
      }
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = cbMaxSubKeyLen + 1;
        std::wstring::resize(v63, cbMaxSubKeyLen + 1, 0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::GetImpl'::`2'::impl) )
        {
          v19 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
          v20 = v58;
        }
        else
        {
          v19 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
          v20 = hKey;
        }
        v21 = RegEnumKeyExW(v20, i, v19, &cchName, 0, 0, 0, 0);
        StringFromRegistry = v21;
        if ( v21 > 0 )
          StringFromRegistry = (unsigned __int16)v21 | 0x80070000;
        if ( StringFromRegistry >= 0 )
        {
          std::wstring::resize(v63, cchName, 0);
          v25 = std::operator+<unsigned short>(v76, &v72, L"\\");
          std::operator+<unsigned short>(v75, v25, v63);
          std::wstring::_Tidy_deallocate(v76);
          v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
          CommonUtil::GetDwordFromRegistry(v26, L"Enable", Data, v27);
          *(_DWORD *)v47 = 0;
          v28 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
          CommonUtil::GetDwordFromRegistry(v28, L"State", v47, v29);
          LODWORD(v50) = *(_DWORD *)v47;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl) )
          {
            v30 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
            if ( (int)CommonUtil::GetDwordFromRegistry(v30, L"MaximumAttempts", v49, v31) < 0 )
              *(_DWORD *)v49 = 3;
            if ( (int)CommonUtil::GetDwordFromRegistry(v30, L"DownloadsAttempted", v48, v32) < 0 )
              *(_DWORD *)v48 = 0;
            if ( (int)CommonUtil::GetQuadFromRegistry(v30, v33, v55, v34) < 0 )
              *(_QWORD *)v55 = 0;
            if ( (int)CommonUtil::GetStringFromRegistry(v30, L"ProfileId") < 0 )
              std::wstring::assign(v66, &qword_1801130E8);
            *(_DWORD *)v54 = 0;
            v36 = 0;
            if ( (int)CommonUtil::GetDwordFromRegistry(v30, L"ErrorDetail", v54, v35) >= 0 )
              v36 = *(_DWORD *)v54;
            *(_DWORD *)v51 = 0;
          }
          else
          {
            v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
            CommonUtil::GetDwordFromRegistry(v37, L"RetriesLeft", v51, v38);
            *(_DWORD *)v49 = 0;
            *(_DWORD *)v48 = 0;
            *(_QWORD *)v55 = 0;
            std::wstring::assign(v66, &qword_1801130E8);
            v36 = 0;
          }
          v39 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
          StringFromRegistry = CommonUtil::GetStringFromRegistry(v39, L"AccountId");
          v40 = *(_DWORD *)Data != 0;
          v76[0] = operator new(0x88u);
          LOBYTE(v41) = v40;
          v50 = (const char *)LPA::EnterpriseManager::ConfiguredDownloadServer::ConfiguredDownloadServer(
                                v76[0],
                                (unsigned int)v63,
                                v41,
                                (_DWORD)v50,
                                *(_DWORD *)v51,
                                *(_DWORD *)v49,
                                *(_DWORD *)v48,
                                *(__int64 *)v55,
                                (__int64)v66,
                                v36,
                                (__int64)v69);
          v57 |= 1u;
          v42 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>::_Try_emplace<std::wstring const &,>(
                  v61,
                  v62,
                  v63);
          std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>::operator=<std::default_delete<LPA::EnterpriseManager::ConfiguredDownloadServer>,0>(
            (__int64 *)(*(_QWORD *)v42 + 64LL),
            (__int64 *)&v50);
          std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>::~unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>(&v50);
          std::wstring::_Tidy_deallocate(v75);
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v50) = StringFromRegistry;
          v60 = "LPA::EnterpriseManager::LoadDownloadServersFromRegistry";
          v76[0] = "LpaServiceEnterpriseManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)word_18012B952,
            v23,
            v24,
            (__int64)v76,
            (__int64)&v60,
            (__int64)&v50);
        }
      }
    }
  }
  std::wstring::_Tidy_deallocate(v69);
  std::wstring::_Tidy_deallocate(v66);
  std::wstring::_Tidy_deallocate(v63);
  std::wstring::_Tidy_deallocate(&v72);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
  return (unsigned int)StringFromRegistry;
}

```

## disassembly

```asm
0x18007ac3c  mov     r11, rsp
0x18007ac3f  push    rbx
0x18007ac40  push    rsi
0x18007ac41  push    rdi
0x18007ac42  push    r12
0x18007ac44  push    r13
0x18007ac46  push    r14
0x18007ac48  push    r15
0x18007ac4a  sub     rsp, 1A0h
0x18007ac51  mov     rax, cs:__security_cookie
0x18007ac58  xor     rax, rsp
0x18007ac5b  mov     [rsp+1D8h+var_48], rax
0x18007ac63  mov     rsi, r8
0x18007ac66  mov     [rsp+1D8h+var_120], r8
0x18007ac6e  mov     rdi, rdx
0x18007ac71  mov     rbx, rcx
0x18007ac74  xor     r15d, r15d
0x18007ac77  mov     [rsp+1D8h+var_13C], r15d
0x18007ac7f  mov     [r11-130h], r15
0x18007ac86  mov     [r11-138h], r15
0x18007ac8d  mov     [r11-154h], r15d
0x18007ac94  mov     [r11-150h], r15d
0x18007ac9b  xorps   xmm0, xmm0
0x18007ac9e  movups  [rsp+1D8h+var_A8], xmm0
0x18007aca6  mov     [r11-98h], r15
0x18007acad  lea     ecx, [r15+7]
0x18007acb1  mov     [r11-90h], rcx
0x18007acb8  mov     [r11-0A8h], r15w
0x18007acc0  mov     [r11-140h], r15d
0x18007acc7  mov     byte ptr [rsp+1D8h+var_178], r15b
0x18007accc  movups  xmmword ptr [rsp+1D8h+var_108], xmm0
0x18007acd4  mov     [r11-0F8h], r15
0x18007acdb  mov     [r11-0F0h], rcx
0x18007ace2  mov     [r11-108h], r15w
0x18007acea  mov     dword ptr [rsp+1D8h+var_170], r15d
0x18007acef  mov     [r11-158h], r15d
0x18007acf6  mov     dword ptr [rsp+1D8h+var_168], r15d
0x18007acfb  mov     dword ptr [rsp+1D8h+var_16C], r15d
0x18007ad00  mov     [r11-148h], r15
0x18007ad07  movups  xmmword ptr [rsp+1D8h+var_E8], xmm0
0x18007ad0f  mov     [r11-0D8h], r15
0x18007ad16  mov     [r11-0D0h], rcx
0x18007ad1d  mov     [r11-0E8h], r15w
0x18007ad25  mov     [rsp+1D8h+cchName], r15d
0x18007ad2a  movups  xmmword ptr [rsp+1D8h+var_C8], xmm0
0x18007ad32  mov     [r11-0B8h], r15
0x18007ad39  mov     [r11-0B0h], rcx
0x18007ad40  mov     [r11-0C8h], r15w
0x18007ad48  lea     r8, [r11-0A8h]
0x18007ad4f  mov     rcx, rbx
0x18007ad52  call    ?GetEnterpriseSettingsEuiccsDownloadServerKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(ushort const (&)[33],std::wstring &)
0x18007ad57  lea     rax, [rsp+1D8h+var_C8]
0x18007ad5f  mov     [rsp+1D8h+lpftLastWriteTime], rax; __int64
0x18007ad64  lea     rax, [rsp+1D8h+cchName]
0x18007ad69  mov     [rsp+1D8h+lpcbSecurityDescriptor], rax; __int64
0x18007ad6e  lea     rax, [rsp+1D8h+var_E8]
0x18007ad76  mov     [rsp+1D8h+lpcbMaxValueLen], rax; __int64
0x18007ad7b  lea     rax, [rsp+1D8h+var_148]
0x18007ad83  mov     [rsp+1D8h+lpcbMaxValueNameLen], rax; unsigned __int16 *
0x18007ad88  lea     rax, [rsp+1D8h+var_16C]
0x18007ad8d  mov     [rsp+1D8h+lpcValues], rax; LPBYTE
0x18007ad92  lea     rax, [rsp+1D8h+var_168]
0x18007ad97  mov     [rsp+1D8h+lpcbMaxClassLen], rax; lpData
0x18007ad9c  lea     rax, [rsp+1D8h+var_158]
0x18007ada4  mov     [rsp+1D8h+lpcbMaxSubKeyLen], rax; LPBYTE
0x18007ada9  lea     rax, [rsp+1D8h+var_170]
0x18007adae  mov     [rsp+1D8h+phkResult], rax; __int64
0x18007adb3  lea     r9, [rsp+1D8h+var_178]; int
0x18007adb8  lea     r8, [rsp+1D8h+var_108]; int
0x18007adc0  mov     rdx, rdi; int
0x18007adc3  mov     rcx, rbx; int
0x18007adc6  call    ?LoadDownloadServerFromRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAW4LPAENTERPRISEDISCOVERYSTATE@@AEAK44AEA_K1AEAW4LPAERROR@@1@Z; LPA::EnterpriseManager::LoadDownloadServerFromRegistry(ushort const (*)[33],std::wstring &,bool &,LPAENTERPRISEDISCOVERYSTATE &,ulong &,ulong &,ulong &,unsigned __int64 &,std::wstring &,LPAERROR &,std::wstring &)
0x18007adcb  test    eax, eax
0x18007adcd  js      loc_18007AE76
0x18007add3  lea     rax, [rsp+1D8h+var_C8]
0x18007addb  mov     [rsp+1D8h+lpcbSecurityDescriptor], rax
0x18007ade0  lea     rax, [rsp+1D8h+cchName]
0x18007ade5  mov     [rsp+1D8h+lpcbMaxValueLen], rax
0x18007adea  lea     rax, [rsp+1D8h+var_E8]
0x18007adf2  mov     [rsp+1D8h+lpcbMaxValueNameLen], rax
0x18007adf7  lea     rax, [rsp+1D8h+var_148]
0x18007adff  mov     [rsp+1D8h+lpcValues], rax
0x18007ae04  lea     rax, [rsp+1D8h+var_16C]
0x18007ae09  mov     [rsp+1D8h+lpcbMaxClassLen], rax
0x18007ae0e  lea     rax, [rsp+1D8h+var_168]
0x18007ae13  mov     [rsp+1D8h+lpcbMaxSubKeyLen], rax
0x18007ae18  lea     rax, [rsp+1D8h+var_158]
0x18007ae20  mov     [rsp+1D8h+phkResult], rax
0x18007ae25  lea     r9, [rsp+1D8h+var_170]
0x18007ae2a  lea     r8, [rsp+1D8h+var_178]
0x18007ae2f  lea     rdx, [rsp+1D8h+var_108]
0x18007ae37  lea     rcx, [rsp+1D8h+var_160]
0x18007ae3c  call    ??$make_unique@VConfiguredDownloadServer@EnterpriseManager@LPA@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAW4LPAENTERPRISEDISCOVERYSTATE@@AEAKAEAKAEAKAEA_KAEAV45@AEAW4LPAERROR@@AEAV45@$0A@@std@@YA?AV?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEA_NAEAW4LPAENTERPRISEDISCOVERYSTATE@@AEAK33AEA_K0AEAW4LPAERROR@@0@Z; std::make_unique<LPA::EnterpriseManager::ConfiguredDownloadServer,std::wstring &,bool &,LPAENTERPRISEDISCOVERYSTATE &,ulong &,ulong &,ulong &,unsigned __int64 &,std::wstring &,LPAERROR &,std::wstring &,0>(std::wstring &,bool &,LPAENTERPRISEDISCOVERYSTATE &,ulong &,ulong &,ulong &,unsigned __int64 &,std::wstring &,LPAERROR &,std::wstring &)
0x18007ae41  mov     rbx, rax
0x18007ae44  lea     r8, [rsp+1D8h+var_108]
0x18007ae4c  lea     rdx, [rsp+1D8h+var_68]
0x18007ae54  mov     rcx, rsi
0x18007ae57  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18007ae5c  mov     rcx, [rax]
0x18007ae5f  add     rcx, 40h ; '@'
0x18007ae63  mov     rdx, rbx
0x18007ae66  call    ??$?4U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>::operator=<std::default_delete<LPA::EnterpriseManager::ConfiguredDownloadServer>,0>(std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer> &&)
0x18007ae6b  nop
0x18007ae6c  lea     rcx, [rsp+1D8h+var_160]
0x18007ae71  call    ??1?$unique_ptr@VConfiguredDownloadServer@EnterpriseManager@LPA@@U?$default_delete@VConfiguredDownloadServer@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>::~unique_ptr<LPA::EnterpriseManager::ConfiguredDownloadServer>(void)
0x18007ae76  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY> `wil::Feature<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::GetImpl(void)'::`2'::impl
0x18007ae7d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::__private_IsEnabled(void)
0x18007ae82  test    al, al
0x18007ae84  jz      short loc_18007AEAD
0x18007ae86  lea     rcx, [rsp+1D8h+var_138]
0x18007ae8e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18007ae93  mov     rbx, rax
0x18007ae96  lea     rcx, [rsp+1D8h+var_A8]
0x18007ae9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007aea3  mov     rdx, rax
0x18007aea6  mov     [rsp+1D8h+phkResult], rbx
0x18007aeab  jmp     short loc_18007AECA
0x18007aead  lea     rcx, [rsp+1D8h+var_A8]
0x18007aeb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007aeba  mov     rdx, rax; lpSubKey
0x18007aebd  lea     rax, [rsp+1D8h+hKey]
0x18007aec5  mov     [rsp+1D8h+phkResult], rax; phkResult
0x18007aeca  mov     r9d, 20019h; samDesired
0x18007aed0  xor     r8d, r8d; ulOptions
0x18007aed3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007aeda  call    cs:__imp_RegOpenKeyExW
0x18007aee0  test    eax, eax
0x18007aee2  mov     edi, 80070000h
0x18007aee7  mov     ebx, eax
0x18007aee9  jle     short loc_18007AEF0
0x18007aeeb  movzx   ebx, ax
0x18007aeee  or      ebx, edi
0x18007aef0  test    ebx, ebx
0x18007aef2  js      loc_18007B3CD
0x18007aef8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY> `wil::Feature<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::GetImpl(void)'::`2'::impl
0x18007aeff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::__private_IsEnabled(void)
0x18007af04  mov     [rsp+1D8h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18007af09  xor     r9d, r9d; lpReserved
0x18007af0c  xor     r8d, r8d; lpcchClass
0x18007af0f  xor     edx, edx; lpClass
0x18007af11  mov     [rsp+1D8h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18007af16  mov     [rsp+1D8h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18007af1b  mov     [rsp+1D8h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18007af20  mov     [rsp+1D8h+lpcValues], r15; lpcValues
0x18007af25  mov     [rsp+1D8h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18007af2a  test    al, al
0x18007af2c  lea     rax, [rsp+1D8h+cbMaxSubKeyLen]
0x18007af34  mov     [rsp+1D8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18007af39  lea     rax, [rsp+1D8h+cSubKeys]
0x18007af41  mov     [rsp+1D8h+phkResult], rax; lpcSubKeys
0x18007af46  mov     rcx, [rsp+1D8h+var_138]
0x18007af4e  jnz     short loc_18007AF58
0x18007af50  mov     rcx, [rsp+1D8h+hKey]; hKey
0x18007af58  call    cs:__imp_RegQueryInfoKeyW
0x18007af5e  test    eax, eax
0x18007af60  mov     ebx, eax
0x18007af62  jle     short loc_18007AF69
0x18007af64  movzx   ebx, ax
0x18007af67  or      ebx, edi
0x18007af69  test    ebx, ebx
0x18007af6b  js      loc_18007B3CD
0x18007af71  mov     eax, cs:CallbackContext
0x18007af77  cmp     eax, 4
0x18007af7a  jbe     short loc_18007AFFA
0x18007af7c  mov     dword ptr [rsp+1D8h+var_14C], ebx
0x18007af83  mov     eax, [rsp+1D8h+cSubKeys]
0x18007af8a  mov     dword ptr [rsp+1D8h+var_170], eax
0x18007af8e  mov     eax, [rsp+1D8h+cbMaxSubKeyLen]
0x18007af95  mov     [rsp+1D8h+cchName], eax
0x18007af99  lea     r12, aLpaEnterprisem_5; "LPA::EnterpriseManager::LoadDownloadSer"...
0x18007afa0  mov     [rsp+1D8h+var_160], r12
0x18007afa5  lea     r13, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007afac  mov     [rsp+1D8h+var_128], r13
0x18007afb4  lea     rax, [rsp+1D8h+var_14C]
0x18007afbc  mov     [rsp+1D8h+lpcbMaxValueNameLen], rax
0x18007afc1  lea     rax, [rsp+1D8h+var_170]
0x18007afc6  mov     [rsp+1D8h+lpcValues], rax
0x18007afcb  lea     rax, [rsp+1D8h+cchName]
0x18007afd0  mov     [rsp+1D8h+lpcbMaxClassLen], rax
0x18007afd5  lea     rax, [rsp+1D8h+var_160]
0x18007afda  mov     [rsp+1D8h+lpcbMaxSubKeyLen], rax
0x18007afdf  lea     rax, [rsp+1D8h+var_128]
0x18007afe7  mov     [rsp+1D8h+phkResult], rax
0x18007afec  lea     rdx, byte_18012B9B3
0x18007aff3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007aff8  jmp     short loc_18007B008
0x18007affa  lea     r12, aLpaEnterprisem_5; "LPA::EnterpriseManager::LoadDownloadSer"...
0x18007b001  lea     r13, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007b008  mov     r14d, r15d
0x18007b00b  cmp     r14d, [rsp+1D8h+cSubKeys]
0x18007b013  jnb     loc_18007B3CD
0x18007b019  mov     eax, [rsp+1D8h+cbMaxSubKeyLen]
0x18007b020  inc     eax
0x18007b022  mov     [rsp+1D8h+cchName], eax
0x18007b026  xor     r8d, r8d
0x18007b029  mov     edx, eax
0x18007b02b  lea     rcx, [rsp+1D8h+var_108]
0x18007b033  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007b038  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY> `wil::Feature<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::GetImpl(void)'::`2'::impl
0x18007b03f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ENTERPRISE_MANAGER_CLOSEKEY>::__private_IsEnabled(void)
0x18007b044  lea     rcx, [rsp+1D8h+var_108]
0x18007b04c  test    al, al
0x18007b04e  jz      short loc_18007B05F
0x18007b050  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b055  mov     rcx, [rsp+1D8h+var_138]
0x18007b05d  jmp     short loc_18007B06C
0x18007b05f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b064  mov     rcx, [rsp+1D8h+hKey]; hKey
0x18007b06c  mov     [rsp+1D8h+lpcValues], r15; lpftLastWriteTime
0x18007b071  mov     [rsp+1D8h+lpcbMaxClassLen], r15; lpcchClass
0x18007b076  mov     [rsp+1D8h+lpcbMaxSubKeyLen], r15; lpClass
0x18007b07b  mov     [rsp+1D8h+phkResult], r15; lpReserved
0x18007b080  lea     r9, [rsp+1D8h+cchName]; lpcchName
0x18007b085  mov     r8, rax; lpName
0x18007b088  mov     edx, r14d; dwIndex
0x18007b08b  call    cs:__imp_RegEnumKeyExW
0x18007b091  test    eax, eax
0x18007b093  mov     ebx, eax
0x18007b095  jle     short loc_18007B09C
0x18007b097  movzx   ebx, ax
0x18007b09a  or      ebx, edi
0x18007b09c  test    ebx, ebx
0x18007b09e  jns     short loc_18007B0F8
0x18007b0a0  mov     eax, cs:CallbackContext
0x18007b0a6  cmp     eax, 2
0x18007b0a9  jbe     loc_18007B3C5
0x18007b0af  mov     dword ptr [rsp+1D8h+var_160], ebx
0x18007b0b3  mov     [rsp+1D8h+var_128], r12
0x18007b0bb  mov     [rsp+1D8h+var_68], r13
0x18007b0c3  lea     rax, [rsp+1D8h+var_160]
0x18007b0c8  mov     [rsp+1D8h+lpcbMaxClassLen], rax
0x18007b0cd  lea     rax, [rsp+1D8h+var_128]
0x18007b0d5  mov     [rsp+1D8h+lpcbMaxSubKeyLen], rax
0x18007b0da  lea     rax, [rsp+1D8h+var_68]
0x18007b0e2  mov     [rsp+1D8h+phkResult], rax
0x18007b0e7  lea     rdx, word_18012B952
0x18007b0ee  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007b0f3  jmp     loc_18007B3C5
0x18007b0f8  xor     r8d, r8d
0x18007b0fb  mov     edx, [rsp+1D8h+cchName]
0x18007b0ff  lea     rcx, [rsp+1D8h+var_108]
0x18007b107  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007b10c  lea     r8, asc_1801118E4; "\\"
0x18007b113  lea     rdx, [rsp+1D8h+var_A8]
0x18007b11b  lea     rcx, [rsp+1D8h+var_68]
0x18007b123  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18007b128  nop
0x18007b129  lea     r8, [rsp+1D8h+var_108]
0x18007b131  mov     rdx, rax
0x18007b134  lea     rcx, [rsp+1D8h+var_88]
0x18007b13c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18007b141  nop
0x18007b142  lea     rcx, [rsp+1D8h+var_68]
0x18007b14a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b14f  lea     rcx, [rsp+1D8h+var_88]
0x18007b157  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b15c  mov     rcx, rax; lpSubKey
0x18007b15f  lea     r8, [rsp+1D8h+Data]; lpData
0x18007b167  lea     rdx, aEnable; "Enable"
0x18007b16e  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007b173  mov     dword ptr [rsp+1D8h+var_170], r15d
0x18007b178  lea     rcx, [rsp+1D8h+var_88]
0x18007b180  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b185  mov     rcx, rax; lpSubKey
0x18007b188  lea     r8, [rsp+1D8h+var_170]; lpData
0x18007b18d  lea     rdx, aState; "State"
0x18007b194  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007b199  mov     eax, dword ptr [rsp+1D8h+var_170]
0x18007b19d  mov     dword ptr [rsp+1D8h+var_160], eax
0x18007b1a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007b1a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007b1ad  lea     rcx, [rsp+1D8h+var_88]
0x18007b1b5  test    al, al
0x18007b1b7  jz      loc_18007B283
0x18007b1bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b1c2  mov     rbx, rax
0x18007b1c5  lea     r8, [rsp+1D8h+var_168]; lpData
0x18007b1ca  lea     rdx, aMaximumattempt; "MaximumAttempts"
0x18007b1d1  mov     rcx, rax; lpSubKey
0x18007b1d4  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007b1d9  test    eax, eax
0x18007b1db  jns     short loc_18007B1E5
0x18007b1dd  mov     dword ptr [rsp+1D8h+var_168], 3
0x18007b1e5  lea     r8, [rsp+1D8h+var_16C]; lpData
0x18007b1ea  lea     rdx, aDownloadsattem; "DownloadsAttempted"
0x18007b1f1  mov     rcx, rbx; lpSubKey
0x18007b1f4  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007b1f9  test    eax, eax
0x18007b1fb  jns     short loc_18007B202
0x18007b1fd  mov     dword ptr [rsp+1D8h+var_16C], r15d
0x18007b202  lea     r8, [rsp+1D8h+var_148]; unsigned __int16 *
0x18007b20a  mov     rcx, rbx; lpSubKey
0x18007b20d  call    ?GetQuadFromRegistry@CommonUtil@@YAJPEBG0AEA_K@Z; CommonUtil::GetQuadFromRegistry(ushort const *,ushort const *,unsigned __int64 &)
0x18007b212  test    eax, eax
0x18007b214  jns     short loc_18007B21E
0x18007b216  mov     qword ptr [rsp+1D8h+var_148], r15
0x18007b21e  lea     r8, [rsp+1D8h+var_E8]
0x18007b226  lea     rdx, aProfileid; "ProfileId"
0x18007b22d  mov     rcx, rbx; lpSubKey
0x18007b230  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
  ... truncated ...
```
