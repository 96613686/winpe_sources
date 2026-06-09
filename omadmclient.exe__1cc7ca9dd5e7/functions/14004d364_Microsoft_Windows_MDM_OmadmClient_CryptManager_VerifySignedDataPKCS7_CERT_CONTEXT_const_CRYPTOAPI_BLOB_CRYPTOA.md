# Microsoft::Windows::MDM::OmadmClient::CryptManager::VerifySignedDataPKCS7(_CERT_CONTEXT const *,_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *)

- ea: `0x14004d364`
- end: `0x14004d62b`
- name: `?VerifySignedDataPKCS7@CryptManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBU_CERT_CONTEXT@@PEAU_CRYPTOAPI_BLOB@@1@Z`
- size: `711`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::CryptManager *__hidden this, const struct _CERT_CONTEXT *, struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14004ce70`

## callees

- `0x14000b0f4`
- `0x14000e610`
- `0x140010f18`
- `0x140013404`
- `0x1400134a4`
- `0x14004cfa4`
- `0x14004d364`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004d586`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004d586`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004d4e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004d4e6`
- `CRYPT32!CertCompareCertificate` at `0x14004d5a5`
- `CRYPT32!CertCompareCertificate` at `0x14004d5a5`
- `CRYPT32!CryptVerifyMessageSignature` at `0x14004d4a0`
- `CRYPT32!CryptVerifyMessageSignature` at `0x14004d547`
- `CRYPT32!CryptVerifyMessageSignature` at `0x14004d4a0`
- `CRYPT32!CryptVerifyMessageSignature` at `0x14004d547`
- `CRYPT32!CertFreeCertificateContext` at `0x14004d5c6`
- `CRYPT32!CertFreeCertificateContext` at `0x14004d5eb`
- `CRYPT32!CertFreeCertificateContext` at `0x14004d5c6`
- `CRYPT32!CertFreeCertificateContext` at `0x14004d5eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::CryptManager::VerifySignedDataPKCS7(
        Microsoft::Windows::MDM::OmadmClient::CryptManager *this,
        const struct _CERT_CONTEXT *a2,
        struct _CRYPTOAPI_BLOB *a3,
        struct _CRYPTOAPI_BLOB *a4)
{
  struct COmaDmLogger *Logger; // rax
  __int64 v8; // rcx
  signed int v9; // edi
  unsigned int v10; // r8d
  signed int LastError; // eax
  HLOCAL v12; // rbx
  signed int v13; // eax
  BOOL v14; // eax
  const CERT_CONTEXT *v15; // rcx
  int pbDecoded; // [rsp+28h] [rbp-49h]
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-29h] BYREF
  __int64 v19; // [rsp+50h] [rbp-21h] BYREF
  _CRYPT_VERIFY_MESSAGE_PARA pVerifyPara; // [rsp+58h] [rbp-19h] BYREF
  _QWORD v21[3]; // [rsp+78h] [rbp+7h] BYREF
  int v22; // [rsp+90h] [rbp+1Fh]
  int *v23; // [rsp+98h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  int v25; // [rsp+D8h] [rbp+67h] BYREF
  int v26; // [rsp+DCh] [rbp+6Bh]
  DWORD pcbDecoded; // [rsp+E8h] [rbp+77h] BYREF
  __int16 v28; // [rsp+ECh] [rbp+7Bh]

  v26 = HIDWORD(this);
  v25 = 0;
  pCertContext = 0;
  Logger = COmaDmLogger::GetLogger();
  Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Logger, 2, "VerifySignedDataPKCS7", 0);
  v21[0] = 0;
  v21[1] = "VerifySignedDataPKCS7";
  v21[2] = COmaDmLogger::GetLogger();
  v22 = 2;
  v23 = &v25;
  if ( !a3 )
  {
    v9 = -805306128;
LABEL_5:
    v25 = v9;
    goto LABEL_29;
  }
  if ( !a4 )
  {
    v9 = -805306127;
    goto LABEL_5;
  }
  a4->cbData = 0;
  a4->pbData = 0;
  pVerifyPara.cbSize = 32;
  pVerifyPara.dwMsgAndCertEncodingType = 65537;
  memset(&pVerifyPara.hCryptProv, 0, 24);
  v10 = *(_DWORD *)Feature_Servicing_OmadmclientCertCompare__descriptor;
  if ( (*(_DWORD *)Feature_Servicing_OmadmclientCertCompare__descriptor & 4) == 0 )
  {
    v19 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmclientCertCompare>::GetCachedFeatureEnabledState(
                       v8,
                       &v19);
    v10 = v19;
  }
  pcbDecoded = 0;
  v28 = 3;
  wil::details::ReportUsageToService(&qword_140085288, 51546953, (v10 >> 10) & 1, (v10 >> 11) & 1);
  pcbDecoded = 0;
  if ( !CryptVerifyMessageSignature(&pVerifyPara, 0, a3->pbData, a3->cbData, 0, &pcbDecoded, &pCertContext) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v25 = v9;
    if ( v9 < 0 )
    {
      LODWORD(v21[0]) = 12073;
      HIDWORD(v21[0]) = v9;
      goto LABEL_29;
    }
  }
  v12 = LocalAlloc(0, pcbDecoded);
  if ( !v12 )
  {
    v9 = -2147024882;
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\cryptmanager.cpp",
      (const char *)0x8007000ELL,
      pbDecoded);
    goto LABEL_29;
  }
  v25 = 0;
  if ( !CryptVerifyMessageSignature(&pVerifyPara, 0, a3->pbData, a3->cbData, (BYTE *)v12, &pcbDecoded, &pCertContext) )
  {
    v13 = GetLastError();
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    v25 = v9;
    if ( v9 < 0 )
    {
      LODWORD(v21[0]) = 12074;
LABEL_20:
      HIDWORD(v21[0]) = v9;
      LocalFree(v12);
      goto LABEL_29;
    }
  }
  v14 = CertCompareCertificate(0x10001u, a2->pCertInfo, pCertContext->pCertInfo);
  v15 = pCertContext;
  if ( !v14 )
  {
    v9 = -2146762485;
    v25 = -2146762485;
    if ( pCertContext )
    {
      CertFreeCertificateContext(pCertContext);
      v9 = v25;
      v15 = pCertContext;
    }
    if ( v9 < 0 )
    {
      LODWORD(v21[0]) = 12084;
      goto LABEL_20;
    }
  }
  if ( v15 )
    CertFreeCertificateContext(v15);
  a4->pbData = (BYTE *)v12;
  a4->cbData = pcbDecoded;
  v9 = 0;
LABEL_29:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004d364  mov     rax, rsp
0x14004d367  mov     [rax+10h], rbx
0x14004d36b  mov     [rax+20h], rsi
0x14004d36f  mov     [rax+8], rcx
0x14004d373  push    rbp
0x14004d374  push    rdi
0x14004d375  push    r12
0x14004d377  push    r14
0x14004d379  push    r15
0x14004d37b  lea     rbp, [rax-5Fh]
0x14004d37f  sub     rsp, 0A0h
0x14004d386  mov     rsi, r9
0x14004d389  mov     r14, r8
0x14004d38c  mov     r15, rdx
0x14004d38f  xor     r12d, r12d
0x14004d392  mov     [rbp+57h+arg_0], r12d
0x14004d396  mov     [rbp+57h+pCertContext], r12
0x14004d39a  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004d39f  xor     r9d, r9d
0x14004d3a2  lea     rbx, aVerifysignedda; "VerifySignedDataPKCS7"
0x14004d3a9  mov     r8, rbx
0x14004d3ac  lea     edi, [r12+2]
0x14004d3b1  mov     edx, edi
0x14004d3b3  mov     rcx, rax
0x14004d3b6  call    ?LogFunctionEntryMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@PEBDPEBGZZ; Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Microsoft::Windows::TracingLevel,char const *,ushort const *,...)
0x14004d3bb  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004d3c0  mov     [rbp+57h+var_50], r12
0x14004d3c4  mov     [rbp+57h+var_48], rbx
0x14004d3c8  mov     [rbp+57h+var_40], rax
0x14004d3cc  mov     [rbp+57h+var_38], edi
0x14004d3cf  lea     rax, [rbp+57h+arg_0]
0x14004d3d3  mov     [rbp+57h+var_30], rax
0x14004d3d7  test    r14, r14
0x14004d3da  jnz     short loc_14004D3E3
0x14004d3dc  mov     edi, 0D00000F0h
0x14004d3e1  jmp     short loc_14004D3ED
0x14004d3e3  test    rsi, rsi
0x14004d3e6  jnz     short loc_14004D3F5
0x14004d3e8  mov     edi, 0D00000F1h
0x14004d3ed  mov     [rbp+57h+arg_0], edi
0x14004d3f0  jmp     loc_14004D603
0x14004d3f5  mov     [rsi], r12d
0x14004d3f8  mov     [rsi+8], r12
0x14004d3fc  mov     [rbp+57h+pVerifyPara.cbSize], 20h ; ' '
0x14004d403  mov     [rbp+57h+pVerifyPara.dwMsgAndCertEncodingType], 10001h
0x14004d40a  mov     [rbp+57h+pVerifyPara.hCryptProv], r12
0x14004d40e  mov     [rbp+57h+pVerifyPara.pfnGetSignerCertificate], r12
0x14004d412  mov     [rbp+57h+pVerifyPara.pvGetArg], r12
0x14004d416  mov     rax, cs:Feature_Servicing_OmadmclientCertCompare__descriptor
0x14004d41d  mov     r8d, [rax]
0x14004d420  test    r8b, 4
0x14004d424  jnz     short loc_14004D439
0x14004d426  lea     rdx, [rbp+57h+var_78]
0x14004d42a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OmadmclientCertCompare@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmclientCertCompare>::GetCachedFeatureEnabledState(void)
0x14004d42f  mov     rcx, [rax]
0x14004d432  mov     [rbp+57h+var_78], rcx
0x14004d436  mov     r8d, ecx
0x14004d439  mov     [rbp+57h+arg_10], r12d
0x14004d43d  mov     [rbp+57h+arg_14], 3
0x14004d443  mov     r9d, r8d
0x14004d446  shr     r9d, 0Bh
0x14004d44a  and     r9d, 1
0x14004d44e  shr     r8d, 0Ah
0x14004d452  and     r8d, 1
0x14004d456  mov     dword ptr [rsp+0C0h+pcbDecoded], 1
0x14004d45e  lea     rax, [rbp+57h+arg_10]
0x14004d462  mov     [rsp+0C0h+pbDecoded], rax
0x14004d467  mov     edx, 3128B49h
0x14004d46c  lea     rcx, qword_140085288
0x14004d473  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14004d478  mov     [rbp+57h+arg_10], r12d
0x14004d47c  lea     rax, [rbp+57h+pCertContext]
0x14004d480  mov     [rsp+0C0h+ppSignerCert], rax; ppSignerCert
0x14004d485  lea     rax, [rbp+57h+arg_10]
0x14004d489  mov     [rsp+0C0h+pcbDecoded], rax; pcbDecoded
0x14004d48e  mov     [rsp+0C0h+pbDecoded], r12; int
0x14004d493  mov     r9d, [r14]; cbSignedBlob
0x14004d496  mov     r8, [r14+8]; pbSignedBlob
0x14004d49a  xor     edx, edx; dwSignerIndex
0x14004d49c  lea     rcx, [rbp+57h+pVerifyPara]; pVerifyPara
0x14004d4a0  call    cs:__imp_CryptVerifyMessageSignature
0x14004d4a7  nop     dword ptr [rax+rax+00h]
0x14004d4ac  test    eax, eax
0x14004d4ae  jnz     short loc_14004D4E1
0x14004d4b0  call    cs:__imp_GetLastError
0x14004d4b7  nop     dword ptr [rax+rax+00h]
0x14004d4bc  mov     edi, eax
0x14004d4be  test    eax, eax
0x14004d4c0  jle     short loc_14004D4CB
0x14004d4c2  movzx   edi, ax
0x14004d4c5  or      edi, 80070000h
0x14004d4cb  mov     [rbp+57h+arg_0], edi
0x14004d4ce  test    edi, edi
0x14004d4d0  jns     short loc_14004D4E1
0x14004d4d2  mov     dword ptr [rbp+57h+var_50], 2F29h
0x14004d4d9  mov     dword ptr [rbp+57h+var_50+4], edi
0x14004d4dc  jmp     loc_14004D603
0x14004d4e1  mov     edx, [rbp+57h+arg_10]; uBytes
0x14004d4e4  xor     ecx, ecx; uFlags
0x14004d4e6  call    cs:__imp_LocalAlloc
0x14004d4ed  nop     dword ptr [rax+rax+00h]
0x14004d4f2  mov     rbx, rax
0x14004d4f5  test    rax, rax
0x14004d4f8  jnz     short loc_14004D51F
0x14004d4fa  mov     edi, 8007000Eh
0x14004d4ff  mov     [rbp+57h+arg_0], edi
0x14004d502  mov     rcx, [rbp+5Fh]; this
0x14004d506  mov     r9d, edi; char *
0x14004d509  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004d510  mov     edx, 105h; void *
0x14004d515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004d51a  jmp     loc_14004D603
0x14004d51f  mov     [rbp+57h+arg_0], r12d
0x14004d523  lea     rax, [rbp+57h+pCertContext]
0x14004d527  mov     [rsp+0C0h+ppSignerCert], rax; ppSignerCert
0x14004d52c  lea     rax, [rbp+57h+arg_10]
0x14004d530  mov     [rsp+0C0h+pcbDecoded], rax; pcbDecoded
0x14004d535  mov     [rsp+0C0h+pbDecoded], rbx; pbDecoded
0x14004d53a  mov     r9d, [r14]; cbSignedBlob
0x14004d53d  mov     r8, [r14+8]; pbSignedBlob
0x14004d541  xor     edx, edx; dwSignerIndex
0x14004d543  lea     rcx, [rbp+57h+pVerifyPara]; pVerifyPara
0x14004d547  call    cs:__imp_CryptVerifyMessageSignature
0x14004d54e  nop     dword ptr [rax+rax+00h]
0x14004d553  test    eax, eax
0x14004d555  jnz     short loc_14004D594
0x14004d557  call    cs:__imp_GetLastError
0x14004d55e  nop     dword ptr [rax+rax+00h]
0x14004d563  mov     edi, eax
0x14004d565  test    eax, eax
0x14004d567  jle     short loc_14004D572
0x14004d569  movzx   edi, ax
0x14004d56c  or      edi, 80070000h
0x14004d572  mov     [rbp+57h+arg_0], edi
0x14004d575  test    edi, edi
0x14004d577  jns     short loc_14004D594
0x14004d579  mov     dword ptr [rbp+57h+var_50], 2F2Ah
0x14004d580  mov     dword ptr [rbp+57h+var_50+4], edi
0x14004d583  mov     rcx, rbx; hMem
0x14004d586  call    cs:__imp_LocalFree
0x14004d58d  nop     dword ptr [rax+rax+00h]
0x14004d592  jmp     short loc_14004D603
0x14004d594  mov     r8, [rbp+57h+pCertContext]
0x14004d598  mov     r8, [r8+18h]; pCertId2
0x14004d59c  mov     rdx, [r15+18h]; pCertId1
0x14004d5a0  mov     ecx, 10001h; dwCertEncodingType
0x14004d5a5  call    cs:__imp_CertCompareCertificate
0x14004d5ac  nop     dword ptr [rax+rax+00h]
0x14004d5b1  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x14004d5b5  test    eax, eax
0x14004d5b7  jnz     short loc_14004D5E6
0x14004d5b9  mov     edi, 800B010Bh
0x14004d5be  mov     [rbp+57h+arg_0], edi
0x14004d5c1  test    rcx, rcx
0x14004d5c4  jz      short loc_14004D5D9
0x14004d5c6  call    cs:__imp_CertFreeCertificateContext
0x14004d5cd  nop     dword ptr [rax+rax+00h]
0x14004d5d2  mov     edi, [rbp+57h+arg_0]
0x14004d5d5  mov     rcx, [rbp+57h+pCertContext]
0x14004d5d9  test    edi, edi
0x14004d5db  jns     short loc_14004D5E6
0x14004d5dd  mov     dword ptr [rbp+57h+var_50], 2F34h
0x14004d5e4  jmp     short loc_14004D580
0x14004d5e6  test    rcx, rcx
0x14004d5e9  jz      short loc_14004D5F7
0x14004d5eb  call    cs:__imp_CertFreeCertificateContext
0x14004d5f2  nop     dword ptr [rax+rax+00h]
0x14004d5f7  mov     [rsi+8], rbx
0x14004d5fb  mov     eax, [rbp+57h+arg_10]
0x14004d5fe  mov     [rsi], eax
0x14004d600  mov     edi, r12d
0x14004d603  lea     rcx, [rbp+57h+var_50]; this
0x14004d607  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004d60c  mov     eax, edi
0x14004d60e  lea     r11, [rsp+0C0h+var_20]
0x14004d616  mov     rbx, [r11+38h]
0x14004d61a  mov     rsi, [r11+48h]
0x14004d61e  mov     rsp, r11
0x14004d621  pop     r15
0x14004d623  pop     r14
0x14004d625  pop     r12
0x14004d627  pop     rdi
0x14004d628  pop     rbp
0x14004d629  retn
```
