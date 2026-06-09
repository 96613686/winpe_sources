# CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthWASC(LogonTypeFlags)

- ea: `0x1400aa174`
- end: `0x1400aa8ab`
- name: `?s_shouldLaunchCloudExperienceHostForNthWASC@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z`
- size: `1847`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1400a08d0`

## callees

- `0x140005aa8`
- `0x140006edc`
- `0x140012800`
- `0x14001b2c8`
- `0x14001e1b0`
- `0x14001e1e0`
- `0x14001e6a8`
- `0x14001e750`
- `0x14001e9bc`
- `0x140026320`
- `0x140026964`
- `0x140048514`
- `0x14007c1f4`
- `0x14007ee60`
- `0x14007ffec`
- `0x140082820`
- `0x140086c1c`
- `0x140087498`
- `0x140087994`
- `0x14008f4a8`
- `0x1400aa174`
- `0x1400aa8b4`
- `0x1400aa924`
- `0x1400aa96c`
- `0x1400aa9a8`
- `0x1400af3c4`
- `0x14010e160`
- `0x140141870`
- `0x140143830`
- `0x140193bcc`
- `0x140193c28`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400aa2b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400aa2f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400aa2b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400aa2f8`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1400aa25d`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1400aa25d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400aa3e2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400aa3e2`

## string_xrefs

- `0x1400aa3fd`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa43e`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa4c2`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa65b`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa6c7`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa70d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa748`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa783`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa7e7`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa863`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400aa2a2`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1400aa2ea`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1400aa3bc`: `WindowsUdk.Services.UnifiedConsent.WindowsAccountSyncConsentCoordinator`

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
      || (unsigned int)IsCurrentUserAssignedAccessSingleAppClassicApp()
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
        (void *)0x2021,
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
        (void *)0x2024,
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
          (void *)0x202C,
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
        (void *)0x2040,
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
          (void *)0x205E,
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
            (void *)0x2063,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v25,
            pdwType);
        v36 = 0;
        v26 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pcbData + 64LL))(*(_QWORD *)pcbData, &v36);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2066,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v26,
            pdwType);
        v34 = 0;
        v27 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)pcbData + 72LL))(*(_QWORD *)pcbData, &v34);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2069,
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
            (void *)0x2079,
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
        (void *)0x208C,
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
          (void *)0x2097,
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
0x1400aa174  mov     [rsp+arg_0], rbx
0x1400aa179  mov     [rsp+arg_8], rsi
0x1400aa17e  push    rdi
0x1400aa17f  sub     rsp, 0A0h
0x1400aa186  mov     rax, cs:__security_cookie
0x1400aa18d  xor     rax, rsp
0x1400aa190  mov     [rsp+0A8h+var_10], rax
0x1400aa198  mov     esi, ecx
0x1400aa19a  xor     edi, edi
0x1400aa19c  mov     bl, dil
0x1400aa19f  mov     [rsp+0A8h+var_68], bl
0x1400aa1a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_44077960@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_44077960@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_44077960> `wil::Feature<__WilFeatureTraits_Feature_44077960>::GetImpl(void)'::`2'::impl
0x1400aa1aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_44077960@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_44077960>::__private_IsEnabled(void)
0x1400aa1af  test    al, al
0x1400aa1b1  jz      loc_1400AA874
0x1400aa1b7  mov     qword ptr [rsp+0A8h+var_38.dwLowDateTime], rdi
0x1400aa1bc  lea     r9, [rsp+0A8h+var_38]; struct _FILETIME *
0x1400aa1c1  lea     r8, aNthwasctimesta; "NthWascTimestamp"
0x1400aa1c8  lea     rdx, aSoftwareMicros_99; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400aa1cf  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1400aa1d6  call    ?SHRegGetFILETIME@@YAJPEAUHKEY__@@PEBG1PEAU_FILETIME@@@Z; SHRegGetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME *)
0x1400aa1db  test    eax, eax
0x1400aa1dd  js      short loc_1400AA231
0x1400aa1df  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x1400aa1e4  mov     r8, rax
0x1400aa1e7  shr     r8, 20h
0x1400aa1eb  mov     ecx, [rsp+0A8h+var_38.dwHighDateTime]
0x1400aa1ef  sub     r8, rcx
0x1400aa1f2  shl     r8, 20h
0x1400aa1f6  mov     ecx, [rsp+0A8h+var_38.dwLowDateTime]
0x1400aa1fa  sub     r8, rcx
0x1400aa1fd  mov     eax, eax
0x1400aa1ff  add     rax, r8
0x1400aa202  xor     edx, edx
0x1400aa204  mov     rcx, 0C92A69C000h
0x1400aa20e  div     rcx
0x1400aa211  cmp     eax, 7
0x1400aa214  ja      short loc_1400AA231
0x1400aa216  call    ?NthWASCFrequencyBlock@NthWASCConsentTelemetry@@SAXXZ; NthWASCConsentTelemetry::NthWASCFrequencyBlock(void)
0x1400aa21b  mov     [rsp+0A8h+var_67], dil
0x1400aa220  lea     rcx, [rsp+0A8h+var_67]
0x1400aa225  call    ??$ShouldShowNthWASCConsentForUser@_N@NthWASCConsentTelemetry@@SAX$$QEA_N@Z; NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(bool &&)
0x1400aa22a  xor     al, al
0x1400aa22c  jmp     loc_1400AA876
0x1400aa231  test    esi, 3308h
0x1400aa237  jnz     loc_1400AA824
0x1400aa23d  mov     dl, 1
0x1400aa23f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_46635544@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544> `wil::Feature<__WilFeatureTraits_Feature_46635544>::GetImpl(void)'::`2'::impl
0x1400aa246  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400aa24b  call    ?s_IsCompanionDeviceAccount@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsCompanionDeviceAccount(void)
0x1400aa250  test    al, al
0x1400aa252  jnz     loc_1400AA824
0x1400aa258  mov     ecx, 0Dh; dwOS
0x1400aa25d  call    cs:__imp_IsOS
0x1400aa264  nop     dword ptr [rax+rax+00h]
0x1400aa269  test    eax, eax
0x1400aa26b  jnz     loc_1400AA824
0x1400aa271  mov     dword ptr [rsp+0A8h+var_58], edi
0x1400aa275  lea     esi, [rax+4]
0x1400aa278  mov     [rsp+0A8h+var_60], esi
0x1400aa27c  lea     rax, [rsp+0A8h+var_60]
0x1400aa281  mov     [rsp+0A8h+pcbData], rax; pcbData
0x1400aa286  lea     rax, [rsp+0A8h+var_58]
0x1400aa28b  mov     [rsp+0A8h+pvData], rax; pvData
0x1400aa290  mov     [rsp+0A8h+pdwType], rdi; pdwType
0x1400aa295  mov     r9d, 10010h; dwFlags
0x1400aa29b  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400aa2a2  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1400aa2a9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400aa2b0  call    cs:__imp_RegGetValueW
0x1400aa2b7  nop     dword ptr [rax+rax+00h]
0x1400aa2bc  test    eax, eax
0x1400aa2be  jz      short loc_1400AA304
0x1400aa2c0  mov     [rsp+0A8h+var_60], esi
0x1400aa2c4  lea     rax, [rsp+0A8h+var_60]
0x1400aa2c9  mov     [rsp+0A8h+pcbData], rax; pcbData
0x1400aa2ce  lea     rax, [rsp+0A8h+var_58]
0x1400aa2d3  mov     [rsp+0A8h+pvData], rax; pvData
0x1400aa2d8  mov     [rsp+0A8h+pdwType], rdi; int
0x1400aa2dd  mov     r9d, 20010010h; dwFlags
0x1400aa2e3  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400aa2ea  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400aa2f1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400aa2f8  call    cs:__imp_RegGetValueW
0x1400aa2ff  nop     dword ptr [rax+rax+00h]
0x1400aa304  cmp     dword ptr [rsp+0A8h+var_58], edi
0x1400aa308  jnz     loc_1400AA824
0x1400aa30e  call    ?IsSharedPCMode@@YA_NXZ; IsSharedPCMode(void)
0x1400aa313  test    al, al
0x1400aa315  jnz     loc_1400AA824
0x1400aa31b  call    ?s_IsExplorerRestart@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsExplorerRestart(void)
0x1400aa320  test    al, al
0x1400aa322  jnz     loc_1400AA824
0x1400aa328  call    ?IsShellLauncherEnabledForCurrentUser@@YA_NXZ; IsShellLauncherEnabledForCurrentUser(void)
0x1400aa32d  test    al, al
0x1400aa32f  jnz     loc_1400AA824
0x1400aa335  call    ?IsPreserveOobeAutologonCredentialsSet@@YA_NXZ; IsPreserveOobeAutologonCredentialsSet(void)
0x1400aa33a  test    al, al
0x1400aa33c  jnz     loc_1400AA824
0x1400aa342  call    ?IsUnattendedAutoLogonSet@@YA_NXZ; IsUnattendedAutoLogonSet(void)
0x1400aa347  test    al, al
0x1400aa349  jnz     loc_1400AA824
0x1400aa34f  mov     rsi, 0FFFFFFFFFFFFFFFCh
0x1400aa356  mov     rcx, rsi; TokenHandle
0x1400aa359  call    IsUserAssignedAccessSingleApp
0x1400aa35e  test    eax, eax
0x1400aa360  jnz     loc_1400AA824
0x1400aa366  mov     rcx, rsi; TokenHandle
0x1400aa369  call    IsUserAssignedAccessMultiApp
0x1400aa36e  test    eax, eax
0x1400aa370  jnz     loc_1400AA824
0x1400aa376  call    IsCurrentUserAssignedAccessSingleAppClassicApp
0x1400aa37b  test    eax, eax
0x1400aa37d  jnz     loc_1400AA824
0x1400aa383  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48986217@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217> `wil::Feature<__WilFeatureTraits_Feature_48986217>::GetImpl(void)'::`2'::impl
0x1400aa38a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::__private_IsEnabled(void)
0x1400aa38f  test    al, al
0x1400aa391  jz      short loc_1400AA3A0
0x1400aa393  call    ?s_IsDJorAADJUser@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsDJorAADJUser(void)
0x1400aa398  test    al, al
0x1400aa39a  jnz     loc_1400AA824
0x1400aa3a0  mov     qword ptr [rsp+0A8h+var_60], rdi
0x1400aa3a5  mov     qword ptr [rsp+0A8h+var_40.dwLowDateTime], rdi
0x1400aa3aa  mov     [rsp+0A8h+var_18], rdi
0x1400aa3b2  mov     r9d, 47h ; 'G'; unsigned int
0x1400aa3b8  lea     r8d, [r9+1]; unsigned int
0x1400aa3bc  lea     rdx, ?RuntimeClass_WindowsUdk_Services_UnifiedConsent_WindowsAccountSyncConsentCoordinator@@3QBGB; "WindowsUdk.Services.UnifiedConsent.Wind"...
0x1400aa3c3  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1400aa3c8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400aa3cd  nop
0x1400aa3ce  lea     r8, [rsp+0A8h+var_40]
0x1400aa3d3  lea     rdx, _GUID_d62d507d_d865_520b_8850_7245169004c6
0x1400aa3da  mov     rcx, [rsp+0A8h+var_18]
0x1400aa3e2  call    cs:__imp_RoGetActivationFactory
0x1400aa3e9  nop     dword ptr [rax+rax+00h]
0x1400aa3ee  mov     rcx, [rsp+0A8h]; this
0x1400aa3f6  test    eax, eax
0x1400aa3f8  jns     short loc_1400AA40F
0x1400aa3fa  mov     r9d, eax; char *
0x1400aa3fd  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400aa404  mov     edx, 2021h; void *
0x1400aa409  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400aa40f  mov     [rsp+0A8h+var_48], rdi
0x1400aa414  mov     rcx, qword ptr [rsp+0A8h+var_40.dwLowDateTime]
0x1400aa419  mov     rax, [rcx]
0x1400aa41c  mov     [rsp+0A8h+var_48], rdi
0x1400aa421  lea     rdx, [rsp+0A8h+var_48]
0x1400aa426  mov     rax, [rax+30h]
0x1400aa42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa42f  mov     rcx, [rsp+0A8h]; this
0x1400aa437  test    eax, eax
0x1400aa439  jns     short loc_1400AA44F
0x1400aa43b  mov     r9d, eax; char *
0x1400aa43e  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400aa445  mov     edx, 2024h; void *
0x1400aa44a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400aa44f  mov     [rsp+0A8h+var_50], rdi
0x1400aa454  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48986217@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217> `wil::Feature<__WilFeatureTraits_Feature_48986217>::GetImpl(void)'::`2'::impl
0x1400aa45b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::__private_IsEnabled(void)
0x1400aa460  test    al, al
0x1400aa462  jz      loc_1400AA52E
0x1400aa468  lea     rdx, [rsp+0A8h+var_58]
0x1400aa46d  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_48986217@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48986217>::GetCachedVariantState(void)
0x1400aa472  mov     ebx, dword ptr [rsp+0A8h+var_58+4]
0x1400aa476  mov     byte ptr [rsp+0A8h+var_66], dil
0x1400aa47b  mov     rcx, [rsp+0A8h+var_50]
0x1400aa480  mov     [rsp+0A8h+var_50], rdi
0x1400aa485  test    rcx, rcx
0x1400aa488  jz      short loc_1400AA497
0x1400aa48a  mov     rax, [rcx]
0x1400aa48d  mov     rax, [rax+10h]
0x1400aa491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa496  nop
0x1400aa497  lea     rax, [rsp+0A8h+var_66]
0x1400aa49c  mov     [rsp+0A8h+pdwType], rax; int
0x1400aa4a1  mov     r9d, ebx
0x1400aa4a4  lea     rdx, [rsp+0A8h+var_50]
0x1400aa4a9  mov     rcx, [rsp+0A8h+var_48]
0x1400aa4ae  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@Foundation@Windows@@PEAPEAUIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@Foundation@Windows@@PEAPEAUIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *> *,WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator * *>(Windows::Foundation::IAsyncOperation<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *> *,WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator * *,tagCOWAIT_FLAGS,ulong,bool *)
0x1400aa4b3  mov     rcx, [rsp+0A8h]; this
0x1400aa4bb  test    eax, eax
0x1400aa4bd  jns     short loc_1400AA4D3
0x1400aa4bf  mov     r9d, eax; char *
0x1400aa4c2  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400aa4c9  mov     edx, 202Ch; void *
0x1400aa4ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400aa4d3  cmp     byte ptr [rsp+0A8h+var_66], dil
0x1400aa4d8  jz      loc_1400AA593
0x1400aa4de  mov     dword ptr [rsp+0A8h+var_58], ebx
0x1400aa4e2  lea     rcx, [rsp+0A8h+var_58]
0x1400aa4e7  call    ??$NthWASCCoordinatorTimeout@I@NthWASCConsentTelemetry@@SAX$$QEAI@Z; NthWASCConsentTelemetry::NthWASCCoordinatorTimeout<uint>(uint &&)
0x1400aa4ec  mov     [rsp+0A8h+var_67], dil
0x1400aa4f1  lea     rcx, [rsp+0A8h+var_67]
0x1400aa4f6  call    ??$ShouldShowNthWASCConsentForUser@_N@NthWASCConsentTelemetry@@SAX$$QEA_N@Z; NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(bool &&)
0x1400aa4fb  nop
0x1400aa4fc  lea     rcx, [rsp+0A8h+var_50]
0x1400aa501  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa506  nop
0x1400aa507  lea     rcx, [rsp+0A8h+var_48]
0x1400aa50c  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa511  nop
0x1400aa512  lea     rcx, [rsp+0A8h+var_40]
0x1400aa517  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa51c  nop
0x1400aa51d  lea     rcx, [rsp+0A8h+var_60]
0x1400aa522  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa527  xor     al, al
0x1400aa529  jmp     loc_1400AA876
0x1400aa52e  mov     rdx, [rsp+0A8h+var_48]
0x1400aa533  lea     rcx, [rsp+0A8h+var_58]
0x1400aa538  call    ??$wait_for_completion@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@V?$ComPtr@UIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVWindowsAccountSyncConsentCoordinator@UnifiedConsent@Services@WindowsUdk@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *,Microsoft::WRL::ComPtr<WindowsUdk::Services::UnifiedConsent::IWindowsAccountSyncConsentCoordinator>>(Windows::Foundation::IAsyncOperation<WindowsUdk::Services::UnifiedConsent::WindowsAccountSyncConsentCoordinator *> *,tagCOWAIT_FLAGS)
0x1400aa53d  mov     rcx, [rsp+0A8h+var_58]
0x1400aa542  mov     [rsp+0A8h+var_58], rdi
0x1400aa547  mov     rbx, [rsp+0A8h+var_50]
0x1400aa54c  mov     [rsp+0A8h+var_50], rcx
0x1400aa551  test    rcx, rcx
0x1400aa554  jz      short loc_1400AA562
0x1400aa556  mov     rax, [rcx]
0x1400aa559  mov     rax, [rax+8]
0x1400aa55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa562  test    rbx, rbx
0x1400aa565  jz      short loc_1400AA577
0x1400aa567  mov     rax, [rbx]
0x1400aa56a  mov     rcx, rbx
0x1400aa56d  mov     rax, [rax+10h]
0x1400aa571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa576  nop
0x1400aa577  mov     rcx, [rsp+0A8h+var_58]
0x1400aa57c  test    rcx, rcx
0x1400aa57f  jz      short loc_1400AA593
0x1400aa581  mov     [rsp+0A8h+var_58], rdi
0x1400aa586  mov     rax, [rcx]
0x1400aa589  mov     rax, [rax+10h]
0x1400aa58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa592  nop
0x1400aa593  mov     dl, 1
0x1400aa595  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_46635544@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544> `wil::Feature<__WilFeatureTraits_Feature_46635544>::GetImpl(void)'::`2'::impl
0x1400aa59c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_46635544@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46635544>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400aa5a1  mov     rbx, [rsp+0A8h+var_50]
0x1400aa5a6  test    rbx, rbx
0x1400aa5a9  jnz     short loc_1400AA5ED
0x1400aa5ab  mov     [rsp+0A8h+var_67], dil
0x1400aa5b0  lea     rcx, [rsp+0A8h+var_67]
0x1400aa5b5  call    ??$ShouldShowNthWASCConsentForUser@_N@NthWASCConsentTelemetry@@SAX$$QEA_N@Z; NthWASCConsentTelemetry::ShouldShowNthWASCConsentForUser<bool>(bool &&)
0x1400aa5ba  nop
0x1400aa5bb  lea     rcx, [rsp+0A8h+var_50]
0x1400aa5c0  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa5c5  nop
0x1400aa5c6  lea     rcx, [rsp+0A8h+var_48]
0x1400aa5cb  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa5d0  nop
0x1400aa5d1  lea     rcx, [rsp+0A8h+var_40]
0x1400aa5d6  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa5db  nop
0x1400aa5dc  lea     rcx, [rsp+0A8h+var_60]
0x1400aa5e1  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa5e6  xor     al, al
0x1400aa5e8  jmp     loc_1400AA876
0x1400aa5ed  mov     rax, [rbx]
0x1400aa5f0  mov     rsi, [rax+30h]
0x1400aa5f4  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x1400aa5f9  mov     qword ptr [rsp+0A8h+var_60], rdi
0x1400aa5fe  test    rcx, rcx
0x1400aa601  jz      short loc_1400AA610
0x1400aa603  mov     rax, [rcx]
0x1400aa606  mov     rax, [rax+10h]
0x1400aa60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa60f  nop
0x1400aa610  mov     [rsp+0A8h+var_18], rdi
0x1400aa618  mov     r9d, 0Bh; unsigned int
0x1400aa61e  lea     r8d, [r9+1]; unsigned int
0x1400aa622  lea     rdx, aDatasharing; "DataSharing"
0x1400aa629  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x1400aa62e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400aa633  nop
0x1400aa634  lea     r8, [rsp+0A8h+var_60]
0x1400aa639  mov     rdx, [rsp+0A8h+var_18]
0x1400aa641  mov     rcx, rbx
0x1400aa644  mov     rax, rsi
0x1400aa647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa64c  mov     rcx, [rsp+0A8h]; this
0x1400aa654  test    eax, eax
0x1400aa656  jns     short loc_1400AA66D
0x1400aa658  mov     r9d, eax; char *
0x1400aa65b  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400aa662  mov     edx, 2040h; void *
0x1400aa667  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400aa66d  lea     rcx, [rsp+0A8h+var_50]
0x1400aa672  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa677  nop
0x1400aa678  lea     rcx, [rsp+0A8h+var_48]
0x1400aa67d  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa682  nop
0x1400aa683  lea     rcx, [rsp+0A8h+var_40]
0x1400aa688  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400aa68d  nop
0x1400aa68e  mov     bl, 1
0x1400aa690  mov     [rsp+0A8h+var_68], bl
0x1400aa694  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x1400aa699  test    rcx, rcx
  ... truncated ...
```
