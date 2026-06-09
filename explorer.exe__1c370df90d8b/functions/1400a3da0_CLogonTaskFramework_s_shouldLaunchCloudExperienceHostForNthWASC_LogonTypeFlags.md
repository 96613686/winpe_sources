# CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthWASC(LogonTypeFlags)

- ea: `0x1400a3da0`
- end: `0x1400a44c1`
- name: `?s_shouldLaunchCloudExperienceHostForNthWASC@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z`
- size: `1825`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14009d5c0`

## callees

- `0x140011984`
- `0x140013790`
- `0x140013bb4`
- `0x140013c48`
- `0x140013e6c`
- `0x140019308`
- `0x14001eba8`
- `0x140028b38`
- `0x14002f838`
- `0x140033070`
- `0x140033a3c`
- `0x14003401c`
- `0x1400770ac`
- `0x140079928`
- `0x14007a850`
- `0x14007ce08`
- `0x140080b6c`
- `0x140081214`
- `0x140081aa8`
- `0x14008a118`
- `0x1400a3da0`
- `0x1400a44c8`
- `0x1400a4538`
- `0x1400a4580`
- `0x1400a45bc`
- `0x1400a9f80`
- `0x1401040e0`
- `0x1401357ec`
- `0x1401376d8`
- `0x140187a44`
- `0x140187aa0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a3ed6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a3f18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a3ed6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a3f18`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1400a3e89`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1400a3e89`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400a3fff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400a3fff`

## string_xrefs

- `0x1400a4014`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a4055`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a40d9`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a4272`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a42de`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a4324`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a435f`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a439a`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a43fe`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a447a`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a3ec8`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1400a3f0a`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1400a3fd9`: `WindowsUdk.Services.UnifiedConsent.WindowsAccountSyncConsentCoordinator`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
char __fastcall CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthWASC(__int16 a1)
{
  char v2; // bl
  unsigned __int64 v3; // rdx
  wil::filetime *v4; // rcx
  unsigned __int64 system_time; // rax
  int ActivationFactory; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64, DWORD *); // rsi
  __int64 v21; // rcx
  int v22; // eax
  const char *v23; // r9
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  wil::filetime *v29; // rcx
  HKEY v30; // rcx
  int v31; // eax
  int pdwType; // [rsp+20h] [rbp-88h]
  char v33; // [rsp+40h] [rbp-68h] BYREF
  char v34; // [rsp+41h] [rbp-67h] BYREF
  char v35; // [rsp+42h] [rbp-66h] BYREF
  char v36; // [rsp+43h] [rbp-65h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-60h] BYREF
  __int64 pvData; // [rsp+50h] [rbp-58h] BYREF
  __int64 v39; // [rsp+58h] [rbp-50h] BYREF
  __int64 v40; // [rsp+60h] [rbp-48h] BYREF
  struct _FILETIME v41; // [rsp+68h] [rbp-40h] BYREF
  struct _FILETIME v42; // [rsp+70h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-30h] BYREF
  __int64 v44; // [rsp+90h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v2 = 0;
  v33 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_44077960>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_44077960>::GetImpl'::`2'::impl) )
  {
    v42 = 0;
    if ( (int)SHRegGetFILETIME(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\UnifiedConsent",
                L"NthWascTimestamp",
                &v42) >= 0 )
    {
      system_time = (unsigned __int64)wil::filetime::get_system_time(v4);
      v3 = (((HIDWORD(system_time) - v42.dwHighDateTime) << 32) - v42.dwLowDateTime + (unsigned int)system_time)
         % 0xC92A69C000uLL;
      if ( (unsigned int)((((HIDWORD(system_time) - v42.dwHighDateTime) << 32)
                         - v42.dwLowDateTime
                         + (unsigned int)system_time)
                        / 0xC92A69C000uLL) <= 7 )
      {
        NthWASCConsentTelemetry::NthWASCFrequencyBlock();
        v34 = 0;
        NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(&v34);
        return 0;
      }
    }
    if ( (a1 & 0x3308) != 0 )
      goto LABEL_67;
    LOBYTE(v3) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_46635544>::GetImpl'::`2'::impl,
      v3);
    if ( CLogonTaskFramework::s_IsCompanionDeviceAccount() || IsOS(0xDu) )
      goto LABEL_67;
    LODWORD(pvData) = 0;
    pcbData[0] = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
           L"Enabled",
           0x10010u,
           0,
           &pvData,
           pcbData) )
    {
      pcbData[0] = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
        L"Enabled",
        0x20010010u,
        0,
        &pvData,
        pcbData);
    }
    if ( (_DWORD)pvData
      || IsSharedPCMode()
      || CLogonTaskFramework::s_IsExplorerRestart()
      || IsShellLauncherEnabledForCurrentUser()
      || IsPreserveOobeAutologonCredentialsSet()
      || IsUnattendedAutoLogonSet()
      || (unsigned int)IsUserAssignedAccessSingleApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
      || IsUserAssignedAccessMultiApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
      || IsUserAssignedAccessSingleAppClassicApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_48986217>::GetImpl'::`2'::impl)
      && CLogonTaskFramework::s_IsDJorAADJUser() )
    {
      goto LABEL_67;
    }
    *(_QWORD *)pcbData = 0;
    v41 = 0;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"WindowsUdk.Services.UnifiedConsent.WindowsAccountSyncConsentCoordinator",
      0x48u,
      0x47u);
    ActivationFactory = RoGetActivationFactory(v44, &GUID_d62d507d_d865_520b_8850_7245169004c6, &v41);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2007,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)ActivationFactory,
        pdwType);
    v40 = 0;
    v8 = **(_QWORD **)&v41;
    v40 = 0;
    v9 = (*(__int64 (__fastcall **)(struct _FILETIME, __int64 *))(v8 + 48))(v41, &v40);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x200A,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v9,
        pdwType);
    v39 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_48986217>::GetImpl'::`2'::impl) )
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::GetCachedVariantState(v10, &pvData);
      v12 = HIDWORD(pvData);
      v35 = 0;
      v13 = v39;
      v39 = 0;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v14 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *> *,WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator * *>(
              v40,
              (unsigned int)&v39,
              v11,
              v12,
              (__int64)&v35);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2012,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v14,
          pdwType);
      if ( v35 )
      {
        LODWORD(pvData) = v12;
        NthWASCConsentTelemetry::NthWASCCoordinatorTimeout<unsigned int>(&pvData);
        v34 = 0;
        NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(&v34);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v41);
        wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(pcbData);
        return 0;
      }
    }
    else
    {
      wil::wait_for_completion<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *,Microsoft::WRL::ComPtr<WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator>>(
        &pvData,
        v40);
      v16 = pvData;
      pvData = 0;
      v17 = v39;
      v39 = v16;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v18 = pvData;
      if ( pvData )
      {
        pvData = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    LOBYTE(v15) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_46635544>::GetImpl'::`2'::impl,
      v15);
    v19 = v39;
    if ( !v39 )
    {
      v34 = 0;
      NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(&v34);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v41);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(pcbData);
      return 0;
    }
    v20 = *(__int64 (__fastcall **)(__int64, __int64, DWORD *))(*(_QWORD *)v39 + 48LL);
    v21 = *(_QWORD *)pcbData;
    *(_QWORD *)pcbData = 0;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DataSharing", 0xCu, 0xBu);
    v22 = v20(v19, v44, pcbData);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2026,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v22,
        pdwType);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v39);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v40);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v41);
    try
    {
      v2 = 1;
      v33 = 1;
      if ( !*(_QWORD *)pcbData )
        goto LABEL_72;
      v35 = 0;
      v24 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pcbData + 48LL))(*(_QWORD *)pcbData, &v35);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2044,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v24,
          pdwType);
      if ( v35 )
      {
        v33 = 0;
        v25 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pcbData + 56LL))(*(_QWORD *)pcbData, &v33);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2049,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v25,
            pdwType);
        v36 = 0;
        v26 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pcbData + 64LL))(*(_QWORD *)pcbData, &v36);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x204C,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v26,
            pdwType);
        v34 = 0;
        v27 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pcbData + 72LL))(*(_QWORD *)pcbData, &v34);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x204F,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v27,
            pdwType);
        if ( !v33 || !v36 && v34 )
        {
          v2 = 1;
LABEL_65:
          v33 = v2;
          goto LABEL_72;
        }
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentNotApplicableDefaultValue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentNotApplicableDefaultValue>::GetImpl'::`2'::impl) )
      {
        v33 = 0;
        v28 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pcbData + 72LL))(*(_QWORD *)pcbData, &v33);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x205F,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v28,
            pdwType);
        if ( v33 )
        {
          NthWASCConsentTelemetry::NthWASCCoordinatorDefaultValueTriggered();
          v2 = 1;
          if ( v33 )
            goto LABEL_65;
        }
      }
      v2 = 0;
      goto LABEL_65;
    }
    catch ( ... )
    {
      v33 = 0;
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2072,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        v23);
      v2 = v33;
    }
LABEL_72:
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(pcbData);
LABEL_67:
    NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool &>(&v33);
    if ( v2 )
    {
      v41 = wil::filetime::get_system_time(v29);
      v31 = SHRegSetFILETIME(
              v30,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\UnifiedConsent",
              L"NthWascTimestamp",
              &v41);
      if ( v31 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x207D,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v31,
          pdwType);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400a3da0  mov     [rsp+arg_0], rbx
0x1400a3da5  mov     [rsp+arg_8], rsi
0x1400a3daa  push    rdi
0x1400a3dab  sub     rsp, 0A0h
0x1400a3db2  mov     rax, cs:__security_cookie
0x1400a3db9  xor     rax, rsp
0x1400a3dbc  mov     [rsp+0A8h+var_10], rax
0x1400a3dc4  mov     esi, ecx
0x1400a3dc6  xor     edi, edi
0x1400a3dc8  mov     bl, dil
0x1400a3dcb  mov     [rsp+0A8h+var_68], bl
0x1400a3dcf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_44077960@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_44077960@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_44077960> `wil::Feature<__WilFeatureTraits_Feature_44077960>::GetImpl(void)'::`2'::impl
0x1400a3dd6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_44077960@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_44077960>::__private_IsEnabled(void)
0x1400a3ddb  test    al, al
0x1400a3ddd  jz      loc_1400A448B
0x1400a3de3  mov     qword ptr [rsp+0A8h+var_38.dwLowDateTime], rdi
0x1400a3de8  lea     r9, [rsp+0A8h+var_38]; struct _FILETIME *
0x1400a3ded  lea     r8, aNthwasctimesta; "NthWascTimestamp"
0x1400a3df4  lea     rdx, aSoftwareMicros_99; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a3dfb  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1400a3e02  call    ?SHRegGetFILETIME@@YAJPEAUHKEY__@@PEBG1PEAU_FILETIME@@@Z; SHRegGetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME *)
0x1400a3e07  test    eax, eax
0x1400a3e09  js      short loc_1400A3E5D
0x1400a3e0b  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x1400a3e10  mov     r8, rax
0x1400a3e13  shr     r8, 20h
0x1400a3e17  mov     ecx, [rsp+0A8h+var_38.dwHighDateTime]
0x1400a3e1b  sub     r8, rcx
0x1400a3e1e  shl     r8, 20h
0x1400a3e22  mov     ecx, [rsp+0A8h+var_38.dwLowDateTime]
0x1400a3e26  sub     r8, rcx
0x1400a3e29  mov     eax, eax
0x1400a3e2b  add     rax, r8
0x1400a3e2e  xor     edx, edx
0x1400a3e30  mov     rcx, 0C92A69C000h
0x1400a3e3a  div     rcx
0x1400a3e3d  cmp     eax, 7
0x1400a3e40  ja      short loc_1400A3E5D
0x1400a3e42  call    ?NthWASCFrequencyBlock@NthWASCConsentTelemetry@@SAXXZ; NthWASCConsentTelemetry::NthWASCFrequencyBlock(void)
0x1400a3e47  mov     [rsp+0A8h+var_67], dil
0x1400a3e4c  lea     rcx, [rsp+0A8h+var_67]
0x1400a3e51  call    ??$ShouldShowNthWASCConsentForUser@_N@NthWASCConsentTelemetry@@SAX$$QEA_N@Z; NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(bool &&)
0x1400a3e56  xor     al, al
0x1400a3e58  jmp     loc_1400A448D
0x1400a3e5d  test    esi, 3308h
0x1400a3e63  jnz     loc_1400A443B
0x1400a3e69  mov     dl, 1
0x1400a3e6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_46635544@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544> `wil::Feature<__WilFeatureTraits_Feature_46635544>::GetImpl(void)'::`2'::impl
0x1400a3e72  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400a3e77  call    ?s_IsCompanionDeviceAccount@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsCompanionDeviceAccount(void)
0x1400a3e7c  test    al, al
0x1400a3e7e  jnz     loc_1400A443B
0x1400a3e84  mov     ecx, 0Dh; dwOS
0x1400a3e89  call    cs:__imp_IsOS
0x1400a3e8f  test    eax, eax
0x1400a3e91  jnz     loc_1400A443B
0x1400a3e97  mov     dword ptr [rsp+0A8h+var_58], edi
0x1400a3e9b  lea     esi, [rax+4]
0x1400a3e9e  mov     [rsp+0A8h+var_60], esi
0x1400a3ea2  lea     rax, [rsp+0A8h+var_60]
0x1400a3ea7  mov     [rsp+0A8h+pcbData], rax; pcbData
0x1400a3eac  lea     rax, [rsp+0A8h+var_58]
0x1400a3eb1  mov     [rsp+0A8h+pvData], rax; pvData
0x1400a3eb6  mov     [rsp+0A8h+pdwType], rdi; pdwType
0x1400a3ebb  mov     r9d, 10010h; dwFlags
0x1400a3ec1  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400a3ec8  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1400a3ecf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400a3ed6  call    cs:__imp_RegGetValueW
0x1400a3edc  test    eax, eax
0x1400a3ede  jz      short loc_1400A3F1E
0x1400a3ee0  mov     [rsp+0A8h+var_60], esi
0x1400a3ee4  lea     rax, [rsp+0A8h+var_60]
0x1400a3ee9  mov     [rsp+0A8h+pcbData], rax; pcbData
0x1400a3eee  lea     rax, [rsp+0A8h+var_58]
0x1400a3ef3  mov     [rsp+0A8h+pvData], rax; pvData
0x1400a3ef8  mov     [rsp+0A8h+pdwType], rdi; int
0x1400a3efd  mov     r9d, 20010010h; dwFlags
0x1400a3f03  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400a3f0a  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a3f11  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400a3f18  call    cs:__imp_RegGetValueW
0x1400a3f1e  cmp     dword ptr [rsp+0A8h+var_58], edi
0x1400a3f22  jnz     loc_1400A443B
0x1400a3f28  call    ?IsSharedPCMode@@YA_NXZ; IsSharedPCMode(void)
0x1400a3f2d  test    al, al
0x1400a3f2f  jnz     loc_1400A443B
0x1400a3f35  call    ?s_IsExplorerRestart@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsExplorerRestart(void)
0x1400a3f3a  test    al, al
0x1400a3f3c  jnz     loc_1400A443B
0x1400a3f42  call    ?IsShellLauncherEnabledForCurrentUser@@YA_NXZ; IsShellLauncherEnabledForCurrentUser(void)
0x1400a3f47  test    al, al
0x1400a3f49  jnz     loc_1400A443B
0x1400a3f4f  call    ?IsPreserveOobeAutologonCredentialsSet@@YA_NXZ; IsPreserveOobeAutologonCredentialsSet(void)
0x1400a3f54  test    al, al
0x1400a3f56  jnz     loc_1400A443B
0x1400a3f5c  call    ?IsUnattendedAutoLogonSet@@YA_NXZ; IsUnattendedAutoLogonSet(void)
0x1400a3f61  test    al, al
0x1400a3f63  jnz     loc_1400A443B
0x1400a3f69  mov     rsi, 0FFFFFFFFFFFFFFFCh
0x1400a3f70  mov     rcx, rsi; TokenHandle
0x1400a3f73  call    IsUserAssignedAccessSingleApp
0x1400a3f78  test    eax, eax
0x1400a3f7a  jnz     loc_1400A443B
0x1400a3f80  mov     rcx, rsi; TokenHandle
0x1400a3f83  call    IsUserAssignedAccessMultiApp
0x1400a3f88  test    eax, eax
0x1400a3f8a  jnz     loc_1400A443B
0x1400a3f90  mov     rcx, rsi; TokenHandle
0x1400a3f93  call    IsUserAssignedAccessSingleAppClassicApp
0x1400a3f98  test    eax, eax
0x1400a3f9a  jnz     loc_1400A443B
0x1400a3fa0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48986217@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217> `wil::Feature<__WilFeatureTraits_Feature_48986217>::GetImpl(void)'::`2'::impl
0x1400a3fa7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::__private_IsEnabled(void)
0x1400a3fac  test    al, al
0x1400a3fae  jz      short loc_1400A3FBD
0x1400a3fb0  call    ?s_IsDJorAADJUser@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsDJorAADJUser(void)
0x1400a3fb5  test    al, al
0x1400a3fb7  jnz     loc_1400A443B
0x1400a3fbd  mov     qword ptr [rsp+0A8h+var_60], rdi
0x1400a3fc2  mov     qword ptr [rsp+0A8h+var_40.dwLowDateTime], rdi
0x1400a3fc7  mov     [rsp+0A8h+var_18], rdi
0x1400a3fcf  mov     r9d, 47h ; 'G'; unsigned int
0x1400a3fd5  lea     r8d, [r9+1]; unsigned int
0x1400a3fd9  lea     rdx, ?RuntimeClass_WindowsUdk_Services_UnifiedConsent_WindowsAccountSyncConsentCoordinator@@3QBGB; "WindowsUdk.Services.UnifiedConsent.Wind"...
0x1400a3fe0  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1400a3fe5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400a3fea  nop
0x1400a3feb  lea     r8, [rsp+0A8h+var_40]
0x1400a3ff0  lea     rdx, _GUID_d62d507d_d865_520b_8850_7245169004c6
0x1400a3ff7  mov     rcx, [rsp+0A8h+var_18]
0x1400a3fff  call    cs:__imp_RoGetActivationFactory
0x1400a4005  mov     rcx, [rsp+0A8h]; this
0x1400a400d  test    eax, eax
0x1400a400f  jns     short loc_1400A4026
0x1400a4011  mov     r9d, eax; char *
0x1400a4014  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a401b  mov     edx, 2007h; void *
0x1400a4020  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a4026  mov     [rsp+0A8h+var_48], rdi
0x1400a402b  mov     rcx, qword ptr [rsp+0A8h+var_40.dwLowDateTime]
0x1400a4030  mov     rax, [rcx]
0x1400a4033  mov     [rsp+0A8h+var_48], rdi
0x1400a4038  lea     rdx, [rsp+0A8h+var_48]
0x1400a403d  mov     rax, [rax+30h]
0x1400a4041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4046  mov     rcx, [rsp+0A8h]; this
0x1400a404e  test    eax, eax
0x1400a4050  jns     short loc_1400A4066
0x1400a4052  mov     r9d, eax; char *
0x1400a4055  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a405c  mov     edx, 200Ah; void *
0x1400a4061  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a4066  mov     [rsp+0A8h+var_50], rdi
0x1400a406b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48986217@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217> `wil::Feature<__WilFeatureTraits_Feature_48986217>::GetImpl(void)'::`2'::impl
0x1400a4072  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::__private_IsEnabled(void)
0x1400a4077  test    al, al
0x1400a4079  jz      loc_1400A4145
0x1400a407f  lea     rdx, [rsp+0A8h+var_58]
0x1400a4084  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::GetCachedVariantState(void)
0x1400a4089  mov     ebx, dword ptr [rsp+0A8h+var_58+4]
0x1400a408d  mov     byte ptr [rsp+0A8h+var_66], dil
0x1400a4092  mov     rcx, [rsp+0A8h+var_50]
0x1400a4097  mov     [rsp+0A8h+var_50], rdi
0x1400a409c  test    rcx, rcx
0x1400a409f  jz      short loc_1400A40AE
0x1400a40a1  mov     rax, [rcx]
0x1400a40a4  mov     rax, [rax+10h]
0x1400a40a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a40ad  nop
0x1400a40ae  lea     rax, [rsp+0A8h+var_66]
0x1400a40b3  mov     [rsp+0A8h+pdwType], rax; int
0x1400a40b8  mov     r9d, ebx
0x1400a40bb  lea     rdx, [rsp+0A8h+var_50]
0x1400a40c0  mov     rcx, [rsp+0A8h+var_48]
0x1400a40c5  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@Foundation@Windows@@PEAPEAUIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@Foundation@Windows@@PEAPEAUIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *> *,WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator * *>(Windows::Foundation::IAsyncOperation<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *> *,WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator * *,tagCOWAIT_FLAGS,ulong,bool *)
0x1400a40ca  mov     rcx, [rsp+0A8h]; this
0x1400a40d2  test    eax, eax
0x1400a40d4  jns     short loc_1400A40EA
0x1400a40d6  mov     r9d, eax; char *
0x1400a40d9  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a40e0  mov     edx, 2012h; void *
0x1400a40e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a40ea  cmp     byte ptr [rsp+0A8h+var_66], dil
0x1400a40ef  jz      loc_1400A41AA
0x1400a40f5  mov     dword ptr [rsp+0A8h+var_58], ebx
0x1400a40f9  lea     rcx, [rsp+0A8h+var_58]
0x1400a40fe  call    ??$NthWASCCoordinatorTimeout@I@NthWASCConsentTelemetry@@SAX$$QEAI@Z; NthWASCConsentTelemetry::NthWASCCoordinatorTimeout<uint>(uint &&)
0x1400a4103  mov     [rsp+0A8h+var_67], dil
0x1400a4108  lea     rcx, [rsp+0A8h+var_67]
0x1400a410d  call    ??$ShouldShowNthWASCConsentForUser@_N@NthWASCConsentTelemetry@@SAX$$QEA_N@Z; NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(bool &&)
0x1400a4112  nop
0x1400a4113  lea     rcx, [rsp+0A8h+var_50]
0x1400a4118  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a411d  nop
0x1400a411e  lea     rcx, [rsp+0A8h+var_48]
0x1400a4123  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a4128  nop
0x1400a4129  lea     rcx, [rsp+0A8h+var_40]
0x1400a412e  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a4133  nop
0x1400a4134  lea     rcx, [rsp+0A8h+var_60]
0x1400a4139  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a413e  xor     al, al
0x1400a4140  jmp     loc_1400A448D
0x1400a4145  mov     rdx, [rsp+0A8h+var_48]
0x1400a414a  lea     rcx, [rsp+0A8h+var_58]
0x1400a414f  call    ??$wait_for_completion@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@V?$ComPtr@UIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *,Microsoft::WRL::ComPtr<WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator>>(Windows::Foundation::IAsyncOperation<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *> *,tagCOWAIT_FLAGS)
0x1400a4154  mov     rcx, [rsp+0A8h+var_58]
0x1400a4159  mov     [rsp+0A8h+var_58], rdi
0x1400a415e  mov     rbx, [rsp+0A8h+var_50]
0x1400a4163  mov     [rsp+0A8h+var_50], rcx
0x1400a4168  test    rcx, rcx
0x1400a416b  jz      short loc_1400A4179
0x1400a416d  mov     rax, [rcx]
0x1400a4170  mov     rax, [rax+8]
0x1400a4174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4179  test    rbx, rbx
0x1400a417c  jz      short loc_1400A418E
0x1400a417e  mov     rax, [rbx]
0x1400a4181  mov     rcx, rbx
0x1400a4184  mov     rax, [rax+10h]
0x1400a4188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a418d  nop
0x1400a418e  mov     rcx, [rsp+0A8h+var_58]
0x1400a4193  test    rcx, rcx
0x1400a4196  jz      short loc_1400A41AA
0x1400a4198  mov     [rsp+0A8h+var_58], rdi
0x1400a419d  mov     rax, [rcx]
0x1400a41a0  mov     rax, [rax+10h]
0x1400a41a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a41a9  nop
0x1400a41aa  mov     dl, 1
0x1400a41ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_46635544@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544> `wil::Feature<__WilFeatureTraits_Feature_46635544>::GetImpl(void)'::`2'::impl
0x1400a41b3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400a41b8  mov     rbx, [rsp+0A8h+var_50]
0x1400a41bd  test    rbx, rbx
0x1400a41c0  jnz     short loc_1400A4204
0x1400a41c2  mov     [rsp+0A8h+var_67], dil
0x1400a41c7  lea     rcx, [rsp+0A8h+var_67]
0x1400a41cc  call    ??$ShouldShowNthWASCConsentForUser@_N@NthWASCConsentTelemetry@@SAX$$QEA_N@Z; NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(bool &&)
0x1400a41d1  nop
0x1400a41d2  lea     rcx, [rsp+0A8h+var_50]
0x1400a41d7  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a41dc  nop
0x1400a41dd  lea     rcx, [rsp+0A8h+var_48]
0x1400a41e2  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a41e7  nop
0x1400a41e8  lea     rcx, [rsp+0A8h+var_40]
0x1400a41ed  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a41f2  nop
0x1400a41f3  lea     rcx, [rsp+0A8h+var_60]
0x1400a41f8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a41fd  xor     al, al
0x1400a41ff  jmp     loc_1400A448D
0x1400a4204  mov     rax, [rbx]
0x1400a4207  mov     rsi, [rax+30h]
0x1400a420b  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x1400a4210  mov     qword ptr [rsp+0A8h+var_60], rdi
0x1400a4215  test    rcx, rcx
0x1400a4218  jz      short loc_1400A4227
0x1400a421a  mov     rax, [rcx]
0x1400a421d  mov     rax, [rax+10h]
0x1400a4221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4226  nop
0x1400a4227  mov     [rsp+0A8h+var_18], rdi
0x1400a422f  mov     r9d, 0Bh; unsigned int
0x1400a4235  lea     r8d, [r9+1]; unsigned int
0x1400a4239  lea     rdx, aDatasharing; "DataSharing"
0x1400a4240  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1400a4245  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400a424a  nop
0x1400a424b  lea     r8, [rsp+0A8h+var_60]
0x1400a4250  mov     rdx, [rsp+0A8h+var_18]
0x1400a4258  mov     rcx, rbx
0x1400a425b  mov     rax, rsi
0x1400a425e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4263  mov     rcx, [rsp+0A8h]; this
0x1400a426b  test    eax, eax
0x1400a426d  jns     short loc_1400A4284
0x1400a426f  mov     r9d, eax; char *
0x1400a4272  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a4279  mov     edx, 2026h; void *
0x1400a427e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a4284  lea     rcx, [rsp+0A8h+var_50]
0x1400a4289  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a428e  nop
0x1400a428f  lea     rcx, [rsp+0A8h+var_48]
0x1400a4294  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a4299  nop
0x1400a429a  lea     rcx, [rsp+0A8h+var_40]
0x1400a429f  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a42a4  nop
0x1400a42a5  mov     bl, 1
0x1400a42a7  mov     [rsp+0A8h+var_68], bl
0x1400a42ab  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x1400a42b0  test    rcx, rcx
0x1400a42b3  jz      loc_1400A442B
0x1400a42b9  mov     byte ptr [rsp+0A8h+var_66], dil
0x1400a42be  mov     rax, [rcx]
  ... truncated ...
```
