# I_GetOcspSignerCert

- ea: `0x18000ddb0`
- end: `0x18000e25b`
- name: `I_GetOcspSignerCert`
- size: `1195`
- prototype: `PCCERT_CONTEXT __fastcall(struct _CERT_CONTEXT *pvIssuer, _QWORD *pvSubject, unsigned int, struct _CRYPTOAPI_BLOB *, __int64, struct _CERT_REVOCATION_CHAIN_PARA *, char, struct _OCSP_STRONG_SIGN_PROP_INFO *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000dab0`

## callees

- `0x18000ddb0`
- `0x18000e264`
- `0x18000e344`
- `0x18000e400`
- `0x18000e4ac`
- `0x18000ef28`
- `0x180010b38`
- `0x1800249b8`
- `0x180026546`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dee6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e11a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e192`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dee6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e11a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e125`
- `CRYPT32!I_CertChainEngineIsDisallowedCertificate` at `0x18000dff6`
- `CRYPT32!I_CertChainEngineIsDisallowedCertificate` at `0x18000dff6`
- `CRYPT32!I_CertDiagControl` at `0x18000e182`
- `CRYPT32!I_CertDiagControl` at `0x18000e250`
- `CRYPT32!I_CertDiagControl` at `0x18000e182`
- `CRYPT32!I_CertDiagControl` at `0x18000e250`
- `CRYPT32!CertCloseStore` at `0x18000e009`
- `CRYPT32!CertCloseStore` at `0x18000e009`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000e067`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000e067`
- `CRYPT32!CertOpenStore` at `0x18000dea4`
- `CRYPT32!CertOpenStore` at `0x18000dea4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000df3e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000e0fe`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000df3e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000e0fe`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000df2d`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000df2d`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x18000dfd4`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x18000e056`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x18000e1f4`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x18000dfd4`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x18000e056`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x18000e1f4`
- `CRYPT32!CryptHashCertificate` at `0x18000de5d`
- `CRYPT32!CryptHashCertificate` at `0x18000de5d`

## pseudocode

```c
PCCERT_CONTEXT __fastcall I_GetOcspSignerCert(
        struct _CERT_CONTEXT *pvIssuer,
        _QWORD *pvSubject,
        unsigned int a3,
        struct _CRYPTOAPI_BLOB *a4,
        __int64 a5,
        struct _CERT_REVOCATION_CHAIN_PARA *a6,
        char a7,
        struct _OCSP_STRONG_SIGN_PROP_INFO *a8,
        unsigned int a9)
{
  CERT_CONTEXT *v10; // rbx
  PCERT_INFO v13; // r9
  BYTE *pbData; // rdx
  DWORD cbData; // eax
  __int64 v16; // r14
  unsigned int v17; // esi
  HCERTSTORE v18; // rdi
  int v19; // edi
  const wchar_t *v20; // rsi
  struct _OCSP_STRONG_SIGN_PROP_INFO *pvExtra; // rsi
  unsigned int v22; // r14d
  HCERTCHAINENGINE hChainEngine; // rcx
  PCERT_INFO pCertInfo; // rax
  DWORD LastError; // eax
  const wchar_t *v27; // rdx
  DWORD v28; // edi
  int v29; // [rsp+40h] [rbp-89h]
  DWORD v30; // [rsp+44h] [rbp-85h]
  DWORD pcbComputedHash[4]; // [rsp+48h] [rbp-81h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-71h]
  struct _CERT_REVOCATION_CHAIN_PARA *v33; // [rsp+60h] [rbp-69h]
  __int64 v34; // [rsp+68h] [rbp-61h]
  __int64 v35; // [rsp+70h] [rbp-59h] BYREF
  DWORD v36; // [rsp+78h] [rbp-51h]
  int v37; // [rsp+7Ch] [rbp-4Dh]
  const wchar_t *v38; // [rsp+80h] [rbp-49h]
  __int128 v39; // [rsp+88h] [rbp-41h]
  __int128 v40; // [rsp+98h] [rbp-31h]
  struct _OCSP_STRONG_SIGN_PROP_INFO *v41; // [rsp+A8h] [rbp-21h]
  BYTE pbComputedHash[24]; // [rsp+B0h] [rbp-19h] BYREF

  v10 = 0;
  v32 = a3;
  v34 = a5;
  v33 = a6;
  v41 = a8;
  *(_OWORD *)pcbComputedHash = 0;
  if ( a3 == 1 )
  {
    pCertInfo = pvIssuer->pCertInfo;
    pbData = pCertInfo->Subject.pbData;
    *(_QWORD *)&pcbComputedHash[2] = pbData;
    cbData = pCertInfo->Subject.cbData;
    pcbComputedHash[0] = cbData;
    goto LABEL_5;
  }
  if ( a3 != 2 )
  {
    SetLastError(0xDu);
    goto LABEL_7;
  }
  v13 = pvIssuer->pCertInfo;
  *(_QWORD *)&pcbComputedHash[2] = pbComputedHash;
  pcbComputedHash[0] = 20;
  if ( !CryptHashCertificate(
          0,
          0x8004u,
          0,
          v13->SubjectPublicKeyInfo.PublicKey.pbData,
          v13->SubjectPublicKeyInfo.PublicKey.cbData,
          pbComputedHash,
          pcbComputedHash) )
  {
LABEL_7:
    v16 = pvSubject[9];
    v17 = *((_DWORD *)pvSubject + 16);
    v18 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
    if ( !v18 )
      goto LABEL_8;
    v29 = 0;
    *(_QWORD *)pcbComputedHash = 0;
    v30 = 0;
    if ( v17 )
    {
      do
      {
        CertAddEncodedCertificateToStore(
          v18,
          1u,
          *(const BYTE **)(v16 + 16LL * (unsigned int)v10 + 8),
          *(_DWORD *)(v16 + 16LL * (unsigned int)v10),
          4u,
          0);
        LODWORD(v10) = (_DWORD)v10 + 1;
      }
      while ( (unsigned int)v10 < v17 );
    }
    v10 = (CERT_CONTEXT *)CertEnumCertificatesInStore(v18, 0);
    if ( !v10 )
    {
LABEL_24:
      CertCloseStore(v18, 0);
      if ( v10 )
        return v10;
      if ( v29 )
      {
        v19 = v30;
        v20 = *(const wchar_t **)pcbComputedHash;
        goto LABEL_9;
      }
LABEL_8:
      v19 = -2146885628;
      v20 = L"GetOcspSignerCertificate";
      CertDiagRejectOcsp(v34, L"GetOcspSignerCertificate", 2148081668LL, 0);
LABEL_9:
      if ( (a9 & 1) != 0 )
      {
        v35 = 5;
        v37 = 0;
        v36 = v19;
        v38 = v20;
        v39 = 0;
        v40 = 0;
        I_CertDiagControl(24, &v35, 0);
      }
      SetLastError(0x80092004);
      return v10;
    }
    pvExtra = v41;
    v22 = v32;
    while ( !(unsigned int)I_IsOcspSignerCert(v10, v22, a4) )
    {
LABEL_35:
      v10 = (CERT_CONTEXT *)CertEnumCertificatesInStore(v18, v10);
      if ( !v10 )
        goto LABEL_24;
    }
    if ( (unsigned int)I_IsOcspPotentialSignerCert(v10, a9) )
    {
      if ( (unsigned int)I_IsOcspDelegatedSignerCert(v10, pvIssuer, pvExtra) )
      {
        if ( I_HasNoRevocationChecking(v10) )
        {
          if ( CryptVerifyCertificateSignatureEx(0, 1u, 4u, pvSubject, 2u, v10, 4u, pvExtra) )
          {
            if ( v33 )
              hChainEngine = v33->hChainEngine;
            else
              hChainEngine = 0;
            if ( !(unsigned int)I_CertChainEngineIsDisallowedCertificate(hChainEngine, v10) )
              goto LABEL_24;
            SetLastError(0x800B0111);
          }
          goto LABEL_32;
        }
        v27 = L"HasRevocationChecking";
LABEL_47:
        LastError = 50;
        v29 = 1;
LABEL_34:
        v30 = LastError;
        *(_QWORD *)pcbComputedHash = v27;
        CertDiagRejectOcsp(v34, v27, LastError, v10);
        goto LABEL_35;
      }
      if ( v33 && (unsigned int)I_IsOcspIndependentSignerCert(v10, v18, v33, a7, pvExtra) )
      {
        if ( CryptVerifyCertificateSignatureEx(0, 1u, 4u, pvSubject, 2u, v10, 4u, pvExtra) )
          goto LABEL_24;
LABEL_32:
        v29 = 1;
        OcspFreeStrongSignPropInfo(pvExtra);
        LastError = GetLastError();
        v27 = L"IsResponseSignatureValid";
        if ( !LastError )
          LastError = -2147418113;
        goto LABEL_34;
      }
    }
    v27 = L"GetOcspSignerCertificate";
    goto LABEL_47;
  }
  pbData = *(BYTE **)&pcbComputedHash[2];
  cbData = pcbComputedHash[0];
LABEL_5:
  if ( a4->cbData != cbData || memcmp_0(a4->pbData, pbData, cbData) )
    goto LABEL_7;
  if ( CryptVerifyCertificateSignatureEx(0, 1u, 4u, pvSubject, 2u, pvIssuer, 4u, a8) )
    return CertDuplicateCertificateContext(pvIssuer);
  v28 = GetLastError();
  CertDiagRejectOcsp(a5, L"IsResponseSignatureValid", v28, 0);
  if ( (a9 & 1) != 0 )
  {
    v35 = 5;
    v37 = 0;
    v36 = v28;
    v38 = L"IsResponseSignatureValid";
    v39 = 0;
    v40 = 0;
    I_CertDiagControl(24, &v35, 0);
  }
  return v10;
}

```

## disassembly

```asm
0x18000ddb0  mov     [rsp-8+arg_10], rbx
0x18000ddb5  push    rbp
0x18000ddb6  push    rsi
0x18000ddb7  push    rdi
0x18000ddb8  push    r12
0x18000ddba  push    r13
0x18000ddbc  push    r14
0x18000ddbe  push    r15
0x18000ddc0  lea     rbp, [rsp-7]
0x18000ddc5  sub     rsp, 0D0h
0x18000ddcc  mov     rax, cs:__security_cookie
0x18000ddd3  xor     rax, rsp
0x18000ddd6  mov     [rbp+37h+var_38], rax
0x18000ddda  mov     r14, [rbp+37h+arg_20]
0x18000ddde  mov     eax, r8d
0x18000dde1  mov     rdi, [rbp+37h+arg_38]
0x18000dde5  mov     r15, rcx
0x18000dde8  mov     rcx, [rbp+37h+arg_28]
0x18000ddec  xor     ebx, ebx
0x18000ddee  mov     [rbp+37h+var_A8], eax
0x18000ddf1  xorps   xmm0, xmm0
0x18000ddf4  mov     [rbp+37h+var_98], r14
0x18000ddf8  mov     r12, r9
0x18000ddfb  mov     [rbp+37h+var_A0], rcx
0x18000ddff  mov     r13, rdx
0x18000de02  mov     [rbp+37h+var_58], rdi
0x18000de06  movups  xmmword ptr [rsp+100h+var_B8], xmm0
0x18000de0b  sub     eax, 1
0x18000de0e  jz      loc_18000E09A
0x18000de14  cmp     eax, 1
0x18000de17  jnz     loc_18000E115
0x18000de1d  mov     r9, [r15+18h]
0x18000de21  lea     rax, [rbp+37h+var_50]
0x18000de25  mov     qword ptr [rbp+37h+var_B8+8], rax
0x18000de29  xor     r8d, r8d; dwFlags
0x18000de2c  mov     [rsp+100h+var_B8], 14h
0x18000de34  lea     rax, [rsp+100h+var_B8]
0x18000de39  mov     [rsp+100h+pcbComputedHash], rax; pcbComputedHash
0x18000de3e  mov     edx, 8004h; Algid
0x18000de43  lea     rax, [rbp+37h+var_50]
0x18000de47  xor     ecx, ecx; hCryptProv
0x18000de49  mov     [rsp+100h+pbComputedHash], rax; pbComputedHash
0x18000de4e  mov     eax, [r9+78h]
0x18000de52  mov     r9, [r9+80h]; pbEncoded
0x18000de59  mov     [rsp+100h+cbEncoded], eax; cbEncoded
0x18000de5d  call    cs:__imp_CryptHashCertificate
0x18000de63  test    eax, eax
0x18000de65  jz      short loc_18000DE8A
0x18000de67  mov     rdx, qword ptr [rbp+37h+var_B8+8]; Buf2
0x18000de6b  mov     eax, [rsp+100h+var_B8]
0x18000de6f  cmp     [r12], eax
0x18000de73  jnz     short loc_18000DE8A
0x18000de75  mov     rcx, [r12+8]; Buf1
0x18000de7a  mov     r8d, eax; Size
0x18000de7d  call    memcmp_0
0x18000de82  test    eax, eax
0x18000de84  jz      loc_18000E02C
0x18000de8a  mov     r14, [r13+48h]
0x18000de8e  xor     r9d, r9d; dwFlags
0x18000de91  mov     esi, [r13+40h]
0x18000de95  xor     r8d, r8d; hCryptProv
0x18000de98  xor     edx, edx; dwEncodingType
0x18000de9a  mov     qword ptr [rsp+100h+cbEncoded], rbx; pvPara
0x18000de9f  mov     ecx, 2; lpszStoreProvider
0x18000dea4  call    cs:__imp_CertOpenStore
0x18000deaa  mov     rdi, rax
0x18000dead  test    rax, rax
0x18000deb0  jnz     short loc_18000DEF1
0x18000deb2  mov     rcx, [rbp+37h+var_98]
0x18000deb6  lea     rdx, aGetocspsignerc; "GetOcspSignerCertificate"
0x18000debd  mov     edi, 80092004h
0x18000dec2  lea     rsi, aGetocspsignerc; "GetOcspSignerCertificate"
0x18000dec9  mov     r8d, edi
0x18000decc  xor     r9d, r9d
0x18000decf  call    CertDiagRejectOcsp
0x18000ded4  test    byte ptr [rbp+37h+arg_40], 1
0x18000dedb  jnz     loc_18000E220
0x18000dee1  mov     ecx, 80092004h; dwErrCode
0x18000dee6  call    cs:__imp_SetLastError
0x18000deec  jmp     loc_18000E070
0x18000def1  xor     edx, edx
0x18000def3  mov     [rsp+100h+var_C0], ebx
0x18000def7  xor     eax, eax
0x18000def9  mov     qword ptr [rsp+100h+var_B8], rdx
0x18000defe  mov     [rsp+100h+var_BC], eax
0x18000df02  test    esi, esi
0x18000df04  jz      short loc_18000DF39
0x18000df06  mov     eax, ebx
0x18000df08  mov     edx, 1; dwCertEncodingType
0x18000df0d  add     rax, rax
0x18000df10  mov     [rsp+100h+pbComputedHash], 0; ppCertContext
0x18000df19  mov     rcx, rdi; hCertStore
0x18000df1c  mov     [rsp+100h+cbEncoded], 4; dwAddDisposition
0x18000df24  mov     r9d, [r14+rax*8]; cbCertEncoded
0x18000df28  mov     r8, [r14+rax*8+8]; pbCertEncoded
0x18000df2d  call    cs:__imp_CertAddEncodedCertificateToStore
0x18000df33  inc     ebx
0x18000df35  cmp     ebx, esi
0x18000df37  jb      short loc_18000DF06
0x18000df39  xor     edx, edx; pPrevCertContext
0x18000df3b  mov     rcx, rdi; hCertStore
0x18000df3e  call    cs:__imp_CertEnumCertificatesInStore
0x18000df44  mov     rbx, rax
0x18000df47  test    rax, rax
0x18000df4a  jz      loc_18000E004
0x18000df50  mov     rsi, [rbp+37h+var_58]
0x18000df54  mov     r14d, [rbp+37h+var_A8]
0x18000df58  mov     r8, r12; struct _CRYPTOAPI_BLOB *
0x18000df5b  mov     edx, r14d; unsigned int
0x18000df5e  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18000df61  call    ?I_IsOcspSignerCert@@YAHPEBU_CERT_CONTEXT@@KPEAU_CRYPTOAPI_BLOB@@@Z; I_IsOcspSignerCert(_CERT_CONTEXT const *,ulong,_CRYPTOAPI_BLOB *)
0x18000df66  test    eax, eax
0x18000df68  jz      loc_18000E0F8
0x18000df6e  mov     edx, [rbp+37h+arg_40]
0x18000df74  mov     rcx, rbx
0x18000df77  call    I_IsOcspPotentialSignerCert
0x18000df7c  test    eax, eax
0x18000df7e  jz      loc_18000E207
0x18000df84  mov     r8, rsi; struct _OCSP_STRONG_SIGN_PROP_INFO *
0x18000df87  mov     rdx, r15; pvIssuer
0x18000df8a  mov     rcx, rbx; pCertContext
0x18000df8d  call    ?I_IsOcspDelegatedSignerCert@@YAHPEBU_CERT_CONTEXT@@0PEAU_OCSP_STRONG_SIGN_PROP_INFO@@@Z; I_IsOcspDelegatedSignerCert(_CERT_CONTEXT const *,_CERT_CONTEXT const *,_OCSP_STRONG_SIGN_PROP_INFO *)
0x18000df92  test    eax, eax
0x18000df94  jz      loc_18000E1A6
0x18000df9a  mov     rcx, rbx; pvPara
0x18000df9d  call    ?I_HasNoRevocationChecking@@YAHPEBU_CERT_CONTEXT@@@Z; I_HasNoRevocationChecking(_CERT_CONTEXT const *)
0x18000dfa2  test    eax, eax
0x18000dfa4  jz      loc_18000E19D
0x18000dfaa  mov     [rsp+100h+pvExtra], rsi; pvExtra
0x18000dfaf  mov     r9, r13; pvSubject
0x18000dfb2  mov     dword ptr [rsp+100h+pcbComputedHash], 4; dwFlags
0x18000dfba  mov     edx, 1; dwCertEncodingType
0x18000dfbf  mov     [rsp+100h+pbComputedHash], rbx; pvIssuer
0x18000dfc4  xor     ecx, ecx; hCryptProv
0x18000dfc6  mov     r8d, 4; dwSubjectType
0x18000dfcc  mov     [rsp+100h+cbEncoded], 2; dwIssuerType
0x18000dfd4  call    cs:__imp_CryptVerifyCertificateSignatureEx
0x18000dfda  test    eax, eax
0x18000dfdc  jz      loc_18000E0B9
0x18000dfe2  mov     rax, [rbp+37h+var_A0]
0x18000dfe6  test    rax, rax
0x18000dfe9  jz      loc_18000E0B2
0x18000dfef  mov     rcx, [rax+8]
0x18000dff3  mov     rdx, rbx
0x18000dff6  call    cs:__imp_I_CertChainEngineIsDisallowedCertificate
0x18000dffc  test    eax, eax
0x18000dffe  jnz     loc_18000E18D
0x18000e004  xor     edx, edx; dwFlags
0x18000e006  mov     rcx, rdi; hCertStore
0x18000e009  call    cs:__imp_CertCloseStore
0x18000e00f  test    rbx, rbx
0x18000e012  jnz     short loc_18000E070
0x18000e014  cmp     [rsp+100h+var_C0], ebx
0x18000e018  jz      loc_18000DEB2
0x18000e01e  mov     edi, [rsp+100h+var_BC]
0x18000e022  mov     rsi, qword ptr [rsp+100h+var_B8]
0x18000e027  jmp     loc_18000DED4
0x18000e02c  mov     [rsp+100h+pvExtra], rdi; pvExtra
0x18000e031  mov     r9, r13; pvSubject
0x18000e034  mov     dword ptr [rsp+100h+pcbComputedHash], 4; dwFlags
0x18000e03c  mov     edx, 1; dwCertEncodingType
0x18000e041  mov     [rsp+100h+pbComputedHash], r15; pvIssuer
0x18000e046  xor     ecx, ecx; hCryptProv
0x18000e048  mov     r8d, 4; dwSubjectType
0x18000e04e  mov     [rsp+100h+cbEncoded], 2; dwIssuerType
0x18000e056  call    cs:__imp_CryptVerifyCertificateSignatureEx
0x18000e05c  test    eax, eax
0x18000e05e  jz      loc_18000E125
0x18000e064  mov     rcx, r15; pCertContext
0x18000e067  call    cs:__imp_CertDuplicateCertificateContext
0x18000e06d  mov     rbx, rax
0x18000e070  mov     rax, rbx
0x18000e073  mov     rcx, [rbp+37h+var_38]
0x18000e077  xor     rcx, rsp; StackCookie
0x18000e07a  call    __security_check_cookie
0x18000e07f  mov     rbx, [rsp+100h+arg_10]
0x18000e087  add     rsp, 0D0h
0x18000e08e  pop     r15
0x18000e090  pop     r14
0x18000e092  pop     r13
0x18000e094  pop     r12
0x18000e096  pop     rdi
0x18000e097  pop     rsi
0x18000e098  pop     rbp
0x18000e099  retn
0x18000e09a  mov     rax, [r15+18h]
0x18000e09e  mov     rdx, [rax+58h]
0x18000e0a2  mov     qword ptr [rbp+37h+var_B8+8], rdx
0x18000e0a6  mov     eax, [rax+50h]
0x18000e0a9  mov     [rsp+100h+var_B8], eax
0x18000e0ad  jmp     loc_18000DE6F
0x18000e0b2  xor     ecx, ecx
0x18000e0b4  jmp     loc_18000DFF3
0x18000e0b9  mov     rcx, rsi; struct _OCSP_STRONG_SIGN_PROP_INFO *
0x18000e0bc  mov     [rsp+100h+var_C0], 1
0x18000e0c4  call    ?OcspFreeStrongSignPropInfo@@YAXPEAU_OCSP_STRONG_SIGN_PROP_INFO@@@Z; OcspFreeStrongSignPropInfo(_OCSP_STRONG_SIGN_PROP_INFO *)
0x18000e0c9  call    cs:__imp_GetLastError
0x18000e0cf  mov     ecx, 8000FFFFh
0x18000e0d4  lea     rdx, aIsresponsesign; "IsResponseSignatureValid"
0x18000e0db  test    eax, eax
0x18000e0dd  cmovz   eax, ecx
0x18000e0e0  mov     rcx, [rbp+37h+var_98]
0x18000e0e4  mov     r9, rbx
0x18000e0e7  mov     r8d, eax
0x18000e0ea  mov     [rsp+100h+var_BC], eax
0x18000e0ee  mov     qword ptr [rsp+100h+var_B8], rdx
0x18000e0f3  call    CertDiagRejectOcsp
0x18000e0f8  mov     rdx, rbx; pPrevCertContext
0x18000e0fb  mov     rcx, rdi; hCertStore
0x18000e0fe  call    cs:__imp_CertEnumCertificatesInStore
0x18000e104  mov     rbx, rax
0x18000e107  test    rax, rax
0x18000e10a  jz      loc_18000E004
0x18000e110  jmp     loc_18000DF58
0x18000e115  mov     ecx, 0Dh; dwErrCode
0x18000e11a  call    cs:__imp_SetLastError
0x18000e120  jmp     loc_18000DE8A
0x18000e125  call    cs:__imp_GetLastError
0x18000e12b  lea     rsi, aIsresponsesign; "IsResponseSignatureValid"
0x18000e132  xor     r9d, r9d
0x18000e135  mov     r8d, eax
0x18000e138  mov     rdx, rsi
0x18000e13b  mov     rcx, r14
0x18000e13e  mov     edi, eax
0x18000e140  call    CertDiagRejectOcsp
0x18000e145  test    byte ptr [rbp+37h+arg_40], 1
0x18000e14c  jz      loc_18000E070
0x18000e152  xor     eax, eax
0x18000e154  mov     [rbp+37h+var_90], 5
0x18000e15c  xorps   xmm0, xmm0
0x18000e15f  mov     [rbp+37h+var_84], eax
0x18000e162  xorps   xmm1, xmm1
0x18000e165  mov     [rbp+37h+var_88], edi
0x18000e168  xor     r8d, r8d
0x18000e16b  mov     [rbp+37h+var_80], rsi
0x18000e16f  lea     rdx, [rbp+37h+var_90]
0x18000e173  mov     ecx, 18h
0x18000e178  movdqu  [rbp+37h+var_78], xmm0
0x18000e17d  movdqu  [rbp+37h+var_68], xmm1
0x18000e182  call    cs:__imp_I_CertDiagControl
0x18000e188  jmp     loc_18000E070
0x18000e18d  mov     ecx, 800B0111h; dwErrCode
0x18000e192  call    cs:__imp_SetLastError
0x18000e198  jmp     loc_18000E0B9
0x18000e19d  lea     rdx, aHasrevocationc; "HasRevocationChecking"
0x18000e1a4  jmp     short loc_18000E20E
0x18000e1a6  mov     rax, [rbp+37h+var_A0]
0x18000e1aa  test    rax, rax
0x18000e1ad  jz      short loc_18000E207
0x18000e1af  mov     r9d, dword ptr [rbp+37h+arg_30]; unsigned int
0x18000e1b3  mov     r8, rax; struct _CERT_REVOCATION_CHAIN_PARA *
0x18000e1b6  mov     rdx, rdi; hCertStore
0x18000e1b9  mov     qword ptr [rsp+100h+cbEncoded], rsi; struct _OCSP_STRONG_SIGN_PROP_INFO *
0x18000e1be  mov     rcx, rbx; pCertContext
0x18000e1c1  call    ?I_IsOcspIndependentSignerCert@@YAHPEBU_CERT_CONTEXT@@PEAXPEAU_CERT_REVOCATION_CHAIN_PARA@@KPEAU_OCSP_STRONG_SIGN_PROP_INFO@@@Z; I_IsOcspIndependentSignerCert(_CERT_CONTEXT const *,void *,_CERT_REVOCATION_CHAIN_PARA *,ulong,_OCSP_STRONG_SIGN_PROP_INFO *)
0x18000e1c6  test    eax, eax
0x18000e1c8  jz      short loc_18000E207
0x18000e1ca  mov     [rsp+100h+pvExtra], rsi; pvExtra
0x18000e1cf  mov     r9, r13; pvSubject
0x18000e1d2  mov     dword ptr [rsp+100h+pcbComputedHash], 4; dwFlags
0x18000e1da  mov     edx, 1; dwCertEncodingType
0x18000e1df  mov     [rsp+100h+pbComputedHash], rbx; pvIssuer
0x18000e1e4  xor     ecx, ecx; hCryptProv
0x18000e1e6  mov     r8d, 4; dwSubjectType
0x18000e1ec  mov     [rsp+100h+cbEncoded], 2; dwIssuerType
0x18000e1f4  call    cs:__imp_CryptVerifyCertificateSignatureEx
0x18000e1fa  test    eax, eax
0x18000e1fc  jnz     loc_18000E004
0x18000e202  jmp     loc_18000E0B9
0x18000e207  lea     rdx, aGetocspsignerc; "GetOcspSignerCertificate"
0x18000e20e  mov     eax, 32h ; '2'
0x18000e213  mov     [rsp+100h+var_C0], 1
0x18000e21b  jmp     loc_18000E0E0
0x18000e220  xor     eax, eax
0x18000e222  mov     [rbp+37h+var_90], 5
0x18000e22a  xorps   xmm0, xmm0
0x18000e22d  mov     [rbp+37h+var_84], eax
0x18000e230  xorps   xmm1, xmm1
0x18000e233  mov     [rbp+37h+var_88], edi
0x18000e236  xor     r8d, r8d
0x18000e239  mov     [rbp+37h+var_80], rsi
0x18000e23d  lea     rdx, [rbp+37h+var_90]
0x18000e241  mov     ecx, 18h
0x18000e246  movdqu  [rbp+37h+var_78], xmm0
0x18000e24b  movdqu  [rbp+37h+var_68], xmm1
0x18000e250  call    cs:__imp_I_CertDiagControl
0x18000e256  jmp     loc_18000DEE1
```
