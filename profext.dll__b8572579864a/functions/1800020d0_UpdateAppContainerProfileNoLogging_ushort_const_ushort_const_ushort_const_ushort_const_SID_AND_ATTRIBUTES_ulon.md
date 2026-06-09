# UpdateAppContainerProfileNoLogging(ushort const *,ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,APP_CONTAINER_PROFILE_TYPE,unsigned __int64,_GUID const *,ushort *)

- ea: `0x1800020d0`
- end: `0x180002a6c`
- name: `?UpdateAppContainerProfileNoLogging@@YAJPEBG000PEAU_SID_AND_ATTRIBUTES@@KW4APP_CONTAINER_PROFILE_TYPE@@_KPEBU_GUID@@PEAG@Z`
- size: `2460`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e650`

## callees

- `0x180001854`
- `0x180001ba0`
- `0x180001ef0`
- `0x180002030`
- `0x1800020d0`
- `0x180003c00`
- `0x180004030`
- `0x1800040c0`
- `0x1800044e0`
- `0x180004594`
- `0x18000beb0`
- `0x18000ea1c`
- `0x18000f440`
- `0x18000f614`
- `0x180016740`
- `0x180017014`
- `0x18001a86c`
- `0x18001b914`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800024fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800024fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028d6`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x1800029d5`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x1800029d5`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180002660`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180002660`
- `ntdll!RtlFreeSid` at `0x180002431`
- `ntdll!RtlFreeSid` at `0x18000244f`
- `ntdll!RtlFreeSid` at `0x1800024ef`
- `ntdll!RtlFreeSid` at `0x1800027d6`
- `ntdll!RtlFreeSid` at `0x1800027ed`
- `ntdll!RtlFreeSid` at `0x180002431`
- `ntdll!RtlFreeSid` at `0x18000244f`
- `ntdll!RtlFreeSid` at `0x1800024ef`
- `ntdll!RtlFreeSid` at `0x1800027d6`
- `ntdll!RtlFreeSid` at `0x1800027ed`
- `ntdll!RtlDowncaseUnicodeString` at `0x180002590`
- `ntdll!RtlDowncaseUnicodeString` at `0x180002590`
- `ntdll!RtlInitUnicodeString` at `0x180002579`
- `ntdll!RtlInitUnicodeString` at `0x180002579`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180002517`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180002517`

## string_xrefs

- `0x18000222d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800021eb`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000228a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800022df`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800023a1`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002405`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000247c`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800024ae`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800025d4`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000261e`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002684`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002749`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002778`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800027a7`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800028a7`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002932`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180002a30`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UpdateAppContainerProfileNoLogging(
        const unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        unsigned __int16 *a10)
{
  unsigned __int16 *v14; // rdx
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rdi
  unsigned int v18; // esi
  int v19; // ebx
  __int64 v20; // r9
  int v21; // ebx
  int v22; // eax
  wil::details::in1diag3 *v23; // rcx
  __int64 v25; // rdi
  int v26; // ebx
  __int64 v27; // rcx
  const unsigned __int16 *v28; // rax
  int v29; // eax
  unsigned __int16 *v30; // rsi
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // ebx
  PSID v34; // rcx
  int AppContainerSidFromToken; // ebx
  PSID v36; // rdi
  DWORD LastError; // ebx
  unsigned int v38; // ebx
  NTSTATUS v39; // ebx
  unsigned int v40; // eax
  int v41; // eax
  int v42; // eax
  __int64 v43; // rsi
  __int64 v44; // r14
  PSID v45; // rcx
  __int64 v46; // rdx
  HANDLE v47; // rbx
  int IsAppContainerToken; // edi
  __int64 v49; // rdx
  unsigned int PackageFamilyNameFromToken; // ebx
  unsigned int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+20h] [rbp-E0h]
  __int64 v58; // [rsp+50h] [rbp-B0h]
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+70h] [rbp-90h] BYREF
  PSID v62; // [rsp+78h] [rbp-88h] BYREF
  int v63; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING UniDest; // [rsp+88h] [rbp-78h] BYREF
  __int64 v65; // [rsp+98h] [rbp-68h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  __int64 v68; // [rsp+B0h] [rbp-50h]
  _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  char v70[2]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v68 = a3;
  v67 = a2;
  v66 = a5;
  v65 = a9;
  v14 = a10;
  hObject = a10;
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v14 = (unsigned __int16 *)hObject;
  }
  if ( !a4 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v14 = (unsigned __int16 *)hObject;
  }
  if ( !a3 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v14 = (unsigned __int16 *)hObject;
  }
  if ( !a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v14 = (unsigned __int16 *)hObject;
  }
  if ( a5 )
  {
    if ( a6 )
      goto LABEL_12;
    goto LABEL_11;
  }
  if ( a6 )
  {
LABEL_11:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v14 = (unsigned __int16 *)hObject;
  }
LABEL_12:
  if ( !a1 )
  {
    v18 = -2147024809;
    v19 = -2147024809;
LABEL_78:
    v17 = 0;
    goto LABEL_19;
  }
  v15 = 65;
  v16 = a1;
  while ( *v16 )
  {
    ++v16;
    if ( !--v15 )
    {
      v17 = 0;
      v18 = -2147024809;
      v19 = -2147024809;
      goto LABEL_18;
    }
  }
  v17 = 65 - v15;
  v19 = 0;
  v18 = -2147024809;
LABEL_18:
  if ( v19 < 0 )
    goto LABEL_78;
LABEL_19:
  AppContainerRegistrationHelper::SetAPIContextIfFailed(v19, 0xA40u, a1, 0x104u, v14);
  if ( v19 == -2147024809 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA42,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Name %ls",
      (const char *)a1);
    return 2147942487LL;
  }
  v20 = 2147942487LL;
  if ( v17 )
    v20 = 0;
  v21 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0xA45,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v20,
          (__int64)"Name %ls",
          (const char *)a1);
  if ( v21 < 0 )
  {
    v54 = 2631;
    v22 = StringCchPrintfW(
            (unsigned __int16 *)hObject,
            0x104u,
            L"%ls Line:%d ",
            L"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp");
    v23 = retaddr;
    if ( v22 < 0 )
    {
      v46 = 3304;
    }
    else
    {
      if ( !a1 )
        goto LABEL_26;
      v22 = StringCchCatW((unsigned __int16 *)hObject, 0x104u, a1);
      v23 = retaddr;
      if ( v22 >= 0 )
        goto LABEL_26;
      v46 = 3310;
    }
    wil::details::in1diag3::_Log_Hr(
      v23,
      (void *)v46,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v22,
      2631);
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA47,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v21,
      v54);
    return (unsigned int)v21;
  }
  if ( !a4 )
  {
    v26 = -2147024809;
LABEL_84:
    v25 = 0;
    goto LABEL_29;
  }
  v27 = 2048;
  v28 = a4;
  do
  {
    if ( !*v28 )
    {
      v25 = 2048 - v27;
      v26 = 0;
      goto LABEL_28;
    }
    ++v28;
    --v27;
  }
  while ( v27 );
  v25 = 0;
  v26 = -2147024809;
LABEL_28:
  if ( v26 < 0 )
    goto LABEL_84;
LABEL_29:
  AppContainerRegistrationHelper::SetAPIContextIfFailed(v26, 0xA4Cu, a4, 0x104u, (unsigned __int16 *)hObject);
  if ( v26 == -2147024809 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA4D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Desc %ls",
      (const char *)a4);
    return 2147942487LL;
  }
  if ( v25 )
    v18 = 0;
  v29 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0xA50,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v18,
          (__int64)"Desc %ls",
          (const char *)a4);
  v30 = (unsigned __int16 *)hObject;
  v31 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v29, 0xA52u, a4, 0x104u, (unsigned __int16 *)hObject);
  v32 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA52,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v31,
      v55);
    return v32;
  }
  hObject = 0;
  v33 = AppContainerRegistrationHelper::OpenCurrentUserToken((char *)0xE, &hObject);
  AppContainerRegistrationHelper::SetAPIContextIfFailed(v33, 0xA59u, a1, 0x104u, v30);
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA5B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v33,
      (int)"Name %ls",
      (const char *)a1);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return (unsigned int)v33;
  }
  packageFamilyNameLength = 0;
  v47 = hObject;
  IsAppContainerToken = AppContainerRegistrationHelper::IsAppContainerToken(hObject, (int *)&packageFamilyNameLength);
  AppContainerRegistrationHelper::SetAPIContextIfFailed(IsAppContainerToken, 0xA5Fu, a1, 0x104u, v30);
  if ( IsAppContainerToken < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA61,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)IsAppContainerToken,
      (int)"Name %ls",
      (const char *)a1);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return (unsigned int)IsAppContainerToken;
  }
  v63 = 2162688;
  AppModelPolicy_GetPolicy(v47, v49, &v63);
  Sid = 0;
  if ( packageFamilyNameLength )
  {
    Sid = 0;
    AppContainerSidFromToken = AppContainerRegistrationHelper::GetAppContainerSidFromToken(v47, &Sid);
    AppContainerRegistrationHelper::SetAPIContextIfFailed(AppContainerSidFromToken, 0xA72u, a1, 0x104u, v30);
    if ( AppContainerSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA74,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)AppContainerSidFromToken,
        (int)"Name %ls",
        (const char *)a1);
      v34 = Sid;
      if ( !Sid )
        goto LABEL_45;
      goto LABEL_44;
    }
  }
  else if ( v63 == 2162689 )
  {
    packageFamilyNameLength = 65;
    PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v47, &packageFamilyNameLength, packageFamilyName);
    AppContainerRegistrationHelper::SetAPIContextIfFailed(PackageFamilyNameFromToken, 0xA7Bu, a1, 0x104u, v30);
    if ( PackageFamilyNameFromToken )
    {
      AppContainerSidFromToken = wil::details::in1diag3::Return_Win32Msg(
                                   retaddr,
                                   (void *)0xA7D,
                                   (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                                   (const char *)PackageFamilyNameFromToken,
                                   (unsigned int)"Name %ls",
                                   (const char *)a1);
      v34 = Sid;
      if ( !Sid )
        goto LABEL_45;
      goto LABEL_44;
    }
    v36 = Sid;
    if ( Sid )
    {
      LastError = GetLastError();
      RtlFreeSid(v36);
      SetLastError(LastError);
    }
    Sid = 0;
    v38 = PackageSidFromFamilyName(packageFamilyName, &Sid);
    AppContainerRegistrationHelper::SetAPIContextIfFailed(v38, 0xA81u, packageFamilyName, 0x104u, v30);
    if ( v38 )
    {
      AppContainerSidFromToken = wil::details::in1diag3::Return_Win32Msg(
                                   retaddr,
                                   (void *)0xA82,
                                   (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                                   (const char *)v38,
                                   (unsigned int)"Name %ls family %ls",
                                   (const char *)a1,
                                   packageFamilyName);
      v34 = Sid;
      if ( !Sid )
        goto LABEL_45;
LABEL_44:
      RtlFreeSid(v34);
LABEL_45:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      return (unsigned int)AppContainerSidFromToken;
    }
  }
  memset_0(v70, 0, 0x82u);
  *(_QWORD *)&UniDest.Length = 8519680;
  UniDest.Buffer = (PWSTR)v70;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a1);
  v39 = RtlDowncaseUnicodeString(&UniDest, &DestinationString, 0);
  AppContainerRegistrationHelper::SetAPIContextIfFailed(v39, 0xA8Eu, a1, 0x104u, v30);
  if ( v39 < 0 )
  {
    AppContainerSidFromToken = wil::details::in1diag3::Return_NtStatusMsg(
                                 retaddr,
                                 (void *)0xA8F,
                                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                                 (const char *)(unsigned int)v39,
                                 (int)"Name %ls",
                                 (const char *)a1);
    v34 = Sid;
    if ( !Sid )
      goto LABEL_45;
    goto LABEL_44;
  }
  v62 = 0;
  if ( Sid )
  {
    v51 = AppContainerRegistrationHelper::DeriveChildAppContainerSid(Sid, (char *)UniDest.Buffer, &v62);
    v52 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0xAA5,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)v51,
            (__int64)"Name %ls",
            v70);
    v53 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v52, 0xAA7u, (const unsigned __int16 *)v70, 0x104u, v30);
    AppContainerSidFromToken = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA7,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v53,
        v57);
      v45 = v62;
      if ( v62 )
        goto LABEL_46;
      goto LABEL_47;
    }
  }
  else
  {
    v40 = AppContainerDeriveSidFromMoniker(UniDest.Buffer, &v62);
    v41 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0xA9B,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)v40,
            (__int64)"Name %ls",
            v70);
    v42 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v41, 0xA9Du, (const unsigned __int16 *)v70, 0x104u, v30);
    AppContainerSidFromToken = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v42,
        v56);
      v45 = v62;
      if ( v62 )
        goto LABEL_46;
      goto LABEL_47;
    }
  }
  HIDWORD(v58) = HIDWORD(v65);
  v43 = v67;
  v44 = v68;
  AppContainerSidFromToken = AppContainerRegistrationHelper::UpdateProfile(v65, a1, v68, v67, a4, v66, a6, v62, a7);
  if ( AppContainerSidFromToken < 0 )
  {
    LODWORD(v58) = a7;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xAB8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)AppContainerSidFromToken,
      (int)"Name %ls, %ls, %ls, %ls, %d, %d",
      (const char *)a1,
      v44,
      v43,
      a4,
      a6,
      v58);
    v45 = v62;
    if ( v62 )
LABEL_46:
      RtlFreeSid(v45);
LABEL_47:
    v34 = Sid;
    if ( !Sid )
      goto LABEL_45;
    goto LABEL_44;
  }
  if ( v62 )
    RtlFreeSid(v62);
  if ( Sid )
    RtlFreeSid(Sid);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  return 0;
}

```

## disassembly

```asm
0x1800020d0  push    rbp
0x1800020d2  push    rbx
0x1800020d3  push    rsi
0x1800020d4  push    rdi
0x1800020d5  push    r12
0x1800020d7  push    r13
0x1800020d9  push    r14
0x1800020db  push    r15
0x1800020dd  lea     rbp, [rsp-108h]
0x1800020e5  sub     rsp, 208h
0x1800020ec  mov     rax, cs:__security_cookie
0x1800020f3  xor     rax, rsp
0x1800020f6  mov     [rbp+140h+var_50], rax
0x1800020fd  mov     r13, r9
0x180002100  mov     rdi, r8
0x180002103  mov     [rbp+140h+var_190], r8
0x180002107  mov     rbx, rdx
0x18000210a  mov     [rbp+140h+var_198], rdx
0x18000210e  mov     r12, rcx
0x180002111  mov     rsi, [rbp+140h+arg_20]
0x180002118  mov     [rbp+140h+var_1A0], rsi
0x18000211c  mov     rax, [rbp+140h+arg_40]
0x180002123  mov     [rbp+140h+var_1A8], rax
0x180002127  mov     rdx, [rbp+140h+arg_48]
0x18000212e  mov     [rsp+240h+hObject], rdx
0x180002133  test    rcx, rcx
0x180002136  jz      loc_18000280B
0x18000213c  test    r13, r13
0x18000213f  jz      loc_18000281A
0x180002145  test    rdi, rdi
0x180002148  jz      loc_180002829
0x18000214e  test    rbx, rbx
0x180002151  jz      loc_180002838
0x180002157  test    rsi, rsi
0x18000215a  jz      loc_180002847
0x180002160  cmp     [rbp+140h+arg_28], 0
0x180002167  jnz     short loc_180002173
0x180002169  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000216e  mov     rdx, [rsp+240h+hObject]
0x180002173  test    r12, r12
0x180002176  jz      loc_18000285E
0x18000217c  mov     ecx, 41h ; 'A'
0x180002181  mov     rax, r12
0x180002184  cmp     word ptr [rax], 0
0x180002188  jz      short loc_1800021A3
0x18000218a  add     rax, 2
0x18000218e  sub     rcx, 1
0x180002192  jnz     short loc_180002184
0x180002194  xor     r14d, r14d
0x180002197  mov     edi, r14d
0x18000219a  mov     esi, 80070057h
0x18000219f  mov     ebx, esi
0x1800021a1  jmp     short loc_1800021B6
0x1800021a3  mov     edi, 41h ; 'A'
0x1800021a8  sub     rdi, rcx
0x1800021ab  xor     r14d, r14d
0x1800021ae  mov     ebx, r14d
0x1800021b1  mov     esi, 80070057h
0x1800021b6  test    ebx, ebx
0x1800021b8  js      loc_180002868
0x1800021be  mov     [rsp+240h+var_220], rdx; unsigned __int16 *
0x1800021c3  mov     r9d, 104h; unsigned __int64
0x1800021c9  mov     r8, r12; unsigned __int16 *
0x1800021cc  mov     edx, 0A40h; unsigned int
0x1800021d1  mov     ecx, ebx; int
0x1800021d3  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x1800021d8  mov     rcx, [rbp+148h]; this
0x1800021df  mov     [rsp+240h+var_218], r12; char *
0x1800021e4  lea     r15, aNameLs; "Name %ls"
0x1800021eb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800021f2  mov     [rsp+240h+var_220], r15; int
0x1800021f7  cmp     ebx, esi
0x1800021f9  jz      loc_180002870
0x1800021ff  test    ebx, ebx
0x180002201  js      loc_180002884
0x180002207  mov     r9d, esi
0x18000220a  test    rdi, rdi
0x18000220d  cmovnz  r9d, r14d; char *
0x180002211  mov     edx, 0A45h; void *
0x180002216  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000221b  mov     ebx, eax
0x18000221d  test    eax, eax
0x18000221f  jns     loc_18000232A
0x180002225  mov     dword ptr [rsp+240h+var_220], 0A47h; int
0x18000222d  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002234  lea     r8, aLsLineD; "%ls Line:%d "
0x18000223b  mov     edx, 104h; unsigned __int64
0x180002240  mov     rdi, [rsp+240h+hObject]
0x180002245  mov     rcx, rdi; unsigned __int16 *
0x180002248  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000224d  mov     rcx, [rbp+148h]
0x180002254  test    eax, eax
0x180002256  js      loc_180002898
0x18000225c  test    r12, r12
0x18000225f  jz      short loc_180002280
0x180002261  mov     r8, r12; unsigned __int16 *
0x180002264  mov     edx, 104h; unsigned __int64
0x180002269  mov     rcx, rdi; unsigned __int16 *
0x18000226c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002271  mov     rcx, [rbp+148h]; this
0x180002278  test    eax, eax
0x18000227a  js      loc_18000289F
0x180002280  mov     rcx, [rbp+148h]; this
0x180002287  mov     r9d, ebx; char *
0x18000228a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002291  mov     edx, 0A47h; void *
0x180002296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000229b  mov     eax, ebx
0x18000229d  jmp     short loc_180002306
0x18000229f  sub     rdi, rcx
0x1800022a2  mov     ebx, r14d
0x1800022a5  test    ebx, ebx
0x1800022a7  js      loc_1800028BA
0x1800022ad  mov     rax, [rsp+240h+hObject]
0x1800022b2  mov     [rsp+240h+var_220], rax; unsigned __int16 *
0x1800022b7  mov     r9d, 104h; unsigned __int64
0x1800022bd  mov     r8, r13; unsigned __int16 *
0x1800022c0  mov     edx, 0A4Ch; unsigned int
0x1800022c5  mov     ecx, ebx; int
0x1800022c7  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x1800022cc  mov     rcx, [rbp+148h]; this
0x1800022d3  mov     [rsp+240h+var_218], r13; char *
0x1800022d8  lea     rax, aDescLs; "Desc %ls"
0x1800022df  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800022e6  mov     [rsp+240h+var_220], rax; int
0x1800022eb  cmp     ebx, esi
0x1800022ed  jz      loc_1800028C2
0x1800022f3  test    ebx, ebx
0x1800022f5  jns     short loc_18000235E
0x1800022f7  mov     r9d, ebx; char *
0x1800022fa  mov     edx, 0A4Eh; void *
0x1800022ff  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180002304  mov     eax, ebx
0x180002306  mov     rcx, [rbp+140h+var_50]
0x18000230d  xor     rcx, rsp; StackCookie
0x180002310  call    __security_check_cookie
0x180002315  add     rsp, 208h
0x18000231c  pop     r15
0x18000231e  pop     r14
0x180002320  pop     r13
0x180002322  pop     r12
0x180002324  pop     rdi
0x180002325  pop     rsi
0x180002326  pop     rbx
0x180002327  pop     rbp
0x180002328  retn
0x18000232a  test    r13, r13
0x18000232d  jz      loc_1800028B8
0x180002333  mov     edi, 800h
0x180002338  mov     ecx, edi
0x18000233a  mov     rax, r13
0x18000233d  nop     dword ptr [rax]
0x180002340  cmp     word ptr [rax], 0
0x180002344  jz      loc_18000229F
0x18000234a  add     rax, 2
0x18000234e  sub     rcx, 1
0x180002352  jnz     short loc_180002340
0x180002354  mov     rdi, r14
0x180002357  mov     ebx, esi
0x180002359  jmp     loc_1800022A5
0x18000235e  test    rdi, rdi
0x180002361  cmovnz  esi, r14d
0x180002365  mov     r9d, esi; char *
0x180002368  mov     edx, 0A50h; void *
0x18000236d  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180002372  mov     rsi, [rsp+240h+hObject]
0x180002377  mov     [rsp+240h+var_220], rsi; int
0x18000237c  mov     r9d, 104h; unsigned __int64
0x180002382  mov     r8, r13; unsigned __int16 *
0x180002385  mov     edx, 0A52h; unsigned int
0x18000238a  mov     ecx, eax; int
0x18000238c  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002391  mov     ebx, eax
0x180002393  test    eax, eax
0x180002395  jns     short loc_1800023B9
0x180002397  mov     rcx, [rbp+148h]; this
0x18000239e  mov     r9d, eax; char *
0x1800023a1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800023a8  mov     edx, 0A52h; void *
0x1800023ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800023b2  mov     eax, ebx
0x1800023b4  jmp     loc_180002306
0x1800023b9  mov     [rsp+240h+hObject], r14
0x1800023be  lea     rdx, [rsp+240h+hObject]; void **
0x1800023c3  mov     ecx, 0Eh; char *
0x1800023c8  call    ?OpenCurrentUserToken@AppContainerRegistrationHelper@@SAJKPEAPEAX@Z; AppContainerRegistrationHelper::OpenCurrentUserToken(ulong,void * *)
0x1800023cd  mov     ebx, eax
0x1800023cf  mov     [rsp+240h+var_220], rsi; unsigned __int16 *
0x1800023d4  mov     r9d, 104h; unsigned __int64
0x1800023da  mov     r8, r12; unsigned __int16 *
0x1800023dd  mov     edx, 0A59h; unsigned int
0x1800023e2  mov     ecx, eax; int
0x1800023e4  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x1800023e9  test    ebx, ebx
0x1800023eb  jns     loc_1800028E7
0x1800023f1  mov     rcx, [rbp+148h]; this
0x1800023f8  mov     [rsp+240h+var_218], r12; char *
0x1800023fd  mov     [rsp+240h+var_220], r15; int
0x180002402  mov     r9d, ebx; char *
0x180002405  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000240c  mov     edx, 0A5Bh; void *
0x180002411  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180002416  nop
0x180002417  mov     rcx, [rsp+240h+hObject]; hObject
0x18000241c  lea     rax, [rcx-1]
0x180002420  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002424  jbe     loc_1800028D6
0x18000242a  mov     eax, ebx
0x18000242c  jmp     loc_180002306
0x180002431  call    cs:__imp_RtlFreeSid
0x180002438  nop     dword ptr [rax+rax+00h]
0x18000243d  nop
0x18000243e  lea     rcx, [rsp+240h+hObject]
0x180002443  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180002448  mov     eax, ebx
0x18000244a  jmp     loc_180002306
0x18000244f  call    cs:__imp_RtlFreeSid
0x180002456  nop     dword ptr [rax+rax+00h]
0x18000245b  nop
0x18000245c  mov     rcx, [rsp+240h+Sid]; Sid
0x180002461  test    rcx, rcx
0x180002464  jz      short loc_18000243E
0x180002466  jmp     short loc_180002431
0x180002468  mov     rcx, [rbp+148h]; this
0x18000246f  mov     [rsp+240h+var_218], r12; char *
0x180002474  mov     [rsp+240h+var_220], r15; int
0x180002479  mov     r9d, ebx; char *
0x18000247c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180002483  mov     edx, 0A74h; void *
0x180002488  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000248d  nop
0x18000248e  mov     rcx, [rsp+240h+Sid]
0x180002493  test    rcx, rcx
0x180002496  jz      short loc_18000243E
0x180002498  jmp     short loc_180002431
0x18000249a  mov     rcx, [rbp+148h]; this
0x1800024a1  mov     [rsp+240h+var_218], r12; char *
0x1800024a6  mov     [rsp+240h+var_220], r15; unsigned int
0x1800024ab  mov     r9d, ebx; char *
0x1800024ae  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800024b5  mov     edx, 0A7Dh; void *
0x1800024ba  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800024bf  mov     ebx, eax
0x1800024c1  mov     rcx, [rsp+240h+Sid]
0x1800024c6  test    rcx, rcx
0x1800024c9  jz      loc_18000243E
0x1800024cf  jmp     loc_180002431
0x1800024d4  mov     rdi, [rsp+240h+Sid]
0x1800024d9  test    rdi, rdi
0x1800024dc  jz      short loc_180002509
0x1800024de  call    cs:__imp_GetLastError
0x1800024e5  nop     dword ptr [rax+rax+00h]
0x1800024ea  mov     ebx, eax
0x1800024ec  mov     rcx, rdi; Sid
0x1800024ef  call    cs:__imp_RtlFreeSid
0x1800024f6  nop     dword ptr [rax+rax+00h]
0x1800024fb  mov     ecx, ebx; dwErrCode
0x1800024fd  call    cs:__imp_SetLastError
0x180002504  nop     dword ptr [rax+rax+00h]
0x180002509  mov     [rsp+240h+Sid], r14
0x18000250e  lea     rdx, [rsp+240h+Sid]
0x180002513  lea     rcx, [rbp+140h+packageFamilyName]
0x180002517  call    cs:__imp_PackageSidFromFamilyName
0x18000251e  nop     dword ptr [rax+rax+00h]
0x180002523  mov     ebx, eax
0x180002525  mov     [rsp+240h+var_220], rsi; unsigned __int16 *
0x18000252a  mov     r9d, 104h; unsigned __int64
0x180002530  lea     r8, [rbp+140h+packageFamilyName]; unsigned __int16 *
0x180002534  mov     edx, 0A81h; unsigned int
0x180002539  mov     ecx, eax; int
0x18000253b  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180002540  test    ebx, ebx
0x180002542  jnz     loc_1800025FA
0x180002548  mov     ebx, 82h
0x18000254d  mov     r8d, ebx; Size
0x180002550  xor     edx, edx; Val
0x180002552  lea     rcx, [rbp+140h+var_170]; void *
0x180002556  call    memset_0
0x18000255b  xorps   xmm0, xmm0
0x18000255e  movups  xmmword ptr [rbp+140h+UniDest.Length], xmm0
0x180002562  lea     rax, [rbp+140h+var_170]
0x180002566  mov     [rbp+140h+UniDest.Buffer], rax
0x18000256a  mov     [rbp+140h+UniDest.MaximumLength], bx
0x18000256e  movups  xmmword ptr [rbp+140h+DestinationString.Length], xmm0
0x180002572  mov     rdx, r12; SourceString
0x180002575  lea     rcx, [rbp+140h+DestinationString]; DestinationString
0x180002579  call    cs:__imp_RtlInitUnicodeString
0x180002580  nop     dword ptr [rax+rax+00h]
0x180002585  xor     r8d, r8d; AllocateDestinationString
0x180002588  lea     rdx, [rbp+140h+DestinationString]; UniSource
0x18000258c  lea     rcx, [rbp+140h+UniDest]; UniDest
0x180002590  call    cs:__imp_RtlDowncaseUnicodeString
0x180002597  nop     dword ptr [rax+rax+00h]
0x18000259c  mov     ebx, eax
0x18000259e  mov     [rsp+240h+var_220], rsi; unsigned __int16 *
0x1800025a3  mov     r9d, 104h; unsigned __int64
0x1800025a9  mov     r8, r12; unsigned __int16 *
0x1800025ac  mov     edx, 0A8Eh; unsigned int
0x1800025b1  mov     ecx, eax; int
0x1800025b3  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
  ... truncated ...
```
