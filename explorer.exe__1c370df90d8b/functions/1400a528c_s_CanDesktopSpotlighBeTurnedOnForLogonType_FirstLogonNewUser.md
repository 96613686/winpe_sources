# s_CanDesktopSpotlighBeTurnedOnForLogonType_FirstLogonNewUser

- ea: `0x1400a528c`
- end: `0x1400a56da`
- name: `s_CanDesktopSpotlighBeTurnedOnForLogonType_FirstLogonNewUser`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400a4d00`

## callees

- `0x140013e6c`
- `0x14001eba8`
- `0x140033070`
- `0x140033a3c`
- `0x14003401c`
- `0x1400770ac`
- `0x1400817d8`
- `0x140081aa8`
- `0x1400a528c`
- `0x1400a56e0`
- `0x1400a56fc`
- `0x1400a5788`
- `0x1400a57c0`
- `0x1400a69d0`
- `0x1400a6ad8`
- `0x140137b2c`
- `0x140137bb4`
- `0x140137c3c`
- `0x140137cc4`
- `0x140137d4c`
- `0x140137dd4`
- `0x140137e5c`
- `0x140137ee4`
- `0x140137f6c`
- `0x1401a0374`
- `0x1401a16cc`
- `0x1401a5594`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400a535e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400a535e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400a5338`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400a5338`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a5401`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a5440`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a5401`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a5440`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1400a5323`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1400a5323`

## string_xrefs

- `0x1400a5349`: `shell\lib\logontasks\DesktopSpotlightLogonTaskHelper.h`
- `0x1400a5699`: `shell\lib\logontasks\DesktopSpotlightLogonTaskHelper.h`
- `0x1400a53f0`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1400a5436`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_CanDesktopSpotlighBeTurnedOnForLogonType_FirstLogonNewUser(__int16 a1)
{
  LSTATUS v2; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  _QWORD v16[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY phkResult; // [rsp+78h] [rbp+28h] BYREF
  __int64 pcbData; // [rsp+80h] [rbp+30h] BYREF
  int pvData; // [rsp+88h] [rbp+38h] BYREF

  LODWORD(phkResult) = isDesktopSpotlightEnabledThroughRegistry(&phkResult);
  if ( (_DWORD)phkResult )
  {
    tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>>(v16);
    if ( (a1 & 0x3308) != 0 )
    {
      v4 = 1;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                              v16,
                              &pcbData)
               + 274LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
      DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[20],long &>(v5, &phkResult);
    }
    else
    {
      pvData = 0;
      v4 = 4;
      LODWORD(pcbData) = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Enabled",
             0x10010u,
             0,
             &pvData,
             (LPDWORD)&pcbData) )
      {
        LODWORD(pcbData) = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
          L"Enabled",
          0x20010010u,
          0,
          &pvData,
          (LPDWORD)&pcbData);
      }
      if ( pvData )
      {
        v4 = 3;
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 275LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[15],long &>(
          L"RetailDemoMode",
          &phkResult);
      }
      else if ( (unsigned int)IsUserAssignedAccessSingleApp((HANDLE)0xFFFFFFFFFFFFFFFCLL) )
      {
        v4 = 5;
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 277LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[39],long &>(
          v6,
          &phkResult);
      }
      else if ( IsUserAssignedAccessMultiApp((HANDLE)0xFFFFFFFFFFFFFFFCLL) )
      {
        v4 = 7;
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 278LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[38],long &>(
          v7,
          &phkResult);
      }
      else if ( IsUserAssignedAccessSingleAppClassicApp((HANDLE)0xFFFFFFFFFFFFFFFCLL) )
      {
        v4 = 6;
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 279LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[49],long &>(
          v8,
          &phkResult);
      }
      else if ( IsSharedPCMode() )
      {
        v4 = 8;
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 280LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[13],long &>(
          v9,
          &phkResult);
      }
      else if ( IsShellLauncherEnabledForCurrentUser() )
      {
        v4 = 9;
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 281LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[35],long &>(
          v10,
          &phkResult);
      }
      else if ( IsUnattendedAutoLogonSet() )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 276LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[24],long &>(
          v11,
          &phkResult);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation>::GetImpl'::`2'::impl) )
        {
          v4 = 0;
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                  v16,
                                  &pcbData)
                   + 276LL) = 0;
          tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                  v16,
                                  &pcbData)
                   + 282LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
          DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[33],long &>(
            v12,
            &phkResult);
        }
      }
      else
      {
        v4 = 0;
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                                v16,
                                &pcbData)
                 + 273LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&pcbData);
        DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[14],long &>(
          v13,
          &phkResult);
      }
    }
    v14 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
            L"SpotlightNotOnboardedReason",
            v4);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x488,
        (unsigned int)"shell\\lib\\logontasks\\DesktopSpotlightLogonTaskHelper.h",
        (const char *)(unsigned int)v14,
        pdwType);
    if ( v16[0] )
      tip2::details::shared_data<0,0,0>::complete_without_lock(v16[0] + 8LL);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>(v16);
    return v4 != 0 ? 0x80004005 : 0;
  }
  else
  {
    DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<unsigned short const (&)[15],long &>(
      L"UnexpectedCase",
      &phkResult);
    tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>>(&pcbData);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(
                            &pcbData,
                            &phkResult)
             + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(&phkResult);
    if ( pcbData )
      tip2::details::shared_data<0,0,0>::complete_without_lock(pcbData + 8);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason>::GetImpl'::`2'::impl) == 1 )
    {
      phkResult = 0;
      if ( !RegOpenKeyW(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
              &phkResult) )
      {
        v2 = RegDeleteValueW(phkResult, L"EnabledState");
        if ( v2 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x42F,
            (unsigned int)"shell\\lib\\logontasks\\DesktopSpotlightLogonTaskHelper.h",
            (const char *)(unsigned int)v2,
            pdwType);
        RegCloseKey(phkResult);
      }
    }
    wil::com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>(&pcbData);
    return 0;
  }
}

```

## disassembly

```asm
0x1400a528c  push    rbp
0x1400a528e  push    rbx
0x1400a528f  push    rsi
0x1400a5290  mov     rbp, rsp
0x1400a5293  sub     rsp, 50h
0x1400a5297  mov     ebx, ecx
0x1400a5299  lea     rcx, [rbp+phkResult]
0x1400a529d  call    isDesktopSpotlightEnabledThroughRegistry
0x1400a52a2  mov     dword ptr [rbp+phkResult], eax
0x1400a52a5  test    eax, eax
0x1400a52a7  jnz     loc_1400A5375
0x1400a52ad  lea     rdx, [rbp+phkResult]
0x1400a52b1  lea     rcx, aUnexpectedcase; "UnexpectedCase"
0x1400a52b8  call    ??$SpotlightNotOnboardedReasonV2@AEAY0P@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0P@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[15],long &>(ushort const (&)[15],long &)
0x1400a52bd  lea     rcx, [rbp+arg_10]
0x1400a52c1  call    ??$start@V?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>>(void)
0x1400a52c6  nop
0x1400a52c7  lea     rdx, [rbp+phkResult]
0x1400a52cb  lea     rcx, [rbp+arg_10]
0x1400a52cf  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a52d4  mov     rcx, [rax]
0x1400a52d7  mov     byte ptr [rcx+110h], 1
0x1400a52de  lea     rcx, [rbp+phkResult]
0x1400a52e2  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a52e7  mov     rcx, [rbp+arg_10]
0x1400a52eb  test    rcx, rcx
0x1400a52ee  jz      short loc_1400A52F9
0x1400a52f0  add     rcx, 8
0x1400a52f4  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1400a52f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason>::GetImpl(void)'::`2'::impl
0x1400a5300  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@@details@wil@@QEAA?AW4Variant_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason>::__private_GetVariant(wil::VariantReportingKind,bool)
0x1400a5305  cmp     al, 1
0x1400a5307  jnz     short loc_1400A5365
0x1400a5309  mov     [rbp+phkResult], 0
0x1400a5311  lea     r8, [rbp+phkResult]; phkResult
0x1400a5315  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a531c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a5323  call    cs:__imp_RegOpenKeyW
0x1400a5329  test    eax, eax
0x1400a532b  jnz     short loc_1400A5365
0x1400a532d  lea     rdx, aEnabledstate; "EnabledState"
0x1400a5334  mov     rcx, [rbp+phkResult]; hKey
0x1400a5338  call    cs:__imp_RegDeleteValueW
0x1400a533e  mov     rcx, [rbp+18h]; this
0x1400a5342  test    eax, eax
0x1400a5344  jns     short loc_1400A535A
0x1400a5346  mov     r9d, eax; char *
0x1400a5349  lea     r8, aShellLibLogont; "shell\\lib\\logontasks\\DesktopSpotligh"...
0x1400a5350  mov     edx, 42Fh; void *
0x1400a5355  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a535a  mov     rcx, [rbp+phkResult]; hKey
0x1400a535e  call    cs:__imp_RegCloseKey
0x1400a5364  nop
0x1400a5365  lea     rcx, [rbp+arg_10]
0x1400a5369  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>(void)
0x1400a536e  xor     eax, eax
0x1400a5370  jmp     loc_1400A56D2
0x1400a5375  lea     rcx, [rbp+var_10]
0x1400a5379  call    ??$start@V?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>>(void)
0x1400a537e  nop
0x1400a537f  test    ebx, 3308h
0x1400a5385  jz      short loc_1400A53B9
0x1400a5387  mov     ebx, 1
0x1400a538c  lea     rdx, [rbp+arg_10]
0x1400a5390  lea     rcx, [rbp+var_10]
0x1400a5394  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a5399  mov     rcx, [rax]
0x1400a539c  mov     [rcx+112h], bl
0x1400a53a2  lea     rcx, [rbp+arg_10]
0x1400a53a6  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a53ab  lea     rdx, [rbp+phkResult]
0x1400a53af  call    ??$SpotlightNotOnboardedReasonV2@AEAY0BE@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0BE@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[20],long &>(ushort const (&)[20],long &)
0x1400a53b4  jmp     loc_1400A5671
0x1400a53b9  mov     [rbp+arg_18], 0
0x1400a53c0  mov     ebx, 4
0x1400a53c5  mov     dword ptr [rbp+arg_10], ebx
0x1400a53c8  lea     rax, [rbp+arg_10]
0x1400a53cc  mov     [rsp+50h+pcbData], rax; pcbData
0x1400a53d1  lea     rax, [rbp+arg_18]
0x1400a53d5  mov     [rsp+50h+pvData], rax; pvData
0x1400a53da  mov     [rsp+50h+pdwType], 0; pdwType
0x1400a53e3  mov     r9d, 10010h; dwFlags
0x1400a53e9  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400a53f0  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1400a53f7  mov     rsi, 0FFFFFFFF80000002h
0x1400a53fe  mov     rcx, rsi; hkey
0x1400a5401  call    cs:__imp_RegGetValueW
0x1400a5407  test    eax, eax
0x1400a5409  jz      short loc_1400A5446
0x1400a540b  mov     dword ptr [rbp+arg_10], ebx
0x1400a540e  lea     rax, [rbp+arg_10]
0x1400a5412  mov     [rsp+50h+pcbData], rax; pcbData
0x1400a5417  lea     rax, [rbp+arg_18]
0x1400a541b  mov     [rsp+50h+pvData], rax; pvData
0x1400a5420  mov     [rsp+50h+pdwType], 0; int
0x1400a5429  mov     r9d, 20010010h; dwFlags
0x1400a542f  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400a5436  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a543d  mov     rcx, rsi; hkey
0x1400a5440  call    cs:__imp_RegGetValueW
0x1400a5446  cmp     [rbp+arg_18], 0
0x1400a544a  jz      short loc_1400A5486
0x1400a544c  mov     ebx, 3
0x1400a5451  lea     rdx, [rbp+arg_10]
0x1400a5455  lea     rcx, [rbp+var_10]
0x1400a5459  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a545e  mov     rcx, [rax]
0x1400a5461  mov     byte ptr [rcx+113h], 1
0x1400a5468  lea     rcx, [rbp+arg_10]
0x1400a546c  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a5471  lea     rdx, [rbp+phkResult]
0x1400a5475  lea     rcx, aRetaildemomode_0; "RetailDemoMode"
0x1400a547c  call    ??$SpotlightNotOnboardedReasonV2@AEAY0P@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0P@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[15],long &>(ushort const (&)[15],long &)
0x1400a5481  jmp     loc_1400A5671
0x1400a5486  mov     rsi, 0FFFFFFFFFFFFFFFCh
0x1400a548d  mov     rcx, rsi; TokenHandle
0x1400a5490  call    IsUserAssignedAccessSingleApp
0x1400a5495  test    eax, eax
0x1400a5497  jz      short loc_1400A54CA
0x1400a5499  lea     ebx, [rsi+9]
0x1400a549c  lea     rdx, [rbp+arg_10]
0x1400a54a0  lea     rcx, [rbp+var_10]
0x1400a54a4  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a54a9  mov     rcx, [rax]
0x1400a54ac  mov     byte ptr [rcx+115h], 1
0x1400a54b3  lea     rcx, [rbp+arg_10]
0x1400a54b7  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a54bc  lea     rdx, [rbp+phkResult]
0x1400a54c0  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CH@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CH@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[39],long &>(ushort const (&)[39],long &)
0x1400a54c5  jmp     loc_1400A5671
0x1400a54ca  mov     rcx, rsi; TokenHandle
0x1400a54cd  call    IsUserAssignedAccessMultiApp
0x1400a54d2  test    eax, eax
0x1400a54d4  jz      short loc_1400A5509
0x1400a54d6  mov     ebx, 7
0x1400a54db  lea     rdx, [rbp+arg_10]
0x1400a54df  lea     rcx, [rbp+var_10]
0x1400a54e3  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a54e8  mov     rcx, [rax]
0x1400a54eb  mov     byte ptr [rcx+116h], 1
0x1400a54f2  lea     rcx, [rbp+arg_10]
0x1400a54f6  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a54fb  lea     rdx, [rbp+phkResult]
0x1400a54ff  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CG@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CG@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[38],long &>(ushort const (&)[38],long &)
0x1400a5504  jmp     loc_1400A5671
0x1400a5509  mov     rcx, rsi; TokenHandle
0x1400a550c  call    IsUserAssignedAccessSingleAppClassicApp
0x1400a5511  test    eax, eax
0x1400a5513  jz      short loc_1400A5548
0x1400a5515  mov     ebx, 6
0x1400a551a  lea     rdx, [rbp+arg_10]
0x1400a551e  lea     rcx, [rbp+var_10]
0x1400a5522  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a5527  mov     rcx, [rax]
0x1400a552a  mov     byte ptr [rcx+117h], 1
0x1400a5531  lea     rcx, [rbp+arg_10]
0x1400a5535  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a553a  lea     rdx, [rbp+phkResult]
0x1400a553e  call    ??$SpotlightNotOnboardedReasonV2@AEAY0DB@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0DB@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[49],long &>(ushort const (&)[49],long &)
0x1400a5543  jmp     loc_1400A5671
0x1400a5548  call    ?IsSharedPCMode@@YA_NXZ; IsSharedPCMode(void)
0x1400a554d  test    al, al
0x1400a554f  jz      short loc_1400A5584
0x1400a5551  mov     ebx, 8
0x1400a5556  lea     rdx, [rbp+arg_10]
0x1400a555a  lea     rcx, [rbp+var_10]
0x1400a555e  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a5563  mov     rcx, [rax]
0x1400a5566  mov     byte ptr [rcx+118h], 1
0x1400a556d  lea     rcx, [rbp+arg_10]
0x1400a5571  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a5576  lea     rdx, [rbp+phkResult]
0x1400a557a  call    ??$SpotlightNotOnboardedReasonV2@AEAY0N@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0N@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[13],long &>(ushort const (&)[13],long &)
0x1400a557f  jmp     loc_1400A5671
0x1400a5584  call    ?IsShellLauncherEnabledForCurrentUser@@YA_NXZ; IsShellLauncherEnabledForCurrentUser(void)
0x1400a5589  test    al, al
0x1400a558b  jz      short loc_1400A55C0
0x1400a558d  mov     ebx, 9
0x1400a5592  lea     rdx, [rbp+arg_10]
0x1400a5596  lea     rcx, [rbp+var_10]
0x1400a559a  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a559f  mov     rcx, [rax]
0x1400a55a2  mov     byte ptr [rcx+119h], 1
0x1400a55a9  lea     rcx, [rbp+arg_10]
0x1400a55ad  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a55b2  lea     rdx, [rbp+phkResult]
0x1400a55b6  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CD@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CD@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[35],long &>(ushort const (&)[35],long &)
0x1400a55bb  jmp     loc_1400A5671
0x1400a55c0  call    ?IsUnattendedAutoLogonSet@@YA_NXZ; IsUnattendedAutoLogonSet(void)
0x1400a55c5  lea     rdx, [rbp+arg_10]
0x1400a55c9  lea     rcx, [rbp+var_10]
0x1400a55cd  test    al, al
0x1400a55cf  jz      short loc_1400A564E
0x1400a55d1  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a55d6  mov     rcx, [rax]
0x1400a55d9  mov     byte ptr [rcx+114h], 1
0x1400a55e0  lea     rcx, [rbp+arg_10]
0x1400a55e4  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a55e9  lea     rdx, [rbp+phkResult]
0x1400a55ed  call    ??$SpotlightNotOnboardedReasonV2@AEAY0BI@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0BI@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[24],long &>(ushort const (&)[24],long &)
0x1400a55f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation>::GetImpl(void)'::`2'::impl
0x1400a55f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation>::__private_IsEnabled(void)
0x1400a55fe  test    al, al
0x1400a5600  jz      short loc_1400A5671
0x1400a5602  xor     ebx, ebx
0x1400a5604  lea     rdx, [rbp+arg_10]
0x1400a5608  lea     rcx, [rbp+var_10]
0x1400a560c  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a5611  mov     rcx, [rax]
0x1400a5614  mov     [rcx+114h], bl
0x1400a561a  lea     rcx, [rbp+arg_10]
0x1400a561e  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a5623  lea     rdx, [rbp+arg_10]
0x1400a5627  lea     rcx, [rbp+var_10]
0x1400a562b  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a5630  mov     rcx, [rax]
0x1400a5633  mov     byte ptr [rcx+11Ah], 1
0x1400a563a  lea     rcx, [rbp+arg_10]
0x1400a563e  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a5643  lea     rdx, [rbp+phkResult]
0x1400a5647  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CB@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CB@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[33],long &>(ushort const (&)[33],long &)
0x1400a564c  jmp     short loc_1400A5671
0x1400a564e  xor     ebx, ebx
0x1400a5650  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400a5655  mov     rcx, [rax]
0x1400a5658  mov     byte ptr [rcx+111h], 1
0x1400a565f  lea     rcx, [rbp+arg_10]
0x1400a5663  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400a5668  lea     rdx, [rbp+phkResult]
0x1400a566c  call    ??$SpotlightNotOnboardedReasonV2@AEAY0O@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0O@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[14],long &>(ushort const (&)[14],long &)
0x1400a5671  mov     r9d, ebx; unsigned int
0x1400a5674  lea     r8, aSpotlightnoton; "SpotlightNotOnboardedReason"
0x1400a567b  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a5682  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1400a5689  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400a568e  mov     rcx, [rbp+18h]; this
0x1400a5692  test    eax, eax
0x1400a5694  jns     short loc_1400A56AA
0x1400a5696  mov     r9d, eax; char *
0x1400a5699  lea     r8, aShellLibLogont; "shell\\lib\\logontasks\\DesktopSpotligh"...
0x1400a56a0  mov     edx, 488h; void *
0x1400a56a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a56aa  mov     rcx, [rbp+var_10]
0x1400a56ae  test    rcx, rcx
0x1400a56b1  jz      short loc_1400A56BD
0x1400a56b3  add     rcx, 8
0x1400a56b7  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1400a56bc  nop
0x1400a56bd  neg     ebx
0x1400a56bf  sbb     ebx, ebx
0x1400a56c1  and     ebx, 80004005h
0x1400a56c7  lea     rcx, [rbp+var_10]
0x1400a56cb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>(void)
0x1400a56d0  mov     eax, ebx
0x1400a56d2  add     rsp, 50h
0x1400a56d6  pop     rsi
0x1400a56d7  pop     rbx
0x1400a56d8  pop     rbp
0x1400a56d9  retn
```
