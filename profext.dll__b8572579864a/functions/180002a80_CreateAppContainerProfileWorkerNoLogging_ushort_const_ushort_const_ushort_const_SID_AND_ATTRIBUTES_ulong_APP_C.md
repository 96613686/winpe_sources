# CreateAppContainerProfileWorkerNoLogging(ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,APP_CONTAINER_PROFILE_TYPE,unsigned __int64,_GUID const *,ushort *,void * *)

- ea: `0x180002a80`
- end: `0x180003bf0`
- name: `?CreateAppContainerProfileWorkerNoLogging@@YAJPEBG00PEAU_SID_AND_ATTRIBUTES@@KW4APP_CONTAINER_PROFILE_TYPE@@_KPEBU_GUID@@PEAGPEAPEAX@Z`
- size: `4464`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d610`

## callees

- `0x180001854`
- `0x180001bd4`
- `0x180001cfc`
- `0x180001e98`
- `0x180001ef0`
- `0x180002a80`
- `0x180003c00`
- `0x1800040c0`
- `0x1800044e0`
- `0x180004594`
- `0x180006760`
- `0x18000d980`
- `0x18000f614`
- `0x18000f83c`
- `0x180016740`
- `0x180017014`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000308d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003142`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003211`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003326`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000371e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000308d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003142`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003211`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003326`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000371e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6c`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x180003586`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x180003586`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180002fcd`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180002fcd`
- `ntdll!RtlFreeSid` at `0x18000316c`
- `ntdll!RtlFreeSid` at `0x18000317d`
- `ntdll!RtlFreeSid` at `0x180003337`
- `ntdll!RtlFreeSid` at `0x180003348`
- `ntdll!RtlFreeSid` at `0x180003359`
- `ntdll!RtlFreeSid` at `0x18000336a`
- `ntdll!RtlFreeSid` at `0x18000337b`
- `ntdll!RtlFreeSid` at `0x180003399`
- `ntdll!RtlFreeSid` at `0x18000344d`
- `ntdll!RtlFreeSid` at `0x1800034a3`
- `ntdll!RtlFreeSid` at `0x1800034dd`
- `ntdll!RtlFreeSid` at `0x180003774`
- `ntdll!RtlFreeSid` at `0x18000380e`
- `ntdll!RtlFreeSid` at `0x18000385d`
- `ntdll!RtlFreeSid` at `0x180003893`
- `ntdll!RtlFreeSid` at `0x180003b2a`
- `ntdll!RtlFreeSid` at `0x18000316c`
- `ntdll!RtlFreeSid` at `0x18000317d`
- `ntdll!RtlFreeSid` at `0x180003337`
- `ntdll!RtlFreeSid` at `0x180003348`
- `ntdll!RtlFreeSid` at `0x180003359`
- `ntdll!RtlFreeSid` at `0x18000336a`
- `ntdll!RtlFreeSid` at `0x18000337b`
- `ntdll!RtlFreeSid` at `0x180003399`
- `ntdll!RtlFreeSid` at `0x18000344d`
- `ntdll!RtlFreeSid` at `0x1800034a3`
- `ntdll!RtlFreeSid` at `0x1800034dd`
- `ntdll!RtlFreeSid` at `0x180003774`
- `ntdll!RtlFreeSid` at `0x18000380e`
- `ntdll!RtlFreeSid` at `0x18000385d`
- `ntdll!RtlFreeSid` at `0x180003893`
- `ntdll!RtlFreeSid` at `0x180003b2a`
- `ntdll!RtlDowncaseUnicodeString` at `0x180002f5a`
- `ntdll!RtlDowncaseUnicodeString` at `0x180002f5a`
- `ntdll!NtQueryInformationToken` at `0x180002ddd`
- `ntdll!NtQueryInformationToken` at `0x180002ddd`
- `ntdll!RtlInitUnicodeString` at `0x180002f43`
- `ntdll!RtlInitUnicodeString` at `0x180002f43`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002eb3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003009`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002eb3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003009`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180003617`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180003617`

## string_xrefs

- `0x180002b9f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002c5f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002d1a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002edd`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002f7e`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003033`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003072`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003289`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800032ec`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800033c9`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003431`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003487`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000354c`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800035b9`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003656`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003690`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800036b5`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003703`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003759`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800037dd`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003962`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800039d4`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003a54`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003a98`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CreateAppContainerProfileWorkerNoLogging(
        const unsigned __int16 *a1,
        char *a2,
        char *a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        unsigned __int16 *a9,
        _QWORD *a10)
{
  unsigned __int16 *v14; // r15
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  PSID v17; // rdi
  __int64 v18; // rsi
  int v19; // ebx
  __int64 v20; // r9
  int v21; // eax
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  char *v25; // rax
  __int64 v26; // rsi
  int v27; // ebx
  __int64 v28; // r9
  int v29; // eax
  int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rcx
  char *v33; // rax
  __int64 v34; // rsi
  int v35; // ebx
  __int64 v36; // r9
  int v37; // eax
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // eax
  int v41; // eax
  unsigned int v42; // ebx
  char *v43; // r14
  NTSTATUS v44; // eax
  unsigned int v45; // r8d
  int v46; // ebx
  int v47; // eax
  __int64 v48; // rdx
  unsigned int Profile; // esi
  bool v50; // si
  int UserSid; // eax
  int v52; // eax
  int v53; // ebx
  PSID v54; // rbx
  signed int LastError; // eax
  int v56; // eax
  int v57; // eax
  NTSTATUS v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  signed int v62; // eax
  int v63; // eax
  int v64; // eax
  char *v66; // r13
  char *v67; // r12
  PSID v68; // rcx
  PSID v69; // rcx
  int AppContainerSidFromToken; // eax
  int PackageFamilyNameFromToken; // eax
  int v72; // eax
  __int64 v73; // rdx
  signed int v74; // eax
  int v75; // eax
  LPWSTR v76; // rcx
  PSID v77; // rax
  int v78; // r15d
  int v79; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  int ReturnLengthc; // [rsp+20h] [rbp-E0h]
  int ReturnLengthd; // [rsp+20h] [rbp-E0h]
  int ReturnLengthe; // [rsp+20h] [rbp-E0h]
  int ReturnLengthf; // [rsp+20h] [rbp-E0h]
  int ReturnLengthg; // [rsp+20h] [rbp-E0h]
  __int64 v88; // [rsp+50h] [rbp-B0h]
  __int64 v89; // [rsp+58h] [rbp-A8h]
  PSID pSid; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  PSID v92; // [rsp+80h] [rbp-80h] BYREF
  int TokenInformation; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR v95; // [rsp+98h] [rbp-68h] BYREF
  PSID Sid; // [rsp+A0h] [rbp-60h] BYREF
  ULONG packageFamilyNameLength[2]; // [rsp+A8h] [rbp-58h] BYREF
  char *v98; // [rsp+B0h] [rbp-50h]
  char *v99; // [rsp+B8h] [rbp-48h]
  struct _UNICODE_STRING UniDest; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v101; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v102; // [rsp+D8h] [rbp-28h]
  __int64 v103; // [rsp+E0h] [rbp-20h]
  _QWORD *v104; // [rsp+E8h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  char v106[144]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v103 = a4;
  v98 = a3;
  v99 = a2;
  v102 = a8;
  v14 = a9;
  Sid = a9;
  v104 = a10;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a10 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a9 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
  {
    if ( !a5 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( !a5 )
LABEL_13:
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_14:
  if ( !a1 )
  {
    v19 = -2147024809;
    v17 = 0;
LABEL_166:
    v18 = 0;
    goto LABEL_21;
  }
  v15 = 65;
  v16 = a1;
  while ( *v16 )
  {
    ++v16;
    if ( !--v15 )
    {
      v17 = 0;
      v18 = 0;
      v19 = -2147024809;
      goto LABEL_20;
    }
  }
  v18 = 65 - v15;
  v17 = 0;
  v19 = 0;
LABEL_20:
  if ( v19 < 0 )
    goto LABEL_166;
LABEL_21:
  AppContainerRegistrationHelper::SetAPIContextIfFailed(v19, 0x943u, a1, 0x208u, a9);
  if ( v19 == -2147024809 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x944,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Name %ls",
      (const char *)a1);
    return 2147942487LL;
  }
  v20 = 0;
  if ( !v18 )
    v20 = 2147942487LL;
  v21 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x947,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v20,
          (__int64)"Name %ls",
          (const char *)a1);
  v22 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v21, 0x949u, a1, 0x208u, a9);
  v23 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x949,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v22,
      ReturnLength);
    return v23;
  }
  if ( !v99 )
  {
    v27 = -2147024809;
LABEL_170:
    v26 = 0;
    goto LABEL_32;
  }
  v24 = 512;
  v25 = v99;
  while ( *(_WORD *)v25 )
  {
    v25 += 2;
    if ( !--v24 )
    {
      v26 = 0;
      v27 = -2147024809;
      goto LABEL_31;
    }
  }
  v26 = 512 - v24;
  v27 = 0;
LABEL_31:
  if ( v27 < 0 )
    goto LABEL_170;
LABEL_32:
  AppContainerRegistrationHelper::SetAPIContextIfFailed(v27, 0x94Cu, (const unsigned __int16 *)v99, 0x208u, a9);
  if ( v27 == -2147024809 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x94D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Display %ls",
      v99);
    return 2147942487LL;
  }
  v28 = 0;
  if ( !v26 )
    v28 = 2147942487LL;
  v29 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x950,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v28,
          (__int64)"Display %ls",
          v99);
  v30 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v29, 0x952u, (const unsigned __int16 *)v99, 0x208u, a9);
  v31 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x952,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v30,
      ReturnLengtha);
    return v31;
  }
  if ( !v98 )
  {
    v35 = -2147024809;
LABEL_174:
    v34 = 0;
    goto LABEL_43;
  }
  v32 = 2048;
  v33 = v98;
  while ( *(_WORD *)v33 )
  {
    v33 += 2;
    if ( !--v32 )
    {
      v34 = 0;
      v35 = -2147024809;
      goto LABEL_42;
    }
  }
  v34 = 2048 - v32;
  v35 = 0;
LABEL_42:
  if ( v35 < 0 )
    goto LABEL_174;
LABEL_43:
  AppContainerRegistrationHelper::SetAPIContextIfFailed(v35, 0x955u, (const unsigned __int16 *)v98, 0x208u, a9);
  if ( v35 == -2147024809 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x956,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Disc %ls",
      v98);
    return 2147942487LL;
  }
  v36 = 0;
  if ( !v34 )
    v36 = 2147942487LL;
  v37 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x959,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v36,
          (__int64)"Disc %ls",
          v98);
  v38 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v37, 0x95Bu, (const unsigned __int16 *)v98, 0x208u, a9);
  v39 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v38,
      ReturnLengthb);
    return v39;
  }
  TokenHandle = 0;
  v40 = AppContainerRegistrationHelper::OpenCurrentUserToken((char *)0xE, &TokenHandle);
  v41 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v40, 0x962u, a1, 0x208u, a9);
  v42 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x963,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v41,
      (int)"Name %ls",
      (const char *)a1);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v42;
  }
  TokenInformation = 0;
  packageFamilyNameLength[0] = 0;
  v43 = (char *)TokenHandle;
  v44 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, packageFamilyNameLength);
  v46 = 0;
  if ( v44 < 0 )
  {
    v47 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x168,
            v45,
            (const char *)(unsigned int)v44,
            ReturnLengthc);
  }
  else
  {
    LOBYTE(v46) = TokenInformation != 0;
    v47 = 0;
  }
  Profile = AppContainerRegistrationHelper::SetAPIContextIfFailed(v47, 0x968u, a1, 0x208u, a9);
  if ( (Profile & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x969,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)Profile,
      (int)"Name %ls",
      (const char *)a1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return Profile;
  }
  TokenInformation = 2162688;
  *(_QWORD *)packageFamilyNameLength = 0;
  v101 = 0;
  AppModelPolicy_GetPolicy_Internal(v43, v48, &TokenInformation, &v101, packageFamilyNameLength);
  v50 = TokenInformation == 2162689;
  pSid = 0;
  if ( v46 || TokenInformation == 2162689 )
  {
    v78 = StringCchLengthW(a1, 0x33u, &v101);
    AppContainerRegistrationHelper::SetAPIContextIfFailed(v78, 0x97Bu, a1, 0x208u, (unsigned __int16 *)Sid);
    if ( v78 == -2147024809 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x97C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)0x80070057LL,
        (int)"Name %ls",
        (const char *)a1);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return 2147942487LL;
    }
    if ( v78 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x97D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v78,
        (int)"Name %ls",
        (const char *)a1);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return (unsigned int)v78;
    }
    if ( !v46 )
    {
      if ( !v50 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      packageFamilyNameLength[0] = 65;
      PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v43, packageFamilyNameLength, packageFamilyName);
      if ( PackageFamilyNameFromToken > 0 )
        PackageFamilyNameFromToken = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
      v72 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x98D,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)(unsigned int)PackageFamilyNameFromToken,
              (__int64)"Name %ls",
              (const char *)a1);
      v14 = (unsigned __int16 *)Sid;
      v53 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v72, 0x98Fu, a1, 0x208u, (unsigned __int16 *)Sid);
      if ( v53 >= 0 )
      {
        pSid = 0;
        v74 = PackageSidFromFamilyName(packageFamilyName, &pSid);
        if ( v74 > 0 )
          v74 = (unsigned __int16)v74 | 0x80070000;
        v75 = wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x992,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                (const char *)(unsigned int)v74,
                (__int64)"Name %ls family %ls",
                (const char *)a1,
                packageFamilyName);
        v53 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v75, 0x994u, a1, 0x208u, v14);
        if ( v53 >= 0 )
          goto LABEL_53;
        v73 = 2452;
      }
      else
      {
        v73 = 2447;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v73,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v53,
        ReturnLengthg);
      goto LABEL_112;
    }
    pSid = 0;
    AppContainerSidFromToken = AppContainerRegistrationHelper::GetAppContainerSidFromToken(v43, &pSid);
    v14 = (unsigned __int16 *)Sid;
    v53 = AppContainerRegistrationHelper::SetAPIContextIfFailed(
            AppContainerSidFromToken,
            0x983u,
            a1,
            0x208u,
            (unsigned __int16 *)Sid);
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x984,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v53,
        (int)"Name %ls",
        (const char *)a1);
      v68 = pSid;
      if ( !pSid )
        goto LABEL_107;
LABEL_106:
      RtlFreeSid(v68);
LABEL_107:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return (unsigned int)v53;
    }
  }
LABEL_53:
  Sid = 0;
  UserSid = GetUserSid(v43, &Sid);
  v52 = AppContainerRegistrationHelper::SetAPIContextIfFailed(UserSid, 0x99Au, a1, 0x208u, v14);
  v53 = v52;
  if ( v52 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x99B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v52,
      (int)"Name %ls",
      (const char *)a1);
    if ( Sid )
      ResultFromHeapFree(Sid);
LABEL_112:
    v68 = pSid;
    if ( !pSid )
      goto LABEL_107;
    goto LABEL_106;
  }
  StringSid = 0;
  v54 = Sid;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v56 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x99F,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)LastError,
          (__int64)"Name %ls",
          (const char *)a1);
  v57 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v56, 0x9A1u, a1, 0x208u, v14);
  Profile = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A1,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v57,
      ReturnLengthd);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v54 )
      ResultFromHeapFree(v54);
    v69 = pSid;
    if ( !pSid )
      goto LABEL_109;
LABEL_108:
    RtlFreeSid(v69);
LABEL_109:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return Profile;
  }
  memset_0(v106, 0, 0x82u);
  *(_QWORD *)&UniDest.Length = 8519680;
  UniDest.Buffer = (PWSTR)v106;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a1);
  v58 = RtlDowncaseUnicodeString(&UniDest, &DestinationString, 0);
  v59 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x9AB,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(v58 | 0x10000000u),
          (__int64)"Name %ls",
          (const char *)a1);
  v60 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v59, 0x9ADu, a1, 0x208u, v14);
  Profile = v60;
  if ( v60 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9AD,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v60,
      ReturnLengthe);
    if ( StringSid )
      LocalFree(StringSid);
    if ( !v54 )
    {
LABEL_116:
      v69 = pSid;
      if ( !pSid )
        goto LABEL_109;
      goto LABEL_108;
    }
LABEL_141:
    ResultFromHeapFree(v54);
    goto LABEL_116;
  }
  v92 = 0;
  if ( pSid )
  {
    v79 = AppContainerRegistrationHelper::DeriveChildAppContainerSid(pSid, (char *)UniDest.Buffer, &v92);
    Profile = AppContainerRegistrationHelper::SetAPIContextIfFailed(v79, 0x9C3u, a1, 0x208u, v14);
    if ( (Profile & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9C4,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)Profile,
        (int)"Name %ls",
        v106);
      if ( v92 )
        RtlFreeSid(v92);
      v76 = StringSid;
      if ( StringSid )
        goto LABEL_114;
      goto LABEL_115;
    }
  }
  else
  {
    v61 = AppContainerDeriveSidFromMoniker(UniDest.Buffer, &v92);
    Profile = AppContainerRegistrationHelper::SetAPIContextIfFailed(v61, 0x9BAu, a1, 0x208u, v14);
    if ( (Profile & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9BB,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)Profile,
        (int)"Name %ls",
        v106);
      if ( v92 )
        RtlFreeSid(v92);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v54 )
        ResultFromHeapFree(v54);
      if ( pSid )
        RtlFreeSid(pSid);
      if ( (unsigned __int64)(v43 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        return Profile;
LABEL_92:
      CloseHandle(v43);
      return Profile;
    }
  }
  v95 = 0;
  if ( ConvertSidToStringSidW(v92, &v95) )
  {
    v62 = 0;
  }
  else
  {
    v62 = GetLastError();
    if ( v62 > 0 )
      v62 = (unsigned __int16)v62 | 0x80070000;
  }
  v63 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x9C9,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v62,
          (__int64)"Name %ls",
          (const char *)a1);
  v64 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v63, 0x9CBu, a1, 0x208u, v14);
  Profile = v64;
  if ( v64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9CB,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v64,
      ReturnLengthf);
    if ( v95 )
      LocalFree(v95);
    if ( v92 )
      RtlFreeSid(v92);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v54 )
      ResultFromHeapFree(v54);
    if ( pSid )
      RtlFreeSid(pSid);
    if ( (unsigned __int64)(v43 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return Profile;
    goto LABEL_92;
  }
  v66 = v98;
  v67 = v99;
  Profile = AppContainerRegistrationHelper::CreateProfile(
              pSid,
              UniDest.Buffer,
              v99,
              v98,
              StringSid,
              v95,
              v103,
              a5,
              v92,
              a6,
              520,
              v102,
              v14);
  if ( Profile == -2147024713 || Profile == -2147024886 || Profile == -2147023878 )
  {
    if ( v95 )
      LocalFree(v95);
    if ( v92 )
      RtlFreeSid(v92);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v54 )
      ResultFromHeapFree(v54);
    if ( pSid )
      RtlFreeSid(pSid);
    if ( (unsigned __int64)(v43 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return Profile;
    goto LABEL_92;
  }
  if ( (Profile & 0x80000000) != 0 )
  {
    LODWORD(v89) = a6;
    LODWORD(v88) = a5;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x9E3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)Profile,
      (int)"Name %ls, %ls, %ls, %ls, %ls, %d, %d",
      v106,
      v67,
      v66,
      StringSid,
      v95,
      v88,
      v89);
    if ( v95 )
      LocalFree(v95);
    if ( v92 )
      RtlFreeSid(v92);
    v76 = StringSid;
    if ( StringSid )
LABEL_114:
      LocalFree(v76);
LABEL_115:
    if ( !v54 )
      goto LABEL_116;
    goto LABEL_141;
  }
  v77 = v92;
  v92 = 0;
  *v104 = v77;
  if ( v95 )
  {
    LocalFree(v95);
    v17 = v92;
  }
  if ( v17 )
    RtlFreeSid(v17);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v54 )
    ResultFromHeapFree(v54);
  if ( pSid )
    RtlFreeSid(pSid);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180002a80  push    rbp
0x180002a82  push    rbx
0x180002a83  push    rsi
0x180002a84  push    rdi
0x180002a85  push    r12
0x180002a87  push    r13
0x180002a89  push    r14
0x180002a8b  push    r15
0x180002a8d  lea     rbp, [rsp-138h]
0x180002a95  sub     rsp, 238h
0x180002a9c  mov     rax, cs:__security_cookie
0x180002aa3  xor     rax, rsp
0x180002aa6  mov     [rbp+170h+var_50], rax
0x180002aad  mov     rsi, r9
0x180002ab0  mov     [rbp+170h+var_190], r9
0x180002ab4  mov     rdi, r8
0x180002ab7  mov     [rbp+170h+var_1C0], r8
0x180002abb  mov     rbx, rdx
0x180002abe  mov     [rbp+170h+var_1B8], rdx
0x180002ac2  mov     r12, rcx
0x180002ac5  mov     rax, [rbp+170h+arg_38]
0x180002acc  mov     [rbp+170h+var_198], rax
0x180002ad0  mov     r15, [rbp+170h+arg_40]
0x180002ad7  mov     [rbp+170h+Sid], r15
0x180002adb  mov     r14, [rbp+170h+arg_48]
0x180002ae2  mov     [rbp+170h+var_188], r14
0x180002ae6  test    rcx, rcx
0x180002ae9  jz      loc_1800038B1
0x180002aef  test    rbx, rbx
0x180002af2  jz      loc_1800038BB
0x180002af8  test    rdi, rdi
0x180002afb  jz      loc_1800038C5
0x180002b01  test    r14, r14
0x180002b04  jz      loc_1800038CF
0x180002b0a  test    r15, r15
0x180002b0d  jz      loc_1800038D9
0x180002b13  test    rsi, rsi
0x180002b16  jnz     loc_1800038ED
0x180002b1c  cmp     [rbp+170h+arg_20], esi
0x180002b22  jnz     loc_1800038E3
0x180002b28  test    r12, r12
0x180002b2b  jz      loc_180003904
0x180002b31  mov     ecx, 41h ; 'A'
0x180002b36  mov     rax, r12
0x180002b39  nop     dword ptr [rax+00000000h]
0x180002b40  cmp     word ptr [rax], 0
0x180002b44  jz      short loc_180002B5F
0x180002b46  add     rax, 2
0x180002b4a  sub     rcx, 1
0x180002b4e  jnz     short loc_180002B40
0x180002b50  xor     edi, edi
0x180002b52  mov     esi, edi
0x180002b54  mov     r13d, 80070057h
0x180002b5a  mov     ebx, r13d
0x180002b5d  jmp     short loc_180002B71
0x180002b5f  mov     esi, 41h ; 'A'
0x180002b64  sub     rsi, rcx
0x180002b67  xor     edi, edi
0x180002b69  mov     ebx, edi
0x180002b6b  mov     r13d, 80070057h
0x180002b71  test    ebx, ebx
0x180002b73  js      loc_18000390F
0x180002b79  mov     [rsp+270h+ReturnLength], r15; unsigned __int16 *
0x180002b7e  mov     r9d, 208h; unsigned __int64
0x180002b84  mov     r8, r12; unsigned __int16 *
0x180002b87  mov     edx, 943h; unsigned int
0x180002b8c  mov     ecx, ebx; int
0x180002b8e  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002b93  mov     rcx, [rbp+178h]; this
0x180002b9a  mov     [rsp+270h+var_248], r12; char *
0x180002b9f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002ba6  cmp     ebx, r13d
0x180002ba9  jz      loc_180003917
0x180002baf  test    ebx, ebx
0x180002bb1  js      loc_180003938
0x180002bb7  mov     r9d, edi
0x180002bba  test    rsi, rsi
0x180002bbd  cmovz   r9d, r13d; char *
0x180002bc1  lea     r14, aNameLs; "Name %ls"
0x180002bc8  mov     [rsp+270h+ReturnLength], r14; __int64
0x180002bcd  mov     edx, 947h; void *
0x180002bd2  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180002bd7  mov     [rsp+270h+ReturnLength], r15; int
0x180002bdc  mov     r9d, 208h; unsigned __int64
0x180002be2  mov     r8, r12; unsigned __int16 *
0x180002be5  mov     edx, 949h; unsigned int
0x180002bea  mov     ecx, eax; int
0x180002bec  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002bf1  mov     ebx, eax
0x180002bf3  test    eax, eax
0x180002bf5  js      loc_180003958
0x180002bfb  mov     rdx, [rbp+170h+var_1B8]
0x180002bff  test    rdx, rdx
0x180002c02  jz      loc_18000397A
0x180002c08  mov     esi, 200h
0x180002c0d  mov     ecx, esi
0x180002c0f  mov     rax, rdx
0x180002c12  cmp     word ptr [rax], 0
0x180002c16  jz      short loc_180002C2A
0x180002c18  add     rax, 2
0x180002c1c  sub     rcx, 1
0x180002c20  jnz     short loc_180002C12
0x180002c22  mov     rsi, rdi
0x180002c25  mov     ebx, r13d
0x180002c28  jmp     short loc_180002C2F
0x180002c2a  sub     rsi, rcx
0x180002c2d  mov     ebx, edi
0x180002c2f  test    ebx, ebx
0x180002c31  js      loc_18000397D
0x180002c37  mov     [rsp+270h+ReturnLength], r15; unsigned __int16 *
0x180002c3c  mov     r9d, 208h; unsigned __int64
0x180002c42  mov     r8, rdx; unsigned __int16 *
0x180002c45  mov     edx, 94Ch; unsigned int
0x180002c4a  mov     ecx, ebx; int
0x180002c4c  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002c51  mov     rcx, [rbp+178h]; this
0x180002c58  lea     rax, aDisplayLs; "Display %ls"
0x180002c5f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002c66  cmp     ebx, r13d
0x180002c69  jz      loc_180003985
0x180002c6f  test    ebx, ebx
0x180002c71  js      loc_1800039A8
0x180002c77  mov     r9d, edi
0x180002c7a  test    rsi, rsi
0x180002c7d  cmovz   r9d, r13d; char *
0x180002c81  mov     rbx, [rbp+170h+var_1B8]
0x180002c85  mov     [rsp+270h+var_248], rbx; char *
0x180002c8a  mov     [rsp+270h+ReturnLength], rax; __int64
0x180002c8f  mov     edx, 950h; void *
0x180002c94  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180002c99  mov     [rsp+270h+ReturnLength], r15; int
0x180002c9e  mov     r9d, 208h; unsigned __int64
0x180002ca4  mov     r8, rbx; unsigned __int16 *
0x180002ca7  mov     edx, 952h; unsigned int
0x180002cac  mov     ecx, eax; int
0x180002cae  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002cb3  mov     ebx, eax
0x180002cb5  test    eax, eax
0x180002cb7  js      loc_1800039CA
0x180002cbd  mov     rdx, [rbp+170h+var_1C0]
0x180002cc1  test    rdx, rdx
0x180002cc4  jz      loc_1800039EC
0x180002cca  mov     esi, 800h
0x180002ccf  mov     ecx, esi
0x180002cd1  mov     rax, rdx
0x180002cd4  cmp     word ptr [rax], 0
0x180002cd8  jz      short loc_180002CEC
0x180002cda  add     rax, 2
0x180002cde  sub     rcx, 1
0x180002ce2  jnz     short loc_180002CD4
0x180002ce4  mov     rsi, rdi
0x180002ce7  mov     ebx, r13d
0x180002cea  jmp     short loc_180002CF1
0x180002cec  sub     rsi, rcx
0x180002cef  mov     ebx, edi
0x180002cf1  test    ebx, ebx
0x180002cf3  js      loc_1800039EF
0x180002cf9  mov     [rsp+270h+ReturnLength], r15; unsigned __int16 *
0x180002cfe  mov     r9d, 208h; unsigned __int64
0x180002d04  mov     r8, rdx; unsigned __int16 *
0x180002d07  mov     edx, 955h; unsigned int
0x180002d0c  mov     ecx, ebx; int
0x180002d0e  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002d13  mov     rcx, [rbp+178h]; this
0x180002d1a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002d21  cmp     ebx, r13d
0x180002d24  jz      loc_1800039F7
0x180002d2a  test    ebx, ebx
0x180002d2c  js      loc_180003A21
0x180002d32  mov     r9d, edi
0x180002d35  test    rsi, rsi
0x180002d38  cmovz   r9d, r13d; char *
0x180002d3c  mov     rbx, [rbp+170h+var_1C0]
0x180002d40  mov     [rsp+270h+var_248], rbx; char *
0x180002d45  lea     rax, aDiscLs; "Disc %ls"
0x180002d4c  mov     [rsp+270h+ReturnLength], rax; __int64
0x180002d51  mov     edx, 959h; void *
0x180002d56  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180002d5b  mov     [rsp+270h+ReturnLength], r15; int
0x180002d60  mov     r9d, 208h; unsigned __int64
0x180002d66  mov     r8, rbx; unsigned __int16 *
0x180002d69  mov     edx, 95Bh; unsigned int
0x180002d6e  mov     ecx, eax; int
0x180002d70  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002d75  mov     ebx, eax
0x180002d77  test    eax, eax
0x180002d79  js      loc_180003A4A
0x180002d7f  mov     [rsp+270h+TokenHandle], rdi
0x180002d84  lea     rdx, [rsp+270h+TokenHandle]; void **
0x180002d89  mov     ecx, 0Eh; char *
0x180002d8e  call    ?OpenCurrentUserToken@AppContainerRegistrationHelper@@SAJKPEAPEAX@Z; AppContainerRegistrationHelper::OpenCurrentUserToken(ulong,void * *)
0x180002d93  mov     ecx, eax; int
0x180002d95  mov     [rsp+270h+ReturnLength], r15; unsigned __int16 *
0x180002d9a  mov     r9d, 208h; unsigned __int64
0x180002da0  mov     r8, r12; unsigned __int16 *
0x180002da3  mov     edx, 962h; unsigned int
0x180002da8  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002dad  mov     ebx, eax
0x180002daf  test    eax, eax
0x180002db1  js      loc_1800032D8
0x180002db7  mov     [rbp+170h+TokenInformation], edi
0x180002dba  mov     [rbp+170h+packageFamilyNameLength], edi
0x180002dbd  lea     rax, [rbp+170h+packageFamilyNameLength]
0x180002dc1  mov     [rsp+270h+ReturnLength], rax; int
0x180002dc6  mov     r9d, 4; TokenInformationLength
0x180002dcc  lea     r8, [rbp+170h+TokenInformation]; TokenInformation
0x180002dd0  mov     edx, 1Dh; TokenInformationClass
0x180002dd5  mov     r14, [rsp+270h+TokenHandle]
0x180002dda  mov     rcx, r14; TokenHandle
0x180002ddd  call    cs:__imp_NtQueryInformationToken
0x180002de4  nop     dword ptr [rax+rax+00h]
0x180002de9  mov     ebx, edi
0x180002deb  test    eax, eax
0x180002ded  js      loc_180003153
0x180002df3  cmp     [rbp+170h+TokenInformation], 0
0x180002df7  setnz   bl
0x180002dfa  mov     eax, edi
0x180002dfc  mov     [rsp+270h+ReturnLength], r15; unsigned __int16 *
0x180002e01  mov     r9d, 208h; unsigned __int64
0x180002e07  mov     r8, r12; unsigned __int16 *
0x180002e0a  mov     edx, 968h; unsigned int
0x180002e0f  mov     ecx, eax; int
0x180002e11  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002e16  mov     esi, eax
0x180002e18  test    eax, eax
0x180002e1a  js      loc_180003A7D
0x180002e20  mov     [rbp+170h+TokenInformation], 210000h
0x180002e27  mov     qword ptr [rbp+170h+packageFamilyNameLength], rdi
0x180002e2b  mov     [rbp+170h+var_1A0], rdi
0x180002e2f  lea     rax, [rbp+170h+packageFamilyNameLength]
0x180002e33  mov     [rsp+270h+ReturnLength], rax
0x180002e38  lea     r9, [rbp+170h+var_1A0]
0x180002e3c  lea     r8, [rbp+170h+TokenInformation]
0x180002e40  mov     rcx, r14
0x180002e43  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x180002e48  cmp     [rbp+170h+TokenInformation], 210001h
0x180002e4f  setz    sil
0x180002e53  mov     [rsp+270h+pSid], rdi
0x180002e58  test    ebx, ebx
0x180002e5a  jnz     loc_180003AB9
0x180002e60  test    sil, sil
0x180002e63  jnz     loc_180003AB9
0x180002e69  lea     r13, aNameLs; "Name %ls"
0x180002e70  mov     [rbp+170h+Sid], rdi
0x180002e74  lea     rdx, [rbp+170h+Sid]; void **
0x180002e78  mov     rcx, r14; TokenHandle
0x180002e7b  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180002e80  mov     ecx, eax; int
0x180002e82  mov     [rsp+270h+ReturnLength], r15; unsigned __int16 *
0x180002e87  mov     r9d, 208h; unsigned __int64
0x180002e8d  mov     r8, r12; unsigned __int16 *
0x180002e90  mov     edx, 99Ah; unsigned int
0x180002e95  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002e9a  mov     ebx, eax
0x180002e9c  test    eax, eax
0x180002e9e  js      loc_1800033B5
0x180002ea4  mov     [rbp+170h+StringSid], rdi
0x180002ea8  lea     rdx, [rbp+170h+StringSid]; StringSid
0x180002eac  mov     rbx, [rbp+170h+Sid]
0x180002eb0  mov     rcx, rbx; Sid
0x180002eb3  call    cs:__imp_ConvertSidToStringSidW
0x180002eba  nop     dword ptr [rax+rax+00h]
0x180002ebf  test    eax, eax
0x180002ec1  jz      loc_1800030FF
0x180002ec7  mov     eax, edi
0x180002ec9  mov     rcx, [rbp+178h]; this
0x180002ed0  mov     [rsp+270h+var_248], r12; char *
0x180002ed5  mov     [rsp+270h+ReturnLength], r13; __int64
0x180002eda  mov     r9d, eax; char *
0x180002edd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002ee4  mov     edx, 99Fh; void *
0x180002ee9  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180002eee  mov     [rsp+270h+ReturnLength], r15; int
0x180002ef3  mov     r9d, 208h; unsigned __int64
0x180002ef9  mov     r8, r12; unsigned __int16 *
0x180002efc  mov     edx, 9A1h; unsigned int
0x180002f01  mov     ecx, eax; int
0x180002f03  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002f08  mov     esi, eax
0x180002f0a  test    eax, eax
0x180002f0c  js      loc_1800036AB
0x180002f12  mov     esi, 82h
0x180002f17  mov     r8d, esi; Size
0x180002f1a  xor     edx, edx; Val
0x180002f1c  lea     rcx, [rbp+170h+var_170]; void *
0x180002f20  call    memset_0
0x180002f25  xorps   xmm0, xmm0
0x180002f28  movups  xmmword ptr [rbp+170h+UniDest.Length], xmm0
0x180002f2c  lea     rax, [rbp+170h+var_170]
0x180002f30  mov     [rbp+170h+UniDest.Buffer], rax
0x180002f34  mov     [rbp+170h+UniDest.MaximumLength], si
0x180002f38  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x180002f3c  mov     rdx, r12; SourceString
0x180002f3f  lea     rcx, [rbp+170h+DestinationString]; DestinationString
0x180002f43  call    cs:__imp_RtlInitUnicodeString
0x180002f4a  nop     dword ptr [rax+rax+00h]
0x180002f4f  xor     r8d, r8d; AllocateDestinationString
0x180002f52  lea     rdx, [rbp+170h+DestinationString]; UniSource
0x180002f56  lea     rcx, [rbp+170h+UniDest]; UniDest
0x180002f5a  call    cs:__imp_RtlDowncaseUnicodeString
  ... truncated ...
```
