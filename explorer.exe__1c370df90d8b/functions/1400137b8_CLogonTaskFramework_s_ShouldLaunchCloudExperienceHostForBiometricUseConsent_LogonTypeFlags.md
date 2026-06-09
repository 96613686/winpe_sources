# CLogonTaskFramework::s_ShouldLaunchCloudExperienceHostForBiometricUseConsent(LogonTypeFlags)

- ea: `0x1400137b8`
- end: `0x140013bad`
- name: `?s_ShouldLaunchCloudExperienceHostForBiometricUseConsent@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z`
- size: `1013`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14009d5c0`

## callees

- `0x140011a10`
- `0x1400130d4`
- `0x140013790`
- `0x1400137b8`
- `0x140013bb4`
- `0x140013c48`
- `0x140013e6c`
- `0x140015710`
- `0x140033070`
- `0x140033a3c`
- `0x14003401c`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401c0694`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013863`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001389f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400139c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013a1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013ad6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013b20`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013863`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001389f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400139c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013a1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013ad6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013b20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013a77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013a77`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x140013814`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x140013814`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140013945`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140013945`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140013934`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140013934`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1400137e6`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1400137e6`
- `ext-ms-win-biometrics-winbio-core-l1-1-5!WinBioGetLastBioUseTime` at `0x140013961`
- `ext-ms-win-biometrics-winbio-core-l1-1-5!WinBioGetLastBioUseTime` at `0x140013961`

## string_xrefs

- `0x140013852`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x140013895`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CLogonTaskFramework::s_ShouldLaunchCloudExperienceHostForBiometricUseConsent(__int16 a1)
{
  __int64 v2; // rcx
  PSID v3; // rbx
  unsigned __int64 v4; // rsi
  LSTATUS ValueW; // eax
  wil::filetime *v6; // rcx
  bool v7; // sf
  bool v8; // di
  LSTATUS v9; // eax
  wil::filetime *v10; // rcx
  bool v11; // sf
  struct _FILETIME system_time; // rax
  LSTATUS v14; // eax
  bool v15; // sf
  LSTATUS v16; // eax
  bool v17; // sf
  struct _FILETIME v18; // r8
  char v19[4]; // [rsp+40h] [rbp-69h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-65h] BYREF
  PSID pSourceSid; // [rsp+48h] [rbp-61h] BYREF
  __int64 pvData; // [rsp+50h] [rbp-59h] BYREF
  __int64 v23; // [rsp+58h] [rbp-51h] BYREF
  _DWORD v24[2]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pDestinationSid[72]; // [rsp+68h] [rbp-41h] BYREF

  if ( GetSystemMetrics(4096) || (a1 & 0x330A) != 0 || CLogonTaskFramework::s_IsCompanionDeviceAccount() || IsOS(0xDu) )
    return 0;
  LODWORD(pSourceSid) = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
         L"Enabled",
         0x10010u,
         0,
         &pSourceSid,
         &pcbData) )
  {
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
      L"Enabled",
      0x20010010u,
      0,
      &pSourceSid,
      &pcbData);
  }
  if ( (_DWORD)pSourceSid
    || IsPreserveOobeAutologonCredentialsSet()
    || IsUnattendedAutoLogonSet()
    || (unsigned int)IsUserAssignedAccessSingleApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
    || IsUserAssignedAccessMultiApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
    || IsUserAssignedAccessSingleAppClassicApp((HANDLE)0xFFFFFFFFFFFFFFFCLL) )
  {
    return 0;
  }
  memset_0(v24, 0, 0x4Cu);
  pSourceSid = 0;
  if ( (int)GetCurrentUserSid(&pSourceSid) < 0 || (v3 = pSourceSid, !CopySid(0x44u, pDestinationSid, pSourceSid)) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
LABEL_41:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSourceSid);
    return 0;
  }
  v24[1] = GetLengthSid(v3);
  v24[0] = 3;
  v23 = 0;
  if ( (int)WinBioGetLastBioUseTime(v24, &v23) < 0 )
    goto LABEL_41;
  v4 = (unsigned int)v23 + ((unsigned __int64)HIDWORD(v23) << 32);
  if ( !v4 )
    goto LABEL_41;
  pvData = 0;
  LODWORD(pSourceSid) = 8;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\WindowsHello",
             L"BioConsentNoticeShownTime",
             8u,
             0,
             &pvData,
             (LPDWORD)&pSourceSid);
  v7 = ValueW < 0;
  if ( ValueW > 0 )
    v7 = 1;
  if ( v7 || (_DWORD)pSourceSid != 8 )
  {
    pvData = 0;
    v8 = 1;
    v19[0] = 1;
    LODWORD(pSourceSid) = 0;
    pcbData = 4;
    v9 = RegGetValueW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\WindowsHello",
           L"LearnMoreAvailable",
           0x10u,
           0,
           &pSourceSid,
           &pcbData);
    v11 = v9 < 0;
    if ( v9 > 0 )
      v11 = 1;
    if ( v11 )
    {
      pcbData = 4;
      v14 = RegGetValueW(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\WindowsHello",
              L"LearnMoreAvailableInSCOOBE",
              0x10u,
              0,
              &pSourceSid,
              &pcbData);
      v15 = v14 < 0;
      if ( v14 > 0 )
        v15 = 1;
      if ( v15 )
      {
        pcbData = 4;
        v16 = RegGetValueW(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\WindowsHello",
                L"LearnMoreAvailableInSettings",
                0x10u,
                0,
                &pSourceSid,
                &pcbData);
        v17 = v16 < 0;
        if ( v16 > 0 )
          v17 = 1;
        if ( v17 )
          goto LABEL_25;
      }
    }
    system_time = wil::filetime::get_system_time(v10);
    v8 = system_time.dwLowDateTime + (*(_QWORD *)&system_time & 0xFFFFFFFF00000000uLL) - v4 > 0x11ED178C6C000LL;
  }
  else
  {
    v18 = wil::filetime::get_system_time(v6);
    if ( *(_QWORD *)&v18 - v4 <= 0x11ED178C6C000LL
      || (v8 = 1, *(_QWORD *)&v18 - ((unsigned __int64)HIDWORD(pvData) << 32) - (unsigned int)pvData <= 0x11ED178C6C000LL) )
    {
      v8 = 0;
    }
  }
  v19[0] = v8;
LABEL_25:
  BiometricConsentTelemetry::ShouldShowUnusedBiometricConsentForUserWithBiometrics<bool &>(v19);
  if ( v3 )
    LocalFree(v3);
  return v8;
}

```

## disassembly

```asm
0x1400137b8  push    rbp
0x1400137ba  push    rbx
0x1400137bb  push    rsi
0x1400137bc  push    rdi
0x1400137bd  push    r12
0x1400137bf  push    r13
0x1400137c1  push    r14
0x1400137c3  push    r15
0x1400137c5  lea     rbp, [rsp-1Fh]
0x1400137ca  sub     rsp, 0C8h
0x1400137d1  mov     rax, cs:__security_cookie
0x1400137d8  xor     rax, rsp
0x1400137db  mov     [rbp+57h+var_50], rax
0x1400137df  mov     ebx, ecx
0x1400137e1  mov     ecx, 1000h; nIndex
0x1400137e6  call    cs:__imp_GetSystemMetrics
0x1400137ec  xor     r14d, r14d
0x1400137ef  test    eax, eax
0x1400137f1  jnz     loc_140013AA0
0x1400137f7  test    ebx, 330Ah
0x1400137fd  jnz     loc_140013AA0
0x140013803  call    ?s_IsCompanionDeviceAccount@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsCompanionDeviceAccount(void)
0x140013808  test    al, al
0x14001380a  jnz     loc_140013AA0
0x140013810  lea     ecx, [r14+0Dh]; dwOS
0x140013814  call    cs:__imp_IsOS
0x14001381a  test    eax, eax
0x14001381c  jnz     loc_140013AA0
0x140013822  mov     dword ptr [rbp+57h+pSourceSid], r14d
0x140013826  lea     r12d, [r14+4]
0x14001382a  mov     [rbp+57h+var_BC], r12d
0x14001382e  lea     rax, [rbp+57h+var_BC]
0x140013832  mov     [rsp+100h+pcbData], rax; pcbData
0x140013837  lea     rax, [rbp+57h+pSourceSid]
0x14001383b  mov     [rsp+100h+pvData], rax; pvData
0x140013840  mov     [rsp+100h+pdwType], r14; pdwType
0x140013845  mov     r9d, 10010h; dwFlags
0x14001384b  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x140013852  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x140013859  mov     rbx, 0FFFFFFFF80000002h
0x140013860  mov     rcx, rbx; hkey
0x140013863  call    cs:__imp_RegGetValueW
0x140013869  test    eax, eax
0x14001386b  jz      short loc_1400138A5
0x14001386d  mov     [rbp+57h+var_BC], r12d
0x140013871  lea     rax, [rbp+57h+var_BC]
0x140013875  mov     [rsp+100h+pcbData], rax; pcbData
0x14001387a  lea     rax, [rbp+57h+pSourceSid]
0x14001387e  mov     [rsp+100h+pvData], rax; pvData
0x140013883  mov     [rsp+100h+pdwType], r14; pdwType
0x140013888  mov     r9d, 20010010h; dwFlags
0x14001388e  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x140013895  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001389c  mov     rcx, rbx; hkey
0x14001389f  call    cs:__imp_RegGetValueW
0x1400138a5  cmp     dword ptr [rbp+57h+pSourceSid], r14d
0x1400138a9  jnz     loc_140013AA0
0x1400138af  call    ?IsPreserveOobeAutologonCredentialsSet@@YA_NXZ; IsPreserveOobeAutologonCredentialsSet(void)
0x1400138b4  test    al, al
0x1400138b6  jnz     loc_140013AA0
0x1400138bc  call    ?IsUnattendedAutoLogonSet@@YA_NXZ; IsUnattendedAutoLogonSet(void)
0x1400138c1  test    al, al
0x1400138c3  jnz     loc_140013AA0
0x1400138c9  mov     rbx, 0FFFFFFFFFFFFFFFCh
0x1400138d0  mov     rcx, rbx; TokenHandle
0x1400138d3  call    IsUserAssignedAccessSingleApp
0x1400138d8  test    eax, eax
0x1400138da  jnz     loc_140013AA0
0x1400138e0  mov     rcx, rbx; TokenHandle
0x1400138e3  call    IsUserAssignedAccessMultiApp
0x1400138e8  test    eax, eax
0x1400138ea  jnz     loc_140013AA0
0x1400138f0  mov     rcx, rbx; TokenHandle
0x1400138f3  call    IsUserAssignedAccessSingleAppClassicApp
0x1400138f8  test    eax, eax
0x1400138fa  jnz     loc_140013AA0
0x140013900  xor     edx, edx; Val
0x140013902  lea     r8d, [rbx+50h]; Size
0x140013906  lea     rcx, [rbp+57h+var_A0]; void *
0x14001390a  call    memset_0
0x14001390f  mov     [rbp+57h+pSourceSid], r14
0x140013913  lea     rcx, [rbp+57h+pSourceSid]; void **
0x140013917  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x14001391c  test    eax, eax
0x14001391e  js      loc_140013B99
0x140013924  mov     rbx, [rbp+57h+pSourceSid]
0x140013928  mov     r8, rbx; pSourceSid
0x14001392b  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x14001392f  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x140013934  call    cs:__imp_CopySid
0x14001393a  test    eax, eax
0x14001393c  jz      loc_140013B99
0x140013942  mov     rcx, rbx; pSid
0x140013945  call    cs:__imp_GetLengthSid
0x14001394b  mov     [rbp+57h+var_9C], eax
0x14001394e  mov     [rbp+57h+var_A0], 3
0x140013955  mov     [rbp+57h+var_A8], r14
0x140013959  lea     rdx, [rbp+57h+var_A8]
0x14001395d  lea     rcx, [rbp+57h+var_A0]
0x140013961  call    cs:__imp_WinBioGetLastBioUseTime
0x140013967  test    eax, eax
0x140013969  js      loc_140013B9F
0x14001396f  mov     esi, dword ptr [rbp+57h+var_A8+4]
0x140013972  shl     rsi, 20h
0x140013976  mov     eax, dword ptr [rbp+57h+var_A8]
0x140013979  add     rsi, rax
0x14001397c  jz      loc_140013B9F
0x140013982  mov     [rbp+57h+var_B0], r14
0x140013986  mov     edi, 8
0x14001398b  mov     dword ptr [rbp+57h+pSourceSid], edi
0x14001398e  lea     rax, [rbp+57h+pSourceSid]
0x140013992  mov     [rsp+100h+pcbData], rax; pcbData
0x140013997  lea     rax, [rbp+57h+var_B0]
0x14001399b  mov     [rsp+100h+pvData], rax; pvData
0x1400139a0  mov     [rsp+100h+pdwType], r14; pdwType
0x1400139a5  mov     r9d, edi; dwFlags
0x1400139a8  lea     r8, aBioconsentnoti; "BioConsentNoticeShownTime"
0x1400139af  lea     rdx, aSoftwareMicros_96; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400139b6  mov     r13, 0FFFFFFFF80000001h
0x1400139bd  mov     rcx, r13; hkey
0x1400139c0  call    cs:__imp_RegGetValueW
0x1400139c6  mov     r15d, 80070000h
0x1400139cc  test    eax, eax
0x1400139ce  jle     short loc_1400139D8
0x1400139d0  movzx   eax, ax
0x1400139d3  or      eax, r15d
0x1400139d6  test    eax, eax
0x1400139d8  jns     loc_140013B3D
0x1400139de  mov     [rbp+57h+var_B0], r14
0x1400139e2  mov     dil, 1
0x1400139e5  mov     [rbp+57h+var_C0], dil
0x1400139e9  mov     dword ptr [rbp+57h+pSourceSid], r14d
0x1400139ed  mov     [rbp+57h+var_BC], r12d
0x1400139f1  lea     rax, [rbp+57h+var_BC]
0x1400139f5  mov     [rsp+100h+pcbData], rax; pcbData
0x1400139fa  lea     rax, [rbp+57h+pSourceSid]
0x1400139fe  mov     [rsp+100h+pvData], rax; pvData
0x140013a03  mov     [rsp+100h+pdwType], r14; pdwType
0x140013a08  mov     r9d, 10h; dwFlags
0x140013a0e  lea     r8, aLearnmoreavail_0; "LearnMoreAvailable"
0x140013a15  lea     rdx, aSoftwareMicros_89; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140013a1c  mov     rcx, r13; hkey
0x140013a1f  call    cs:__imp_RegGetValueW
0x140013a25  test    eax, eax
0x140013a27  jle     short loc_140013A31
0x140013a29  movzx   eax, ax
0x140013a2c  or      eax, r15d
0x140013a2f  test    eax, eax
0x140013a31  js      short loc_140013AA4
0x140013a33  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x140013a38  mov     rdx, rax
0x140013a3b  mov     rcx, 0FFFFFFFF00000000h
0x140013a45  and     rdx, rcx
0x140013a48  sub     rdx, rsi
0x140013a4b  mov     ecx, eax
0x140013a4d  add     rdx, rcx
0x140013a50  mov     rcx, 11ED178C6C000h
0x140013a5a  cmp     rdx, rcx
0x140013a5d  setnbe  dil
0x140013a61  mov     [rbp+57h+var_C0], dil
0x140013a65  lea     rcx, [rbp+57h+var_C0]
0x140013a69  call    ??$ShouldShowUnusedBiometricConsentForUserWithBiometrics@AEA_N@BiometricConsentTelemetry@@SAXAEA_N@Z; BiometricConsentTelemetry::ShouldShowUnusedBiometricConsentForUserWithBiometrics<bool &>(bool &)
0x140013a6e  nop
0x140013a6f  test    rbx, rbx
0x140013a72  jz      short loc_140013A7D
0x140013a74  mov     rcx, rbx; hMem
0x140013a77  call    cs:__imp_LocalFree
0x140013a7d  mov     al, dil
0x140013a80  mov     rcx, [rbp+57h+var_50]
0x140013a84  xor     rcx, rsp; StackCookie
0x140013a87  call    __security_check_cookie
0x140013a8c  add     rsp, 0C8h
0x140013a93  pop     r15
0x140013a95  pop     r14
0x140013a97  pop     r13
0x140013a99  pop     r12
0x140013a9b  pop     rdi
0x140013a9c  pop     rsi
0x140013a9d  pop     rbx
0x140013a9e  pop     rbp
0x140013a9f  retn
0x140013aa0  xor     al, al
0x140013aa2  jmp     short loc_140013A80
0x140013aa4  mov     [rbp+57h+var_BC], r12d
0x140013aa8  lea     rax, [rbp+57h+var_BC]
0x140013aac  mov     [rsp+100h+pcbData], rax; pcbData
0x140013ab1  lea     rax, [rbp+57h+pSourceSid]
0x140013ab5  mov     [rsp+100h+pvData], rax; pvData
0x140013aba  mov     [rsp+100h+pdwType], r14; pdwType
0x140013abf  mov     r9d, 10h; dwFlags
0x140013ac5  lea     r8, aLearnmoreavail_1; "LearnMoreAvailableInSCOOBE"
0x140013acc  lea     rdx, aSoftwareMicros_89; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140013ad3  mov     rcx, r13; hkey
0x140013ad6  call    cs:__imp_RegGetValueW
0x140013adc  test    eax, eax
0x140013ade  jle     short loc_140013AE8
0x140013ae0  movzx   eax, ax
0x140013ae3  or      eax, r15d
0x140013ae6  test    eax, eax
0x140013ae8  jns     loc_140013A33
0x140013aee  mov     [rbp+57h+var_BC], r12d
0x140013af2  lea     rax, [rbp+57h+var_BC]
0x140013af6  mov     [rsp+100h+pcbData], rax; pcbData
0x140013afb  lea     rax, [rbp+57h+pSourceSid]
0x140013aff  mov     [rsp+100h+pvData], rax; pvData
0x140013b04  mov     [rsp+100h+pdwType], r14; pdwType
0x140013b09  mov     r9d, 10h; dwFlags
0x140013b0f  lea     r8, aLearnmoreavail; "LearnMoreAvailableInSettings"
0x140013b16  lea     rdx, aSoftwareMicros_96; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140013b1d  mov     rcx, r13; hkey
0x140013b20  call    cs:__imp_RegGetValueW
0x140013b26  test    eax, eax
0x140013b28  jle     short loc_140013B32
0x140013b2a  movzx   eax, ax
0x140013b2d  or      eax, r15d
0x140013b30  test    eax, eax
0x140013b32  jns     loc_140013A33
0x140013b38  jmp     loc_140013A65
0x140013b3d  cmp     dword ptr [rbp+57h+pSourceSid], edi
0x140013b40  jnz     loc_1400139DE
0x140013b46  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x140013b4b  mov     r8, rax
0x140013b4e  mov     rcx, 0FFFFFFFF00000000h
0x140013b58  and     r8, rcx
0x140013b5b  mov     ecx, eax
0x140013b5d  add     r8, rcx
0x140013b60  mov     rax, r8
0x140013b63  sub     rax, rsi
0x140013b66  mov     rcx, 11ED178C6C000h
0x140013b70  cmp     rax, rcx
0x140013b73  jbe     short loc_140013B91
0x140013b75  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x140013b78  shl     rax, 20h
0x140013b7c  sub     r8, rax
0x140013b7f  mov     eax, dword ptr [rbp+57h+var_B0]
0x140013b82  sub     r8, rax
0x140013b85  cmp     r8, rcx
0x140013b88  mov     dil, 1
0x140013b8b  ja      loc_140013A61
0x140013b91  mov     dil, r14b
0x140013b94  jmp     loc_140013A61
0x140013b99  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "Failed to create WINBIO_IDENTITY for user")
0x140013b9e  nop
0x140013b9f  lea     rcx, [rbp+57h+pSourceSid]
0x140013ba3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x140013ba8  jmp     loc_140013AA0
```
