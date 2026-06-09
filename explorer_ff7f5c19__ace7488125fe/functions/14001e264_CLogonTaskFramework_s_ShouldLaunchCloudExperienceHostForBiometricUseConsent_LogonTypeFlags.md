# CLogonTaskFramework::s_ShouldLaunchCloudExperienceHostForBiometricUseConsent(LogonTypeFlags)

- ea: `0x14001e264`
- end: `0x14001e69f`
- name: `?s_ShouldLaunchCloudExperienceHostForBiometricUseConsent@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z`
- size: `1083`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400a08d0`

## callees

- `0x14001da84`
- `0x14001e1b0`
- `0x14001e1e0`
- `0x14001e264`
- `0x14001e6a8`
- `0x14001e750`
- `0x14001e9bc`
- `0x1400203a4`
- `0x140026320`
- `0x140026964`
- `0x1400485bc`
- `0x14010e160`
- `0x14010ed90`
- `0x1401bf000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e31b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e35d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e493`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e4f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e5bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e60c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e31b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e35d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e493`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e4f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e5bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001e60c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001e556`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001e556`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14001e2c6`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14001e2c6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001e3f5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001e3f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001e40c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001e40c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001e292`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14001e292`
- `ext-ms-win-biometrics-winbio-core-l1-1-5!WinBioGetLastBioUseTime` at `0x14001e42e`
- `ext-ms-win-biometrics-winbio-core-l1-1-5!WinBioGetLastBioUseTime` at `0x14001e42e`

## string_xrefs

- `0x14001e30a`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x14001e353`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

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
    || (unsigned int)IsCurrentUserAssignedAccessSingleAppClassicApp() )
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
0x14001e264  push    rbp
0x14001e266  push    rbx
0x14001e267  push    rsi
0x14001e268  push    rdi
0x14001e269  push    r12
0x14001e26b  push    r13
0x14001e26d  push    r14
0x14001e26f  push    r15
0x14001e271  lea     rbp, [rsp-1Fh]
0x14001e276  sub     rsp, 0C8h
0x14001e27d  mov     rax, cs:__security_cookie
0x14001e284  xor     rax, rsp
0x14001e287  mov     [rbp+57h+var_50], rax
0x14001e28b  mov     ebx, ecx
0x14001e28d  mov     ecx, 1000h; nIndex
0x14001e292  call    cs:__imp_GetSystemMetrics
0x14001e299  nop     dword ptr [rax+rax+00h]
0x14001e29e  xor     r14d, r14d
0x14001e2a1  test    eax, eax
0x14001e2a3  jnz     loc_14001E586
0x14001e2a9  test    ebx, 330Ah
0x14001e2af  jnz     loc_14001E586
0x14001e2b5  call    ?s_IsCompanionDeviceAccount@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsCompanionDeviceAccount(void)
0x14001e2ba  test    al, al
0x14001e2bc  jnz     loc_14001E586
0x14001e2c2  lea     ecx, [r14+0Dh]; dwOS
0x14001e2c6  call    cs:__imp_IsOS
0x14001e2cd  nop     dword ptr [rax+rax+00h]
0x14001e2d2  test    eax, eax
0x14001e2d4  jnz     loc_14001E586
0x14001e2da  mov     dword ptr [rbp+57h+pSourceSid], r14d
0x14001e2de  lea     r12d, [r14+4]
0x14001e2e2  mov     [rbp+57h+var_BC], r12d
0x14001e2e6  lea     rax, [rbp+57h+var_BC]
0x14001e2ea  mov     [rsp+100h+pcbData], rax; pcbData
0x14001e2ef  lea     rax, [rbp+57h+pSourceSid]
0x14001e2f3  mov     [rsp+100h+pvData], rax; pvData
0x14001e2f8  mov     [rsp+100h+pdwType], r14; pdwType
0x14001e2fd  mov     r9d, 10010h; dwFlags
0x14001e303  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x14001e30a  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x14001e311  mov     rbx, 0FFFFFFFF80000002h
0x14001e318  mov     rcx, rbx; hkey
0x14001e31b  call    cs:__imp_RegGetValueW
0x14001e322  nop     dword ptr [rax+rax+00h]
0x14001e327  test    eax, eax
0x14001e329  jz      short loc_14001E369
0x14001e32b  mov     [rbp+57h+var_BC], r12d
0x14001e32f  lea     rax, [rbp+57h+var_BC]
0x14001e333  mov     [rsp+100h+pcbData], rax; pcbData
0x14001e338  lea     rax, [rbp+57h+pSourceSid]
0x14001e33c  mov     [rsp+100h+pvData], rax; pvData
0x14001e341  mov     [rsp+100h+pdwType], r14; pdwType
0x14001e346  mov     r9d, 20010010h; dwFlags
0x14001e34c  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x14001e353  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001e35a  mov     rcx, rbx; hkey
0x14001e35d  call    cs:__imp_RegGetValueW
0x14001e364  nop     dword ptr [rax+rax+00h]
0x14001e369  cmp     dword ptr [rbp+57h+pSourceSid], r14d
0x14001e36d  jnz     loc_14001E586
0x14001e373  call    ?IsPreserveOobeAutologonCredentialsSet@@YA_NXZ; IsPreserveOobeAutologonCredentialsSet(void)
0x14001e378  test    al, al
0x14001e37a  jnz     loc_14001E586
0x14001e380  call    ?IsUnattendedAutoLogonSet@@YA_NXZ; IsUnattendedAutoLogonSet(void)
0x14001e385  test    al, al
0x14001e387  jnz     loc_14001E586
0x14001e38d  mov     rbx, 0FFFFFFFFFFFFFFFCh
0x14001e394  mov     rcx, rbx; TokenHandle
0x14001e397  call    IsUserAssignedAccessSingleApp
0x14001e39c  test    eax, eax
0x14001e39e  jnz     loc_14001E586
0x14001e3a4  mov     rcx, rbx; TokenHandle
0x14001e3a7  call    IsUserAssignedAccessMultiApp
0x14001e3ac  test    eax, eax
0x14001e3ae  jnz     loc_14001E586
0x14001e3b4  call    IsCurrentUserAssignedAccessSingleAppClassicApp
0x14001e3b9  test    eax, eax
0x14001e3bb  jnz     loc_14001E586
0x14001e3c1  xor     edx, edx; Val
0x14001e3c3  lea     r8d, [rbx+50h]; Size
0x14001e3c7  lea     rcx, [rbp+57h+var_A0]; void *
0x14001e3cb  call    memset_0
0x14001e3d0  mov     [rbp+57h+pSourceSid], r14
0x14001e3d4  lea     rcx, [rbp+57h+pSourceSid]; void **
0x14001e3d8  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x14001e3dd  test    eax, eax
0x14001e3df  js      loc_14001E68B
0x14001e3e5  mov     rbx, [rbp+57h+pSourceSid]
0x14001e3e9  mov     r8, rbx; pSourceSid
0x14001e3ec  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x14001e3f0  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x14001e3f5  call    cs:__imp_CopySid
0x14001e3fc  nop     dword ptr [rax+rax+00h]
0x14001e401  test    eax, eax
0x14001e403  jz      loc_14001E68B
0x14001e409  mov     rcx, rbx; pSid
0x14001e40c  call    cs:__imp_GetLengthSid
0x14001e413  nop     dword ptr [rax+rax+00h]
0x14001e418  mov     [rbp+57h+var_9C], eax
0x14001e41b  mov     [rbp+57h+var_A0], 3
0x14001e422  mov     [rbp+57h+var_A8], r14
0x14001e426  lea     rdx, [rbp+57h+var_A8]
0x14001e42a  lea     rcx, [rbp+57h+var_A0]
0x14001e42e  call    cs:__imp_WinBioGetLastBioUseTime
0x14001e435  nop     dword ptr [rax+rax+00h]
0x14001e43a  test    eax, eax
0x14001e43c  js      loc_14001E691
0x14001e442  mov     esi, dword ptr [rbp+57h+var_A8+4]
0x14001e445  shl     rsi, 20h
0x14001e449  mov     eax, dword ptr [rbp+57h+var_A8]
0x14001e44c  add     rsi, rax
0x14001e44f  jz      loc_14001E691
0x14001e455  mov     [rbp+57h+var_B0], r14
0x14001e459  mov     edi, 8
0x14001e45e  mov     dword ptr [rbp+57h+pSourceSid], edi
0x14001e461  lea     rax, [rbp+57h+pSourceSid]
0x14001e465  mov     [rsp+100h+pcbData], rax; pcbData
0x14001e46a  lea     rax, [rbp+57h+var_B0]
0x14001e46e  mov     [rsp+100h+pvData], rax; pvData
0x14001e473  mov     [rsp+100h+pdwType], r14; pdwType
0x14001e478  mov     r9d, edi; dwFlags
0x14001e47b  lea     r8, aBioconsentnoti; "BioConsentNoticeShownTime"
0x14001e482  lea     rdx, aSoftwareMicros_96; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001e489  mov     r13, 0FFFFFFFF80000001h
0x14001e490  mov     rcx, r13; hkey
0x14001e493  call    cs:__imp_RegGetValueW
0x14001e49a  nop     dword ptr [rax+rax+00h]
0x14001e49f  mov     r15d, 80070000h
0x14001e4a5  test    eax, eax
0x14001e4a7  jle     short loc_14001E4B1
0x14001e4a9  movzx   eax, ax
0x14001e4ac  or      eax, r15d
0x14001e4af  test    eax, eax
0x14001e4b1  jns     loc_14001E62F
0x14001e4b7  mov     [rbp+57h+var_B0], r14
0x14001e4bb  mov     dil, 1
0x14001e4be  mov     [rbp+57h+var_C0], dil
0x14001e4c2  mov     dword ptr [rbp+57h+pSourceSid], r14d
0x14001e4c6  mov     [rbp+57h+var_BC], r12d
0x14001e4ca  lea     rax, [rbp+57h+var_BC]
0x14001e4ce  mov     [rsp+100h+pcbData], rax; pcbData
0x14001e4d3  lea     rax, [rbp+57h+pSourceSid]
0x14001e4d7  mov     [rsp+100h+pvData], rax; pvData
0x14001e4dc  mov     [rsp+100h+pdwType], r14; pdwType
0x14001e4e1  mov     r9d, 10h; dwFlags
0x14001e4e7  lea     r8, aLearnmoreavail_0; "LearnMoreAvailable"
0x14001e4ee  lea     rdx, aSoftwareMicros_89; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001e4f5  mov     rcx, r13; hkey
0x14001e4f8  call    cs:__imp_RegGetValueW
0x14001e4ff  nop     dword ptr [rax+rax+00h]
0x14001e504  test    eax, eax
0x14001e506  jle     short loc_14001E510
0x14001e508  movzx   eax, ax
0x14001e50b  or      eax, r15d
0x14001e50e  test    eax, eax
0x14001e510  js      short loc_14001E58A
0x14001e512  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x14001e517  mov     rdx, rax
0x14001e51a  mov     rcx, 0FFFFFFFF00000000h
0x14001e524  and     rdx, rcx
0x14001e527  sub     rdx, rsi
0x14001e52a  mov     ecx, eax
0x14001e52c  add     rdx, rcx
0x14001e52f  mov     rcx, 11ED178C6C000h
0x14001e539  cmp     rdx, rcx
0x14001e53c  setnbe  dil
0x14001e540  mov     [rbp+57h+var_C0], dil
0x14001e544  lea     rcx, [rbp+57h+var_C0]
0x14001e548  call    ??$ShouldShowUnusedBiometricConsentForUserWithBiometrics@AEA_N@BiometricConsentTelemetry@@SAXAEA_N@Z; BiometricConsentTelemetry::ShouldShowUnusedBiometricConsentForUserWithBiometrics<bool &>(bool &)
0x14001e54d  nop
0x14001e54e  test    rbx, rbx
0x14001e551  jz      short loc_14001E562
0x14001e553  mov     rcx, rbx; hMem
0x14001e556  call    cs:__imp_LocalFree
0x14001e55d  nop     dword ptr [rax+rax+00h]
0x14001e562  mov     al, dil
0x14001e565  mov     rcx, [rbp+57h+var_50]
0x14001e569  xor     rcx, rsp; StackCookie
0x14001e56c  call    __security_check_cookie
0x14001e571  add     rsp, 0C8h
0x14001e578  pop     r15
0x14001e57a  pop     r14
0x14001e57c  pop     r13
0x14001e57e  pop     r12
0x14001e580  pop     rdi
0x14001e581  pop     rsi
0x14001e582  pop     rbx
0x14001e583  pop     rbp
0x14001e584  retn
0x14001e586  xor     al, al
0x14001e588  jmp     short loc_14001E565
0x14001e58a  mov     [rbp+57h+var_BC], r12d
0x14001e58e  lea     rax, [rbp+57h+var_BC]
0x14001e592  mov     [rsp+100h+pcbData], rax; pcbData
0x14001e597  lea     rax, [rbp+57h+pSourceSid]
0x14001e59b  mov     [rsp+100h+pvData], rax; pvData
0x14001e5a0  mov     [rsp+100h+pdwType], r14; pdwType
0x14001e5a5  mov     r9d, 10h; dwFlags
0x14001e5ab  lea     r8, aLearnmoreavail_1; "LearnMoreAvailableInSCOOBE"
0x14001e5b2  lea     rdx, aSoftwareMicros_89; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001e5b9  mov     rcx, r13; hkey
0x14001e5bc  call    cs:__imp_RegGetValueW
0x14001e5c3  nop     dword ptr [rax+rax+00h]
0x14001e5c8  test    eax, eax
0x14001e5ca  jle     short loc_14001E5D4
0x14001e5cc  movzx   eax, ax
0x14001e5cf  or      eax, r15d
0x14001e5d2  test    eax, eax
0x14001e5d4  jns     loc_14001E512
0x14001e5da  mov     [rbp+57h+var_BC], r12d
0x14001e5de  lea     rax, [rbp+57h+var_BC]
0x14001e5e2  mov     [rsp+100h+pcbData], rax; pcbData
0x14001e5e7  lea     rax, [rbp+57h+pSourceSid]
0x14001e5eb  mov     [rsp+100h+pvData], rax; pvData
0x14001e5f0  mov     [rsp+100h+pdwType], r14; pdwType
0x14001e5f5  mov     r9d, 10h; dwFlags
0x14001e5fb  lea     r8, aLearnmoreavail; "LearnMoreAvailableInSettings"
0x14001e602  lea     rdx, aSoftwareMicros_96; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001e609  mov     rcx, r13; hkey
0x14001e60c  call    cs:__imp_RegGetValueW
0x14001e613  nop     dword ptr [rax+rax+00h]
0x14001e618  test    eax, eax
0x14001e61a  jle     short loc_14001E624
0x14001e61c  movzx   eax, ax
0x14001e61f  or      eax, r15d
0x14001e622  test    eax, eax
0x14001e624  jns     loc_14001E512
0x14001e62a  jmp     loc_14001E544
0x14001e62f  cmp     dword ptr [rbp+57h+pSourceSid], edi
0x14001e632  jnz     loc_14001E4B7
0x14001e638  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x14001e63d  mov     r8, rax
0x14001e640  mov     rcx, 0FFFFFFFF00000000h
0x14001e64a  and     r8, rcx
0x14001e64d  mov     ecx, eax
0x14001e64f  add     r8, rcx
0x14001e652  mov     rax, r8
0x14001e655  sub     rax, rsi
0x14001e658  mov     rcx, 11ED178C6C000h
0x14001e662  cmp     rax, rcx
0x14001e665  jbe     short loc_14001E683
0x14001e667  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x14001e66a  shl     rax, 20h
0x14001e66e  sub     r8, rax
0x14001e671  mov     eax, dword ptr [rbp+57h+var_B0]
0x14001e674  sub     r8, rax
0x14001e677  cmp     r8, rcx
0x14001e67a  mov     dil, 1
0x14001e67d  ja      loc_14001E540
0x14001e683  mov     dil, r14b
0x14001e686  jmp     loc_14001E540
0x14001e68b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001e690  nop
0x14001e691  lea     rcx, [rbp+57h+pSourceSid]
0x14001e695  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14001e69a  jmp     loc_14001E586
```
