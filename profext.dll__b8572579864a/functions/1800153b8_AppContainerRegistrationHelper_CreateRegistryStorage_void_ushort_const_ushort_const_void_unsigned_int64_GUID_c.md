# AppContainerRegistrationHelper::CreateRegistryStorage(void *,ushort const *,ushort const *,void *,unsigned __int64,_GUID const *,ushort *)

- ea: `0x1800153b8`
- end: `0x180015d74`
- name: `?CreateRegistryStorage@AppContainerRegistrationHelper@@CAJPEAXPEBG10_KPEBU_GUID@@PEAG@Z`
- size: `2492`
- prototype: `static int(void *, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned __int64, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009504`

## callees

- `0x180002030`
- `0x180003c00`
- `0x180003d30`
- `0x180004030`
- `0x1800040c0`
- `0x1800044e0`
- `0x180004594`
- `0x18000a4d8`
- `0x18000a540`
- `0x18000a740`
- `0x18000bd18`
- `0x18000f41c`
- `0x18000f614`
- `0x18000f938`
- `0x1800153b8`
- `0x180022830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800157ce`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800157ce`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001587f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001587f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001554e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001554e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015893`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800156a2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015969`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015baf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800156a2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015969`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001543a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001543a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015747`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015539`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015539`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180015a61`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180015c70`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180015a61`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180015c70`

## string_xrefs

- `0x180015499`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180015509`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180015586`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180015577`: `Name %ls Sid %ls`
- `0x180015644`: `Name %ls Sid %ls`
- `0x18001590f`: `Name %ls Sid %ls`
- `0x18001548a`: `Sid %ls len %d`
- `0x1800154fa`: `Name %ls Sid %ls len %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppContainerRegistrationHelper::CreateRegistryStorage(
        void *a1,
        const char *a2,
        const unsigned __int16 *a3,
        void *a4,
        unsigned __int64 a5,
        struct _GUID *a6,
        unsigned __int16 *a7)
{
  __int64 v9; // rax
  unsigned int v10; // edi
  unsigned __int16 *v11; // rax
  const WCHAR *v12; // rbx
  int v13; // ebx
  int v14; // eax
  int v15; // r15d
  signed int LastError; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  HKEY *phkResult; // rax
  int v22; // eax
  int v23; // eax
  int v24; // ebx
  struct _ACL *v25; // rax
  struct _ACL *v26; // rbx
  int v27; // eax
  signed int v28; // eax
  __int64 v29; // rdx
  signed int v30; // eax
  int v31; // eax
  HKEY *v32; // rax
  int v33; // eax
  int v34; // eax
  int v35; // r14d
  struct _GUID *v36; // r15
  int v37; // r14d
  __int64 v38; // rdx
  signed int v39; // eax
  signed int v40; // r14d
  int v41; // eax
  HKEY *v42; // rax
  int v43; // eax
  int v44; // eax
  int v45; // r14d
  signed int v46; // eax
  int v47; // eax
  int v48; // ebx
  int v49; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned __int64 dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  int dwOptionsc; // [rsp+20h] [rbp-E0h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  struct _ACL *v57; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE handle; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID *v60; // [rsp+70h] [rbp-90h]
  void *v61; // [rsp+78h] [rbp-88h]
  __int64 v62; // [rsp+80h] [rbp-80h] BYREF
  PSID pSid; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v64; // [rsp+90h] [rbp-70h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp-68h] BYREF
  WCHAR v66[520]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[520]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+928h] [rbp+828h]

  pSid = a4;
  v61 = a1;
  v60 = a6;
  handle = 0;
  v62 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = 2 * v9 + 358;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(v10);
  v12 = v11;
  v64 = v11;
  if ( v11 )
  {
    v14 = StringCbPrintfW(
            v11,
            v10,
            L"D:(A;OICI;KA;;;CO)(A;OICI;KA;;;SY)(A;OICI;KA;;;%s)(A;OICI;KR;;;S-1-15-3-1024-3635283841-2530182609-996808640"
             "-1887759898-3848208603-3313616867-983405619-2501854204)(A;OICI;KA;;;BA)",
            a3);
    v15 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v14, 0x1FDu, a3, 0x208u, a7);
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v15,
        (int)"Name %ls Sid %ls len %d",
        a2,
        a3,
        v10);
LABEL_8:
      v13 = v15;
      goto LABEL_82;
    }
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v12, 1u, &SecurityDescriptor, 0) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v17 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x205,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)LastError,
            (__int64)"Name %ls Sid %ls",
            a2,
            a3);
    v18 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v17, 0x206u, a3, 0x208u, a7);
    v13 = v18;
    if ( v18 < 0 )
    {
      v19 = 518;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v18,
        dwOptions);
LABEL_16:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
      goto LABEL_82;
    }
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    SecurityAttributes.bInheritHandle = 0;
    if ( !v61 )
    {
      v20 = StringCchPrintfW(
              SubKey,
              0x208u,
              L"%s\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Storage",
              a3);
      v13 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v20, 0x214u, a3, 0x208u, a7);
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x214,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v13,
          (int)"Name %ls Sid %ls",
          a2,
          a3);
        goto LABEL_16;
      }
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v62);
      v22 = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, phkResult, 0);
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      v23 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x220,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)(unsigned int)v22,
              (__int64)"Name %ls subkey %ls",
              a2,
              SubKey);
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( v23 == -2147024891 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        AppContainerRegistrationHelper::LogFailureWithContext(
          &AppModelAppContainerCreateRegistryKeyFailure,
          SubKey,
          v24,
          v60);
        v18 = AppContainerRegistrationHelper::SetAPIContextIfFailed(
                v24,
                0x227u,
                (const unsigned __int16 *)a2,
                0x208u,
                a7);
        v13 = v18;
        if ( v18 < 0 )
        {
          v19 = 551;
          goto LABEL_15;
        }
      }
    }
    v25 = (struct _ACL *)CoTaskMemAlloc(0x58u);
    v26 = v25;
    v57 = v25;
    if ( !v25 )
    {
      v27 = AppContainerRegistrationHelper::SetAPIContextIfFailed(
              -2147024882,
              0x231u,
              (const unsigned __int16 *)a2,
              0x208u,
              a7);
      v13 = v27;
      if ( v27 < 0 )
      {
        LODWORD(lpSecurityAttributes) = 88;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x231,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v27,
          (int)"Name %ls size %d",
          a2,
          lpSecurityAttributes);
      }
      goto LABEL_30;
    }
    if ( InitializeAcl(v25, 0x58u, 2u) )
    {
      v28 = 0;
    }
    else
    {
      v28 = GetLastError();
      if ( v28 > 0 )
        v28 = (unsigned __int16)v28 | 0x80070000;
    }
    v15 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v28, 0x236u, (const unsigned __int16 *)a2, 0x208u, a7);
    if ( v15 < 0 )
    {
      v29 = 566;
LABEL_37:
      LODWORD(lpSecurityAttributes) = 88;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v15,
        (int)"Name %ls size %d",
        a2,
        lpSecurityAttributes);
LABEL_38:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v57);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
      goto LABEL_8;
    }
    if ( AddAccessAllowedAceEx(v26, 2u, 0x23u, 0xF003Fu, pSid) )
    {
      v30 = 0;
    }
    else
    {
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
    }
    v15 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v30, 0x23Eu, (const unsigned __int16 *)a2, 0x208u, a7);
    if ( v15 < 0 )
    {
      v29 = 574;
      goto LABEL_37;
    }
    v31 = AppContainerRegistrationHelper::DeriveTopLevelRegistryKey(
            v61,
            (const unsigned __int16 *)a2,
            a3,
            v66,
            dwOptionsa);
    v15 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v31, 0x246u, a3, 0x208u, a7);
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v15,
        (int)"Name %ls Sid %ls",
        a2,
        a3);
      goto LABEL_38;
    }
    dwDisposition = 0;
    v32 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&handle);
    v33 = RegCreateKeyExW(HKEY_USERS, v66, 0, 0, 0, 0x2001Fu, 0, v32, &dwDisposition);
    if ( v33 > 0 )
      v33 = (unsigned __int16)v33 | 0x80070000;
    v34 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x252,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)v33,
            (__int64)"Name %ls subkey %ls",
            a2,
            v66);
    v35 = v34;
    if ( v34 >= 0 )
    {
      v36 = v60;
    }
    else
    {
      if ( v34 == -2147024891 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v36 = v60;
      AppContainerRegistrationHelper::LogFailureWithContext(
        &AppModelAppContainerCreateRegistryKeyFailure,
        v66,
        v35,
        v60);
      v37 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v35, 0x259u, (const unsigned __int16 *)a2, 0x208u, a7);
      if ( v37 < 0 )
      {
        v38 = 601;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v37,
          dwOptionsb);
LABEL_55:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v57);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
        v13 = v37;
        goto LABEL_82;
      }
    }
    v39 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, v26, 0);
    v40 = v39;
    if ( v39 > 0 )
      v40 = (unsigned __int16)v39 | 0x80070000;
    if ( v40 < 0 )
    {
      if ( v40 == -2147024891 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      AppContainerRegistrationHelper::LogFailureWithContext(
        &AppModelAppContainerCreateRegistryKeyFailure,
        v66,
        v40,
        v36);
      v13 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v40, 0x26Bu, (const unsigned __int16 *)a2, 0x208u, a7);
      if ( v13 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x26B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v13,
          (int)"Name %ws subkey %ws",
          a2,
          v66);
      goto LABEL_30;
    }
    if ( !v61 )
    {
      v41 = StringCchCatW(v66, 0x208u, L"\\Children");
      v37 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v41, 0x274u, L"\\Children", 0x208u, a7);
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x274,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v37,
          (int)"Name %ls prefix %ls",
          a2,
          L"\\Children");
        goto LABEL_55;
      }
      v42 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&handle);
      v43 = RegCreateKeyExW(HKEY_USERS, v66, 0, 0, 0, 0x2001Fu, 0, v42, &dwDisposition);
      if ( v43 > 0 )
        v43 = (unsigned __int16)v43 | 0x80070000;
      v44 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x280,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)(unsigned int)v43,
              (__int64)"Name %ls subkey %ls",
              a2,
              v66);
      v45 = v44;
      if ( v44 < 0 )
      {
        if ( v44 == -2147024891 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        AppContainerRegistrationHelper::LogFailureWithContext(
          &AppModelAppContainerCreateRegistryKeyFailure,
          v66,
          v45,
          v36);
        v37 = AppContainerRegistrationHelper::SetAPIContextIfFailed(
                v45,
                0x287u,
                (const unsigned __int16 *)a2,
                0x208u,
                a7);
        if ( v37 < 0 )
        {
          v38 = 647;
          goto LABEL_54;
        }
      }
      v46 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, v26, 0);
      if ( v46 > 0 )
        v46 = (unsigned __int16)v46 | 0x80070000;
      v47 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x292,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)(unsigned int)v46,
              (__int64)"Name %ls subkey %ls",
              a2,
              v66);
      v48 = v47;
      if ( v47 < 0 )
      {
        if ( v47 == -2147024891 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        AppContainerRegistrationHelper::LogFailureWithContext(
          &AppModelAppContainerCreateRegistryKeyFailure,
          v66,
          v48,
          v36);
        v49 = AppContainerRegistrationHelper::SetAPIContextIfFailed(
                v48,
                0x299u,
                (const unsigned __int16 *)a2,
                0x208u,
                a7);
        v13 = v49;
        if ( v49 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x299,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)v49,
            dwOptionsc);
LABEL_30:
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v57);
          goto LABEL_16;
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v57);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
    v13 = 0;
    goto LABEL_82;
  }
  v13 = AppContainerRegistrationHelper::SetAPIContextIfFailed(-2147024882, 0x1F4u, a3, 0x208u, a7);
  if ( v13 < 0 )
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v13,
      (int)"Sid %ls len %d",
      (const char *)a3,
      v10);
LABEL_82:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v64);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&handle);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800153b8  push    rbp
0x1800153ba  push    rbx
0x1800153bb  push    rsi
0x1800153bc  push    rdi
0x1800153bd  push    r12
0x1800153bf  push    r13
0x1800153c1  push    r14
0x1800153c3  push    r15
0x1800153c5  lea     rbp, [rsp-7E8h]
0x1800153cd  sub     rsp, 8E8h
0x1800153d4  mov     rax, cs:__security_cookie
0x1800153db  xor     rax, rsp
0x1800153de  mov     [rbp+820h+var_50], rax
0x1800153e5  mov     [rbp+820h+pSid], r9
0x1800153e9  mov     r14, r8
0x1800153ec  mov     rsi, rdx
0x1800153ef  mov     [rsp+920h+var_8A8], rcx
0x1800153f4  mov     rax, [rbp+820h+arg_28]
0x1800153fb  mov     [rsp+920h+var_8B0], rax
0x180015400  mov     r13, [rbp+820h+arg_30]
0x180015407  xor     r12d, r12d
0x18001540a  mov     [rsp+920h+handle], r12
0x18001540f  mov     [rbp+820h+var_8A0], r12
0x180015413  xorps   xmm0, xmm0
0x180015416  xor     eax, eax
0x180015418  movups  xmmword ptr [rbp+820h+SecurityAttributes.nLength], xmm0
0x18001541c  mov     qword ptr [rbp+820h+SecurityAttributes.bInheritHandle], rax
0x180015420  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015424  inc     rax
0x180015427  cmp     [r8+rax*2], r12w
0x18001542c  jnz     short loc_180015424
0x18001542e  lea     edi, ds:166h[rax*2]
0x180015435  mov     r15d, edi
0x180015438  mov     ecx, edi; cb
0x18001543a  call    cs:__imp_CoTaskMemAlloc
0x180015441  nop     dword ptr [rax+rax+00h]
0x180015446  mov     rbx, rax
0x180015449  mov     [rbp+820h+var_890], rax
0x18001544d  test    rax, rax
0x180015450  jnz     short loc_1800154AC
0x180015452  mov     qword ptr [rsp+920h+dwOptions], r13; unsigned __int16 *
0x180015457  mov     r9d, 208h; unsigned __int64
0x18001545d  mov     r8, r14; unsigned __int16 *
0x180015460  lea     esi, [r9-14h]
0x180015464  mov     edx, esi; unsigned int
0x180015466  mov     ecx, 8007000Eh; int
0x18001546b  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180015470  mov     ebx, eax
0x180015472  test    eax, eax
0x180015474  jns     loc_180015D30
0x18001547a  mov     rcx, [rbp+828h]; this
0x180015481  mov     dword ptr [rsp+920h+lpSecurityAttributes], edi
0x180015485  mov     qword ptr [rsp+920h+samDesired], r14; char *
0x18001548a  lea     rax, aSidLsLenD; "Sid %ls len %d"
0x180015491  mov     qword ptr [rsp+920h+dwOptions], rax; int
0x180015496  mov     r9d, ebx; char *
0x180015499  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800154a0  mov     edx, esi; void *
0x1800154a2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800154a7  jmp     loc_180015D30
0x1800154ac  mov     r9, r14
0x1800154af  lea     r8, aDAOiciKaCoAOic; "D:(A;OICI;KA;;;CO)(A;OICI;KA;;;SY)(A;OI"...
0x1800154b6  mov     rdx, r15; unsigned __int64
0x1800154b9  mov     rcx, rbx; unsigned __int16 *
0x1800154bc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800154c1  mov     ecx, eax; int
0x1800154c3  mov     qword ptr [rsp+920h+dwOptions], r13; unsigned __int16 *
0x1800154c8  mov     r12d, 208h
0x1800154ce  mov     r9d, r12d; unsigned __int64
0x1800154d1  mov     r8, r14; unsigned __int16 *
0x1800154d4  lea     edx, [r12-0Bh]; unsigned int
0x1800154d9  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x1800154de  mov     r15d, eax
0x1800154e1  test    eax, eax
0x1800154e3  jns     short loc_180015522
0x1800154e5  mov     rcx, [rbp+828h]; this
0x1800154ec  mov     dword ptr [rsp+920h+phkResult], edi
0x1800154f0  mov     [rsp+920h+lpSecurityAttributes], r14
0x1800154f5  mov     qword ptr [rsp+920h+samDesired], rsi; char *
0x1800154fa  lea     rax, aNameLsSidLsLen; "Name %ls Sid %ls len %d"
0x180015501  mov     qword ptr [rsp+920h+dwOptions], rax; int
0x180015506  mov     r9d, r15d; char *
0x180015509  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180015510  lea     edx, [r12-0Bh]; void *
0x180015515  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001551a  mov     ebx, r15d
0x18001551d  jmp     loc_180015D30
0x180015522  xor     r15d, r15d
0x180015525  mov     [rsp+920h+SecurityDescriptor], r15
0x18001552a  xor     r9d, r9d; SecurityDescriptorSize
0x18001552d  lea     r8, [rsp+920h+SecurityDescriptor]; SecurityDescriptor
0x180015532  lea     edx, [r15+1]; StringSDRevision
0x180015536  mov     rcx, rbx; StringSecurityDescriptor
0x180015539  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180015540  nop     dword ptr [rax+rax+00h]
0x180015545  test    eax, eax
0x180015547  jz      short loc_18001554E
0x180015549  mov     eax, r15d
0x18001554c  jmp     short loc_180015566
0x18001554e  call    cs:__imp_GetLastError
0x180015555  nop     dword ptr [rax+rax+00h]
0x18001555a  test    eax, eax
0x18001555c  jle     short loc_180015566
0x18001555e  movzx   eax, ax
0x180015561  or      eax, 80070000h
0x180015566  mov     rcx, [rbp+828h]; this
0x18001556d  mov     [rsp+920h+lpSecurityAttributes], r14
0x180015572  mov     qword ptr [rsp+920h+samDesired], rsi; char *
0x180015577  lea     rdx, aNameLsSidLs; "Name %ls Sid %ls"
0x18001557e  mov     qword ptr [rsp+920h+dwOptions], rdx; __int64
0x180015583  mov     r9d, eax; char *
0x180015586  lea     rdi, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001558d  mov     r8, rdi; unsigned int
0x180015590  mov     edx, 205h; void *
0x180015595  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001559a  mov     qword ptr [rsp+920h+dwOptions], r13; int
0x18001559f  mov     r9, r12; unsigned __int64
0x1800155a2  mov     r8, r14; unsigned __int16 *
0x1800155a5  mov     edx, 206h; unsigned int
0x1800155aa  mov     ecx, eax; int
0x1800155ac  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x1800155b1  mov     ebx, eax
0x1800155b3  test    eax, eax
0x1800155b5  jns     short loc_1800155DE
0x1800155b7  mov     edx, 206h; void *
0x1800155bc  mov     r8, rdi; unsigned int
0x1800155bf  mov     r9d, eax; char *
0x1800155c2  mov     rcx, [rbp+828h]; this
0x1800155c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155ce  nop
0x1800155cf  lea     rcx, [rsp+920h+SecurityDescriptor]
0x1800155d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800155d9  jmp     loc_180015D30
0x1800155de  mov     [rbp+820h+SecurityAttributes.nLength], 18h
0x1800155e5  mov     rax, [rsp+920h+SecurityDescriptor]
0x1800155ea  mov     [rbp+820h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800155ee  mov     [rbp+820h+SecurityAttributes.bInheritHandle], r15d
0x1800155f2  cmp     [rsp+920h+var_8A8], r15
0x1800155f7  jnz     loc_180015742
0x1800155fd  mov     r9, r14
0x180015600  lea     r8, aSSoftwareClass; "%s\\Software\\Classes\\Local Settings\\"...
0x180015607  mov     rdx, r12; unsigned __int64
0x18001560a  lea     rcx, [rbp+820h+SubKey]; unsigned __int16 *
0x180015611  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015616  mov     ecx, eax; int
0x180015618  mov     qword ptr [rsp+920h+dwOptions], r13; unsigned __int16 *
0x18001561d  mov     r9, r12; unsigned __int64
0x180015620  mov     r8, r14; unsigned __int16 *
0x180015623  mov     edx, 214h; unsigned int
0x180015628  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18001562d  mov     ebx, eax
0x18001562f  test    eax, eax
0x180015631  jns     short loc_180015665
0x180015633  mov     rcx, [rbp+828h]; this
0x18001563a  mov     [rsp+920h+lpSecurityAttributes], r14
0x18001563f  mov     qword ptr [rsp+920h+samDesired], rsi; char *
0x180015644  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x18001564b  mov     qword ptr [rsp+920h+dwOptions], rax; int
0x180015650  mov     r9d, ebx; char *
0x180015653  mov     r8, rdi; unsigned int
0x180015656  mov     edx, 214h; void *
0x18001565b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015660  jmp     loc_1800155CF
0x180015665  lea     rcx, [rbp+820h+var_8A0]
0x180015669  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001566e  mov     [rsp+920h+lpdwDisposition], r15; lpdwDisposition
0x180015673  mov     [rsp+920h+phkResult], rax; phkResult
0x180015678  lea     rax, [rbp+820h+SecurityAttributes]
0x18001567c  mov     [rsp+920h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180015681  mov     [rsp+920h+samDesired], 2001Fh; samDesired
0x180015689  mov     [rsp+920h+dwOptions], r15d; dwOptions
0x18001568e  xor     r9d, r9d; lpClass
0x180015691  xor     r8d, r8d; Reserved
0x180015694  lea     rdx, [rbp+820h+SubKey]; lpSubKey
0x18001569b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800156a2  call    cs:__imp_RegCreateKeyExW
0x1800156a9  nop     dword ptr [rax+rax+00h]
0x1800156ae  test    eax, eax
0x1800156b0  jle     short loc_1800156BA
0x1800156b2  movzx   eax, ax
0x1800156b5  or      eax, 80070000h
0x1800156ba  mov     rcx, [rbp+828h]; this
0x1800156c1  lea     rdx, [rbp+820h+SubKey]
0x1800156c8  mov     [rsp+920h+lpSecurityAttributes], rdx
0x1800156cd  mov     qword ptr [rsp+920h+samDesired], rsi; char *
0x1800156d2  lea     rdx, aNameLsSubkeyLs; "Name %ls subkey %ls"
0x1800156d9  mov     qword ptr [rsp+920h+dwOptions], rdx; __int64
0x1800156de  mov     r9d, eax; char *
0x1800156e1  mov     r8, rdi; unsigned int
0x1800156e4  mov     edx, 220h; void *
0x1800156e9  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800156ee  mov     ebx, eax
0x1800156f0  test    eax, eax
0x1800156f2  jns     short loc_180015742
0x1800156f4  cmp     eax, 80070005h
0x1800156f9  jnz     short loc_180015700
0x1800156fb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015700  mov     r9, [rsp+920h+var_8B0]; struct _GUID *
0x180015705  mov     r8d, ebx; int
0x180015708  lea     rdx, [rbp+820h+SubKey]; unsigned __int16 *
0x18001570f  lea     rcx, AppModelAppContainerCreateRegistryKeyFailure; struct _EVENT_DESCRIPTOR *
0x180015716  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18001571b  mov     qword ptr [rsp+920h+dwOptions], r13; unsigned __int16 *
0x180015720  mov     r9, r12; unsigned __int64
0x180015723  mov     r8, rsi; unsigned __int16 *
0x180015726  mov     edx, 227h; unsigned int
0x18001572b  mov     ecx, ebx; int
0x18001572d  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180015732  mov     ebx, eax
0x180015734  test    eax, eax
0x180015736  jns     short loc_180015742
0x180015738  mov     edx, 227h
0x18001573d  jmp     loc_1800155BC
0x180015742  mov     ecx, 58h ; 'X'; cb
0x180015747  call    cs:__imp_CoTaskMemAlloc
0x18001574e  nop     dword ptr [rax+rax+00h]
0x180015753  mov     rbx, rax
0x180015756  mov     [rsp+920h+var_8C8], rax
0x18001575b  test    rax, rax
0x18001575e  jnz     short loc_1800157C2
0x180015760  mov     qword ptr [rsp+920h+dwOptions], r13; unsigned __int16 *
0x180015765  mov     r9, r12; unsigned __int64
0x180015768  mov     r8, rsi; unsigned __int16 *
0x18001576b  mov     r14d, 231h
0x180015771  mov     edx, r14d; unsigned int
0x180015774  mov     ecx, 8007000Eh; int
0x180015779  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18001577e  mov     ebx, eax
0x180015780  test    eax, eax
0x180015782  jns     short loc_1800157B3
0x180015784  mov     dword ptr [rsp+920h+lpSecurityAttributes], 58h ; 'X'
0x18001578c  mov     qword ptr [rsp+920h+samDesired], rsi; char *
0x180015791  lea     r8, aNameLsSizeD; "Name %ls size %d"
0x180015798  mov     qword ptr [rsp+920h+dwOptions], r8; int
0x18001579d  mov     r9d, eax; char *
0x1800157a0  mov     edx, r14d; void *
0x1800157a3  mov     r8, rdi; unsigned int
0x1800157a6  mov     rcx, [rbp+828h]; this
0x1800157ad  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800157b2  nop
0x1800157b3  lea     rcx, [rsp+920h+var_8C8]
0x1800157b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800157bd  jmp     loc_1800155CF
0x1800157c2  mov     edx, 58h ; 'X'; nAclLength
0x1800157c7  lea     r8d, [rdx-56h]; dwAclRevision
0x1800157cb  mov     rcx, rbx; pAcl
0x1800157ce  call    cs:__imp_InitializeAcl
0x1800157d5  nop     dword ptr [rax+rax+00h]
0x1800157da  test    eax, eax
0x1800157dc  jz      short loc_1800157E3
0x1800157de  mov     eax, r15d
0x1800157e1  jmp     short loc_1800157FB
0x1800157e3  call    cs:__imp_GetLastError
0x1800157ea  nop     dword ptr [rax+rax+00h]
0x1800157ef  test    eax, eax
0x1800157f1  jle     short loc_1800157FB
0x1800157f3  movzx   eax, ax
0x1800157f6  or      eax, 80070000h
0x1800157fb  mov     qword ptr [rsp+920h+dwOptions], r13; unsigned __int16 *
0x180015800  mov     r9, r12; unsigned __int64
0x180015803  mov     r8, rsi; unsigned __int16 *
0x180015806  mov     edx, 236h; unsigned int
0x18001580b  mov     ecx, eax; int
0x18001580d  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180015812  mov     r15d, eax
0x180015815  test    eax, eax
0x180015817  jns     short loc_180015864
0x180015819  mov     edx, 236h; void *
0x18001581e  mov     dword ptr [rsp+920h+lpSecurityAttributes], 58h ; 'X'
0x180015826  mov     qword ptr [rsp+920h+samDesired], rsi; char *
0x18001582b  lea     r8, aNameLsSizeD; "Name %ls size %d"
0x180015832  mov     qword ptr [rsp+920h+dwOptions], r8; int
0x180015837  mov     rcx, [rbp+828h]; this
0x18001583e  mov     r9d, r15d; char *
0x180015841  mov     r8, rdi; unsigned int
0x180015844  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015849  nop
0x18001584a  lea     rcx, [rsp+920h+var_8C8]
0x18001584f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180015854  nop
0x180015855  lea     rcx, [rsp+920h+SecurityDescriptor]
0x18001585a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001585f  jmp     loc_18001551A
0x180015864  mov     rax, [rbp+820h+pSid]
0x180015868  mov     qword ptr [rsp+920h+dwOptions], rax; pSid
0x18001586d  mov     edx, 2; dwAceRevision
0x180015872  mov     r9d, 0F003Fh; AccessMask
0x180015878  lea     r8d, [rdx+21h]; AceFlags
0x18001587c  mov     rcx, rbx; pAcl
0x18001587f  call    cs:__imp_AddAccessAllowedAceEx
0x180015886  nop     dword ptr [rax+rax+00h]
0x18001588b  test    eax, eax
0x18001588d  jz      short loc_180015893
0x18001588f  xor     eax, eax
0x180015891  jmp     short loc_1800158AB
0x180015893  call    cs:__imp_GetLastError
0x18001589a  nop     dword ptr [rax+rax+00h]
0x18001589f  test    eax, eax
0x1800158a1  jle     short loc_1800158AB
0x1800158a3  movzx   eax, ax
  ... truncated ...
```
