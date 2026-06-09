# s_CanDesktopSpotlighBeTurnedOnForLogonType_FirstLogonNewUser

- ea: `0x1400ab430`
- end: `0x1400ab888`
- name: `s_CanDesktopSpotlighBeTurnedOnForLogonType_FirstLogonNewUser`
- size: `1112`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400aae5c`

## callees

- `0x14001b2c8`
- `0x14001e1e0`
- `0x14001e9bc`
- `0x140026320`
- `0x140026964`
- `0x14007c1f4`
- `0x140087994`
- `0x1400ab088`
- `0x1400ab430`
- `0x1400ab890`
- `0x1400ab8b0`
- `0x1400acaec`
- `0x140143c9c`
- `0x140143d24`
- `0x140143dac`
- `0x140143e34`
- `0x140143ebc`
- `0x140143f44`
- `0x140143fcc`
- `0x140144054`
- `0x1401440dc`
- `0x140144164`
- `0x140155258`
- `0x140158848`
- `0x1401a25b4`
- `0x1401a39fc`
- `0x1401a6f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400ab4d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400ab4d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ab505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ab505`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ab5ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ab5f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ab5ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ab5f3`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1400ab4be`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1400ab4be`

## string_xrefs

- `0x1400ab4f0`: `shell\lib\logontasks\DesktopSpotlightLogonTaskHelper.h`
- `0x1400ab84f`: `shell\lib\logontasks\DesktopSpotlightLogonTaskHelper.h`
- `0x1400ab59d`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1400ab5e9`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

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
  _BYTE v16[16]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY phkResult; // [rsp+78h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
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
      pcbData = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Enabled",
             0x10010u,
             0,
             &pvData,
             &pcbData) )
      {
        pcbData = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
          L"Enabled",
          0x20010010u,
          0,
          &pvData,
          &pcbData);
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
      else if ( (unsigned int)IsCurrentUserAssignedAccessSingleAppClassicApp() )
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
    tip2::tip_test<tip2::details::merged_data<_tip_s_RetryEnablementTipTest,_tip_s_RetryEnablementTipTest>>::complete(v16);
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
    tip2::tip_test<tip2::details::merged_data<_tip_s_RetryEnablementTipTest,_tip_s_RetryEnablementTipTest>>::complete(&pcbData);
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
0x1400ab430  push    rbp
0x1400ab432  push    rbx
0x1400ab433  push    rsi
0x1400ab434  mov     rbp, rsp
0x1400ab437  sub     rsp, 50h
0x1400ab43b  mov     ebx, ecx
0x1400ab43d  lea     rcx, [rbp+phkResult]
0x1400ab441  call    isDesktopSpotlightEnabledThroughRegistry
0x1400ab446  mov     dword ptr [rbp+phkResult], eax
0x1400ab449  test    eax, eax
0x1400ab44b  jnz     loc_1400AB522
0x1400ab451  lea     rdx, [rbp+phkResult]
0x1400ab455  lea     rcx, aUnexpectedcase; "UnexpectedCase"
0x1400ab45c  call    ??$SpotlightNotOnboardedReasonV2@AEAY0P@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0P@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[15],long &>(ushort const (&)[15],long &)
0x1400ab461  lea     rcx, [rbp+arg_10]
0x1400ab465  call    ??$start@V?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>>(void)
0x1400ab46a  nop
0x1400ab46b  lea     rdx, [rbp+phkResult]
0x1400ab46f  lea     rcx, [rbp+arg_10]
0x1400ab473  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab478  mov     rcx, [rax]
0x1400ab47b  mov     byte ptr [rcx+110h], 1
0x1400ab482  lea     rcx, [rbp+phkResult]
0x1400ab486  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab48b  lea     rcx, [rbp+arg_10]
0x1400ab48f  call    ?complete@?$tip_test@V?$merged_data@U_tip_s_RetryEnablementTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_s_RetryEnablementTipTest,_tip_s_RetryEnablementTipTest>>::complete(void)
0x1400ab494  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason>::GetImpl(void)'::`2'::impl
0x1400ab49b  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@@details@wil@@QEAA?AW4Variant_DesktopSpotlightTipTestForSpotlightNotOnboardedReason@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTipTestForSpotlightNotOnboardedReason>::__private_GetVariant(wil::VariantReportingKind,bool)
0x1400ab4a0  cmp     al, 1
0x1400ab4a2  jnz     short loc_1400AB512
0x1400ab4a4  mov     [rbp+phkResult], 0
0x1400ab4ac  lea     r8, [rbp+phkResult]; phkResult
0x1400ab4b0  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400ab4b7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400ab4be  call    cs:__imp_RegOpenKeyW
0x1400ab4c5  nop     dword ptr [rax+rax+00h]
0x1400ab4ca  test    eax, eax
0x1400ab4cc  jnz     short loc_1400AB512
0x1400ab4ce  lea     rdx, aEnabledstate; "EnabledState"
0x1400ab4d5  mov     rcx, [rbp+phkResult]; hKey
0x1400ab4d9  call    cs:__imp_RegDeleteValueW
0x1400ab4e0  nop     dword ptr [rax+rax+00h]
0x1400ab4e5  mov     rcx, [rbp+18h]; this
0x1400ab4e9  test    eax, eax
0x1400ab4eb  jns     short loc_1400AB501
0x1400ab4ed  mov     r9d, eax; char *
0x1400ab4f0  lea     r8, aShellLibLogont; "shell\\lib\\logontasks\\DesktopSpotligh"...
0x1400ab4f7  mov     edx, 42Fh; void *
0x1400ab4fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ab501  mov     rcx, [rbp+phkResult]; hKey
0x1400ab505  call    cs:__imp_RegCloseKey
0x1400ab50c  nop     dword ptr [rax+rax+00h]
0x1400ab511  nop
0x1400ab512  lea     rcx, [rbp+arg_10]
0x1400ab516  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>(void)
0x1400ab51b  xor     eax, eax
0x1400ab51d  jmp     loc_1400AB87F
0x1400ab522  lea     rcx, [rbp+var_10]
0x1400ab526  call    ??$start@V?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>>(void)
0x1400ab52b  nop
0x1400ab52c  test    ebx, 3308h
0x1400ab532  jz      short loc_1400AB566
0x1400ab534  mov     ebx, 1
0x1400ab539  lea     rdx, [rbp+arg_10]
0x1400ab53d  lea     rcx, [rbp+var_10]
0x1400ab541  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab546  mov     rcx, [rax]
0x1400ab549  mov     [rcx+112h], bl
0x1400ab54f  lea     rcx, [rbp+arg_10]
0x1400ab553  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab558  lea     rdx, [rbp+phkResult]
0x1400ab55c  call    ??$SpotlightNotOnboardedReasonV2@AEAY0BE@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0BE@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[20],long &>(ushort const (&)[20],long &)
0x1400ab561  jmp     loc_1400AB827
0x1400ab566  mov     [rbp+arg_18], 0
0x1400ab56d  mov     ebx, 4
0x1400ab572  mov     [rbp+arg_10], ebx
0x1400ab575  lea     rax, [rbp+arg_10]
0x1400ab579  mov     [rsp+50h+pcbData], rax; pcbData
0x1400ab57e  lea     rax, [rbp+arg_18]
0x1400ab582  mov     [rsp+50h+pvData], rax; pvData
0x1400ab587  mov     [rsp+50h+pdwType], 0; pdwType
0x1400ab590  mov     r9d, 10010h; dwFlags
0x1400ab596  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400ab59d  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1400ab5a4  mov     rsi, 0FFFFFFFF80000002h
0x1400ab5ab  mov     rcx, rsi; hkey
0x1400ab5ae  call    cs:__imp_RegGetValueW
0x1400ab5b5  nop     dword ptr [rax+rax+00h]
0x1400ab5ba  test    eax, eax
0x1400ab5bc  jz      short loc_1400AB5FF
0x1400ab5be  mov     [rbp+arg_10], ebx
0x1400ab5c1  lea     rax, [rbp+arg_10]
0x1400ab5c5  mov     [rsp+50h+pcbData], rax; pcbData
0x1400ab5ca  lea     rax, [rbp+arg_18]
0x1400ab5ce  mov     [rsp+50h+pvData], rax; pvData
0x1400ab5d3  mov     [rsp+50h+pdwType], 0; int
0x1400ab5dc  mov     r9d, 20010010h; dwFlags
0x1400ab5e2  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1400ab5e9  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400ab5f0  mov     rcx, rsi; hkey
0x1400ab5f3  call    cs:__imp_RegGetValueW
0x1400ab5fa  nop     dword ptr [rax+rax+00h]
0x1400ab5ff  cmp     [rbp+arg_18], 0
0x1400ab603  jz      short loc_1400AB63F
0x1400ab605  mov     ebx, 3
0x1400ab60a  lea     rdx, [rbp+arg_10]
0x1400ab60e  lea     rcx, [rbp+var_10]
0x1400ab612  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab617  mov     rcx, [rax]
0x1400ab61a  mov     byte ptr [rcx+113h], 1
0x1400ab621  lea     rcx, [rbp+arg_10]
0x1400ab625  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab62a  lea     rdx, [rbp+phkResult]
0x1400ab62e  lea     rcx, aRetaildemomode_0; "RetailDemoMode"
0x1400ab635  call    ??$SpotlightNotOnboardedReasonV2@AEAY0P@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0P@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[15],long &>(ushort const (&)[15],long &)
0x1400ab63a  jmp     loc_1400AB827
0x1400ab63f  mov     rsi, 0FFFFFFFFFFFFFFFCh
0x1400ab646  mov     rcx, rsi; TokenHandle
0x1400ab649  call    IsUserAssignedAccessSingleApp
0x1400ab64e  test    eax, eax
0x1400ab650  jz      short loc_1400AB683
0x1400ab652  lea     ebx, [rsi+9]
0x1400ab655  lea     rdx, [rbp+arg_10]
0x1400ab659  lea     rcx, [rbp+var_10]
0x1400ab65d  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab662  mov     rcx, [rax]
0x1400ab665  mov     byte ptr [rcx+115h], 1
0x1400ab66c  lea     rcx, [rbp+arg_10]
0x1400ab670  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab675  lea     rdx, [rbp+phkResult]
0x1400ab679  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CH@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CH@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[39],long &>(ushort const (&)[39],long &)
0x1400ab67e  jmp     loc_1400AB827
0x1400ab683  mov     rcx, rsi; TokenHandle
0x1400ab686  call    IsUserAssignedAccessMultiApp
0x1400ab68b  test    eax, eax
0x1400ab68d  jz      short loc_1400AB6C2
0x1400ab68f  mov     ebx, 7
0x1400ab694  lea     rdx, [rbp+arg_10]
0x1400ab698  lea     rcx, [rbp+var_10]
0x1400ab69c  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab6a1  mov     rcx, [rax]
0x1400ab6a4  mov     byte ptr [rcx+116h], 1
0x1400ab6ab  lea     rcx, [rbp+arg_10]
0x1400ab6af  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab6b4  lea     rdx, [rbp+phkResult]
0x1400ab6b8  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CG@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CG@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[38],long &>(ushort const (&)[38],long &)
0x1400ab6bd  jmp     loc_1400AB827
0x1400ab6c2  call    IsCurrentUserAssignedAccessSingleAppClassicApp
0x1400ab6c7  test    eax, eax
0x1400ab6c9  jz      short loc_1400AB6FE
0x1400ab6cb  mov     ebx, 6
0x1400ab6d0  lea     rdx, [rbp+arg_10]
0x1400ab6d4  lea     rcx, [rbp+var_10]
0x1400ab6d8  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab6dd  mov     rcx, [rax]
0x1400ab6e0  mov     byte ptr [rcx+117h], 1
0x1400ab6e7  lea     rcx, [rbp+arg_10]
0x1400ab6eb  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab6f0  lea     rdx, [rbp+phkResult]
0x1400ab6f4  call    ??$SpotlightNotOnboardedReasonV2@AEAY0DB@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0DB@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[49],long &>(ushort const (&)[49],long &)
0x1400ab6f9  jmp     loc_1400AB827
0x1400ab6fe  call    ?IsSharedPCMode@@YA_NXZ; IsSharedPCMode(void)
0x1400ab703  test    al, al
0x1400ab705  jz      short loc_1400AB73A
0x1400ab707  mov     ebx, 8
0x1400ab70c  lea     rdx, [rbp+arg_10]
0x1400ab710  lea     rcx, [rbp+var_10]
0x1400ab714  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab719  mov     rcx, [rax]
0x1400ab71c  mov     byte ptr [rcx+118h], 1
0x1400ab723  lea     rcx, [rbp+arg_10]
0x1400ab727  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab72c  lea     rdx, [rbp+phkResult]
0x1400ab730  call    ??$SpotlightNotOnboardedReasonV2@AEAY0N@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0N@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[13],long &>(ushort const (&)[13],long &)
0x1400ab735  jmp     loc_1400AB827
0x1400ab73a  call    ?IsShellLauncherEnabledForCurrentUser@@YA_NXZ; IsShellLauncherEnabledForCurrentUser(void)
0x1400ab73f  test    al, al
0x1400ab741  jz      short loc_1400AB776
0x1400ab743  mov     ebx, 9
0x1400ab748  lea     rdx, [rbp+arg_10]
0x1400ab74c  lea     rcx, [rbp+var_10]
0x1400ab750  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab755  mov     rcx, [rax]
0x1400ab758  mov     byte ptr [rcx+119h], 1
0x1400ab75f  lea     rcx, [rbp+arg_10]
0x1400ab763  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab768  lea     rdx, [rbp+phkResult]
0x1400ab76c  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CD@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CD@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[35],long &>(ushort const (&)[35],long &)
0x1400ab771  jmp     loc_1400AB827
0x1400ab776  call    ?IsUnattendedAutoLogonSet@@YA_NXZ; IsUnattendedAutoLogonSet(void)
0x1400ab77b  lea     rdx, [rbp+arg_10]
0x1400ab77f  lea     rcx, [rbp+var_10]
0x1400ab783  test    al, al
0x1400ab785  jz      short loc_1400AB804
0x1400ab787  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab78c  mov     rcx, [rax]
0x1400ab78f  mov     byte ptr [rcx+114h], 1
0x1400ab796  lea     rcx, [rbp+arg_10]
0x1400ab79a  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab79f  lea     rdx, [rbp+phkResult]
0x1400ab7a3  call    ??$SpotlightNotOnboardedReasonV2@AEAY0BI@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0BI@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[24],long &>(ushort const (&)[24],long &)
0x1400ab7a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation>::GetImpl(void)'::`2'::impl
0x1400ab7af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUnattendAutoLogonOnboardingInstrumentation>::__private_IsEnabled(void)
0x1400ab7b4  test    al, al
0x1400ab7b6  jz      short loc_1400AB827
0x1400ab7b8  xor     ebx, ebx
0x1400ab7ba  lea     rdx, [rbp+arg_10]
0x1400ab7be  lea     rcx, [rbp+var_10]
0x1400ab7c2  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab7c7  mov     rcx, [rax]
0x1400ab7ca  mov     [rcx+114h], bl
0x1400ab7d0  lea     rcx, [rbp+arg_10]
0x1400ab7d4  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab7d9  lea     rdx, [rbp+arg_10]
0x1400ab7dd  lea     rcx, [rbp+var_10]
0x1400ab7e1  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab7e6  mov     rcx, [rax]
0x1400ab7e9  mov     byte ptr [rcx+11Ah], 1
0x1400ab7f0  lea     rcx, [rbp+arg_10]
0x1400ab7f4  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab7f9  lea     rdx, [rbp+phkResult]
0x1400ab7fd  call    ??$SpotlightNotOnboardedReasonV2@AEAY0CB@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0CB@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[33],long &>(ushort const (&)[33],long &)
0x1400ab802  jmp     short loc_1400AB827
0x1400ab804  xor     ebx, ebx
0x1400ab806  call    ??C?$tip_test@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::operator->(void)
0x1400ab80b  mov     rcx, [rax]
0x1400ab80e  mov     byte ptr [rcx+111h], 1
0x1400ab815  lea     rcx, [rbp+arg_10]
0x1400ab819  call    ??1?$test_data_control@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>::~test_data_control<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>>(void)
0x1400ab81e  lea     rdx, [rbp+phkResult]
0x1400ab822  call    ??$SpotlightNotOnboardedReasonV2@AEAY0O@$$CBGAEAJ@DesktopSpotlightLogonTelemetry@@SAXAEAY0O@$$CBGAEAJ@Z; DesktopSpotlightLogonTelemetry::SpotlightNotOnboardedReasonV2<ushort const (&)[14],long &>(ushort const (&)[14],long &)
0x1400ab827  mov     r9d, ebx; unsigned int
0x1400ab82a  lea     r8, aSpotlightnoton; "SpotlightNotOnboardedReason"
0x1400ab831  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400ab838  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1400ab83f  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400ab844  mov     rcx, [rbp+18h]; this
0x1400ab848  test    eax, eax
0x1400ab84a  jns     short loc_1400AB860
0x1400ab84c  mov     r9d, eax; char *
0x1400ab84f  lea     r8, aShellLibLogont; "shell\\lib\\logontasks\\DesktopSpotligh"...
0x1400ab856  mov     edx, 488h; void *
0x1400ab85b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ab860  lea     rcx, [rbp+var_10]
0x1400ab864  call    ?complete@?$tip_test@V?$merged_data@U_tip_s_RetryEnablementTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_s_RetryEnablementTipTest,_tip_s_RetryEnablementTipTest>>::complete(void)
0x1400ab869  nop
0x1400ab86a  neg     ebx
0x1400ab86c  sbb     ebx, ebx
0x1400ab86e  and     ebx, 80004005h
0x1400ab874  lea     rcx, [rbp+var_10]
0x1400ab878  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser,_tip_CanDesktopSpotlighBeTurnedOnForLogonTypeTest_FirstLogonNewUser>,wil::err_returncode_policy>(void)
0x1400ab87d  mov     eax, ebx
0x1400ab87f  add     rsp, 50h
0x1400ab883  pop     rsi
0x1400ab884  pop     rbx
0x1400ab885  pop     rbp
0x1400ab886  retn
```
