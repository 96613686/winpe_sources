# DeviceRegistrationApi::CompleteJoinResponse(_JOIN_RESPONSE const *,RegistrationController *)

- ea: `0x180053630`
- end: `0x180053bde`
- name: `?CompleteJoinResponse@DeviceRegistrationApi@@SAJPEBU_JOIN_RESPONSE@@PEAVRegistrationController@@@Z`
- size: `1454`
- prototype: `__int64 __fastcall(const struct _JOIN_RESPONSE *, struct RegistrationController *this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800518e0`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180012948`
- `0x180012eb8`
- `0x18001b560`
- `0x1800307c4`
- `0x18003334c`
- `0x180039b50`
- `0x180040df8`
- `0x180043ef8`
- `0x18004651c`
- `0x180046540`
- `0x18004c864`
- `0x18004ecc0`
- `0x18004eeb0`
- `0x18004f068`
- `0x180053630`
- `0x180059e74`
- `0x18005f178`
- `0x1800742e8`
- `0x180075dcc`
- `0x180093f00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053ba5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053ba5`

## string_xrefs

- `0x1800539a9`: `GetCurrentUserSid`
- `0x180053759`: `StringCompare`
- `0x180053819`: `StringCompare`
- `0x180053931`: `AadPluginController::PeformPostJoinSuccessTasks`
- `0x180053688`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x1800536a2`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x1800536c4`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053770`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x18005382a`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x1800538a2`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053979`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x1800539ba`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x1800539db`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053a01`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053a7b`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053ad8`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053b24`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053b41`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x180053bae`: `DeviceRegistrationApi::CompleteJoinResponse`
- `0x18005377a`: `%s: Recovery device certificate is for tenant id %s. Current registration uses tenant id %s. Recovery API should be called with token for current tenant id.`
- `0x180053980`: `%s: ADRS ignored AIKs during registration. Removing any AIKs created for this request.`
- `0x180053a82`: `%s: Failed to determine device public key hash (error 0x%08X). Deletion of token binding AIKs will be skipped.`
- `0x180053afe`: `%s: Successfully removed %s AIK for tenant id %s`
- `0x180053b2b`: `%s: AadPluginController::PerformPostCertificateSavedTasks failed with error code: 0x%08x. Setting the error code to 'requires_reboot'`
- `0x1800539e2`: `%s: Trying to rollback operations.`
- `0x180053a08`: `%s: PerformRollbackTasks failed with error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall DeviceRegistrationApi::CompleteJoinResponse(
        const struct _JOIN_RESPONSE *a1,
        const unsigned __int16 **this)
{
  AadPluginController *v4; // rsi
  unsigned __int16 *v5; // r15
  unsigned __int16 *v6; // r13
  unsigned __int16 *v7; // r12
  unsigned int v8; // ebx
  const unsigned __int16 *v9; // rdx
  int v10; // r12d
  const WCHAR *v11; // rcx
  int CertificateDeviceAndTenantId; // eax
  const wchar_t *v13; // r8
  const WCHAR *v14; // rcx
  unsigned __int16 *v15; // r13
  AadPluginController *v16; // rax
  const struct DevicePolicy *v17; // rax
  AadPluginController *v18; // rcx
  int v19; // r8d
  int v20; // eax
  int EncodedHash; // eax
  unsigned __int64 v22; // rbx
  char *v23; // rax
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // eax
  unsigned int v28; // edx
  unsigned __int16 *v30; // [rsp+20h] [rbp-69h]
  LPCWCH lpString1; // [rsp+30h] [rbp-59h] BYREF
  void *Block; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v33; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v34; // [rsp+48h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-39h] BYREF
  char *v36; // [rsp+60h] [rbp-29h]
  int v37; // [rsp+68h] [rbp-21h]
  _QWORD v38[2]; // [rsp+70h] [rbp-19h]
  int v39; // [rsp+80h] [rbp-9h]
  const wchar_t *v40; // [rsp+88h] [rbp-1h]
  char *v41; // [rsp+90h] [rbp+7h]
  int v42; // [rsp+98h] [rbp+Fh]
  const wchar_t *v43; // [rsp+A0h] [rbp+17h]
  AadPluginController *v44; // [rsp+F0h] [rbp+67h] BYREF
  int v45; // [rsp+100h] [rbp+77h] BYREF
  unsigned __int16 *v46; // [rsp+108h] [rbp+7Fh] BYREF

  Block = 0;
  lpString1 = 0;
  v4 = 0;
  v33 = 0;
  v5 = 0;
  v34 = 0;
  v6 = 0;
  hMem = 0;
  v7 = 0;
  v46 = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationApi::CompleteJoinResponse",
      L"pJoinResponse");
    v9 = L"pJoinResponse";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceRegistrationApi::CompleteJoinResponse", v9);
    goto LABEL_59;
  }
  if ( !this )
  {
    v8 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationApi::CompleteJoinResponse",
      L"pController");
    v9 = L"pController";
    goto LABEL_3;
  }
  v10 = 1;
  if ( ((*((_DWORD *)a1 + 42) - 1) & 0xFFFFFFFB) == 0 && *((_DWORD *)this + 1) == 1 )
  {
    v10 = 0;
    if ( !(unsigned int)IsEmptyString(this[1]) )
    {
      v11 = (const WCHAR *)*((_QWORD *)a1 + 5);
      LODWORD(v44) = 0;
      CertificateDeviceAndTenantId = RegistrationCertStatus::GetCertificateDeviceAndTenantId(
                                       v11,
                                       (unsigned __int16 **)&Block,
                                       (unsigned __int16 **)&lpString1);
      v5 = (unsigned __int16 *)lpString1;
      v8 = CertificateDeviceAndTenantId;
      if ( CertificateDeviceAndTenantId < 0 )
      {
        v13 = L"RegistrationCertStatus::GetCertificateDeviceAndTenantId";
LABEL_40:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"DeviceRegistrationApi::CompleteJoinResponse",
          v13,
          (unsigned int)CertificateDeviceAndTenantId);
        if ( v8 != -2145648625 )
        {
          if ( v4 )
          {
            Logger::TraceVerbose(
              (wchar_t *)L"%s: Trying to rollback operations.",
              L"DeviceRegistrationApi::CompleteJoinResponse");
            v20 = AadPluginController::PerformRollbackTasks(v4);
            if ( v20 < 0 )
              Logger::TraceError(
                L"%s: PerformRollbackTasks failed with error code: 0x%08x.",
                L"DeviceRegistrationApi::CompleteJoinResponse",
                (unsigned int)v20);
          }
        }
        goto LABEL_58;
      }
      CertificateDeviceAndTenantId = StringCompare(lpString1, this[1], 1u, (int *)&v44);
      v8 = CertificateDeviceAndTenantId;
      if ( CertificateDeviceAndTenantId < 0 )
      {
LABEL_12:
        v13 = L"StringCompare";
        goto LABEL_40;
      }
      if ( !(_DWORD)v44 )
      {
        v8 = -2145648585;
        Logger::TraceError(
          L"%s: Recovery device certificate is for tenant id %s. Current registration uses tenant id %s. Recovery API shou"
           "ld be called with token for current tenant id.",
          L"DeviceRegistrationApi::CompleteJoinResponse",
          v5,
          this[1]);
LABEL_58:
        v7 = v46;
        goto LABEL_59;
      }
    }
  }
  if ( (unsigned int)(*((_DWORD *)a1 + 42) - 13) <= 1 )
  {
    v14 = (const WCHAR *)*((_QWORD *)a1 + 5);
    LODWORD(v44) = 0;
    v45 = 0;
    CertificateDeviceAndTenantId = RegistrationCertStatus::GetCertificateDeviceAndTenantId(
                                     v14,
                                     (unsigned __int16 **)&Block,
                                     (unsigned __int16 **)&lpString1);
    v8 = CertificateDeviceAndTenantId;
    if ( CertificateDeviceAndTenantId < 0 )
    {
      v5 = (unsigned __int16 *)lpString1;
      v13 = L"RegistrationCertStatus::GetCertificateDeviceAndTenantId";
      goto LABEL_40;
    }
    CertificateDeviceAndTenantId = RegistrationCertStatus::GetCertificateDeviceAndTenantId(
                                     *((LPCWSTR *)a1 + 9),
                                     &v33,
                                     &v34);
    v5 = (unsigned __int16 *)lpString1;
    v8 = CertificateDeviceAndTenantId;
    if ( CertificateDeviceAndTenantId < 0 )
    {
      v13 = L"RegistrationCertStatus::GetCertificateDeviceAndTenantId";
LABEL_20:
      v6 = v33;
      goto LABEL_40;
    }
    v15 = v34;
    CertificateDeviceAndTenantId = StringCompare(lpString1, v34, 1u, (int *)&v44);
    v8 = CertificateDeviceAndTenantId;
    if ( CertificateDeviceAndTenantId < 0 )
    {
      v13 = L"StringCompare";
      goto LABEL_20;
    }
    if ( !(_DWORD)v44 )
    {
      Logger::TraceError(
        L"%s: Tenant id %s in resource account certificate does not match tenant id %s in device ceritificate",
        L"DeviceRegistrationApi::CompleteJoinResponse",
        v15,
        v5);
      Logger::WriteJoinWithResourceAccountResponseNonMatchingCertificatesEvent(
        L"Tenant ID",
        v15,
        v5,
        *((const unsigned __int16 **)a1 + 25),
        *((const unsigned __int16 **)a1 + 26));
      v6 = v33;
      v8 = -2145648569;
      goto LABEL_58;
    }
    v6 = v33;
    CertificateDeviceAndTenantId = StringCompare((LPCWCH)Block, v33, 1u, &v45);
    v8 = CertificateDeviceAndTenantId;
    if ( CertificateDeviceAndTenantId < 0 )
      goto LABEL_12;
    if ( !v45 )
    {
      Logger::TraceError(
        L"%s: Device id %s in resource account certificate does not match device id %s in device ceritificate",
        L"DeviceRegistrationApi::CompleteJoinResponse",
        v6,
        Block);
      Logger::WriteJoinWithResourceAccountResponseNonMatchingCertificatesEvent(
        L"Device ID",
        v6,
        (const unsigned __int16 *)Block,
        *((const unsigned __int16 **)a1 + 25),
        *((const unsigned __int16 **)a1 + 26));
      v8 = -2145648569;
      goto LABEL_58;
    }
  }
  v16 = (AadPluginController *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v44 = v16;
  v4 = v16;
  if ( !v16 )
  {
    v4 = 0;
    v8 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationApi::CompleteJoinResponse");
    goto LABEL_58;
  }
  *(_QWORD *)v16 = 0;
  v17 = DevicePolicy::Get();
  CertificateDeviceAndTenantId = AadPluginController::PeformPostJoinSuccessTasks(v4, v17, a1, v10);
  v8 = CertificateDeviceAndTenantId;
  if ( CertificateDeviceAndTenantId < 0 )
  {
    v13 = L"AadPluginController::PeformPostJoinSuccessTasks";
    goto LABEL_40;
  }
  CertificateDeviceAndTenantId = RegistrationController::SaveJoinResponse((RegistrationController *)this, a1);
  v8 = CertificateDeviceAndTenantId;
  if ( CertificateDeviceAndTenantId < 0 )
  {
    v13 = L"RegistrationController::SaveJoinResponse";
    goto LABEL_40;
  }
  if ( v10 && (unsigned int)(*((_DWORD *)a1 + 42) - 5) > 1 )
    AadPluginController::ClearRecoveryFlags();
  if ( (*((_BYTE *)a1 + 152) & 1) != 0 )
  {
    Logger::TraceInformation(
      L"%s: ADRS ignored AIKs during registration. Removing any AIKs created for this request.",
      L"DeviceRegistrationApi::CompleteJoinResponse");
    if ( (unsigned int)(*((_DWORD *)a1 + 42) - 5) <= 1 )
    {
      CertificateDeviceAndTenantId = GetCurrentUserSid((LPWSTR *)&hMem);
      v8 = CertificateDeviceAndTenantId;
      if ( CertificateDeviceAndTenantId < 0 )
      {
        v13 = L"GetCurrentUserSid";
        goto LABEL_40;
      }
    }
    v37 = 0;
    v36 = (char *)a1 + 80;
    v39 = 1;
    v38[0] = L"software";
    v42 = 2;
    v38[1] = (char *)a1 + 96;
    v40 = L"TPM";
    v41 = (char *)a1 + 112;
    v43 = L"KeyGuard";
    EncodedHash = ByteArray::GetEncodedHash((const struct _JOIN_RESPONSE *)((char *)a1 + 24), &v46, v19);
    if ( EncodedHash < 0 )
      Logger::TraceWarning(
        (wchar_t *)L"%s: Failed to determine device public key hash (error 0x%08X). Deletion of token binding AIKs will be skipped.",
        L"DeviceRegistrationApi::CompleteJoinResponse",
        (unsigned int)EncodedHash);
    v7 = v46;
    v22 = 0;
    if ( v46 )
    {
      while ( v22 < 3 )
      {
        v23 = (&v36)[3 * v22];
        if ( *(_QWORD *)v23 && *((_QWORD *)v23 + 1) )
        {
          v24 = RegistrationKeyHelper::DeleteAik(
                  LODWORD(v38[3 * v22]),
                  v7,
                  *(_QWORD *)(*((_QWORD *)a1 + 22) + 16LL),
                  hMem);
          v25 = v38[3 * v22];
          v26 = *(_QWORD *)(*((_QWORD *)a1 + 22) + 16LL);
          if ( v24 >= 0 )
          {
            Logger::TraceInformation(
              L"%s: Successfully removed %s AIK for tenant id %s",
              L"DeviceRegistrationApi::CompleteJoinResponse",
              v25,
              v26);
          }
          else
          {
            LODWORD(v30) = v24;
            Logger::TraceWarning(
              (wchar_t *)L"%s: Deleting %s AIK for tenant id %s failed with error 0x%08X",
              L"DeviceRegistrationApi::CompleteJoinResponse",
              v25,
              v26,
              v30);
          }
        }
        ++v22;
      }
    }
  }
  else
  {
    v7 = v46;
  }
  v27 = AadPluginController::PerformPostCertificateSavedTasks(v18, a1);
  v8 = v27;
  if ( v27 < 0 )
  {
    Logger::TraceError(
      L"%s: AadPluginController::PerformPostCertificateSavedTasks failed with error code: 0x%08x. Setting the error code t"
       "o 'requires_reboot'",
      L"DeviceRegistrationApi::CompleteJoinResponse",
      (unsigned int)v27);
    v8 = -2145648625;
  }
LABEL_59:
  operator delete(v5);
  operator delete(Block);
  operator delete(v34);
  operator delete(v6);
  if ( v4 )
  {
    AadPluginController::~AadPluginController((AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT **)v4, v28);
    operator delete(v4);
  }
  SafeFree(v7);
  LocalFree(hMem);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DeviceRegistrationApi::CompleteJoinResponse", v8);
  return v8;
}

```

## disassembly

```asm
0x180053630  mov     [rsp-8+arg_8], rbx
0x180053635  push    rbp
0x180053636  push    rsi
0x180053637  push    rdi
0x180053638  push    r12
0x18005363a  push    r13
0x18005363c  push    r14
0x18005363e  push    r15
0x180053640  lea     rbp, [rsp-27h]
0x180053645  sub     rsp, 0B0h
0x18005364c  xor     ebx, ebx
0x18005364e  mov     r14, rdx
0x180053651  mov     [rbp+57h+Block], rbx
0x180053655  mov     rdi, rcx
0x180053658  mov     [rbp+57h+lpString1], rbx
0x18005365c  mov     esi, ebx
0x18005365e  mov     [rbp+57h+var_A0], rbx
0x180053662  mov     r15d, ebx
0x180053665  mov     [rbp+57h+var_98], rbx
0x180053669  mov     r13d, ebx
0x18005366c  mov     [rbp+57h+hMem], rbx
0x180053670  mov     r12d, ebx
0x180053673  mov     [rbp+57h+arg_18], rbx
0x180053677  test    rcx, rcx
0x18005367a  jnz     short loc_1800536B3
0x18005367c  lea     r8, aPjoinresponse; "pJoinResponse"
0x180053683  mov     ebx, 80070057h
0x180053688  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x18005368f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180053696  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005369b  lea     rdx, aPjoinresponse; "pJoinResponse"
0x1800536a2  lea     rcx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x1800536a9  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800536ae  jmp     loc_180053B5D
0x1800536b3  test    r14, r14
0x1800536b6  jnz     short loc_1800536E0
0x1800536b8  lea     r8, aPcontroller; "pController"
0x1800536bf  mov     ebx, 80070057h
0x1800536c4  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x1800536cb  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800536d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800536d7  lea     rdx, aPcontroller; "pController"
0x1800536de  jmp     short loc_1800536A2
0x1800536e0  mov     eax, [rcx+0A8h]
0x1800536e6  mov     r12d, 1
0x1800536ec  dec     eax
0x1800536ee  test    eax, 0FFFFFFFBh
0x1800536f3  jnz     loc_180053790
0x1800536f9  cmp     [rdx+4], r12d
0x1800536fd  jnz     loc_180053790
0x180053703  mov     rcx, [rdx+8]; unsigned __int16 *
0x180053707  mov     r12d, ebx
0x18005370a  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18005370f  test    eax, eax
0x180053711  jnz     short loc_180053790
0x180053713  mov     rcx, [rdi+28h]; pszString
0x180053717  lea     r8, [rbp+57h+lpString1]; unsigned __int16 **
0x18005371b  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x18005371f  mov     dword ptr [rbp+57h+arg_0], ebx
0x180053722  call    ?GetCertificateDeviceAndTenantId@RegistrationCertStatus@@SAJPEBGPEAPEAG1@Z; RegistrationCertStatus::GetCertificateDeviceAndTenantId(ushort const *,ushort * *,ushort * *)
0x180053727  mov     r15, [rbp+57h+lpString1]
0x18005372b  mov     ebx, eax
0x18005372d  test    eax, eax
0x18005372f  jns     short loc_18005373D
0x180053731  lea     r8, aRegistrationce_8; "RegistrationCertStatus::GetCertificateD"...
0x180053738  jmp     loc_1800539B0
0x18005373d  mov     rdx, [r14+8]; unsigned __int16 *
0x180053741  lea     r9, [rbp+57h+arg_0]; int *
0x180053745  mov     r8d, 1; unsigned int
0x18005374b  mov     rcx, r15; lpString1
0x18005374e  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180053753  mov     ebx, eax
0x180053755  test    eax, eax
0x180053757  jns     short loc_180053765
0x180053759  lea     r8, aStringcompare; "StringCompare"
0x180053760  jmp     loc_1800539B0
0x180053765  xor     ebx, ebx
0x180053767  cmp     dword ptr [rbp+57h+arg_0], ebx
0x18005376a  jnz     short loc_180053790
0x18005376c  mov     r9, [r14+8]
0x180053770  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x180053777  mov     r8, r15
0x18005377a  lea     rcx, aSRecoveryDevic; "%s: Recovery device certificate is for "...
0x180053781  mov     ebx, 801C0037h
0x180053786  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005378b  jmp     loc_180053B59
0x180053790  mov     eax, [rdi+0A8h]
0x180053796  sub     eax, 0Dh
0x180053799  cmp     eax, 1
0x18005379c  ja      loc_1800538E8
0x1800537a2  mov     rcx, [rdi+28h]; pszString
0x1800537a6  lea     r8, [rbp+57h+lpString1]; unsigned __int16 **
0x1800537aa  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x1800537ae  mov     dword ptr [rbp+57h+arg_0], ebx
0x1800537b1  mov     [rbp+57h+arg_10], ebx
0x1800537b4  call    ?GetCertificateDeviceAndTenantId@RegistrationCertStatus@@SAJPEBGPEAPEAG1@Z; RegistrationCertStatus::GetCertificateDeviceAndTenantId(ushort const *,ushort * *,ushort * *)
0x1800537b9  mov     ebx, eax
0x1800537bb  test    eax, eax
0x1800537bd  jns     short loc_1800537CF
0x1800537bf  mov     r15, [rbp+57h+lpString1]
0x1800537c3  lea     r8, aRegistrationce_8; "RegistrationCertStatus::GetCertificateD"...
0x1800537ca  jmp     loc_1800539B0
0x1800537cf  mov     rcx, [rdi+48h]; pszString
0x1800537d3  lea     r8, [rbp+57h+var_98]; unsigned __int16 **
0x1800537d7  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x1800537db  call    ?GetCertificateDeviceAndTenantId@RegistrationCertStatus@@SAJPEBGPEAPEAG1@Z; RegistrationCertStatus::GetCertificateDeviceAndTenantId(ushort const *,ushort * *,ushort * *)
0x1800537e0  mov     r15, [rbp+57h+lpString1]
0x1800537e4  mov     ebx, eax
0x1800537e6  test    eax, eax
0x1800537e8  jns     short loc_1800537FA
0x1800537ea  lea     r8, aRegistrationce_8; "RegistrationCertStatus::GetCertificateD"...
0x1800537f1  mov     r13, [rbp+57h+var_A0]
0x1800537f5  jmp     loc_1800539B0
0x1800537fa  mov     r13, [rbp+57h+var_98]
0x1800537fe  lea     r9, [rbp+57h+arg_0]; int *
0x180053802  mov     rdx, r13; unsigned __int16 *
0x180053805  mov     r8d, 1; unsigned int
0x18005380b  mov     rcx, r15; lpString1
0x18005380e  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180053813  mov     ebx, eax
0x180053815  test    eax, eax
0x180053817  jns     short loc_180053822
0x180053819  lea     r8, aStringcompare; "StringCompare"
0x180053820  jmp     short loc_1800537F1
0x180053822  cmp     dword ptr [rbp+57h+arg_0], esi
0x180053825  jnz     short loc_180053873
0x180053827  mov     r9, r15
0x18005382a  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x180053831  mov     r8, r13
0x180053834  lea     rcx, aSTenantIdSInRe; "%s: Tenant id %s in resource account ce"...
0x18005383b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180053840  mov     rax, [rdi+0D0h]
0x180053847  lea     rcx, aTenantId; "Tenant ID"
0x18005384e  mov     r9, [rdi+0C8h]; unsigned __int16 *
0x180053855  mov     r8, r15; unsigned __int16 *
0x180053858  mov     rdx, r13; unsigned __int16 *
0x18005385b  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x180053860  call    ?WriteJoinWithResourceAccountResponseNonMatchingCertificatesEvent@Logger@@SAJPEBG0000@Z; Logger::WriteJoinWithResourceAccountResponseNonMatchingCertificatesEvent(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180053865  mov     r13, [rbp+57h+var_A0]
0x180053869  mov     ebx, 801C0047h
0x18005386e  jmp     loc_180053B59
0x180053873  mov     r13, [rbp+57h+var_A0]
0x180053877  lea     r9, [rbp+57h+arg_10]; int *
0x18005387b  mov     rcx, [rbp+57h+Block]; lpString1
0x18005387f  mov     rdx, r13; unsigned __int16 *
0x180053882  mov     r8d, 1; unsigned int
0x180053888  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18005388d  mov     ebx, eax
0x18005388f  test    eax, eax
0x180053891  js      loc_180053759
0x180053897  xor     ebx, ebx
0x180053899  cmp     [rbp+57h+arg_10], ebx
0x18005389c  jnz     short loc_1800538E8
0x18005389e  mov     r9, [rbp+57h+Block]
0x1800538a2  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x1800538a9  mov     r8, r13
0x1800538ac  lea     rcx, aSDeviceIdSInRe; "%s: Device id %s in resource account ce"...
0x1800538b3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800538b8  mov     rax, [rdi+0D0h]
0x1800538bf  lea     rcx, aDeviceId; "Device ID"
0x1800538c6  mov     r9, [rdi+0C8h]; unsigned __int16 *
0x1800538cd  mov     rdx, r13; unsigned __int16 *
0x1800538d0  mov     r8, [rbp+57h+Block]; unsigned __int16 *
0x1800538d4  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x1800538d9  call    ?WriteJoinWithResourceAccountResponseNonMatchingCertificatesEvent@Logger@@SAJPEBG0000@Z; Logger::WriteJoinWithResourceAccountResponseNonMatchingCertificatesEvent(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800538de  mov     ebx, 801C0047h
0x1800538e3  jmp     loc_180053B59
0x1800538e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800538ef  mov     ecx, 8; unsigned __int64
0x1800538f4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800538f9  mov     [rbp+57h+arg_0], rax
0x1800538fd  mov     rsi, rax
0x180053900  test    rax, rax
0x180053903  jz      loc_180053B3E
0x180053909  mov     [rax], rbx
0x18005390c  test    rax, rax
0x18005390f  jz      loc_180053B41
0x180053915  call    ?Get@DevicePolicy@@SAAEBV1@XZ; DevicePolicy::Get(void)
0x18005391a  mov     rdx, rax; struct DevicePolicy *
0x18005391d  mov     r9d, r12d; int
0x180053920  mov     r8, rdi; struct _JOIN_RESPONSE *
0x180053923  mov     rcx, rsi; this
0x180053926  call    ?PeformPostJoinSuccessTasks@AadPluginController@@QEAAJAEBVDevicePolicy@@PEBU_JOIN_RESPONSE@@H@Z; AadPluginController::PeformPostJoinSuccessTasks(DevicePolicy const &,_JOIN_RESPONSE const *,int)
0x18005392b  mov     ebx, eax
0x18005392d  test    eax, eax
0x18005392f  jns     short loc_18005393A
0x180053931  lea     r8, aAadplugincontr_5; "AadPluginController::PeformPostJoinSucc"...
0x180053938  jmp     short loc_1800539B0
0x18005393a  mov     rdx, rdi; struct _JOIN_RESPONSE *
0x18005393d  mov     rcx, r14; this
0x180053940  call    ?SaveJoinResponse@RegistrationController@@QEAAJPEBU_JOIN_RESPONSE@@@Z; RegistrationController::SaveJoinResponse(_JOIN_RESPONSE const *)
0x180053945  mov     ebx, eax
0x180053947  test    eax, eax
0x180053949  jns     short loc_180053954
0x18005394b  lea     r8, aRegistrationco_16; "RegistrationController::SaveJoinRespons"...
0x180053952  jmp     short loc_1800539B0
0x180053954  test    r12d, r12d
0x180053957  jz      short loc_18005396C
0x180053959  mov     eax, [rdi+0A8h]
0x18005395f  sub     eax, 5
0x180053962  cmp     eax, 1
0x180053965  jbe     short loc_18005396C
0x180053967  call    ?ClearRecoveryFlags@AadPluginController@@SAJXZ; AadPluginController::ClearRecoveryFlags(void)
0x18005396c  test    byte ptr [rdi+98h], 1
0x180053973  jz      loc_180053B0F
0x180053979  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x180053980  lea     rcx, aSAdrsIgnoredAi; "%s: ADRS ignored AIKs during registrati"...
0x180053987  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005398c  mov     eax, [rdi+0A8h]
0x180053992  sub     eax, 5
0x180053995  cmp     eax, 1
0x180053998  ja      short loc_180053A19
0x18005399a  lea     rcx, [rbp+57h+hMem]; StringSid
0x18005399e  call    ?GetCurrentUserSid@@YAJPEAPEAG@Z; GetCurrentUserSid(ushort * *)
0x1800539a3  mov     ebx, eax
0x1800539a5  test    eax, eax
0x1800539a7  jns     short loc_180053A19
0x1800539a9  lea     r8, aGetcurrentuser_0; "GetCurrentUserSid"
0x1800539b0  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800539b7  mov     r9d, eax
0x1800539ba  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x1800539c1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800539c6  cmp     ebx, 801C000Fh
0x1800539cc  jz      loc_180053B59
0x1800539d2  test    rsi, rsi
0x1800539d5  jz      loc_180053B59
0x1800539db  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x1800539e2  lea     rcx, aSTryingToRollb; "%s: Trying to rollback operations."
0x1800539e9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800539ee  mov     rcx, rsi; this
0x1800539f1  call    ?PerformRollbackTasks@AadPluginController@@QEAAJXZ; AadPluginController::PerformRollbackTasks(void)
0x1800539f6  test    eax, eax
0x1800539f8  jns     loc_180053B59
0x1800539fe  mov     r8d, eax
0x180053a01  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x180053a08  lea     rcx, aSPerformrollba; "%s: PerformRollbackTasks failed with er"...
0x180053a0f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180053a14  jmp     loc_180053B59
0x180053a19  lea     rax, [rdi+50h]
0x180053a1d  mov     [rbp+57h+var_78], 0
0x180053a24  mov     [rbp+57h+var_80], rax
0x180053a28  lea     rcx, [rdi+18h]; this
0x180053a2c  lea     rax, aSoftware_0; "software"
0x180053a33  mov     [rbp+57h+var_60], 1
0x180053a3a  mov     [rbp+57h+var_70], rax
0x180053a3e  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x180053a42  lea     rax, [rdi+60h]
0x180053a46  mov     [rbp+57h+var_48], 2
0x180053a4d  mov     [rbp+57h+var_68], rax
0x180053a51  lea     rax, aTpm; "TPM"
0x180053a58  mov     [rbp+57h+var_58], rax
0x180053a5c  lea     rax, [rdi+70h]
0x180053a60  mov     [rbp+57h+var_50], rax
0x180053a64  lea     rax, aKeyguard; "KeyGuard"
0x180053a6b  mov     [rbp+57h+var_40], rax
0x180053a6f  call    ?GetEncodedHash@ByteArray@@QEBAJPEAPEAGH@Z; ByteArray::GetEncodedHash(ushort * *,int)
0x180053a74  test    eax, eax
0x180053a76  jns     short loc_180053A8E
0x180053a78  mov     r8d, eax
0x180053a7b  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x180053a82  lea     rcx, aSFailedToDeter; "%s: Failed to determine device public k"...
0x180053a89  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180053a8e  mov     r12, [rbp+57h+arg_18]
0x180053a92  xor     ebx, ebx
0x180053a94  test    r12, r12
0x180053a97  jz      short loc_180053B13
0x180053a99  cmp     rbx, 3
0x180053a9d  jnb     short loc_180053B13
0x180053a9f  lea     r14, [rbx+rbx*2]
0x180053aa3  mov     rax, [rbp+r14*8+57h+var_80]
0x180053aa8  cmp     qword ptr [rax], 0
0x180053aac  jz      short loc_180053B0A
0x180053aae  cmp     qword ptr [rax+8], 0
0x180053ab3  jz      short loc_180053B0A
0x180053ab5  mov     r8, [rdi+0B0h]
0x180053abc  mov     rdx, r12
0x180053abf  mov     r9, [rbp+57h+hMem]
0x180053ac3  mov     ecx, [rbp+r14*8+57h+var_78]
0x180053ac8  mov     r8, [r8+10h]
0x180053acc  call    ?DeleteAik@RegistrationKeyHelper@@SAJW4DSREG_AIK_TYPE@@PEBG11@Z; RegistrationKeyHelper::DeleteAik(DSREG_AIK_TYPE,ushort const *,ushort const *,ushort const *)
0x180053ad1  mov     rcx, [rdi+0B0h]
0x180053ad8  lea     rdx, aDeviceregistra_7; "DeviceRegistrationApi::CompleteJoinResp"...
0x180053adf  mov     r8, [rbp+r14*8+57h+var_70]
0x180053ae4  mov     r9, [rcx+10h]
0x180053ae8  test    eax, eax
0x180053aea  jns     short loc_180053AFE
0x180053aec  lea     rcx, aSDeletingSAikF; "%s: Deleting %s AIK for tenant id %s fa"...
0x180053af3  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180053af7  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180053afc  jmp     short loc_180053B0A
0x180053afe  lea     rcx, aSSuccessfullyR; "%s: Successfully removed %s AIK for ten"...
0x180053b05  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180053b0a  inc     rbx
0x180053b0d  jmp     short loc_180053A99
0x180053b0f  mov     r12, [rbp+57h+arg_18]
0x180053b13  mov     rdx, rdi; struct _JOIN_RESPONSE *
0x180053b16  call    ?PerformPostCertificateSavedTasks@AadPluginController@@QEAAJPEBU_JOIN_RESPONSE@@@Z; AadPluginController::PerformPostCertificateSavedTasks(_JOIN_RESPONSE const *)
0x180053b1b  mov     ebx, eax
0x180053b1d  test    eax, eax
0x180053b1f  jns     short loc_180053B5D
  ... truncated ...
```
