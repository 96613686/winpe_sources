# LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry(ushort const (*)[33],std::list<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT,std::default_delete<LPA_ENTERPRISE_DISCOVERY_EVENT>>,std::allocator<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT,std::default_delete<LPA_ENTERPRISE_DISCOVERY_EVENT>>>> &)

- ea: `0x18007b444`
- end: `0x18007b9fa`
- name: `?LoadEnterpriseDiscoveryServersFromRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAV?$list@V?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@V?$allocator@V?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@@2@@std@@@Z`
- size: `1462`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180079620`

## callees

- `0x1800017c8`
- `0x18000df90`
- `0x18005cd20`
- `0x180071344`
- `0x180071650`
- `0x18007430c`
- `0x1800743c4`
- `0x1800748d0`
- `0x180075a30`
- `0x1800769d8`
- `0x180076a90`
- `0x180076cd0`
- `0x180079550`
- `0x180079b14`
- `0x18007a4d8`
- `0x18007b444`
- `0x180080dfc`
- `0x180081104`
- `0x180081154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007b620`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007b620`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b525`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b525`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007b5a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007b5a1`

## string_xrefs

- `0x18007b700`: `LpaServiceEnterpriseManager`
- `0x18007b792`: `LpaServiceEnterpriseManager`
- `0x18007b87f`: `LpaServiceEnterpriseManager`
- `0x18007b5cd`: `LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry`
- `0x18007b787`: `LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry`
- `0x18007b874`: `LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry`
- `0x18007b99d`: `LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry`
- `0x18007b7d8`: `MaximumAttempts`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __m128i si128; // xmm6
  HKEY *phkResult; // rbx
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  signed int v10; // eax
  bool v11; // cc
  int DwordFromRegistry; // edi
  DWORD v13; // r14d
  WCHAR *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  const unsigned __int16 *v18; // rax
  int v19; // ecx
  int v20; // r8d
  unsigned int *v21; // r9
  const char **v22; // rax
  int *v23; // rdx
  const WCHAR *v24; // rsi
  unsigned int *v25; // r9
  int v26; // eax
  int v27; // ecx
  unsigned int *v28; // r9
  const unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // rax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  const WCHAR *v34; // rax
  unsigned int *v35; // r9
  const char **lpcbMaxSubKeyLen; // [rsp+30h] [rbp-D8h]
  BYTE v38[4]; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD cSubKeys[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v41; // [rsp+78h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+80h] [rbp-88h] BYREF
  BYTE v43[4]; // [rsp+84h] [rbp-84h] BYREF
  BYTE v44[8]; // [rsp+88h] [rbp-80h] BYREF
  const char *v45; // [rsp+90h] [rbp-78h] BYREF
  const char *v46; // [rsp+98h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-68h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+A8h] [rbp-60h] BYREF
  DWORD cbMaxValueLen; // [rsp+ACh] [rbp-5Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+B0h] [rbp-58h] BYREF
  DWORD cValues; // [rsp+B4h] [rbp-54h] BYREF
  DWORD cbMaxClassLen; // [rsp+B8h] [rbp-50h] BYREF
  DWORD cchClass; // [rsp+BCh] [rbp-4Ch] BYREF
  int v54; // [rsp+C0h] [rbp-48h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v56; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-28h]
  __int64 v58; // [rsp+E8h] [rbp-20h]
  _OWORD v59[2]; // [rsp+F0h] [rbp-18h] BYREF
  _OWORD v60[2]; // [rsp+110h] [rbp+8h] BYREF
  _OWORD v61[2]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v62[32]; // [rsp+150h] [rbp+48h] BYREF
  _BYTE v63[40]; // [rsp+170h] [rbp+68h] BYREF
  WCHAR Class[264]; // [rsp+198h] [rbp+90h] BYREF

  v61[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v61[1] = si128;
  LOWORD(v61[0]) = 0;
  LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(a1, L"Enterprise", a2, v61);
  hKey = 0;
  cchClass = 260;
  cSubKeys[1] = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  v56 = 0;
  v57 = 0;
  v58 = 7;
  LOWORD(v56) = 0;
  cSubKeys[0] = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, phkResult);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_37;
  }
  v10 = RegQueryInfoKeyW(
          hKey,
          Class,
          &cchClass,
          0,
          &cSubKeys[1],
          &cbMaxSubKeyLen,
          &cbMaxClassLen,
          &cValues,
          &cbMaxValueNameLen,
          &cbMaxValueLen,
          &cbSecurityDescriptor,
          &ftLastWriteTime);
  v11 = v10 <= 0;
  if ( !v10 )
  {
    DwordFromRegistry = 0;
    v13 = 0;
    if ( !cSubKeys[1] )
    {
LABEL_36:
      v9 = DwordFromRegistry;
      goto LABEL_37;
    }
    while ( 1 )
    {
      std::wstring::resize(&v56, cbMaxSubKeyLen + 1, 0);
      cSubKeys[0] = cbMaxSubKeyLen + 1;
      v14 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
      v10 = RegEnumKeyExW(hKey, v13, v14, cSubKeys, 0, 0, 0, &ftLastWriteTime);
      v11 = v10 <= 0;
      if ( v10 )
        break;
      std::wstring::resize(&v56, cSubKeys[0], 0);
      v59[0] = 0;
      v59[1] = si128;
      LOWORD(v59[0]) = 0;
      v15 = std::operator+<unsigned short>(v63, v61, L"\\");
      v16 = std::operator+<unsigned short>(v62, v15, &v56);
      std::wstring::operator=(v59, v16);
      std::wstring::_Tidy_deallocate(v62);
      std::wstring::_Tidy_deallocate(v63);
      std::make_unique<LPA_ENTERPRISE_DISCOVERY_EVENT,,0>(&v41);
      v17 = v41;
      *(_DWORD *)(v41 + 8) = 1;
      v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56);
      DwordFromRegistry = StringCchCopyW((unsigned __int16 *)(v17 + 78), 0x104u, v18);
      if ( DwordFromRegistry >= 0 )
        DwordFromRegistry = StringCchCopyW((unsigned __int16 *)(v17 + 12), 0x21u, a2);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl) )
      {
        if ( DwordFromRegistry >= 0 )
        {
          *(_DWORD *)v38 = 0;
          v34 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
          DwordFromRegistry = CommonUtil::GetDwordFromRegistry(v34, L"Enable", v38, v35);
          if ( DwordFromRegistry >= 0 )
          {
            *(_DWORD *)(v17 + 4) = *(_DWORD *)v38 != 0;
            *(_WORD *)(v17 + 604) = 0;
            std::list<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>>::_Emplace<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>>(
              (__int64)a3,
              *a3,
              &v41);
          }
        }
LABEL_34:
        std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>::~unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>(&v41);
        std::wstring::_Tidy_deallocate(v59);
        v57 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v56) = 0;
        goto LABEL_35;
      }
      if ( DwordFromRegistry >= 0 )
      {
        v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
        *(_DWORD *)Data = 0;
        DwordFromRegistry = CommonUtil::GetDwordFromRegistry(v24, L"Enable", Data, v25);
        if ( DwordFromRegistry >= 0 )
        {
          *(_DWORD *)(v17 + 4) = *(_DWORD *)Data != 0;
          *(_DWORD *)v43 = 0;
          v26 = CommonUtil::GetDwordFromRegistry(v24, L"MaximumAttempts", v43, v21);
          v27 = 3;
          if ( v26 >= 0 )
            v27 = *(_DWORD *)v43;
          *(_DWORD *)(v17 + 600) = v27;
          v60[0] = 0;
          v60[1] = si128;
          LOWORD(v60[0]) = 0;
          if ( (int)CommonUtil::GetStringFromRegistry(v24, L"ProfileId") >= 0 )
          {
            v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
            if ( StringCchCopyW((unsigned __int16 *)(v17 + 604), 0x15u, v29) < 0 )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
                v54 = StringCchCopyW((unsigned __int16 *)(v17 + 604), 0x15u, v30);
                v46 = "LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry";
                v45 = "LpaServiceEnterpriseManager";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v31,
                  (unsigned int)&unk_18012C858,
                  v32,
                  v33,
                  (__int64)&v45,
                  (__int64)&v46,
                  (__int64)&v54);
              }
              std::wstring::_Tidy_deallocate(v60);
              std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>::~unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>(&v41);
              std::wstring::_Tidy_deallocate(v59);
              goto LABEL_35;
            }
          }
          *(_DWORD *)v44 = 0;
          if ( (int)CommonUtil::GetDwordFromRegistry(v24, L"ErrorDetail", v44, v28) >= 0 )
            *(_DWORD *)(v17 + 648) = *(_DWORD *)v44;
          std::list<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>>::_Emplace<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>>(
            (__int64)a3,
            *a3,
            &v41);
          std::wstring::_Tidy_deallocate(v60);
          goto LABEL_34;
        }
        if ( (unsigned int)CallbackContext > 2 )
        {
          v46 = "LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry";
          v45 = "LpaServiceEnterpriseManager";
          lpcbMaxSubKeyLen = &v46;
          v22 = &v45;
          v23 = &dword_18012C8C4;
          goto LABEL_16;
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v45 = "LPA::EnterpriseManager::LoadEnterpriseDiscoveryServersFromRegistry";
        v46 = "LpaServiceEnterpriseManager";
        lpcbMaxSubKeyLen = &v45;
        v22 = &v46;
        v23 = (int *)&unk_18012C930;
LABEL_16:
        *(_DWORD *)v38 = DwordFromRegistry;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (_DWORD)v23,
          v20,
          (_DWORD)v21,
          (__int64)v22,
          (__int64)lpcbMaxSubKeyLen,
          (__int64)v38);
      }
      std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>::~unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>(&v41);
      std::wstring::_Tidy_deallocate(v59);
LABEL_35:
      if ( ++v13 >= cSubKeys[1] )
        goto LABEL_36;
    }
  }
  if ( !v11 )
    v10 = (unsigned __int16)v10 | 0x80070000;
  v9 = v10;
LABEL_37:
  std::wstring::_Tidy_deallocate(&v56);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v61);
  return v9;
}

```

## disassembly

```asm
0x18007b444  mov     rax, rsp
0x18007b447  mov     [rax+20h], rbx
0x18007b44b  push    rbp
0x18007b44c  push    rsi
0x18007b44d  push    rdi
0x18007b44e  push    r12
0x18007b450  push    r13
0x18007b452  push    r14
0x18007b454  push    r15
0x18007b456  lea     rbp, [rax-2F8h]
0x18007b45d  sub     rsp, 3C0h
0x18007b464  movaps  xmmword ptr [rax-48h], xmm6
0x18007b468  mov     rax, cs:__security_cookie
0x18007b46f  xor     rax, rsp
0x18007b472  mov     [rbp+2F0h+var_50], rax
0x18007b479  mov     r12, r8
0x18007b47c  mov     r13, rdx
0x18007b47f  xorps   xmm0, xmm0
0x18007b482  movups  [rbp+2F0h+var_2C8], xmm0
0x18007b486  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18007b48e  movdqu  [rbp+2F0h+var_2B8], xmm6
0x18007b493  xor     r15d, r15d
0x18007b496  mov     word ptr [rbp+2F0h+var_2C8], r15w
0x18007b49b  lea     r9, [rbp+2F0h+var_2C8]
0x18007b49f  mov     r8, rdx
0x18007b4a2  lea     rdx, aEnterprise; "Enterprise"
0x18007b4a9  call    ?GetEnterpriseSettingsEuiccsDiscoveryServerKey@EnterpriseManager@LPA@@AEAAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(ushort const *,ushort const *,std::wstring &)
0x18007b4ae  mov     [rbp+2F0h+hKey], r15
0x18007b4b2  mov     [rbp+2F0h+cchClass], 104h
0x18007b4b9  mov     [rsp+3F0h+cSubKeys+4], r15d
0x18007b4be  mov     [rsp+3F0h+cbMaxSubKeyLen], r15d
0x18007b4c3  mov     [rbp+2F0h+cbMaxClassLen], r15d
0x18007b4c7  mov     [rbp+2F0h+cValues], r15d
0x18007b4cb  mov     [rbp+2F0h+cbMaxValueNameLen], r15d
0x18007b4cf  mov     [rbp+2F0h+cbMaxValueLen], r15d
0x18007b4d3  mov     [rbp+2F0h+cbSecurityDescriptor], r15d
0x18007b4d7  mov     qword ptr [rbp+2F0h+ftLastWriteTime.dwLowDateTime], r15
0x18007b4db  xorps   xmm0, xmm0
0x18007b4de  movups  [rbp+2F0h+var_328], xmm0
0x18007b4e2  mov     [rbp+2F0h+var_318], r15
0x18007b4e6  mov     [rbp+2F0h+var_310], 7
0x18007b4ee  mov     word ptr [rbp+2F0h+var_328], r15w
0x18007b4f3  mov     [rsp+3F0h+cSubKeys], r15d
0x18007b4f8  lea     rcx, [rbp+2F0h+hKey]
0x18007b4fc  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18007b501  mov     rbx, rax
0x18007b504  lea     rcx, [rbp+2F0h+var_2C8]
0x18007b508  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b50d  mov     rdx, rax; lpSubKey
0x18007b510  mov     [rsp+3F0h+phkResult], rbx; phkResult
0x18007b515  mov     r9d, 20019h; samDesired
0x18007b51b  xor     r8d, r8d; ulOptions
0x18007b51e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007b525  call    cs:__imp_RegOpenKeyExW
0x18007b52b  mov     ebx, eax
0x18007b52d  test    eax, eax
0x18007b52f  jz      short loc_18007B545
0x18007b531  jle     loc_18007B9AC
0x18007b537  movzx   ebx, ax
0x18007b53a  or      ebx, 80070000h
0x18007b540  jmp     loc_18007B9AC
0x18007b545  lea     rax, [rbp+2F0h+ftLastWriteTime]
0x18007b549  mov     [rsp+3F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18007b54e  lea     rax, [rbp+2F0h+cbSecurityDescriptor]
0x18007b552  mov     [rsp+3F0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x18007b557  lea     rax, [rbp+2F0h+cbMaxValueLen]
0x18007b55b  mov     [rsp+3F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18007b560  lea     rax, [rbp+2F0h+cbMaxValueNameLen]
0x18007b564  mov     [rsp+3F0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18007b569  lea     rax, [rbp+2F0h+cValues]
0x18007b56d  mov     [rsp+3F0h+lpcValues], rax; lpcValues
0x18007b572  lea     rax, [rbp+2F0h+cbMaxClassLen]
0x18007b576  mov     [rsp+3F0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x18007b57b  lea     rax, [rsp+3F0h+cbMaxSubKeyLen]
0x18007b580  mov     [rsp+3F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18007b585  lea     rax, [rsp+3F0h+cSubKeys+4]
0x18007b58a  mov     [rsp+3F0h+phkResult], rax; lpcSubKeys
0x18007b58f  xor     r9d, r9d; lpReserved
0x18007b592  lea     r8, [rbp+2F0h+cchClass]; lpcchClass
0x18007b596  lea     rdx, [rbp+2F0h+Class]; lpClass
0x18007b59d  mov     rcx, [rbp+2F0h+hKey]; hKey
0x18007b5a1  call    cs:__imp_RegQueryInfoKeyW
0x18007b5a7  test    eax, eax
0x18007b5a9  jz      short loc_18007B5BC
0x18007b5ab  jle     short loc_18007B5B5
0x18007b5ad  movzx   eax, ax
0x18007b5b0  or      eax, 80070000h
0x18007b5b5  mov     ebx, eax
0x18007b5b7  jmp     loc_18007B9AC
0x18007b5bc  mov     edi, r15d
0x18007b5bf  mov     r14d, r15d
0x18007b5c2  cmp     [rsp+3F0h+cSubKeys+4], r15d
0x18007b5c7  jbe     loc_18007B9AA
0x18007b5cd  lea     rsi, aLpaEnterprisem_7; "LPA::EnterpriseManager::LoadEnterpriseD"...
0x18007b5d4  xor     r8d, r8d
0x18007b5d7  mov     edx, [rsp+3F0h+cbMaxSubKeyLen]
0x18007b5db  inc     edx
0x18007b5dd  lea     rcx, [rbp+2F0h+var_328]
0x18007b5e1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007b5e6  mov     eax, [rsp+3F0h+cbMaxSubKeyLen]
0x18007b5ea  inc     eax
0x18007b5ec  mov     [rsp+3F0h+cSubKeys], eax
0x18007b5f0  lea     rcx, [rbp+2F0h+var_328]
0x18007b5f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b5f9  mov     r8, rax; lpName
0x18007b5fc  lea     rax, [rbp+2F0h+ftLastWriteTime]
0x18007b600  mov     [rsp+3F0h+lpcValues], rax; lpftLastWriteTime
0x18007b605  mov     [rsp+3F0h+lpcbMaxClassLen], r15; lpcchClass
0x18007b60a  mov     [rsp+3F0h+lpcbMaxSubKeyLen], r15; lpClass
0x18007b60f  mov     [rsp+3F0h+phkResult], r15; lpReserved
0x18007b614  lea     r9, [rsp+3F0h+cSubKeys]; lpcchName
0x18007b619  mov     edx, r14d; dwIndex
0x18007b61c  mov     rcx, [rbp+2F0h+hKey]; hKey
0x18007b620  call    cs:__imp_RegEnumKeyExW
0x18007b626  test    eax, eax
0x18007b628  jnz     short loc_18007B5AB
0x18007b62a  xor     r8d, r8d
0x18007b62d  mov     edx, [rsp+3F0h+cSubKeys]
0x18007b631  lea     rcx, [rbp+2F0h+var_328]
0x18007b635  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007b63a  xorps   xmm0, xmm0
0x18007b63d  movups  [rbp+2F0h+var_308], xmm0
0x18007b641  movdqu  [rbp+2F0h+var_2F8], xmm6
0x18007b646  mov     word ptr [rbp+2F0h+var_308], r15w
0x18007b64b  lea     r8, asc_1801118E4; "\\"
0x18007b652  lea     rdx, [rbp+2F0h+var_2C8]
0x18007b656  lea     rcx, [rbp+2F0h+var_288]
0x18007b65a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18007b65f  nop
0x18007b660  lea     r8, [rbp+2F0h+var_328]
0x18007b664  mov     rdx, rax
0x18007b667  lea     rcx, [rbp+2F0h+var_2A8]
0x18007b66b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18007b670  mov     rdx, rax
0x18007b673  lea     rcx, [rbp+2F0h+var_308]
0x18007b677  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007b67c  lea     rcx, [rbp+2F0h+var_2A8]
0x18007b680  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b685  nop
0x18007b686  lea     rcx, [rbp+2F0h+var_288]
0x18007b68a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b68f  lea     rcx, [rsp+3F0h+var_380]
0x18007b694  call    ??$make_unique@ULPA_ENTERPRISE_DISCOVERY_EVENT@@$$V$0A@@std@@YA?AV?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@0@XZ; std::make_unique<LPA_ENTERPRISE_DISCOVERY_EVENT,,0>(void)
0x18007b699  nop
0x18007b69a  mov     rbx, [rsp+3F0h+var_380]
0x18007b69f  mov     dword ptr [rbx+8], 1
0x18007b6a6  lea     rcx, [rbp+2F0h+var_328]
0x18007b6aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b6af  mov     r8, rax; unsigned __int16 *
0x18007b6b2  lea     rcx, [rbx+4Eh]; unsigned __int16 *
0x18007b6b6  mov     edx, 104h; unsigned __int64
0x18007b6bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b6c0  mov     edi, eax
0x18007b6c2  test    eax, eax
0x18007b6c4  js      short loc_18007B6D9
0x18007b6c6  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x18007b6ca  mov     r8, r13; unsigned __int16 *
0x18007b6cd  mov     edx, 21h ; '!'; unsigned __int64
0x18007b6d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b6d7  mov     edi, eax
0x18007b6d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007b6e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007b6e5  test    al, al
0x18007b6e7  jz      loc_18007B91C
0x18007b6ed  test    edi, edi
0x18007b6ef  jns     short loc_18007B751
0x18007b6f1  mov     eax, cs:CallbackContext
0x18007b6f7  cmp     eax, 2
0x18007b6fa  jbe     short loc_18007B738
0x18007b6fc  mov     [rbp+2F0h+var_368], rsi
0x18007b700  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007b707  mov     [rbp+2F0h+var_360], rax
0x18007b70b  lea     rax, [rsp+3F0h+var_390]
0x18007b710  mov     [rsp+3F0h+lpcbMaxClassLen], rax
0x18007b715  lea     rax, [rbp+2F0h+var_368]
0x18007b719  mov     [rsp+3F0h+lpcbMaxSubKeyLen], rax
0x18007b71e  lea     rax, [rbp+2F0h+var_360]
0x18007b722  lea     rdx, unk_18012C930
0x18007b729  mov     [rsp+3F0h+phkResult], rax
0x18007b72e  mov     dword ptr [rsp+3F0h+var_390], edi
0x18007b732  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007b737  nop
0x18007b738  lea     rcx, [rsp+3F0h+var_380]
0x18007b73d  call    ??1?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>::~unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>(void)
0x18007b742  nop
0x18007b743  lea     rcx, [rbp+2F0h+var_308]
0x18007b747  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b74c  jmp     loc_18007B995
0x18007b751  lea     rcx, [rbp+2F0h+var_308]
0x18007b755  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b75a  mov     rsi, rax
0x18007b75d  mov     dword ptr [rsp+3F0h+Data], r15d
0x18007b762  lea     r8, [rsp+3F0h+Data]; lpData
0x18007b767  lea     rdx, aEnable; "Enable"
0x18007b76e  mov     rcx, rax; lpSubKey
0x18007b771  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007b776  mov     edi, eax
0x18007b778  test    eax, eax
0x18007b77a  jns     short loc_18007B7C0
0x18007b77c  mov     eax, cs:CallbackContext
0x18007b782  cmp     eax, 2
0x18007b785  jbe     short loc_18007B738
0x18007b787  lea     rax, aLpaEnterprisem_7; "LPA::EnterpriseManager::LoadEnterpriseD"...
0x18007b78e  mov     [rbp+2F0h+var_360], rax
0x18007b792  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007b799  mov     [rbp+2F0h+var_368], rax
0x18007b79d  lea     rax, [rsp+3F0h+var_390]
0x18007b7a2  mov     [rsp+3F0h+lpcbMaxClassLen], rax
0x18007b7a7  lea     rax, [rbp+2F0h+var_360]
0x18007b7ab  mov     [rsp+3F0h+lpcbMaxSubKeyLen], rax
0x18007b7b0  lea     rax, [rbp+2F0h+var_368]
0x18007b7b4  lea     rdx, dword_18012C8C4
0x18007b7bb  jmp     loc_18007B729
0x18007b7c0  mov     eax, r15d
0x18007b7c3  cmp     dword ptr [rsp+3F0h+Data], r15d
0x18007b7c8  setnz   al
0x18007b7cb  mov     [rbx+4], eax
0x18007b7ce  mov     dword ptr [rsp+3F0h+var_374], r15d
0x18007b7d3  lea     r8, [rsp+3F0h+var_374]; lpData
0x18007b7d8  lea     rdx, aMaximumattempt; "MaximumAttempts"
0x18007b7df  mov     rcx, rsi; lpSubKey
0x18007b7e2  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007b7e7  mov     ecx, 3
0x18007b7ec  test    eax, eax
0x18007b7ee  cmovns  ecx, dword ptr [rsp+3F0h+var_374]
0x18007b7f3  mov     [rbx+258h], ecx
0x18007b7f9  xorps   xmm0, xmm0
0x18007b7fc  movups  [rbp+2F0h+var_2E8], xmm0
0x18007b800  movdqu  [rbp+2F0h+var_2D8], xmm6
0x18007b805  mov     word ptr [rbp+2F0h+var_2E8], r15w
0x18007b80a  lea     r8, [rbp+2F0h+var_2E8]
0x18007b80e  lea     rdx, aProfileid; "ProfileId"
0x18007b815  mov     rcx, rsi; lpSubKey
0x18007b818  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007b81d  test    eax, eax
0x18007b81f  js      loc_18007B8DB
0x18007b825  lea     r15, [rbx+25Ch]
0x18007b82c  lea     rcx, [rbp+2F0h+var_2E8]
0x18007b830  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b835  mov     r8, rax; unsigned __int16 *
0x18007b838  mov     edx, 15h; unsigned __int64
0x18007b83d  mov     rcx, r15; unsigned __int16 *
0x18007b840  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b845  test    eax, eax
0x18007b847  jns     loc_18007B8D8
0x18007b84d  mov     eax, cs:CallbackContext
0x18007b853  cmp     eax, 2
0x18007b856  jbe     short loc_18007B8B2
0x18007b858  lea     rcx, [rbp+2F0h+var_2E8]
0x18007b85c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007b861  mov     r8, rax; unsigned __int16 *
0x18007b864  mov     edx, 15h; unsigned __int64
0x18007b869  mov     rcx, r15; unsigned __int16 *
0x18007b86c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b871  mov     [rbp+2F0h+var_338], eax
0x18007b874  lea     rax, aLpaEnterprisem_7; "LPA::EnterpriseManager::LoadEnterpriseD"...
0x18007b87b  mov     [rbp+2F0h+var_360], rax
0x18007b87f  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007b886  mov     [rbp+2F0h+var_368], rax
0x18007b88a  lea     rax, [rbp+2F0h+var_338]
0x18007b88e  mov     [rsp+3F0h+lpcbMaxClassLen], rax
0x18007b893  lea     rax, [rbp+2F0h+var_360]
0x18007b897  mov     [rsp+3F0h+lpcbMaxSubKeyLen], rax
0x18007b89c  lea     rax, [rbp+2F0h+var_368]
0x18007b8a0  mov     [rsp+3F0h+phkResult], rax
0x18007b8a5  lea     rdx, unk_18012C858
0x18007b8ac  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007b8b1  nop
0x18007b8b2  lea     rcx, [rbp+2F0h+var_2E8]
0x18007b8b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b8bb  nop
0x18007b8bc  lea     rcx, [rsp+3F0h+var_380]
0x18007b8c1  call    ??1?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>::~unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>(void)
0x18007b8c6  nop
0x18007b8c7  lea     rcx, [rbp+2F0h+var_308]
0x18007b8cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b8d0  xor     r15d, r15d
0x18007b8d3  jmp     loc_18007B995
0x18007b8d8  xor     r15d, r15d
0x18007b8db  mov     dword ptr [rbp+2F0h+var_370], r15d
0x18007b8df  lea     r8, [rbp+2F0h+var_370]; lpData
0x18007b8e3  lea     rdx, aErrordetail; "ErrorDetail"
0x18007b8ea  mov     rcx, rsi; lpSubKey
0x18007b8ed  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007b8f2  test    eax, eax
0x18007b8f4  js      short loc_18007B8FF
0x18007b8f6  mov     eax, dword ptr [rbp+2F0h+var_370]
0x18007b8f9  mov     [rbx+288h], eax
0x18007b8ff  lea     r8, [rsp+3F0h+var_380]
0x18007b904  mov     rdx, [r12]
0x18007b908  mov     rcx, r12
0x18007b90b  call    ??$_Emplace@V?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@@?$list@V?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@V?$allocator@V?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@std@@PEAX@1@QEAU21@$$QEAV?$unique_ptr@ULPA_ENTERPRISE_DISCOVERY_EVENT@@U?$default_delete@ULPA_ENTERPRISE_DISCOVERY_EVENT@@@std@@@1@@Z; std::list<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>>::_Emplace<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>>(std::_List_node<std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT>,void *> * const,std::unique_ptr<LPA_ENTERPRISE_DISCOVERY_EVENT> &&)
0x18007b910  nop
0x18007b911  lea     rcx, [rbp+2F0h+var_2E8]
0x18007b915  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b91a  jmp     short loc_18007B970
0x18007b91c  test    edi, edi
0x18007b91e  js      short loc_18007B970
0x18007b920  mov     dword ptr [rsp+3F0h+var_390], r15d
0x18007b925  lea     rcx, [rbp+2F0h+var_308]
  ... truncated ...
```
