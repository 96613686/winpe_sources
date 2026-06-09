# _GetManufacturerInfoFromCert(_CERT_CONTEXT const *,ushort * *,ushort * *,EKCAIdType *,ulong *,uchar * *,ulong *,uchar * *)

- ea: `0x1800030f0`
- end: `0x18000373d`
- name: `?_GetManufacturerInfoFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAG1PEAW4EKCAIdType@@PEAKPEAPEAE34@Z`
- size: `1613`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int16 **, unsigned __int16 **, enum EKCAIdType *, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b10`

## callees

- `0x180002310`
- `0x1800030f0`
- `0x180003750`
- `0x180007d80`
- `0x180008840`
- `0x18000a7c2`
- `0x18000a7ce`

## import_xrefs

- `CRYPT32!CertNameToStrW` at `0x180003357`
- `CRYPT32!CertNameToStrW` at `0x180003357`
- `CRYPT32!CryptFormatObject` at `0x18000343e`
- `CRYPT32!CryptFormatObject` at `0x18000343e`
- `CRYPT32!CertFreeCertificateContext` at `0x180003721`
- `CRYPT32!CertFreeCertificateContext` at `0x180003721`
- `CRYPT32!CertGetCertificateChain` at `0x1800032dc`
- `CRYPT32!CertGetCertificateChain` at `0x1800032dc`
- `CRYPT32!CertFindExtension` at `0x1800033ea`
- `CRYPT32!CertFindExtension` at `0x1800033ea`
- `CRYPT32!CryptDecodeObjectEx` at `0x180003550`
- `CRYPT32!CryptDecodeObjectEx` at `0x180003550`
- `CRYPT32!CertCloseStore` at `0x1800031cc`
- `CRYPT32!CertCloseStore` at `0x18000327c`
- `CRYPT32!CertCloseStore` at `0x1800036c9`
- `CRYPT32!CertCloseStore` at `0x180003713`
- `CRYPT32!CertCloseStore` at `0x1800031cc`
- `CRYPT32!CertCloseStore` at `0x18000327c`
- `CRYPT32!CertCloseStore` at `0x1800036c9`
- `CRYPT32!CertCloseStore` at `0x180003713`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003287`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000348b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000348b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003372`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003455`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003372`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003455`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000346e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000355a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000346e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000355a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031d4`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000315c`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000315c`
- `ncrypt!NCryptGetProperty` at `0x180003204`
- `ncrypt!NCryptGetProperty` at `0x180003204`
- `ncrypt!NCryptFreeObject` at `0x18000319c`
- `ncrypt!NCryptFreeObject` at `0x18000326a`
- `ncrypt!NCryptFreeObject` at `0x1800036b7`
- `ncrypt!NCryptFreeObject` at `0x18000319c`
- `ncrypt!NCryptFreeObject` at `0x18000326a`
- `ncrypt!NCryptFreeObject` at `0x1800036b7`

## string_xrefs

- `0x18000316b`: `ERROR: NCryptOpenStorageProvider. Hr=%x\n`
- `0x180003670`: `ERROR: No SAN Directory Name. Return=%d\n`

## pseudocode

```c
__int64 __fastcall _GetManufacturerInfoFromCert(
        PCCERT_CONTEXT pCertContext,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        enum EKCAIdType *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned __int8 **a8)
{
  SECURITY_STATUS v11; // eax
  __int64 LastError; // rsi
  unsigned int v13; // r8d
  NCRYPT_HANDLE v14; // rcx
  HCERTSTORE v15; // rcx
  SECURITY_STATUS Property; // eax
  unsigned int v17; // r8d
  HCERTSTORE v18; // rbx
  const CERT_CONTEXT *v19; // rdi
  PCERT_SIMPLE_CHAIN v20; // rdx
  DWORD cElement; // eax
  PCCERT_CONTEXT v22; // r15
  struct _CRYPTOAPI_BLOB *pCertInfo; // r15
  DWORD v24; // r14d
  WCHAR *v25; // rsi
  DWORD v26; // eax
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r14d
  const BYTE *pbData; // r15
  const CHAR *pszObjId; // r12
  HLOCAL v31; // rsi
  __int16 *v32; // r10
  __int16 v33; // ax
  __int16 *v34; // rdx
  __int16 *v35; // r8
  char v36; // r9
  __int64 i; // rdx
  __int64 v38; // r8
  SIZE_T v39; // r14
  const void *v40; // r15
  int IssuerId; // eax
  unsigned __int8 *v42; // r14
  unsigned __int8 *v43; // rax
  unsigned __int8 *v44; // rcx
  unsigned int v45; // r8d
  int pcbResult; // [rsp+20h] [rbp-C1h]
  int pcbResulta; // [rsp+20h] [rbp-C1h]
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-91h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v51; // [rsp+60h] [rbp-81h] BYREF
  unsigned __int8 *v52; // [rsp+68h] [rbp-79h] BYREF
  unsigned __int8 *v53; // [rsp+70h] [rbp-71h]
  _QWORD *pvStructInfo; // [rsp+78h] [rbp-69h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+80h] [rbp-61h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]
  PCCERT_CHAIN_CONTEXT ppChainContext; // [rsp+138h] [rbp+57h] BYREF
  DWORD pcbStructInfo; // [rsp+140h] [rbp+5Fh] BYREF
  enum EKCAIdType *v60; // [rsp+148h] [rbp+67h]

  v60 = a4;
  *a2 = 0;
  *a3 = 0;
  v53 = 0;
  v52 = 0;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  v51 = 0;
  hCertStore = 0;
  LODWORD(ppChainContext) = 0;
  phProvider = 0;
  v11 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0x40u);
  LODWORD(LastError) = v11;
  if ( v11 < 0 )
  {
    ekTraceFmt(0x30112C2u, 1, "ERROR: NCryptOpenStorageProvider. Hr=%x\n", v11);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x302, v13, (const char *)(unsigned int)LastError, pcbResult);
    v14 = phProvider;
    if ( !phProvider )
      goto LABEL_4;
    goto LABEL_3;
  }
  hCertStore = 0;
  Property = NCryptGetProperty(
               phProvider,
               L"PCP_INTERMEDIATE_CA_EKCERT",
               (PBYTE)&hCertStore,
               8u,
               (DWORD *)&ppChainContext,
               0);
  LODWORD(LastError) = Property;
  if ( Property < 0 )
  {
    ekTraceFmt(0x30E12C2u, 1, "ERROR: NCryptGetProperty(EKCERT). Hr=%x\n", Property);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x30F, v17, (const char *)(unsigned int)LastError, pcbResulta);
    v14 = phProvider;
    if ( !phProvider )
    {
LABEL_4:
      v15 = hCertStore;
      if ( !hCertStore )
        goto LABEL_70;
      goto LABEL_69;
    }
LABEL_3:
    NCryptFreeObject(v14);
    goto LABEL_4;
  }
  v18 = hCertStore;
  if ( !hCertStore )
  {
    LODWORD(LastError) = -2147024809;
    ekTraceFmt(0x31512C2u, 1, "ERROR: NCryptGetProperty. Hr=%x\n", -2147024809);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x316, v45, (const char *)0x80070057LL, pcbResulta);
    if ( phProvider )
      NCryptFreeObject(phProvider);
    v15 = hCertStore;
    if ( !hCertStore )
      goto LABEL_70;
LABEL_69:
    CertCloseStore(v15, 0);
LABEL_70:
    v18 = 0;
    v19 = 0;
    ekTraceFmt(
      0xD7412C2u,
      1,
      "ERROR: _TpmEndorsementKeyGetIntermediateCertificateStore. Return=%d\n",
      (unsigned int)LastError);
    goto LABEL_71;
  }
  hCertStore = 0;
  if ( phProvider )
  {
    NCryptFreeObject(phProvider);
    if ( hCertStore )
      CertCloseStore(hCertStore, 0);
  }
  v19 = CertEnumCertificatesInStore(v18, 0);
  if ( !v19 )
  {
LABEL_19:
    v22 = pCertContext;
LABEL_20:
    pCertInfo = (struct _CRYPTOAPI_BLOB *)v22->pCertInfo;
    v24 = 0;
    v25 = 0;
    while ( 1 )
    {
      v26 = CertNameToStrW(1u, pCertInfo + 3, 0x2000003u, v25, v24);
      v24 = v26;
      if ( !v26 )
        break;
      if ( v25 )
      {
        *a2 = v25;
        goto LABEL_28;
      }
      v25 = (WCHAR *)LocalAlloc(0, 2LL * (v26 + 1));
      if ( !v25 )
      {
        ekTraceFmt(0x4212C3u, 1, "ERROR: LocalAlloc. Hr=%x\n", -2147024882);
        goto LABEL_28;
      }
    }
    ekTraceFmt(0x3512C3u, 1, "ERROR: CertNameToStr. Hr=%x\n", -2147024894);
    if ( v25 )
      LocalFree(v25);
LABEL_28:
    Extension = CertFindExtension(
                  "2.5.29.17",
                  pCertContext->pCertInfo->cExtension,
                  pCertContext->pCertInfo->rgExtension);
    phProvider = (NCRYPT_PROV_HANDLE)Extension;
    if ( Extension )
    {
      cbData = Extension->Value.cbData;
      pbData = Extension->Value.pbData;
      pszObjId = Extension->pszObjId;
      v31 = 0;
      LODWORD(ppChainContext) = 0;
      *a3 = 0;
      while ( 1 )
      {
        if ( !CryptFormatObject(1u, 0, 1u, 0, pszObjId, pbData, cbData, v31, (DWORD *)&ppChainContext) )
        {
          GetLastError();
          if ( v31 )
            LocalFree(v31);
          goto LABEL_52;
        }
        if ( v31 )
          break;
        v31 = LocalAlloc(0, 2LL * (unsigned int)ppChainContext);
        if ( !v31 )
          goto LABEL_52;
      }
      *a3 = (unsigned __int16 *)v31;
      v32 = (__int16 *)*a3;
      if ( *a3 )
      {
        v33 = *v32;
        v34 = (__int16 *)*a3;
        v35 = (__int16 *)*a3;
        if ( *v32 )
        {
          v36 = 0;
          while ( 1 )
          {
            ++v34;
            if ( v33 != 32 && v33 != 10 && v33 != 13 )
              break;
            if ( !v36 )
            {
              v36 = 1;
              v33 = 32;
              goto LABEL_47;
            }
LABEL_48:
            v33 = *v34;
            if ( !*v34 )
              goto LABEL_49;
          }
          v36 = 0;
LABEL_47:
          *v35++ = v33;
          goto LABEL_48;
        }
LABEL_49:
        *v35 = 0;
        if ( v35 > v32 && *(v35 - 1) == 32 )
          *(v35 - 1) = 0;
      }
LABEL_52:
      pcbStructInfo = 0;
      if ( !CryptDecodeObjectEx(
              1u,
              (LPCSTR)0xC,
              *(const BYTE **)(phProvider + 24),
              *(_DWORD *)(phProvider + 16),
              0x8000u,
              0,
              &pvStructInfo,
              &pcbStructInfo) )
      {
        LastError = GetLastError();
        ekTraceFmt(0xDCE12C2u, 1, "ERROR: CryptDecodeObjectEx. Return=%d\n", LastError);
        goto LABEL_71;
      }
      for ( i = 0; (unsigned int)i < *(_DWORD *)pvStructInfo; i = (unsigned int)(i + 1) )
      {
        v38 = pvStructInfo[1] + 24 * i;
        if ( *(_DWORD *)v38 == 5 )
        {
          v39 = *(unsigned int *)(v38 + 8);
          if ( (_DWORD)v39 )
          {
            v40 = *(const void **)(v38 + 16);
            if ( v40 )
            {
              IssuerId = _GetIssuerId(pCertContext, v60, &v52, &v51);
              LODWORD(LastError) = IssuerId;
              if ( IssuerId )
              {
                ekTraceFmt(0xDED12C2u, 1, "ERROR: No AKI. Return=%d\n", IssuerId);
                v42 = v52;
              }
              else
              {
                v43 = (unsigned __int8 *)LocalAlloc(0x40u, v39);
                *a8 = v43;
                if ( v43 )
                {
                  memcpy_0(v43, v40, v39);
                  v44 = v52;
                  *a7 = v39;
                  v42 = 0;
                  LODWORD(LastError) = 0;
                  *a6 = v44;
                  *a5 = v51;
                }
                else
                {
                  LODWORD(LastError) = 14;
                  ekTraceFmt(0xDF512C2u, 1, "ERROR: MIDL_user_allocate. Return=%d\n", 14);
                  v42 = v52;
                }
              }
              goto LABEL_72;
            }
          }
          break;
        }
      }
    }
    LODWORD(LastError) = -2146875389;
    ekTraceFmt(0xDE012C2u, 1, "ERROR: No SAN Directory Name. Return=%d\n", 2148091907LL);
    goto LABEL_71;
  }
  ppChainContext = 0;
  memset_0(&pChainPara.cbSize + 1, 0, 0x5Cu);
  pChainPara.cbSize = 96;
  if ( CertGetCertificateChain(0, pCertContext, 0, v18, &pChainPara, 0, 0, &ppChainContext) )
  {
    if ( ppChainContext->cChain )
    {
      v20 = *ppChainContext->rgpChain;
      cElement = v20->cElement;
      if ( cElement )
      {
        v22 = v20->rgpElement[cElement - 1]->pCertContext;
        if ( v22 )
          goto LABEL_20;
      }
    }
    goto LABEL_19;
  }
  LastError = GetLastError();
  ekTraceFmt(0xD8B12C2u, 1, "ERROR: CertGetCertificateChain. Return=%d\n", LastError);
LABEL_71:
  v42 = v53;
LABEL_72:
  LocalFree(pvStructInfo);
  if ( v42 )
    MIDL_user_free(v42);
  if ( v18 )
    CertCloseStore(v18, 0);
  if ( v19 )
    CertFreeCertificateContext(v19);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800030f0  mov     [rsp-8+arg_18], r9
0x1800030f5  mov     [rsp-8+pCertContext], rcx
0x1800030fa  push    rbp
0x1800030fb  push    rbx
0x1800030fc  push    rsi
0x1800030fd  push    rdi
0x1800030fe  push    r12
0x180003100  push    r13
0x180003102  push    r14
0x180003104  push    r15
0x180003106  lea     rbp, [rsp-7]
0x18000310b  sub     rsp, 0E8h
0x180003112  xor     r15d, r15d
0x180003115  mov     r13, r8
0x180003118  mov     eax, r15d
0x18000311b  mov     [rdx], r15
0x18000311e  mov     [r8], r15
0x180003121  mov     r12, rdx
0x180003124  mov     r14, rcx
0x180003127  mov     [rbp+3Fh+var_B0], rax
0x18000312b  mov     r8d, 40h ; '@'; dwFlags
0x180003131  mov     [rbp+3Fh+var_B8], rax
0x180003135  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18000313c  mov     [rbp+3Fh+pvStructInfo], r15
0x180003140  lea     rcx, [rsp+120h+phProvider]; phProvider
0x180003145  mov     [rbp+3Fh+pcbStructInfo], r15d
0x180003149  mov     [rsp+120h+var_C0], r15d
0x18000314e  mov     [rsp+120h+hCertStore], r15
0x180003153  mov     dword ptr [rbp+3Fh+arg_8], r15d
0x180003157  mov     [rsp+120h+phProvider], r15
0x18000315c  call    cs:__imp_NCryptOpenStorageProvider
0x180003162  mov     esi, eax
0x180003164  test    eax, eax
0x180003166  jns     short loc_1800031B5
0x180003168  mov     r9d, eax
0x18000316b  lea     r8, aErrorNcryptope; "ERROR: NCryptOpenStorageProvider. Hr=%x"...
0x180003172  mov     edx, 1; unsigned int
0x180003177  mov     ecx, 30112C2h; unsigned int
0x18000317c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003181  mov     rcx, [rbp+47h]; this
0x180003185  mov     r9d, esi; char *
0x180003188  mov     edx, 302h; void *
0x18000318d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003192  mov     rcx, [rsp+120h+phProvider]; hObject
0x180003197  test    rcx, rcx
0x18000319a  jz      short loc_1800031A2
0x18000319c  call    cs:__imp_NCryptFreeObject
0x1800031a2  mov     rcx, [rsp+120h+hCertStore]
0x1800031a7  test    rcx, rcx
0x1800031aa  jnz     loc_1800036C7
0x1800031b0  jmp     loc_1800036CF
0x1800031b5  mov     rdi, [rsp+120h+hCertStore]
0x1800031ba  test    rdi, rdi
0x1800031bd  jz      short loc_1800031DA
0x1800031bf  call    cs:__imp_GetLastError
0x1800031c5  xor     edx, edx; dwFlags
0x1800031c7  mov     rcx, rdi; hCertStore
0x1800031ca  mov     ebx, eax
0x1800031cc  call    cs:__imp_CertCloseStore
0x1800031d2  mov     ecx, ebx; dwErrCode
0x1800031d4  call    cs:__imp_SetLastError
0x1800031da  mov     rcx, [rsp+120h+phProvider]; hObject
0x1800031df  lea     rax, [rbp+3Fh+arg_8]
0x1800031e3  mov     [rsp+120h+dwFlags], r15d; dwFlags
0x1800031e8  lea     r8, [rsp+120h+hCertStore]; pbOutput
0x1800031ed  mov     r9d, 8; cbOutput
0x1800031f3  mov     [rsp+120h+pcbResult], rax; int
0x1800031f8  lea     rdx, aPcpIntermediat; "PCP_INTERMEDIATE_CA_EKCERT"
0x1800031ff  mov     [rsp+120h+hCertStore], r15
0x180003204  call    cs:__imp_NCryptGetProperty
0x18000320a  mov     esi, eax
0x18000320c  test    eax, eax
0x18000320e  jns     short loc_18000324D
0x180003210  mov     r9d, eax
0x180003213  lea     r8, aErrorNcryptget_2; "ERROR: NCryptGetProperty(EKCERT). Hr=%x"...
0x18000321a  mov     edx, 1; unsigned int
0x18000321f  mov     ecx, 30E12C2h; unsigned int
0x180003224  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003229  mov     rcx, [rbp+47h]; this
0x18000322d  mov     r9d, esi; char *
0x180003230  mov     edx, 30Fh; void *
0x180003235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000323a  mov     rcx, [rsp+120h+phProvider]
0x18000323f  test    rcx, rcx
0x180003242  jz      loc_1800031A2
0x180003248  jmp     loc_18000319C
0x18000324d  mov     rbx, [rsp+120h+hCertStore]
0x180003252  test    rbx, rbx
0x180003255  jz      loc_18000367E
0x18000325b  mov     rcx, [rsp+120h+phProvider]; hObject
0x180003260  mov     [rsp+120h+hCertStore], r15
0x180003265  test    rcx, rcx
0x180003268  jz      short loc_180003282
0x18000326a  call    cs:__imp_NCryptFreeObject
0x180003270  mov     rcx, [rsp+120h+hCertStore]; hCertStore
0x180003275  test    rcx, rcx
0x180003278  jz      short loc_180003282
0x18000327a  xor     edx, edx; dwFlags
0x18000327c  call    cs:__imp_CertCloseStore
0x180003282  xor     edx, edx; pPrevCertContext
0x180003284  mov     rcx, rbx; hCertStore
0x180003287  call    cs:__imp_CertEnumCertificatesInStore
0x18000328d  mov     rdi, rax
0x180003290  test    rax, rax
0x180003293  jz      loc_18000332E
0x180003299  xor     edx, edx; Val
0x18000329b  mov     [rbp+3Fh+arg_8], r15
0x18000329f  mov     r8d, 5Ch ; '\'; Size
0x1800032a5  lea     rcx, [rbp+3Fh+pChainPara+4]; void *
0x1800032a9  call    memset_0
0x1800032ae  lea     rax, [rbp+3Fh+arg_8]
0x1800032b2  mov     [rbp+3Fh+pChainPara.cbSize], 60h ; '`'
0x1800032b9  mov     [rsp+120h+ppChainContext], rax; ppChainContext
0x1800032be  mov     r9, rbx; hAdditionalStore
0x1800032c1  mov     [rsp+120h+pvReserved], r15; pvReserved
0x1800032c6  lea     rax, [rbp+3Fh+pChainPara]
0x1800032ca  mov     [rsp+120h+dwFlags], r15d; dwFlags
0x1800032cf  xor     r8d, r8d; pTime
0x1800032d2  mov     rdx, r14; pCertContext
0x1800032d5  mov     [rsp+120h+pcbResult], rax; pChainPara
0x1800032da  xor     ecx, ecx; hChainEngine
0x1800032dc  call    cs:__imp_CertGetCertificateChain
0x1800032e2  test    eax, eax
0x1800032e4  jnz     short loc_180003302
0x1800032e6  call    cs:__imp_GetLastError
0x1800032ec  lea     r8, aErrorCertgetce_0; "ERROR: CertGetCertificateChain. Return="...
0x1800032f3  mov     ecx, 0D8B12C2h
0x1800032f8  mov     esi, eax
0x1800032fa  mov     r9d, eax
0x1800032fd  jmp     loc_1800036E4
0x180003302  mov     rax, [rbp+3Fh+arg_8]
0x180003306  cmp     [rax+0Ch], r15d
0x18000330a  jbe     short loc_18000332E
0x18000330c  mov     rax, [rax+10h]
0x180003310  mov     rdx, [rax]
0x180003313  mov     eax, [rdx+0Ch]
0x180003316  test    eax, eax
0x180003318  jz      short loc_18000332E
0x18000331a  lea     ecx, [rax-1]
0x18000331d  mov     rax, [rdx+10h]
0x180003321  mov     rcx, [rax+rcx*8]
0x180003325  mov     r15, [rcx+8]
0x180003329  test    r15, r15
0x18000332c  jnz     short loc_180003331
0x18000332e  mov     r15, r14
0x180003331  mov     r15, [r15+18h]
0x180003335  xor     r14d, r14d
0x180003338  xor     esi, esi
0x18000333a  nop     word ptr [rax+rax+00h]
0x180003340  mov     r9, rsi; psz
0x180003343  mov     dword ptr [rsp+120h+pcbResult], r14d; csz
0x180003348  mov     r8d, 2000003h; dwStrType
0x18000334e  lea     rdx, [r15+30h]; pName
0x180003352  mov     ecx, 1; dwCertEncodingType
0x180003357  call    cs:__imp_CertNameToStrW
0x18000335d  mov     r14d, eax
0x180003360  cmp     eax, 1
0x180003363  jb      short loc_1800033A4
0x180003365  test    rsi, rsi
0x180003368  jnz     short loc_18000339E
0x18000336a  lea     edx, [rax+1]
0x18000336d  xor     ecx, ecx; uFlags
0x18000336f  add     rdx, rdx; uBytes
0x180003372  call    cs:__imp_LocalAlloc
0x180003378  mov     rsi, rax
0x18000337b  test    rax, rax
0x18000337e  jnz     short loc_180003340
0x180003380  mov     r9d, 8007000Eh
0x180003386  lea     r8, aErrorLocalallo_1; "ERROR: LocalAlloc. Hr=%x\n"
0x18000338d  mov     edx, 1; unsigned int
0x180003392  mov     ecx, 4212C3h; unsigned int
0x180003397  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000339c  jmp     short loc_1800033CE
0x18000339e  mov     [r12], rsi
0x1800033a2  jmp     short loc_1800033CE
0x1800033a4  mov     r9d, 80070002h
0x1800033aa  lea     r8, aErrorCertnamet; "ERROR: CertNameToStr. Hr=%x\n"
0x1800033b1  mov     edx, 1; unsigned int
0x1800033b6  mov     ecx, 3512C3h; unsigned int
0x1800033bb  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800033c0  test    rsi, rsi
0x1800033c3  jz      short loc_1800033CE
0x1800033c5  mov     rcx, rsi; hMem
0x1800033c8  call    cs:__imp_LocalFree
0x1800033ce  mov     rdx, [rbp+3Fh+pCertContext]
0x1800033d2  lea     rcx, a252917; "2.5.29.17"
0x1800033d9  mov     rdx, [rdx+18h]
0x1800033dd  mov     r8, [rdx+0C8h]; rgExtensions
0x1800033e4  mov     edx, [rdx+0C0h]; cExtensions
0x1800033ea  call    cs:__imp_CertFindExtension
0x1800033f0  mov     [rsp+120h+phProvider], rax
0x1800033f5  test    rax, rax
0x1800033f8  jz      loc_18000366B
0x1800033fe  mov     r14d, [rax+10h]
0x180003402  mov     r15, [rax+18h]
0x180003406  mov     r12, [rax]
0x180003409  xor     eax, eax
0x18000340b  mov     esi, eax
0x18000340d  mov     dword ptr [rbp+3Fh+arg_8], eax
0x180003410  mov     [r13+0], rax
0x180003414  lea     rax, [rbp+3Fh+arg_8]
0x180003418  mov     ecx, 1; dwCertEncodingType
0x18000341d  mov     [rsp+120h+pcbFormat], rax; pcbFormat
0x180003422  xor     r9d, r9d; pFormatStruct
0x180003425  mov     [rsp+120h+ppChainContext], rsi; pbFormat
0x18000342a  xor     edx, edx; dwFormatType
0x18000342c  mov     dword ptr [rsp+120h+pvReserved], r14d; cbEncoded
0x180003431  mov     r8d, ecx; dwFormatStrType
0x180003434  mov     qword ptr [rsp+120h+dwFlags], r15; pbEncoded
0x180003439  mov     [rsp+120h+pcbResult], r12; lpszStructType
0x18000343e  call    cs:__imp_CryptFormatObject
0x180003444  test    eax, eax
0x180003446  jz      short loc_18000346E
0x180003448  test    rsi, rsi
0x18000344b  jnz     short loc_180003468
0x18000344d  mov     edx, dword ptr [rbp+3Fh+arg_8]
0x180003450  xor     ecx, ecx; uFlags
0x180003452  add     rdx, rdx; uBytes
0x180003455  call    cs:__imp_LocalAlloc
0x18000345b  mov     rsi, rax
0x18000345e  test    rax, rax
0x180003461  jnz     short loc_180003414
0x180003463  jmp     loc_18000350F
0x180003468  mov     [r13+0], rsi
0x18000346c  jmp     short loc_180003496
0x18000346e  call    cs:__imp_GetLastError
0x180003474  mov     r14d, eax
0x180003477  mov     eax, 8007000Dh
0x18000347c  test    r14d, r14d
0x18000347f  cmovz   r14d, eax
0x180003483  test    rsi, rsi
0x180003486  jz      short loc_180003491
0x180003488  mov     rcx, rsi; hMem
0x18000348b  call    cs:__imp_LocalFree
0x180003491  test    r14d, r14d
0x180003494  jnz     short loc_18000350F
0x180003496  mov     r10, [r13+0]
0x18000349a  test    r10, r10
0x18000349d  jz      short loc_18000350F
0x18000349f  movzx   eax, word ptr [r10]
0x1800034a3  xor     ecx, ecx
0x1800034a5  mov     rdx, r10
0x1800034a8  mov     r8, r10
0x1800034ab  mov     r11d, 20h ; ' '
0x1800034b1  cmp     cx, ax
0x1800034b4  jz      short loc_1800034F8
0x1800034b6  xor     r9b, r9b
0x1800034b9  nop     dword ptr [rax+00000000h]
0x1800034c0  lea     rdx, [rdx+2]
0x1800034c4  cmp     ax, r11w
0x1800034c8  jz      short loc_1800034DB
0x1800034ca  cmp     ax, 0Ah
0x1800034ce  jz      short loc_1800034DB
0x1800034d0  cmp     ax, 0Dh
0x1800034d4  jz      short loc_1800034DB
0x1800034d6  xor     r9b, r9b
0x1800034d9  jmp     short loc_1800034E6
0x1800034db  test    r9b, r9b
0x1800034de  jnz     short loc_1800034EE
0x1800034e0  mov     r9b, 1
0x1800034e3  mov     eax, r11d
0x1800034e6  mov     [r8], ax
0x1800034ea  add     r8, 2
0x1800034ee  movzx   eax, word ptr [rdx]
0x1800034f1  xor     ecx, ecx
0x1800034f3  cmp     cx, ax
0x1800034f6  jnz     short loc_1800034C0
0x1800034f8  xor     eax, eax
0x1800034fa  mov     [r8], ax
0x1800034fe  cmp     r8, r10
0x180003501  jbe     short loc_18000350F
0x180003503  cmp     r11w, [r8-2]
0x180003508  jnz     short loc_18000350F
0x18000350a  mov     [r8-2], ax
0x18000350f  mov     r8, [rsp+120h+phProvider]
0x180003514  lea     rax, [rbp+3Fh+pcbStructInfo]
0x180003518  mov     [rsp+120h+ppChainContext], rax; pcbStructInfo
0x18000351d  mov     edx, 0Ch; lpszStructType
0x180003522  mov     [rbp+3Fh+pcbStructInfo], 0
0x180003529  lea     rax, [rbp+3Fh+pvStructInfo]
0x18000352d  mov     [rsp+120h+pvReserved], rax; pvStructInfo
0x180003532  mov     ecx, 1; dwCertEncodingType
0x180003537  mov     r9d, [r8+10h]; cbEncoded
0x18000353b  mov     r8, [r8+18h]; pbEncoded
0x18000353f  mov     qword ptr [rsp+120h+dwFlags], 0; pDecodePara
0x180003548  mov     dword ptr [rsp+120h+pcbResult], 8000h; dwFlags
0x180003550  call    cs:__imp_CryptDecodeObjectEx
0x180003556  test    eax, eax
0x180003558  jnz     short loc_180003576
0x18000355a  call    cs:__imp_GetLastError
0x180003560  lea     r8, aErrorCryptdeco_0; "ERROR: CryptDecodeObjectEx. Return=%d\n"
0x180003567  mov     ecx, 0DCE12C2h
0x18000356c  mov     esi, eax
0x18000356e  mov     r9d, eax
0x180003571  jmp     loc_1800036E4
0x180003576  mov     r9, [rbp+3Fh+pvStructInfo]
0x18000357a  xor     edx, edx
0x18000357c  cmp     edx, [r9]
0x18000357f  jnb     loc_18000366B
0x180003585  mov     rax, [r9+8]
  ... truncated ...
```
