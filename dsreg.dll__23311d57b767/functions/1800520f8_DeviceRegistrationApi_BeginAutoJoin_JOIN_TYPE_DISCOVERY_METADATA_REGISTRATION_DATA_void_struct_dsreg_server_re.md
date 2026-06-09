# DeviceRegistrationApi::BeginAutoJoin(_JOIN_TYPE,_DISCOVERY_METADATA *,_REGISTRATION_DATA *,void (*)(struct_dsreg_server_response,unsigned __int64,long),unsigned __int64,ushort const *,ushort const *)

- ea: `0x1800520f8`
- end: `0x180052691`
- name: `?BeginAutoJoin@DeviceRegistrationApi@@SAJW4_JOIN_TYPE@@PEAU_DISCOVERY_METADATA@@PEAU_REGISTRATION_DATA@@P6AXUstruct_dsreg_server_response@@_KJ@Z4PEBG6@Z`
- size: `1433`
- prototype: `__int64 __fastcall(__int64, _OWORD *, struct _REGISTRATION_DATA *, __int64, __int64, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800360e8`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x18001035c`
- `0x180010640`
- `0x1800307c4`
- `0x180031ae0`
- `0x180043ef8`
- `0x180044300`
- `0x180044d30`
- `0x1800520f8`
- `0x180052698`
- `0x180053db4`
- `0x18005b078`
- `0x18006e600`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800524a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800524a6`

## string_xrefs

- `0x180052381`: `Logger::WriteVerifyAutoSigningCertFailureEvent`
- `0x18005237a`: `EventWriteVerifyAutoSigningCertFailureEvent`
- `0x180052264`: `pRegistrationData->pszComputerObjectGuid`
- `0x180052283`: `pRegistrationData->pszComputerObjectGuid`
- `0x1800522c6`: `token`
- `0x1800522e5`: `token`
- `0x1800522fa`: `pRegistrationData->pszComputerObjectSid`
- `0x180052319`: `pRegistrationData->pszComputerObjectSid`
- `0x180052340`: `%s: Unable to verify or update the signing cert for DEVICE_AUTO join.`

## pseudocode

```c
__int64 __fastcall DeviceRegistrationApi::BeginAutoJoin(
        __int64 a1,
        _OWORD *a2,
        struct _REGISTRATION_DATA *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned __int16 *a7)
{
  _OWORD *v8; // rsi
  unsigned int v9; // r14d
  unsigned __int16 *v10; // r15
  unsigned __int16 *v11; // r12
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  unsigned int v15; // eax
  int FakeUserEmail; // eax
  __int64 v17; // rcx
  char *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  int v26; // eax
  __int64 v27; // rcx
  char *v28; // rax
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  int v36; // eax
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 JoinTypeName; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v43; // [rsp+80h] [rbp-80h]
  __int64 v44; // [rsp+88h] [rbp-78h]
  __int64 v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  __int64 v47; // [rsp+A0h] [rbp-60h]
  int v48; // [rsp+A8h] [rbp-58h]
  char v49; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  char v52; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v53; // [rsp+1E8h] [rbp+E8h]
  struct _SYSTEMTIME SystemTime; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v55[264]; // [rsp+200h] [rbp+100h] BYREF

  v8 = a2;
  *(_QWORD *)&SystemTime.wYear = a6;
  v9 = a1;
  JoinTypeName = GetJoinTypeName(a1, a2, a3, a4);
  Logger::TraceVerbose(
    (wchar_t *)L"%s started. joinType: %d (%s)",
    L"DeviceRegistrationApi::BeginAutoJoin",
    v9,
    JoinTypeName);
  v38 = 0;
  v39 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(&v41, 0, 0x180u);
  if ( !v8 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationApi::BeginAutoJoin",
      L"pDiscoveryMetadata");
    v13 = L"pDiscoveryMetadata";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceRegistrationApi::BeginAutoJoin", v13);
    goto LABEL_41;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceRegistrationApi::BeginAutoJoin", L"pRegistrationData");
    v13 = L"pRegistrationData";
    goto LABEL_3;
  }
  if ( !*((_QWORD *)a3 + 23) )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationApi::BeginAutoJoin",
      L"pRegistrationData->pszAadTenantId");
    v13 = L"pRegistrationData->pszAadTenantId";
    goto LABEL_3;
  }
  if ( !*((_QWORD *)a3 + 22) )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationApi::BeginAutoJoin",
      L"pRegistrationData->pszAadTenantName");
    v13 = L"pRegistrationData->pszAadTenantName";
    goto LABEL_3;
  }
  if ( !*((_QWORD *)a3 + 20) )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationApi::BeginAutoJoin",
      L"pRegistrationData->pszComputerObjectGuid");
    v13 = L"pRegistrationData->pszComputerObjectGuid";
    goto LABEL_3;
  }
  if ( v9 == 7 )
  {
    if ( !*((_QWORD *)a3 + 21) )
    {
      v12 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null.",
        L"DeviceRegistrationApi::BeginAutoJoin",
        L"pRegistrationData->pszComputerObjectSid");
      v13 = L"pRegistrationData->pszComputerObjectSid";
      goto LABEL_3;
    }
  }
  else
  {
    if ( v9 != 10 && v9 != 15 )
    {
      Logger::TraceError(L"%s: Invalid join type: %d", L"DeviceRegistrationApi::BeginAutoJoin", v9);
      v12 = -2147024809;
      goto LABEL_41;
    }
    if ( !a7 )
    {
      v12 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceRegistrationApi::BeginAutoJoin", L"token");
      v13 = L"token";
      goto LABEL_3;
    }
  }
  v14 = RegistrationController::VerifyAutoSigningCert(a3);
  v12 = v14;
  if ( v14 < 0 )
  {
    if ( v9 == 7 )
    {
      Logger::TraceError(
        L"%s: Unable to verify or update the signing cert for DEVICE_AUTO join.",
        L"DeviceRegistrationApi::BeginAutoJoin");
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v15 = McTemplateU0q_EventWriteTransfer(
                &UserDeviceRegistrationEventProvider_Context,
                VerifyAutoSigningCertFailureEvent,
                v12);
        if ( v15 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteVerifyAutoSigningCertFailureEvent",
            L"EventWriteVerifyAutoSigningCertFailureEvent",
            v15);
      }
      goto LABEL_41;
    }
    Logger::TraceWarning(
      (wchar_t *)L"%s: RegistrationController::VerifyAutoSigningCert failed with error code: 0x%08x. The auto signing cert"
                  " is not required for join type %s. Ignore the error...",
      L"DeviceRegistrationApi::BeginAutoJoin",
      (unsigned int)v14,
      JoinTypeName);
  }
  FakeUserEmail = MakeFakeUserEmail(*((const unsigned __int16 **)a3 + 22), &v38);
  v12 = FakeUserEmail;
  if ( FakeUserEmail >= 0 )
  {
    v10 = v38;
    if ( v9 == 7 )
    {
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      StringCchPrintfW(
        v55,
        0x104u,
        L".%04d-%02d-%02d %02d:%02d:%02dZ",
        SystemTime.wYear,
        SystemTime.wMonth,
        SystemTime.wDay,
        SystemTime.wHour,
        SystemTime.wMinute,
        SystemTime.wSecond);
      v26 = StringCat(*((const unsigned __int16 **)a3 + 21), v55, &v39);
      v12 = v26;
      if ( v26 < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"DeviceRegistrationApi::BeginAutoJoin",
          L"StringCat",
          (unsigned int)v26);
        v11 = v39;
        goto LABEL_41;
      }
      v27 = 2;
      v11 = v39;
      v44 = *((_QWORD *)a3 + 23);
      v45 = *((_QWORD *)a3 + 22);
      v42 = *((_QWORD *)a3 + 20);
      v46 = *((_QWORD *)a3 + 24);
      v28 = &v49;
      v41 = v10;
      v43 = v39;
      do
      {
        v29 = v8[1];
        *(_OWORD *)v28 = *v8;
        v30 = v8[2];
        *((_OWORD *)v28 + 1) = v29;
        v31 = v8[3];
        *((_OWORD *)v28 + 2) = v30;
        v32 = v8[4];
        *((_OWORD *)v28 + 3) = v31;
        v33 = v8[5];
        *((_OWORD *)v28 + 4) = v32;
        v34 = v8[6];
        *((_OWORD *)v28 + 5) = v33;
        v35 = v8[7];
        v8 += 8;
        *((_OWORD *)v28 + 6) = v34;
        *((_OWORD *)v28 + 7) = v35;
        v28 += 128;
        --v27;
      }
      while ( v27 );
      if ( *(_QWORD *)a3 && *((_QWORD *)a3 + 1) )
      {
        v47 = *(_QWORD *)a3;
        v48 = *((_DWORD *)a3 + 2);
      }
    }
    else
    {
      v17 = 2;
      LODWORD(v42) = 1;
      v43 = v38;
      v18 = &v52;
      do
      {
        v19 = v8[1];
        *(_OWORD *)v18 = *v8;
        v20 = v8[2];
        *((_OWORD *)v18 + 1) = v19;
        v21 = v8[3];
        *((_OWORD *)v18 + 2) = v20;
        v22 = v8[4];
        *((_OWORD *)v18 + 3) = v21;
        v23 = v8[5];
        *((_OWORD *)v18 + 4) = v22;
        v24 = v8[6];
        *((_OWORD *)v18 + 5) = v23;
        v25 = v8[7];
        v8 += 8;
        *((_OWORD *)v18 + 6) = v24;
        *((_OWORD *)v18 + 7) = v25;
        v18 += 128;
        --v17;
      }
      while ( v17 );
      v50 = *((_QWORD *)a3 + 20);
      v51 = *((_QWORD *)a3 + 23);
      v53 = *(_QWORD *)&SystemTime.wYear;
      v41 = a7;
    }
    v36 = DeviceRegistrationApi::BeginJoin(
            v9,
            &v41,
            (void (__fastcall *)(__int128 *, __int64, _QWORD))&DsrCmdDeviceEnroller::AutoJoinCallback,
            a5,
            &_JOIN_OPERATION_CONTEXT::DEFAULT);
    v12 = v36;
    if ( v36 < 0 )
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DeviceRegistrationApi::BeginAutoJoin",
        L"DeviceRegistrationApi::BeginJoin",
        (unsigned int)v36);
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceRegistrationApi::BeginAutoJoin",
      L"MakeFakeUserEmail",
      (unsigned int)FakeUserEmail);
    v10 = v38;
  }
LABEL_41:
  operator delete(v10);
  SafeFree(v11);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DeviceRegistrationApi::BeginAutoJoin", v12);
  return v12;
}

```

## disassembly

```asm
0x1800520f8  mov     [rsp-8+arg_18], rbx
0x1800520fd  push    rbp
0x1800520fe  push    rsi
0x1800520ff  push    rdi
0x180052100  push    r12
0x180052102  push    r13
0x180052104  push    r14
0x180052106  push    r15
0x180052108  lea     rbp, [rsp-320h]
0x180052110  sub     rsp, 420h
0x180052117  mov     rax, cs:__security_cookie
0x18005211e  xor     rax, rsp
0x180052121  mov     [rbp+350h+var_40], rax
0x180052128  mov     rax, [rbp+350h+arg_28]
0x18005212f  mov     rdi, r8
0x180052132  mov     r13, [rbp+350h+arg_30]
0x180052139  mov     rsi, rdx
0x18005213c  mov     qword ptr [rbp+350h+SystemTime.wYear], rax
0x180052143  mov     r14d, ecx
0x180052146  call    ?GetJoinTypeName@@YAPEBGW4_JOIN_TYPE@@@Z; GetJoinTypeName(_JOIN_TYPE)
0x18005214b  mov     r9, rax
0x18005214e  mov     [rsp+450h+var_3F0], rax
0x180052153  lea     rcx, aSStartedJointy_0; "%s started. joinType: %d (%s)"
0x18005215a  mov     r8d, r14d
0x18005215d  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x180052164  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180052169  xor     ebx, ebx
0x18005216b  lea     rcx, [rsp+450h+var_3E0]; void *
0x180052170  xor     edx, edx; Val
0x180052172  mov     [rsp+450h+var_400], rbx
0x180052177  mov     r8d, 180h; Size
0x18005217d  mov     [rsp+450h+var_3F8], rbx
0x180052182  mov     r15d, ebx
0x180052185  mov     r12d, ebx
0x180052188  call    memset_0
0x18005218d  test    rsi, rsi
0x180052190  jnz     short loc_1800521C9
0x180052192  lea     r8, aPdiscoverymeta; "pDiscoveryMetadata"
0x180052199  mov     ebx, 80070057h
0x18005219e  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x1800521a5  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800521ac  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800521b1  lea     rdx, aPdiscoverymeta; "pDiscoveryMetadata"
0x1800521b8  lea     rcx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x1800521bf  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800521c4  jmp     loc_18005263F
0x1800521c9  test    rdi, rdi
0x1800521cc  jnz     short loc_1800521F6
0x1800521ce  lea     r8, aPregistrationd_2; "pRegistrationData"
0x1800521d5  mov     ebx, 80070057h
0x1800521da  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x1800521e1  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800521e8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800521ed  lea     rdx, aPregistrationd_2; "pRegistrationData"
0x1800521f4  jmp     short loc_1800521B8
0x1800521f6  cmp     [rdi+0B8h], rbx
0x1800521fd  jnz     short loc_180052227
0x1800521ff  lea     r8, aPregistrationd_1; "pRegistrationData->pszAadTenantId"
0x180052206  mov     ebx, 80070057h
0x18005220b  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x180052212  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180052219  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005221e  lea     rdx, aPregistrationd_1; "pRegistrationData->pszAadTenantId"
0x180052225  jmp     short loc_1800521B8
0x180052227  cmp     [rdi+0B0h], rbx
0x18005222e  jnz     short loc_18005225B
0x180052230  lea     r8, aPregistrationd_0; "pRegistrationData->pszAadTenantName"
0x180052237  mov     ebx, 80070057h
0x18005223c  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x180052243  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005224a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005224f  lea     rdx, aPregistrationd_0; "pRegistrationData->pszAadTenantName"
0x180052256  jmp     loc_1800521B8
0x18005225b  cmp     [rdi+0A0h], rbx
0x180052262  jnz     short loc_18005228F
0x180052264  lea     r8, aPregistrationd_3; "pRegistrationData->pszComputerObjectGui"...
0x18005226b  mov     ebx, 80070057h
0x180052270  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x180052277  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005227e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180052283  lea     rdx, aPregistrationd_3; "pRegistrationData->pszComputerObjectGui"...
0x18005228a  jmp     loc_1800521B8
0x18005228f  cmp     r14d, 7
0x180052293  jz      short loc_1800522F1
0x180052295  cmp     r14d, 0Ah
0x180052299  jz      short loc_1800522C1
0x18005229b  cmp     r14d, 0Fh
0x18005229f  jz      short loc_1800522C1
0x1800522a1  mov     r8d, r14d
0x1800522a4  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x1800522ab  lea     rcx, aSInvalidJoinTy; "%s: Invalid join type: %d"
0x1800522b2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800522b7  mov     ebx, 80070057h
0x1800522bc  jmp     loc_18005263F
0x1800522c1  test    r13, r13
0x1800522c4  jnz     short loc_180052325
0x1800522c6  lea     r8, aToken_0; "token"
0x1800522cd  mov     ebx, 80070057h
0x1800522d2  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x1800522d9  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800522e0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800522e5  lea     rdx, aToken_0; "token"
0x1800522ec  jmp     loc_1800521B8
0x1800522f1  cmp     [rdi+0A8h], rbx
0x1800522f8  jnz     short loc_180052325
0x1800522fa  lea     r8, aPregistrationd; "pRegistrationData->pszComputerObjectSid"
0x180052301  mov     ebx, 80070057h
0x180052306  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x18005230d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180052314  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180052319  lea     rdx, aPregistrationd; "pRegistrationData->pszComputerObjectSid"
0x180052320  jmp     loc_1800521B8
0x180052325  mov     rcx, rdi; struct _REGISTRATION_DATA *
0x180052328  call    ?VerifyAutoSigningCert@RegistrationController@@SAJPEAU_REGISTRATION_DATA@@@Z; RegistrationController::VerifyAutoSigningCert(_REGISTRATION_DATA *)
0x18005232d  mov     ebx, eax
0x18005232f  test    eax, eax
0x180052331  jns     short loc_1800523A8
0x180052333  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x18005233a  cmp     r14d, 7
0x18005233e  jnz     short loc_180052394
0x180052340  lea     rcx, aSUnableToVerif; "%s: Unable to verify or update the sign"...
0x180052347  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005234c  lea     ecx, [r14-5]
0x180052350  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, cl
0x180052356  jz      loc_18005263F
0x18005235c  mov     r8d, ebx
0x18005235f  lea     rdx, VerifyAutoSigningCertFailureEvent
0x180052366  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18005236d  call    McTemplateU0q_EventWriteTransfer
0x180052372  test    eax, eax
0x180052374  jz      loc_18005263F
0x18005237a  lea     r8, aEventwriteveri; "EventWriteVerifyAutoSigningCertFailureE"...
0x180052381  lea     rdx, aLoggerWritever; "Logger::WriteVerifyAutoSigningCertFailu"...
0x180052388  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18005238f  jmp     loc_180052637
0x180052394  mov     r9, [rsp+450h+var_3F0]
0x180052399  lea     rcx, aSRegistrationc_0; "%s: RegistrationController::VerifyAutoS"...
0x1800523a0  mov     r8d, ebx
0x1800523a3  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800523a8  mov     rcx, [rdi+0B0h]; unsigned __int16 *
0x1800523af  lea     rdx, [rsp+450h+var_400]; unsigned __int16 **
0x1800523b4  call    ?MakeFakeUserEmail@@YAJPEBGPEAPEAG@Z; MakeFakeUserEmail(ushort const *,ushort * *)
0x1800523b9  mov     ebx, eax
0x1800523bb  test    eax, eax
0x1800523bd  jns     short loc_1800523E6
0x1800523bf  mov     r9d, eax
0x1800523c2  lea     r8, aMakefakeuserem; "MakeFakeUserEmail"
0x1800523c9  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x1800523d0  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800523d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800523dc  mov     r15, [rsp+450h+var_400]
0x1800523e1  jmp     loc_18005263F
0x1800523e6  mov     r15, [rsp+450h+var_400]
0x1800523eb  cmp     r14d, 7
0x1800523ef  jz      loc_180052495
0x1800523f5  cmp     r14d, 0Ah
0x1800523f9  jz      short loc_180052405
0x1800523fb  cmp     r14d, 0Fh
0x1800523ff  jnz     loc_1800525F5
0x180052405  mov     ecx, 2
0x18005240a  mov     dword ptr [rsp+450h+var_3D8], 1
0x180052412  mov     [rbp+350h+var_3D0], r15
0x180052416  lea     rax, [rbp+350h+var_370]
0x18005241a  lea     edx, [rcx+7Eh]
0x18005241d  movups  xmm0, xmmword ptr [rsi]
0x180052420  movups  xmm1, xmmword ptr [rsi+10h]
0x180052424  movups  xmmword ptr [rax], xmm0
0x180052427  movups  xmm0, xmmword ptr [rsi+20h]
0x18005242b  movups  xmmword ptr [rax+10h], xmm1
0x18005242f  movups  xmm1, xmmword ptr [rsi+30h]
0x180052433  movups  xmmword ptr [rax+20h], xmm0
0x180052437  movups  xmm0, xmmword ptr [rsi+40h]
0x18005243b  movups  xmmword ptr [rax+30h], xmm1
0x18005243f  movups  xmm1, xmmword ptr [rsi+50h]
0x180052443  movups  xmmword ptr [rax+40h], xmm0
0x180052447  movups  xmm0, xmmword ptr [rsi+60h]
0x18005244b  movups  xmmword ptr [rax+50h], xmm1
0x18005244f  movups  xmm1, xmmword ptr [rsi+70h]
0x180052453  add     rsi, rdx
0x180052456  movups  xmmword ptr [rax+60h], xmm0
0x18005245a  movups  xmmword ptr [rax+70h], xmm1
0x18005245e  add     rax, rdx
0x180052461  sub     rcx, 1
0x180052465  jnz     short loc_18005241D
0x180052467  mov     rax, [rdi+0A0h]
0x18005246e  mov     [rbp+350h+var_380], rax
0x180052472  mov     rax, [rdi+0B8h]
0x180052479  mov     [rbp+350h+var_378], rax
0x18005247d  mov     rax, qword ptr [rbp+350h+SystemTime.wYear]
0x180052484  mov     [rbp+350h+var_268], rax
0x18005248b  mov     [rsp+450h+var_3E0], r13
0x180052490  jmp     loc_1800525F5
0x180052495  xorps   xmm0, xmm0
0x180052498  lea     rcx, [rbp+350h+SystemTime]; lpSystemTime
0x18005249f  movups  xmmword ptr [rbp+350h+SystemTime.wYear], xmm0
0x1800524a6  call    cs:__imp_GetSystemTime
0x1800524ac  movzx   ecx, [rbp+350h+SystemTime.wMinute]
0x1800524b3  movzx   edx, [rbp+350h+SystemTime.wHour]
0x1800524ba  movzx   r8d, [rbp+350h+SystemTime.wDay]
0x1800524c2  movzx   eax, [rbp+350h+SystemTime.wSecond]
0x1800524c9  movzx   r10d, [rbp+350h+SystemTime.wMonth]
0x1800524d1  movzx   r9d, [rbp+350h+SystemTime.wYear]
0x1800524d9  mov     [rsp+450h+var_410], eax
0x1800524dd  mov     [rsp+450h+var_418], ecx
0x1800524e1  lea     rcx, [rbp+350h+var_250]; unsigned __int16 *
0x1800524e8  mov     [rsp+450h+var_420], edx
0x1800524ec  mov     edx, 104h; unsigned __int64
0x1800524f1  mov     [rsp+450h+var_428], r8d
0x1800524f6  lea     r8, a04d02d02d02d02; ".%04d-%02d-%02d %02d:%02d:%02dZ"
0x1800524fd  mov     dword ptr [rsp+450h+var_430], r10d
0x180052502  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052507  mov     rcx, [rdi+0A8h]; unsigned __int16 *
0x18005250e  lea     r8, [rsp+450h+var_3F8]; unsigned __int16 **
0x180052513  lea     rdx, [rbp+350h+var_250]; unsigned __int16 *
0x18005251a  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18005251f  mov     ebx, eax
0x180052521  test    eax, eax
0x180052523  jns     short loc_18005254C
0x180052525  mov     r9d, eax
0x180052528  lea     r8, aStringcat; "StringCat"
0x18005252f  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x180052536  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005253d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180052542  mov     r12, [rsp+450h+var_3F8]
0x180052547  jmp     loc_18005263F
0x18005254c  mov     rax, [rdi+0B8h]
0x180052553  mov     ecx, 2
0x180052558  mov     r12, [rsp+450h+var_3F8]
0x18005255d  mov     [rbp+350h+var_3C8], rax
0x180052561  mov     rax, [rdi+0B0h]
0x180052568  mov     [rbp+350h+var_3C0], rax
0x18005256c  lea     edx, [rcx+7Eh]
0x18005256f  mov     rax, [rdi+0A0h]
0x180052576  mov     [rsp+450h+var_3D8], rax
0x18005257b  mov     rax, [rdi+0C0h]
0x180052582  mov     [rbp+350h+var_3B8], rax
0x180052586  lea     rax, [rbp+350h+var_3A0]
0x18005258a  mov     [rsp+450h+var_3E0], r15
0x18005258f  mov     [rbp+350h+var_3D0], r12
0x180052593  movups  xmm0, xmmword ptr [rsi]
0x180052596  movups  xmm1, xmmword ptr [rsi+10h]
0x18005259a  movups  xmmword ptr [rax], xmm0
0x18005259d  movups  xmm0, xmmword ptr [rsi+20h]
0x1800525a1  movups  xmmword ptr [rax+10h], xmm1
0x1800525a5  movups  xmm1, xmmword ptr [rsi+30h]
0x1800525a9  movups  xmmword ptr [rax+20h], xmm0
0x1800525ad  movups  xmm0, xmmword ptr [rsi+40h]
0x1800525b1  movups  xmmword ptr [rax+30h], xmm1
0x1800525b5  movups  xmm1, xmmword ptr [rsi+50h]
0x1800525b9  movups  xmmword ptr [rax+40h], xmm0
0x1800525bd  movups  xmm0, xmmword ptr [rsi+60h]
0x1800525c1  movups  xmmword ptr [rax+50h], xmm1
0x1800525c5  movups  xmm1, xmmword ptr [rsi+70h]
0x1800525c9  add     rsi, rdx
0x1800525cc  movups  xmmword ptr [rax+60h], xmm0
0x1800525d0  movups  xmmword ptr [rax+70h], xmm1
0x1800525d4  add     rax, rdx
0x1800525d7  sub     rcx, 1
0x1800525db  jnz     short loc_180052593
0x1800525dd  mov     rax, [rdi]
0x1800525e0  test    rax, rax
0x1800525e3  jz      short loc_1800525F5
0x1800525e5  cmp     [rdi+8], rcx
0x1800525e9  jz      short loc_1800525F5
0x1800525eb  mov     [rbp+350h+var_3B0], rax
0x1800525ef  mov     eax, [rdi+8]
0x1800525f2  mov     [rbp+350h+var_3A8], eax
0x1800525f5  mov     r9, [rbp+350h+arg_20]
0x1800525fc  lea     rax, ?DEFAULT@_JOIN_OPERATION_CONTEXT@@2U1@B; _JOIN_OPERATION_CONTEXT const _JOIN_OPERATION_CONTEXT::DEFAULT
0x180052603  lea     r8, ?AutoJoinCallback@DsrCmdDeviceEnroller@@SAXUstruct_dsreg_server_response@@_KJ@Z; DsrCmdDeviceEnroller::AutoJoinCallback(struct_dsreg_server_response,unsigned __int64,long)
0x18005260a  mov     [rsp+450h+var_430], rax
0x18005260f  lea     rdx, [rsp+450h+var_3E0]
0x180052614  mov     ecx, r14d
0x180052617  call    ?BeginJoin@DeviceRegistrationApi@@SAJW4_JOIN_TYPE@@PEAXP6AXXZ_KPEBU_JOIN_OPERATION_CONTEXT@@@Z; DeviceRegistrationApi::BeginJoin(_JOIN_TYPE,void *,void (*)(void),unsigned __int64,_JOIN_OPERATION_CONTEXT const *)
0x18005261c  mov     ebx, eax
0x18005261e  test    eax, eax
0x180052620  jns     short loc_18005263F
0x180052622  lea     r8, aDeviceregistra_8; "DeviceRegistrationApi::BeginJoin"
0x180052629  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x180052630  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180052637  mov     r9d, eax
0x18005263a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005263f  mov     rcx, r15; Block
0x180052642  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052647  mov     rcx, r12; lpMem
0x18005264a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18005264f  mov     r8d, ebx
0x180052652  lea     rdx, aDeviceregistra_11; "DeviceRegistrationApi::BeginAutoJoin"
0x180052659  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180052660  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180052665  mov     eax, ebx
0x180052667  mov     rcx, [rbp+350h+var_40]
0x18005266e  xor     rcx, rsp; StackCookie
0x180052671  call    __security_check_cookie
0x180052676  mov     rbx, [rsp+450h+arg_18]
0x18005267e  add     rsp, 420h
0x180052685  pop     r15
0x180052687  pop     r14
0x180052689  pop     r13
0x18005268b  pop     r12
  ... truncated ...
```
