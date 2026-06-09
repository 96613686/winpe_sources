# SaveCredsThread(void *)

- ea: `0x180003530`
- end: `0x1800038c5`
- name: `?SaveCredsThread@@YAKPEAX@Z`
- size: `917`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003530`
- `0x180003bd0`
- `0x180004df0`
- `0x180006a20`
- `0x18000ea70`
- `0x180010218`
- `0x18001029c`
- `0x18001124c`
- `0x180013b20`
- `0x180014610`
- `0x1800246a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1800036b7`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1800036d1`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1800036b7`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x1800036d1`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800036ef`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800036ef`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000383f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000383f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000378d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000378d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037df`
- `CRYPT32!CertFreeCertificateContext` at `0x180003606`
- `CRYPT32!CertFreeCertificateContext` at `0x180003606`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x1800037d5`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x1800037d5`

## pseudocode

```c
__int64 __fastcall SaveCredsThread(PVOID Parameter)
{
  char v2; // si
  DWORD v3; // r14d
  __int64 v4; // rdx
  __int64 v5; // r8
  void *v6; // rcx
  int JoinCertificate; // eax
  const CERT_CONTEXT *v8; // rbp
  int v9; // edi
  int v10; // r15d
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  char v13; // di
  void *v14; // rcx
  DWORD LastError; // eax
  DWORD v16; // eax
  PCCERT_CONTEXT pCertContext[2]; // [rsp+30h] [rbp-2A8h] BYREF
  _CREDENTIALA Credential; // [rsp+40h] [rbp-298h] BYREF
  char Destination[528]; // [rsp+90h] [rbp-248h] BYREF

  v2 = 0;
  v3 = 0;
  memset_0(Destination, 0, 0x202u);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
  pCertContext[0] = 0;
  JoinCertificate = DeviceRegistrationStateApi::GetJoinCertificate(v6, v4, v5, pCertContext, 0);
  v8 = pCertContext[0];
  v9 = JoinCertificate;
  v10 = 0;
  if ( JoinCertificate >= 0 )
    LOBYTE(v10) = pCertContext[0] != 0;
  else
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceRegistrationStateApi::IsJoined",
      L"DeviceRegistrationStateApi::GetJoinCertificate",
      (unsigned int)JoinCertificate);
  if ( v8 )
    CertFreeCertificateContext(v8);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"DeviceRegistrationStateApi::IsJoined", (unsigned int)v9);
  if ( v9 >= 0 )
  {
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_34;
      v12 = 51;
      goto LABEL_16;
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrIsDeviceJoinedEx",
      L"DeviceRegistrationStateApi::IsJoined",
      (unsigned int)v9);
  }
  if ( (unsigned int)isMachineJoinedToDomain() )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    v12 = 52;
LABEL_16:
    WPP_SF_(v11[2], v12, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
    goto LABEL_34;
  }
  v13 = 0;
  if ( *(_QWORD *)Parameter && **(_BYTE **)Parameter )
  {
    _o_strcat_s(Destination, 514);
    _o_strcat_s(Destination, 514);
  }
  strncat_s(Destination, 0x202u, *((const char **)Parameter + 1), 0xFFFFFFFFFFFFFFFFuLL);
  Credential.Flags = 0;
  Credential.TargetName = "*Session";
  memset(&Credential.Comment, 0, 32);
  Credential.UserName = Destination;
  memset(&Credential.AttributeCount, 0, 20);
  Credential.Type = 2;
  Credential.Persist = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, Destination);
  v14 = (void *)*((_QWORD *)Parameter + 4);
  Credential.CredentialBlob = (LPBYTE)*((_QWORD *)Parameter + 2);
  Credential.CredentialBlobSize = *((_DWORD *)Parameter + 6);
  if ( v14 != (void *)-1LL )
  {
    if ( !ImpersonateLoggedOnUser(v14) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
      }
      goto LABEL_34;
    }
    v13 = 1;
  }
  if ( CredWriteA(&Credential, 0) )
  {
    v2 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
        Credential.UserName);
  }
  else
  {
    v16 = GetLastError();
    v3 = v16;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v16);
  }
  if ( v13 )
    RevertToSelf();
LABEL_34:
  FreeEapCredStructure(Parameter);
  byte_180033810 = v2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180003530  mov     r11, rsp
0x180003533  push    r14
0x180003535  sub     rsp, 2D0h
0x18000353c  mov     rax, cs:__security_cookie
0x180003543  xor     rax, rsp
0x180003546  mov     [rsp+2D8h+var_38], rax
0x18000354e  mov     [r11+10h], rbx
0x180003552  xor     edx, edx; Val
0x180003554  mov     [r11+18h], rbp
0x180003558  mov     rbx, rcx
0x18000355b  mov     [r11+20h], rsi
0x18000355f  lea     rcx, [r11-248h]; void *
0x180003566  mov     [r11-10h], rdi
0x18000356a  xor     sil, sil
0x18000356d  mov     [r11-18h], r12
0x180003571  mov     r8d, 202h; Size
0x180003577  mov     [r11-20h], r13
0x18000357b  xor     r13d, r13d
0x18000357e  mov     r14d, r13d
0x180003581  call    memset_0
0x180003586  mov     rcx, cs:WPP_GLOBAL_Control
0x18000358d  lea     r12, WPP_GLOBAL_Control
0x180003594  cmp     rcx, r12
0x180003597  jz      short loc_1800035AE
0x180003599  mov     rcx, [rcx+10h]
0x18000359d  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800035a4  mov     edx, 32h ; '2'
0x1800035a9  call    WPP_SF_
0x1800035ae  lea     r9, [rsp+2D8h+pCertContext]
0x1800035b3  mov     [rsp+2D8h+var_28], r15
0x1800035bb  mov     [rsp+2D8h+pCertContext], r13
0x1800035c0  mov     [rsp+2D8h+var_2B8], r13
0x1800035c5  call    ?GetJoinCertificate@DeviceRegistrationStateApi@@SAJPEBGW4_JOIN_TYPE@@W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@PEAH@Z; DeviceRegistrationStateApi::GetJoinCertificate(ushort const *,_JOIN_TYPE,INFO_KIND,_CERT_CONTEXT const * *,int *)
0x1800035ca  mov     rbp, [rsp+2D8h+pCertContext]
0x1800035cf  mov     edi, eax
0x1800035d1  mov     r15d, r13d
0x1800035d4  test    eax, eax
0x1800035d6  jns     short loc_1800035F7
0x1800035d8  mov     r9d, eax
0x1800035db  lea     r8, aDeviceregistra_0; "DeviceRegistrationStateApi::GetJoinCert"...
0x1800035e2  lea     rdx, aDeviceregistra; "DeviceRegistrationStateApi::IsJoined"
0x1800035e9  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800035f0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800035f5  jmp     short loc_1800035FE
0x1800035f7  test    rbp, rbp
0x1800035fa  setnz   r15b
0x1800035fe  test    rbp, rbp
0x180003601  jz      short loc_18000360C
0x180003603  mov     rcx, rbp; pCertContext
0x180003606  call    cs:__imp_CertFreeCertificateContext
0x18000360c  mov     r8d, edi
0x18000360f  lea     rdx, aDeviceregistra; "DeviceRegistrationStateApi::IsJoined"
0x180003616  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000361d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180003622  mov     rbp, [rsp+2D8h+arg_10]
0x18000362a  test    edi, edi
0x18000362c  jns     short loc_18000366B
0x18000362e  mov     r9d, edi
0x180003631  lea     r8, aDeviceregistra; "DeviceRegistrationStateApi::IsJoined"
0x180003638  lea     rdx, aDsrisdevicejoi; "DsrIsDeviceJoinedEx"
0x18000363f  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180003646  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000364b  call    isMachineJoinedToDomain
0x180003650  test    eax, eax
0x180003652  jz      short loc_18000369A
0x180003654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000365b  cmp     rcx, r12
0x18000365e  jz      loc_180003845
0x180003664  mov     edx, 34h ; '4'
0x180003669  jmp     short loc_180003685
0x18000366b  test    r15d, r15d
0x18000366e  jz      short loc_18000364B
0x180003670  mov     rcx, cs:WPP_GLOBAL_Control
0x180003677  cmp     rcx, r12
0x18000367a  jz      loc_180003845
0x180003680  mov     edx, 33h ; '3'
0x180003685  mov     rcx, [rcx+10h]
0x180003689  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180003690  call    WPP_SF_
0x180003695  jmp     loc_180003845
0x18000369a  mov     r8, [rbx]
0x18000369d  xor     dil, dil
0x1800036a0  test    r8, r8
0x1800036a3  jz      short loc_1800036D7
0x1800036a5  cmp     [r8], sil
0x1800036a8  jz      short loc_1800036D7
0x1800036aa  mov     edx, 202h
0x1800036af  lea     rcx, [rsp+2D8h+Destination]
0x1800036b7  call    cs:__imp__o_strcat_s
0x1800036bd  lea     r8, asc_18002A06C; "\\"
0x1800036c4  mov     edx, 202h
0x1800036c9  lea     rcx, [rsp+2D8h+Destination]
0x1800036d1  call    cs:__imp__o_strcat_s
0x1800036d7  mov     r8, [rbx+8]; Source
0x1800036db  lea     rcx, [rsp+2D8h+Destination]; Destination
0x1800036e3  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800036ea  mov     edx, 202h; SizeInBytes
0x1800036ef  call    cs:__imp_strncat_s
0x1800036f5  lea     rax, aSession_0; "*Session"
0x1800036fc  mov     [rsp+2D8h+Credential.Flags], r13d
0x180003701  mov     [rsp+2D8h+Credential.TargetName], rax
0x180003706  xorps   xmm0, xmm0
0x180003709  lea     rax, [rsp+2D8h+Destination]
0x180003711  movdqa  xmmword ptr [rsp+2D8h+Credential.Comment], xmm0
0x180003717  xorps   xmm1, xmm1
0x18000371a  mov     [rsp+2D8h+Credential.UserName], rax
0x180003722  movdqa  xmmword ptr [rsp+2D8h+Credential.CredentialBlobSize], xmm1
0x180003728  mov     qword ptr [rsp+2D8h+Credential.AttributeCount], r13
0x18000372d  mov     [rsp+2D8h+Credential.Attributes+4], r13
0x180003732  mov     dword ptr [rsp+2D8h+Credential.TargetAlias+4], r13d
0x18000373a  mov     [rsp+2D8h+Credential.Type], 2
0x180003742  mov     [rsp+2D8h+Credential.Persist], 1
0x18000374a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003751  cmp     rcx, r12
0x180003754  jz      short loc_180003773
0x180003756  mov     rcx, [rcx+10h]
0x18000375a  lea     r9, [rsp+2D8h+Destination]
0x180003762  mov     edx, 35h ; '5'
0x180003767  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18000376e  call    WPP_SF_s
0x180003773  mov     rax, [rbx+10h]
0x180003777  mov     rcx, [rbx+20h]; hToken
0x18000377b  mov     [rsp+2D8h+Credential.CredentialBlob], rax
0x180003780  mov     eax, [rbx+18h]
0x180003783  mov     [rsp+2D8h+Credential.CredentialBlobSize], eax
0x180003787  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000378b  jz      short loc_1800037CE
0x18000378d  call    cs:__imp_ImpersonateLoggedOnUser
0x180003793  test    eax, eax
0x180003795  jnz     short loc_1800037CB
0x180003797  cmp     cs:WPP_GLOBAL_Control, r12
0x18000379e  jz      loc_180003845
0x1800037a4  call    cs:__imp_GetLastError
0x1800037aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037b1  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800037b8  mov     edx, 36h ; '6'
0x1800037bd  mov     r9d, eax
0x1800037c0  mov     rcx, [rcx+10h]
0x1800037c4  call    WPP_SF_d
0x1800037c9  jmp     short loc_180003845
0x1800037cb  mov     dil, 1
0x1800037ce  xor     edx, edx; Flags
0x1800037d0  lea     rcx, [rsp+2D8h+Credential]; Credential
0x1800037d5  call    cs:__imp_CredWriteA
0x1800037db  test    eax, eax
0x1800037dd  jnz     short loc_18000380E
0x1800037df  call    cs:__imp_GetLastError
0x1800037e5  mov     r14d, eax
0x1800037e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037ef  cmp     rcx, r12
0x1800037f2  jz      short loc_18000383A
0x1800037f4  mov     rcx, [rcx+10h]
0x1800037f8  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800037ff  mov     edx, 37h ; '7'
0x180003804  mov     r9d, eax
0x180003807  call    WPP_SF_d
0x18000380c  jmp     short loc_18000383A
0x18000380e  mov     sil, 1
0x180003811  mov     rcx, cs:WPP_GLOBAL_Control
0x180003818  cmp     rcx, r12
0x18000381b  jz      short loc_18000383A
0x18000381d  mov     r9, [rsp+2D8h+Credential.UserName]
0x180003825  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18000382c  mov     rcx, [rcx+10h]
0x180003830  mov     edx, 38h ; '8'
0x180003835  call    WPP_SF_s
0x18000383a  test    dil, dil
0x18000383d  jz      short loc_180003845
0x18000383f  call    cs:__imp_RevertToSelf
0x180003845  mov     rcx, rbx; hMem
0x180003848  call    ?FreeEapCredStructure@@YAXPEAU_EapCredThreadArgs@@@Z; FreeEapCredStructure(_EapCredThreadArgs *)
0x18000384d  mov     cs:byte_180033810, sil
0x180003854  mov     rcx, cs:WPP_GLOBAL_Control
0x18000385b  mov     r15, [rsp+2D8h+var_28]
0x180003863  cmp     rcx, r12
0x180003866  mov     r12, [rsp+2D8h+var_18]
0x18000386e  mov     r13, [rsp+2D8h+var_20]
0x180003876  mov     rdi, [rsp+2D8h+var_10]
0x18000387e  mov     rsi, [rsp+2D8h+arg_18]
0x180003886  mov     rbx, [rsp+2D8h+arg_8]
0x18000388e  jz      short loc_1800038A8
0x180003890  mov     rcx, [rcx+10h]
0x180003894  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18000389b  mov     edx, 39h ; '9'
0x1800038a0  mov     r9d, r14d
0x1800038a3  call    WPP_SF_d
0x1800038a8  mov     eax, r14d
0x1800038ab  mov     rcx, [rsp+2D8h+var_38]
0x1800038b3  xor     rcx, rsp; StackCookie
0x1800038b6  call    __security_check_cookie
0x1800038bb  add     rsp, 2D0h
0x1800038c2  pop     r14
0x1800038c4  retn
```
