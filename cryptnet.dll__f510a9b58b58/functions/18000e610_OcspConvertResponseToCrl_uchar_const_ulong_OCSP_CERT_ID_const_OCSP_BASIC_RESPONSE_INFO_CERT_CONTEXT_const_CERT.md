# OcspConvertResponseToCrl(uchar const *,ulong,_OCSP_CERT_ID const *,_OCSP_BASIC_RESPONSE_INFO *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_OCSP_STRONG_SIGN_PROP_INFO *,ulong)

- ea: `0x18000e610`
- end: `0x18000ea8d`
- name: `?OcspConvertResponseToCrl@@YAPEBU_CRL_CONTEXT@@PEBEKPEBU_OCSP_CERT_ID@@PEAU_OCSP_BASIC_RESPONSE_INFO@@PEBU_CERT_CONTEXT@@3PEAU_OCSP_STRONG_SIGN_PROP_INFO@@K@Z`
- size: `1149`
- prototype: `const struct _CRL_CONTEXT *__fastcall(struct _OCSP_STRONG_SIGN_PROP_INFO *, unsigned int, const struct _OCSP_CERT_ID *, struct _OCSP_BASIC_RESPONSE_INFO *, PCCERT_CONTEXT pCertContext, const struct _CERT_CONTEXT *, struct _OCSP_STRONG_SIGN_PROP_INFO *, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ca20`
- `0x1800101e0`

## callees

- `0x18000a990`
- `0x18000e610`
- `0x18000eaa0`
- `0x18000ed20`
- `0x18000ef28`
- `0x18000f004`
- `0x18001abbc`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e8e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e8e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea58`
- `CRYPT32!CertFindExtension` at `0x18000e7b7`
- `CRYPT32!CertFindExtension` at `0x18000e7b7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000e76c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000e76c`
- `CRYPT32!CertCreateCRLContext` at `0x18000e861`
- `CRYPT32!CertCreateCRLContext` at `0x18000e861`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x18000e846`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x18000e846`
- `CRYPT32!CryptEncodeObjectEx` at `0x18000ea06`
- `CRYPT32!CryptEncodeObjectEx` at `0x18000ea06`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e709`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e8c0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e8d6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e709`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e8c0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000e8d6`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000e91e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000e91e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e7fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e7fe`

## pseudocode

```c
const struct _CRL_CONTEXT *__fastcall OcspConvertResponseToCrl(
        struct _OCSP_STRONG_SIGN_PROP_INFO *a1,
        unsigned int a2,
        const struct _OCSP_CERT_ID *a3,
        struct _OCSP_BASIC_RESPONSE_INFO *a4,
        PCCERT_CONTEXT pCertContext,
        const struct _CERT_CONTEXT *a6,
        struct _OCSP_STRONG_SIGN_PROP_INFO *a7,
        char a8)
{
  const CRL_CONTEXT *v9; // r14
  struct _OCSP_BASIC_RESPONSE_ENTRY *ResponseEntry; // rax
  struct _OCSP_BASIC_RESPONSE_ENTRY *v14; // rbx
  DWORD dwCertStatus; // eax
  FILETIME NextUpdate; // rax
  PCERT_EXTENSION Extension; // rax
  CRYPT_OBJID_BLOB Value; // xmm1
  DWORD v19; // r8d
  int v20; // ebx
  BYTE *v21; // rdi
  BYTE *pbEncoded; // rax
  const CRL_CONTEXT *CRLContext; // rax
  DWORD v25; // ecx
  const wchar_t *v26; // rbx
  const char *v27; // rdi
  POCSP_BASIC_REVOKED_INFO pRevokedInfo; // rcx
  CRYPT_INTEGER_BLOB SerialNumber; // xmm0
  int v30; // eax
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbCrlEncoded; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v33[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwCrlReasonCode; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL pvEncoded; // [rsp+70h] [rbp-90h] BYREF
  struct _OCSP_STRONG_SIGN_PROP_INFO *v36[2]; // [rsp+78h] [rbp-88h] BYREF
  CRYPT_INTEGER_BLOB v37; // [rsp+88h] [rbp-78h] BYREF
  __int128 v38; // [rsp+98h] [rbp-68h]
  __int128 *v39; // [rsp+A8h] [rbp-58h]
  int pvStructInfo; // [rsp+B0h] [rbp-50h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+B8h] [rbp-48h] BYREF
  CERT_NAME_BLOB Subject; // [rsp+D0h] [rbp-30h]
  FILETIME ThisUpdate; // [rsp+E0h] [rbp-20h] BYREF
  FILETIME FileTime1; // [rsp+E8h] [rbp-18h] BYREF
  int v45; // [rsp+F0h] [rbp-10h]
  CRYPT_INTEGER_BLOB *v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+100h] [rbp+0h]
  const char **v48; // [rsp+108h] [rbp+8h]
  __int128 v49; // [rsp+110h] [rbp+10h] BYREF
  __int128 v50; // [rsp+120h] [rbp+20h]
  const char *v51; // [rsp+130h] [rbp+30h] BYREF
  int v52; // [rsp+138h] [rbp+38h]
  unsigned int v53; // [rsp+140h] [rbp+40h]
  struct _OCSP_STRONG_SIGN_PROP_INFO *v54; // [rsp+148h] [rbp+48h]
  const char *v55; // [rsp+150h] [rbp+50h]
  int v56; // [rsp+158h] [rbp+58h]
  int v57; // [rsp+160h] [rbp+60h]
  _BYTE *v58; // [rsp+168h] [rbp+68h]
  __int128 v59; // [rsp+170h] [rbp+70h]
  CRYPT_OBJID_BLOB v60; // [rsp+180h] [rbp+80h]
  _BYTE pvData[32]; // [rsp+190h] [rbp+90h] BYREF

  v36[0] = a7;
  v9 = 0;
  pvEncoded = 0;
  v33[0] = 0;
  cbCrlEncoded = 0;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  memset_0(&pvStructInfo, 0, 0x60u);
  ResponseEntry = OcspFindResponseEntry(a3, a4);
  v14 = ResponseEntry;
  if ( !ResponseEntry )
  {
    v26 = L"FindResponseEntry";
    v27 = "FindResponseEntry";
LABEL_30:
    v36[0] = (struct _OCSP_STRONG_SIGN_PROP_INFO *)a2;
    v36[1] = a1;
    CertDiagRejectOcsp(v36, v26, 0, 0);
    I_OcspDebugErrorPrintfA(v27, pCertContext);
    goto LABEL_24;
  }
  dwCertStatus = ResponseEntry->dwCertStatus;
  if ( !dwCertStatus )
    goto LABEL_3;
  if ( dwCertStatus != 1 )
  {
    v26 = L"IsCertificateStatusValid";
    v27 = "InvalidCertStatus";
    SetLastError(0xDu);
    goto LABEL_30;
  }
  pRevokedInfo = v14->pRevokedInfo;
  v46 = &v37;
  v49 = 0;
  v38 = 0u;
  v50 = 0;
  SerialNumber = a3->SerialNumber;
  v45 = 1;
  v39 = &v49;
  v37 = SerialNumber;
  *(FILETIME *)&v38 = pRevokedInfo->RevocationDate;
  if ( pRevokedInfo->dwCrlReasonCode
    && (dwCrlReasonCode = pRevokedInfo->dwCrlReasonCode,
        CryptEncodeObjectEx(0x10001u, (LPCSTR)0x1D, &dwCrlReasonCode, 0x8000u, &PkiEncodePara, &pvEncoded, v33)) )
  {
    *(_QWORD *)&v49 = "2.5.29.21";
    LODWORD(v50) = v33[0];
    *((_QWORD *)&v50 + 1) = pvEncoded;
    v30 = 1;
  }
  else
  {
    v30 = 0;
  }
  DWORD2(v38) = v30;
LABEL_3:
  pvStructInfo = 1;
  pSignatureAlgorithm.pszObjId = "1.3.14.3.2.26";
  Subject = a6->pCertInfo->Subject;
  ThisUpdate = v14->ThisUpdate;
  if ( v14->NextUpdate )
    NextUpdate = v14->NextUpdate;
  else
    NextUpdate = (FILETIME)(*(_QWORD *)&ThisUpdate + 10000000LL * (unsigned int)I_GetOcspValiditySeconds());
  FileTime1 = NextUpdate;
  if ( (a8 & 4) != 0
    && (CompareFileTime(&ThisUpdate, &a6->pCertInfo->NotBefore) < 0
     || CompareFileTime(&FileTime1, &a6->pCertInfo->NotAfter) > 0) )
  {
    v25 = -2146762495;
LABEL_23:
    SetLastError(v25);
LABEL_24:
    v21 = 0;
    goto LABEL_19;
  }
  if ( CompareFileTime(&FileTime1, &a6->pCertInfo->NotAfter) > 0 )
    FileTime1 = a6->pCertInfo->NotAfter;
  v47 = 2;
  v48 = &v51;
  memset_0(&v51, 0, 0x60u);
  v52 = 1;
  v51 = "1.3.6.1.5.5.7.48.1.1";
  v54 = a1;
  v53 = a2;
  pcbData = 32;
  if ( !CertGetCertificateContextProperty(pCertContext, 0x6Bu, pvData, &pcbData) )
    goto LABEL_24;
  if ( pcbData != 32 )
  {
    v25 = 13;
    goto LABEL_23;
  }
  v56 = 1;
  v55 = "1.3.6.1.4.1.311.10.11.107";
  v57 = 32;
  v58 = pvData;
  Extension = CertFindExtension("1.3.6.1.4.1.311.21.4", v14->cExtension, v14->rgExtension);
  if ( Extension )
  {
    v59 = *(_OWORD *)&Extension->pszObjId;
    Value = Extension->Value;
    v47 = 3;
    v60 = Value;
  }
  v19 = a2 + 1000;
  v20 = 0;
  cbCrlEncoded = a2 + 1000;
  v21 = 0;
  while ( 1 )
  {
    if ( v21 )
      pbEncoded = (BYTE *)LocalReAlloc(v21, v19, 2u);
    else
      pbEncoded = (BYTE *)LocalAlloc(0, v19);
    if ( !pbEncoded )
    {
      SetLastError(0x8007000E);
      goto LABEL_19;
    }
    v21 = pbEncoded;
    if ( CryptSignAndEncodeCertificate(
           0,
           0,
           1u,
           (LPCSTR)3,
           &pvStructInfo,
           &pSignatureAlgorithm,
           0,
           pbEncoded,
           &cbCrlEncoded) )
    {
      break;
    }
    if ( GetLastError() != 234 || v20 )
      goto LABEL_19;
    v19 = cbCrlEncoded;
    v20 = 1;
  }
  CRLContext = CertCreateCRLContext(1u, v21, cbCrlEncoded);
  v9 = CRLContext;
  if ( CRLContext )
    OcspSetStrongSignProperties(CRLContext, v36[0]);
LABEL_19:
  operator delete(pvEncoded);
  operator delete(v21);
  return v9;
}

```

## disassembly

```asm
0x18000e610  push    rbp
0x18000e612  push    rbx
0x18000e613  push    rsi
0x18000e614  push    rdi
0x18000e615  push    r12
0x18000e617  push    r13
0x18000e619  push    r14
0x18000e61b  push    r15
0x18000e61d  lea     rbp, [rsp-0C8h]
0x18000e625  sub     rsp, 1C8h
0x18000e62c  mov     rax, cs:__security_cookie
0x18000e633  xor     rax, rsp
0x18000e636  mov     [rbp+100h+var_50], rax
0x18000e63d  mov     rax, [rbp+100h+arg_30]
0x18000e644  mov     r12, rcx
0x18000e647  mov     r13, [rbp+100h+pCertContext]
0x18000e64e  xor     ecx, ecx
0x18000e650  mov     rdi, [rbp+100h+arg_28]
0x18000e657  xorps   xmm0, xmm0
0x18000e65a  mov     [rsp+200h+var_188], rax
0x18000e65f  mov     r14d, ecx
0x18000e662  xor     eax, eax
0x18000e664  mov     [rsp+200h+pvEncoded], rcx
0x18000e669  mov     [rsp+200h+var_1A8], ecx
0x18000e66d  mov     r15, r8
0x18000e670  mov     [rsp+200h+cbCrlEncoded], ecx
0x18000e674  mov     esi, edx
0x18000e676  lea     rcx, [rbp+100h+var_150]; void *
0x18000e67a  mov     [rbp+100h+var_158], rax
0x18000e67e  xor     edx, edx; Val
0x18000e680  mov     r8d, 60h ; '`'; Size
0x18000e686  mov     rbx, r9
0x18000e689  movups  [rbp+100h+var_178], xmm0
0x18000e68d  movups  [rbp+100h+var_168], xmm0
0x18000e691  call    memset_0
0x18000e696  mov     rdx, rbx; struct _OCSP_BASIC_RESPONSE_INFO *
0x18000e699  mov     rcx, r15; struct _OCSP_CERT_ID *
0x18000e69c  call    ?OcspFindResponseEntry@@YAPEAU_OCSP_BASIC_RESPONSE_ENTRY@@PEBU_OCSP_CERT_ID@@PEAU_OCSP_BASIC_RESPONSE_INFO@@@Z; OcspFindResponseEntry(_OCSP_CERT_ID const *,_OCSP_BASIC_RESPONSE_INFO *)
0x18000e6a1  mov     rbx, rax
0x18000e6a4  test    rax, rax
0x18000e6a7  jz      loc_18000E929
0x18000e6ad  mov     eax, [rax+48h]
0x18000e6b0  test    eax, eax
0x18000e6b2  jnz     loc_18000E939
0x18000e6b8  mov     [rbp+100h+var_150], 1
0x18000e6bf  lea     rax, a13143226; "1.3.14.3.2.26"
0x18000e6c6  mov     [rbp+100h+var_148.pszObjId], rax
0x18000e6ca  mov     rax, [rdi+18h]
0x18000e6ce  movups  xmm0, xmmword ptr [rax+50h]
0x18000e6d2  movaps  [rbp+100h+var_130], xmm0
0x18000e6d6  mov     rax, [rbx+58h]
0x18000e6da  mov     qword ptr [rbp+100h+var_120.dwLowDateTime], rax
0x18000e6de  cmp     [rbx+60h], r14d
0x18000e6e2  jz      loc_18000E8F4
0x18000e6e8  mov     rax, [rbx+60h]
0x18000e6ec  test    byte ptr [rbp+100h+arg_38], 4
0x18000e6f3  mov     qword ptr [rbp+100h+FileTime1.dwLowDateTime], rax
0x18000e6f7  jnz     loc_18000E8B4
0x18000e6fd  mov     rdx, [rdi+18h]
0x18000e701  lea     rcx, [rbp+100h+FileTime1]; lpFileTime1
0x18000e705  add     rdx, 48h ; 'H'; lpFileTime2
0x18000e709  call    cs:__imp_CompareFileTime
0x18000e70f  test    eax, eax
0x18000e711  jg      loc_18000EA3D
0x18000e717  lea     rax, [rbp+100h+var_D0]
0x18000e71b  mov     [rbp+100h+var_100], 2
0x18000e722  xor     edx, edx; Val
0x18000e724  mov     [rbp+100h+var_F8], rax
0x18000e728  mov     r8d, 60h ; '`'; Size
0x18000e72e  lea     rcx, [rbp+100h+var_D0]; void *
0x18000e732  call    memset_0
0x18000e737  lea     rax, Str2; "1.3.6.1.5.5.7.48.1.1"
0x18000e73e  mov     [rbp+100h+var_C8], 1
0x18000e745  lea     r9, [rsp+200h+pcbData]; pcbData
0x18000e74a  mov     [rbp+100h+var_D0], rax
0x18000e74e  lea     r8, [rbp+100h+pvData]; pvData
0x18000e755  mov     [rbp+100h+var_B8], r12
0x18000e759  mov     edx, 6Bh ; 'k'; dwPropId
0x18000e75e  mov     [rbp+100h+var_C0], esi
0x18000e761  mov     rcx, r13; pCertContext
0x18000e764  mov     [rsp+200h+pcbData], 20h ; ' '
0x18000e76c  call    cs:__imp_CertGetCertificateContextProperty
0x18000e772  test    eax, eax
0x18000e774  jz      loc_18000E8EF
0x18000e77a  cmp     [rsp+200h+pcbData], 20h ; ' '
0x18000e77f  jnz     loc_18000EA4E
0x18000e785  mov     [rbp+100h+var_A8], 1
0x18000e78c  lea     rax, a13614131110111; "1.3.6.1.4.1.311.10.11.107"
0x18000e793  mov     [rbp+100h+var_B0], rax
0x18000e797  lea     rcx, a136141311214; "1.3.6.1.4.1.311.21.4"
0x18000e79e  mov     [rbp+100h+var_A0], 20h ; ' '
0x18000e7a5  lea     rax, [rbp+100h+pvData]
0x18000e7ac  mov     [rbp+100h+var_98], rax
0x18000e7b0  mov     r8, [rbx+70h]; rgExtensions
0x18000e7b4  mov     edx, [rbx+68h]; cExtensions
0x18000e7b7  call    cs:__imp_CertFindExtension
0x18000e7bd  test    rax, rax
0x18000e7c0  jz      short loc_18000E7DB
0x18000e7c2  movups  xmm0, xmmword ptr [rax]
0x18000e7c5  movaps  [rbp+100h+var_90], xmm0
0x18000e7c9  movups  xmm1, xmmword ptr [rax+10h]
0x18000e7cd  mov     [rbp+100h+var_100], 3
0x18000e7d4  movaps  [rbp+100h+var_80], xmm1
0x18000e7db  lea     r8d, [rsi+3E8h]
0x18000e7e2  xor     ebx, ebx
0x18000e7e4  mov     [rsp+200h+cbCrlEncoded], r8d
0x18000e7e9  mov     edi, ebx
0x18000e7eb  cmp     ebx, 2
0x18000e7ee  jnb     short loc_18000E859
0x18000e7f0  mov     edx, r8d; uBytes
0x18000e7f3  test    rdi, rdi
0x18000e7f6  jnz     loc_18000E915
0x18000e7fc  xor     ecx, ecx; uFlags
0x18000e7fe  call    cs:__imp_LocalAlloc
0x18000e804  test    rax, rax
0x18000e807  jz      loc_18000EA7D
0x18000e80d  mov     rdi, rax
0x18000e810  lea     rcx, [rsp+200h+cbCrlEncoded]
0x18000e815  mov     [rsp+200h+pcbEncoded], rcx; pcbEncoded
0x18000e81a  xor     edx, edx; dwKeySpec
0x18000e81c  mov     [rsp+200h+pbEncoded], rax; pbEncoded
0x18000e821  xor     ecx, ecx; hCryptProvOrNCryptKey
0x18000e823  lea     rax, [rbp+100h+var_148]
0x18000e827  mov     [rsp+200h+pvHashAuxInfo], r14; pvHashAuxInfo
0x18000e82c  mov     [rsp+200h+pSignatureAlgorithm], rax; pSignatureAlgorithm
0x18000e831  mov     r9d, 3; lpszStructType
0x18000e837  lea     rax, [rbp+100h+var_150]
0x18000e83b  mov     r8d, 1; dwCertEncodingType
0x18000e841  mov     [rsp+200h+pvStructInfo], rax; pvStructInfo
0x18000e846  call    cs:__imp_CryptSignAndEncodeCertificate
0x18000e84c  test    eax, eax
0x18000e84e  jz      loc_18000EA58
0x18000e854  mov     r8d, [rsp+200h+cbCrlEncoded]; cbCrlEncoded
0x18000e859  mov     rdx, rdi; pbCrlEncoded
0x18000e85c  mov     ecx, 1; dwCertEncodingType
0x18000e861  call    cs:__imp_CertCreateCRLContext
0x18000e867  mov     r14, rax
0x18000e86a  test    rax, rax
0x18000e86d  jz      short loc_18000E87C
0x18000e86f  mov     rdx, [rsp+200h+var_188]; struct _OCSP_STRONG_SIGN_PROP_INFO *
0x18000e874  mov     rcx, rax; pCrlContext
0x18000e877  call    ?OcspSetStrongSignProperties@@YAXPEBU_CRL_CONTEXT@@PEAU_OCSP_STRONG_SIGN_PROP_INFO@@@Z; OcspSetStrongSignProperties(_CRL_CONTEXT const *,_OCSP_STRONG_SIGN_PROP_INFO *)
0x18000e87c  mov     rcx, [rsp+200h+pvEncoded]; hMem
0x18000e881  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e886  mov     rcx, rdi; hMem
0x18000e889  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e88e  mov     rax, r14
0x18000e891  mov     rcx, [rbp+100h+var_50]
0x18000e898  xor     rcx, rsp; StackCookie
0x18000e89b  call    __security_check_cookie
0x18000e8a0  add     rsp, 1C8h
0x18000e8a7  pop     r15
0x18000e8a9  pop     r14
0x18000e8ab  pop     r13
0x18000e8ad  pop     r12
0x18000e8af  pop     rdi
0x18000e8b0  pop     rsi
0x18000e8b1  pop     rbx
0x18000e8b2  pop     rbp
0x18000e8b3  retn
0x18000e8b4  mov     rdx, [rdi+18h]
0x18000e8b8  lea     rcx, [rbp+100h+var_120]; lpFileTime1
0x18000e8bc  add     rdx, 40h ; '@'; lpFileTime2
0x18000e8c0  call    cs:__imp_CompareFileTime
0x18000e8c6  test    eax, eax
0x18000e8c8  js      short loc_18000E8E4
0x18000e8ca  mov     rdx, [rdi+18h]
0x18000e8ce  lea     rcx, [rbp+100h+FileTime1]; lpFileTime1
0x18000e8d2  add     rdx, 48h ; 'H'; lpFileTime2
0x18000e8d6  call    cs:__imp_CompareFileTime
0x18000e8dc  test    eax, eax
0x18000e8de  jle     loc_18000E6FD
0x18000e8e4  mov     ecx, 800B0101h; dwErrCode
0x18000e8e9  call    cs:__imp_SetLastError
0x18000e8ef  mov     rdi, r14
0x18000e8f2  jmp     short loc_18000E87C
0x18000e8f4  cmp     [rbx+64h], r14d
0x18000e8f8  jnz     loc_18000E6E8
0x18000e8fe  call    ?I_GetOcspValiditySeconds@@YAKXZ; I_GetOcspValiditySeconds(void)
0x18000e903  mov     ecx, eax
0x18000e905  imul    rax, rcx, 989680h
0x18000e90c  add     rax, qword ptr [rbp+100h+var_120.dwLowDateTime]
0x18000e910  jmp     loc_18000E6EC
0x18000e915  mov     r8d, 2; uFlags
0x18000e91b  mov     rcx, rdi; hMem
0x18000e91e  call    cs:__imp_LocalReAlloc
0x18000e924  jmp     loc_18000E804
0x18000e929  lea     rbx, aFindresponseen_0; "FindResponseEntry"
0x18000e930  lea     rdi, aFindresponseen; "FindResponseEntry"
0x18000e937  jmp     short loc_18000E957
0x18000e939  cmp     eax, 1
0x18000e93c  jz      short loc_18000E988
0x18000e93e  lea     rbx, aIscertificates; "IsCertificateStatusValid"
0x18000e945  lea     rdi, aInvalidcertsta; "InvalidCertStatus"
0x18000e94c  mov     ecx, 0Dh; dwErrCode
0x18000e951  call    cs:__imp_SetLastError
0x18000e957  xor     eax, eax
0x18000e959  mov     dword ptr [rsp+200h+var_188], esi
0x18000e95d  xor     r9d, r9d
0x18000e960  mov     dword ptr [rsp+200h+var_188+4], eax
0x18000e964  xor     r8d, r8d
0x18000e967  mov     [rbp+100h+var_180], r12
0x18000e96b  mov     rdx, rbx
0x18000e96e  lea     rcx, [rsp+200h+var_188]
0x18000e973  call    CertDiagRejectOcsp
0x18000e978  mov     rdx, r13; struct _CERT_CONTEXT *
0x18000e97b  mov     rcx, rdi; char *
0x18000e97e  call    ?I_OcspDebugErrorPrintfA@@YAXPEBDPEBU_CERT_CONTEXT@@@Z; I_OcspDebugErrorPrintfA(char const *,_CERT_CONTEXT const *)
0x18000e983  jmp     loc_18000E8EF
0x18000e988  mov     rcx, [rbx+50h]
0x18000e98c  lea     rax, [rbp+100h+var_178]
0x18000e990  xorps   xmm0, xmm0
0x18000e993  mov     [rbp+100h+var_108], rax
0x18000e997  movups  [rbp+100h+var_F0], xmm0
0x18000e99b  mov     qword ptr [rbp+100h+var_168], r14
0x18000e99f  lea     rax, [rbp+100h+var_F0]
0x18000e9a3  movups  [rbp+100h+var_E0], xmm0
0x18000e9a7  mov     qword ptr [rbp+100h+var_168+8], r14
0x18000e9ab  movups  xmm0, xmmword ptr [r15+38h]
0x18000e9b0  mov     [rbp+100h+var_110], 1
0x18000e9b7  mov     [rbp+100h+var_158], rax
0x18000e9bb  movups  [rbp+100h+var_178], xmm0
0x18000e9bf  mov     rax, [rcx]
0x18000e9c2  mov     qword ptr [rbp+100h+var_168], rax
0x18000e9c6  mov     eax, [rcx+8]
0x18000e9c9  test    eax, eax
0x18000e9cb  jz      short loc_18000EA32
0x18000e9cd  mov     [rsp+200h+var_198], eax
0x18000e9d1  lea     r8, [rsp+200h+var_198]; pvStructInfo
0x18000e9d6  lea     rax, [rsp+200h+var_1A8]
0x18000e9db  mov     r9d, 8000h; dwFlags
0x18000e9e1  mov     [rsp+200h+pvHashAuxInfo], rax; pcbEncoded
0x18000e9e6  mov     edx, 1Dh; lpszStructType
0x18000e9eb  lea     rax, [rsp+200h+pvEncoded]
0x18000e9f0  mov     ecx, 10001h; dwCertEncodingType
0x18000e9f5  mov     [rsp+200h+pSignatureAlgorithm], rax; pvEncoded
0x18000e9fa  lea     rax, PkiEncodePara
0x18000ea01  mov     [rsp+200h+pvStructInfo], rax; pEncodePara
0x18000ea06  call    cs:__imp_CryptEncodeObjectEx
0x18000ea0c  test    eax, eax
0x18000ea0e  jz      short loc_18000EA32
0x18000ea10  lea     rax, a252921; "2.5.29.21"
0x18000ea17  mov     qword ptr [rbp+100h+var_F0], rax
0x18000ea1b  mov     eax, [rsp+200h+var_1A8]
0x18000ea1f  mov     dword ptr [rbp+100h+var_E0], eax
0x18000ea22  mov     rax, [rsp+200h+pvEncoded]
0x18000ea27  mov     qword ptr [rbp+100h+var_E0+8], rax
0x18000ea2b  mov     eax, 1
0x18000ea30  jmp     short loc_18000EA35
0x18000ea32  mov     eax, r14d
0x18000ea35  mov     dword ptr [rbp+100h+var_168+8], eax
0x18000ea38  jmp     loc_18000E6B8
0x18000ea3d  mov     rax, [rdi+18h]
0x18000ea41  mov     rcx, [rax+48h]
0x18000ea45  mov     qword ptr [rbp+100h+FileTime1.dwLowDateTime], rcx
0x18000ea49  jmp     loc_18000E717
0x18000ea4e  mov     ecx, 0Dh
0x18000ea53  jmp     loc_18000E8E9
0x18000ea58  call    cs:__imp_GetLastError
0x18000ea5e  cmp     eax, 0EAh
0x18000ea63  jnz     loc_18000E87C
0x18000ea69  test    ebx, ebx
0x18000ea6b  jnz     loc_18000E87C
0x18000ea71  mov     r8d, [rsp+200h+cbCrlEncoded]
0x18000ea76  inc     ebx
0x18000ea78  jmp     loc_18000E7EB
0x18000ea7d  mov     ecx, 8007000Eh; dwErrCode
0x18000ea82  call    cs:__imp_SetLastError
0x18000ea88  jmp     loc_18000E87C
```
