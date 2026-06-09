# EKCliTpmGetManufacturerInfo

- ea: `0x180002b10`
- end: `0x1800030e7`
- name: `EKCliTpmGetManufacturerInfo`
- size: `1495`
- prototype: `__int64 __fastcall(wchar_t *String1, unsigned __int16 **, HLOCAL *, enum EKCAIdType *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009b20`

## callees

- `0x180002850`
- `0x180002b10`
- `0x1800030f0`
- `0x180003750`
- `0x180004790`
- `0x1800049f0`
- `0x18000a800`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002c34`
- `msvcrt!_wcsicmp` at `0x180002c34`
- `CRYPT32!CertFreeCertificateContext` at `0x18000308a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800030a0`
- `CRYPT32!CertFreeCertificateContext` at `0x18000308a`
- `CRYPT32!CertFreeCertificateContext` at `0x1800030a0`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180002da0`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180002da0`
- `CRYPT32!CertCloseStore` at `0x180002e12`
- `CRYPT32!CertCloseStore` at `0x180002e22`
- `CRYPT32!CertCloseStore` at `0x180002e12`
- `CRYPT32!CertCloseStore` at `0x180002e22`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180002d62`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180002db9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180002d62`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180002db9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000305c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003071`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000307c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000305c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003071`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000307c`

## pseudocode

```c
__int64 __fastcall EKCliTpmGetManufacturerInfo(
        wchar_t *String1,
        unsigned __int16 **a2,
        HLOCAL *a3,
        enum EKCAIdType *a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  HLOCAL *v9; // r12
  unsigned __int16 *v12; // rsi
  const CERT_CONTEXT *v13; // r14
  unsigned int *v14; // rax
  unsigned int *v15; // rdx
  unsigned __int8 **v16; // rcx
  unsigned int v17; // ebx
  unsigned int v18; // edi
  unsigned int EkCertificateStores; // eax
  HCERTSTORE v20; // r12
  HCERTSTORE v21; // r15
  unsigned int CertificateFromStoreMatchingEkPub; // eax
  unsigned __int16 *VolatileCertIdString; // rax
  const CERT_CONTEXT *v24; // rax
  unsigned int v25; // ebx
  unsigned __int16 *v26; // rax
  const CERT_CONTEXT *v27; // rax
  const CERT_CONTEXT *v28; // rdx
  __int64 v29; // rcx
  unsigned __int8 **v30; // r12
  enum EKCAIdType *v31; // r15
  int ManufacturerInfoFromCert; // eax
  __int64 i; // rbx
  const CERT_CONTEXT *v34; // rcx
  int v35; // eax
  unsigned __int16 *v36; // rcx
  __int64 j; // rsi
  const CERT_CONTEXT *v38; // rcx
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-A1h] BYREF
  HLOCAL v41; // [rsp+48h] [rbp-99h]
  HLOCAL v42; // [rsp+50h] [rbp-91h]
  HCERTSTORE v43; // [rsp+58h] [rbp-89h] BYREF
  unsigned __int16 *v44; // [rsp+60h] [rbp-81h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-79h]
  unsigned __int16 *v46; // [rsp+70h] [rbp-71h] BYREF
  unsigned __int16 *v47; // [rsp+78h] [rbp-69h] BYREF
  unsigned __int16 *v48; // [rsp+80h] [rbp-61h] BYREF
  unsigned __int8 **v49; // [rsp+88h] [rbp-59h]
  unsigned int *v50; // [rsp+90h] [rbp-51h]
  unsigned int *v51; // [rsp+98h] [rbp-49h]
  HLOCAL *v52; // [rsp+A0h] [rbp-41h]
  HCERTSTORE hCertStore; // [rsp+A8h] [rbp-39h] BYREF
  enum EKCAIdType *v54; // [rsp+B0h] [rbp-31h]
  unsigned __int8 **v55; // [rsp+B8h] [rbp-29h]
  PCCERT_CONTEXT v56[2]; // [rsp+C0h] [rbp-21h]
  __int64 v57; // [rsp+D0h] [rbp-11h]

  v9 = a3;
  v51 = a6;
  v49 = a7;
  v52 = a3;
  v50 = a8;
  v54 = a4;
  v55 = a5;
  ekTraceFmt(0xE2212C2u, 2, "TRACE: EKCliTpmGetManufacturerInfo start.\n");
  v47 = 0;
  hMem = 0;
  v12 = 0;
  v46 = 0;
  v13 = 0;
  v41 = 0;
  v48 = 0;
  v42 = 0;
  v44 = 0;
  v57 = 0;
  pCertContext = 0;
  *(_OWORD *)v56 = 0;
  if ( !String1 || !a2 || !v9 || !a4 || (v14 = v51) == 0 || !a5 || (v15 = v50) == 0 || (v16 = v49) == 0 )
  {
    v17 = 160;
    ekTraceFmt(0xE3F12C2u, 1, "ERROR: Arguments. Return=%d\n", 160);
    v18 = 0;
    if ( !a2 )
      goto LABEL_53;
    goto LABEL_52;
  }
  *a2 = 0;
  *v9 = 0;
  *(_DWORD *)a4 = 0;
  *v14 = 0;
  *a5 = 0;
  *v15 = 0;
  *v16 = 0;
  if ( _wcsicmp(String1, L"Microsoft Platform Crypto Provider") )
  {
    v17 = 160;
    v18 = 0;
    ekTraceFmt(0xE4D12C2u, 1, "ERROR: Invalid KSP.Ksp=%ws Return=%d\n", String1, 160);
    goto LABEL_52;
  }
  ekTraceFmt(0x5A012C2u, 2, "TRACE: _TpmEndorsementKeyGetEkCertificates start.\n");
  v43 = 0;
  hCertStore = 0;
  v18 = 0;
  EkCertificateStores = _TpmEndorsementKeyGetEkCertificateStores(&v43, &hCertStore);
  v20 = v43;
  v17 = EkCertificateStores;
  v21 = hCertStore;
  if ( !EkCertificateStores )
  {
    CertificateFromStoreMatchingEkPub = _TpmGetCertificateFromStoreMatchingEkPub(v43, &pCertContext);
    v17 = CertificateFromStoreMatchingEkPub;
    if ( CertificateFromStoreMatchingEkPub == -2147023728 )
    {
      ekTraceFmt(
        0x5BB12C2u,
        1,
        "TRACE: _TpmGetCertificateFromStoreMatchingEkPub failed with E_NOT_SET. A certificate could not be found in the N"
        "V EK Certificate store.\n");
    }
    else
    {
      if ( CertificateFromStoreMatchingEkPub )
      {
        ekTraceFmt(
          0x5C512C2u,
          1,
          "ERROR: _TpmGetCertificateFromStoreMatchingEkPub. Hr=%x\n",
          CertificateFromStoreMatchingEkPub);
        v13 = pCertContext;
        goto LABEL_27;
      }
      ekTraceFmt(
        0x5C012C2u,
        1,
        "TRACE: _TpmGetCertificateFromStoreMatchingEkPub succeeded. A certificate in the NV EK Certificate store matched the EK pub.\n");
    }
    v13 = pCertContext;
    if ( pCertContext )
    {
      LODWORD(v43) = 2;
      VolatileCertIdString = _GetVolatileCertIdString(pCertContext);
      ekTraceFmt(0x5CC12C2u, 2, "TRACE: OneManufacturerCert: %ws\n", VolatileCertIdString);
    }
    else
    {
      LODWORD(v43) = 3;
      ekTraceFmt(0x5D012C2u, 1, "ERROR: _TpmEndorsementKeyGetEkCertificateByIndex. Hr=%x\n", v17);
    }
    v24 = CertEnumCertificatesInStore(v21, 0);
    pCertContext = v24;
    if ( v24 )
    {
      do
      {
        v25 = v18;
        if ( v18 >= (unsigned int)v43 )
          break;
        v26 = _GetVolatileCertIdString(v24);
        ekTraceFmt(0x5E212C2u, 2, "TRACE: OtherCert: %ws\n", v26);
        v27 = CertDuplicateCertificateContext(pCertContext);
        v28 = pCertContext;
        v29 = v18++;
        v25 = v18;
        v56[v29] = v27;
        v24 = CertEnumCertificatesInStore(v21, v28);
        pCertContext = v24;
      }
      while ( v24 );
    }
    else
    {
      v25 = 0;
    }
    ekTraceFmt(0x5E912C2u, 2, "TRACE: OtherEkCertificates. Count=%d\n", v25);
    v17 = 0;
    goto LABEL_27;
  }
  ekTraceFmt(0x5B012C2u, 1, "ERROR: _TpmEndorsementKeyGetEkCertificateStores. Hr=%x\n", EkCertificateStores);
LABEL_27:
  if ( v20 )
    CertCloseStore(v20, 0);
  if ( v21 )
    CertCloseStore(v21, 0);
  ekTraceFmt(0x5F712C2u, 2, "TRACE: _TpmEndorsementKeyGetEkCertificates end.\n");
  if ( v17 )
  {
    ekTraceFmt(0xE5C12C2u, 1, "ERROR: _TpmEndorsementKeyGetEkCertificates. Return=%d\n", v17);
    v9 = v52;
    goto LABEL_52;
  }
  v30 = v55;
  v31 = v54;
  if ( !v13 )
    goto LABEL_36;
  ManufacturerInfoFromCert = _GetManufacturerInfoFromCert(v13, &v47, &v48, v54, v51, v55, v50, v49);
  if ( ManufacturerInfoFromCert )
  {
    ekTraceFmt(0xE7112C2u, 1, "ERROR: _GetManufacturerInfoFromCert. Return=%d\n", ManufacturerInfoFromCert);
    v12 = v47;
    v41 = v48;
LABEL_36:
    ekTraceFmt(0xE7C12C2u, 2, "TRACE: ManufacturerCert not found. Number of other certs:%d\n", v18);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v18 )
      {
        v17 = 1168;
        ekTraceFmt(0xEAA12C2u, 1, "ERROR: EKCliTpmGetManufacturerInfo. Return=%d\n", 1168);
        v9 = v52;
        goto LABEL_52;
      }
      v34 = v56[i];
      if ( v34 )
        break;
LABEL_47:
      ;
    }
    v35 = _GetManufacturerInfoFromCert(v34, &v46, &v44, v31, v51, v30, v50, v49);
    if ( v12 )
    {
      hMem = v46;
      v36 = v44;
    }
    else
    {
      v12 = v46;
      v36 = v44;
      hMem = 0;
      if ( !v46 )
      {
        v41 = v44;
        v42 = 0;
LABEL_45:
        if ( !v35 )
        {
          ekTraceFmt(0xE9A12C2u, 2, "TRACE: ManufacturerCert found from rgEKOtherCertContext\n");
          goto LABEL_49;
        }
        ekTraceFmt(0xE9E12C2u, 1, "ERROR: _GetManufacturerInfoFromCert. Return=%d\n", v35);
        LocalFree(hMem);
        hMem = 0;
        v46 = 0;
        LocalFree(v42);
        v42 = 0;
        v44 = 0;
        goto LABEL_47;
      }
    }
    v42 = v36;
    goto LABEL_45;
  }
  v12 = v47;
  v41 = v48;
  ekTraceFmt(
    0xE7512C2u,
    2,
    "TRACE: ManufacturerInfo found. _TpmEndorsementKeyGetEkCertificates returned pManufacturerCertContext.\n");
LABEL_49:
  v9 = v52;
  v17 = 0;
LABEL_52:
  *a2 = v12;
LABEL_53:
  if ( v9 )
  {
    *v9 = v41;
    v41 = 0;
  }
  LocalFree(0);
  LocalFree(hMem);
  LocalFree(v41);
  LocalFree(v42);
  if ( v13 )
    CertFreeCertificateContext(v13);
  for ( j = 0; (unsigned int)j < v18; j = (unsigned int)(j + 1) )
  {
    v38 = v56[j];
    if ( v38 )
      CertFreeCertificateContext(v38);
  }
  ekTraceFmt(0xECA12C2u, 2, "TRACE: EKCliTpmGetManufacturerInfo end. %d\n", v17);
  return v17;
}

```

## disassembly

```asm
0x180002b10  push    rbp
0x180002b12  push    rbx
0x180002b13  push    rsi
0x180002b14  push    rdi
0x180002b15  push    r12
0x180002b17  push    r13
0x180002b19  push    r14
0x180002b1b  push    r15
0x180002b1d  lea     rbp, [rsp-7]
0x180002b22  sub     rsp, 0E8h
0x180002b29  mov     rax, cs:__security_cookie
0x180002b30  xor     rax, rsp
0x180002b33  mov     [rbp+3Fh+var_48], rax
0x180002b37  mov     rax, [rbp+3Fh+arg_28]
0x180002b3b  mov     rbx, r9
0x180002b3e  mov     rdi, [rbp+3Fh+arg_20]
0x180002b42  mov     r12, r8
0x180002b45  mov     [rbp+3Fh+var_88], rax
0x180002b49  mov     r13, rdx
0x180002b4c  mov     rax, [rbp+3Fh+arg_30]
0x180002b50  mov     r15, rcx
0x180002b53  mov     [rbp+3Fh+var_98], rax
0x180002b57  mov     edx, 2; unsigned int
0x180002b5c  mov     rax, [rbp+3Fh+arg_38]
0x180002b63  mov     ecx, 0E2212C2h; unsigned int
0x180002b68  mov     [rbp+3Fh+var_80], r8
0x180002b6c  lea     r8, aTraceEkclitpmg_0; "TRACE: EKCliTpmGetManufacturerInfo star"...
0x180002b73  mov     [rbp+3Fh+var_90], rax
0x180002b77  mov     [rbp+3Fh+var_70], rbx
0x180002b7b  mov     [rbp+3Fh+var_68], rdi
0x180002b7f  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002b84  xor     r8d, r8d
0x180002b87  xorps   xmm0, xmm0
0x180002b8a  mov     [rbp+3Fh+var_A8], r8
0x180002b8e  mov     eax, r8d
0x180002b91  mov     [rbp+3Fh+hMem], rax
0x180002b95  mov     esi, r8d
0x180002b98  mov     [rbp+3Fh+var_B0], rax
0x180002b9c  mov     r14d, r8d
0x180002b9f  mov     [rsp+120h+var_D8], rax
0x180002ba4  mov     [rbp+3Fh+var_A0], rax
0x180002ba8  mov     [rsp+120h+var_D0], rax
0x180002bad  mov     [rsp+120h+var_C0], rax
0x180002bb2  mov     [rbp+3Fh+var_50], rax
0x180002bb6  mov     [rsp+120h+pCertContext], r8
0x180002bbb  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x180002bbf  test    r15, r15
0x180002bc2  jz      loc_180003017
0x180002bc8  test    r13, r13
0x180002bcb  jz      loc_180003017
0x180002bd1  test    r12, r12
0x180002bd4  jz      loc_180003017
0x180002bda  test    rbx, rbx
0x180002bdd  jz      loc_180003017
0x180002be3  mov     rax, [rbp+3Fh+var_88]
0x180002be7  test    rax, rax
0x180002bea  jz      loc_180003017
0x180002bf0  test    rdi, rdi
0x180002bf3  jz      loc_180003017
0x180002bf9  mov     rdx, [rbp+3Fh+var_90]
0x180002bfd  test    rdx, rdx
0x180002c00  jz      loc_180003017
0x180002c06  mov     rcx, [rbp+3Fh+var_98]
0x180002c0a  test    rcx, rcx
0x180002c0d  jz      loc_180003017
0x180002c13  mov     [r13+0], r8
0x180002c17  mov     [r12], r8
0x180002c1b  mov     [rbx], r8d
0x180002c1e  mov     [rax], r8d
0x180002c21  mov     [rdi], r8
0x180002c24  mov     [rdx], r8d
0x180002c27  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180002c2e  mov     [rcx], r8
0x180002c31  mov     rcx, r15; String1
0x180002c34  call    cs:__imp__wcsicmp
0x180002c3a  test    eax, eax
0x180002c3c  jz      short loc_180002C67
0x180002c3e  mov     ebx, 0A0h
0x180002c43  lea     r8, aErrorInvalidKs; "ERROR: Invalid KSP.Ksp=%ws Return=%d\n"
0x180002c4a  xor     edi, edi
0x180002c4c  mov     dword ptr [rsp+120h+var_100], ebx
0x180002c50  mov     r9, r15
0x180002c53  mov     edx, 1; unsigned int
0x180002c58  mov     ecx, 0E4D12C2h; unsigned int
0x180002c5d  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002c62  jmp     loc_18000303C
0x180002c67  lea     r8, aTraceTpmendors_1; "TRACE: _TpmEndorsementKeyGetEkCertifica"...
0x180002c6e  mov     edx, 2; unsigned int
0x180002c73  mov     ecx, 5A012C2h; unsigned int
0x180002c78  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002c7d  xor     eax, eax
0x180002c7f  lea     rdx, [rbp+3Fh+hCertStore]; void **
0x180002c83  lea     rcx, [rsp+120h+var_C8]; void **
0x180002c88  mov     [rsp+120h+var_C8], rax
0x180002c8d  mov     [rbp+3Fh+hCertStore], rax
0x180002c91  mov     edi, eax
0x180002c93  call    ?_TpmEndorsementKeyGetEkCertificateStores@@YAJPEAPEAX0@Z; _TpmEndorsementKeyGetEkCertificateStores(void * *,void * *)
0x180002c98  mov     r12, [rsp+120h+var_C8]
0x180002c9d  mov     ebx, eax
0x180002c9f  mov     r15, [rbp+3Fh+hCertStore]
0x180002ca3  test    eax, eax
0x180002ca5  jz      short loc_180002CC5
0x180002ca7  mov     r9d, eax
0x180002caa  lea     r8, aErrorTpmendors_3; "ERROR: _TpmEndorsementKeyGetEkCertifica"...
0x180002cb1  mov     edx, 1; unsigned int
0x180002cb6  mov     ecx, 5B012C2h; unsigned int
0x180002cbb  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002cc0  jmp     loc_180002E08
0x180002cc5  lea     rdx, [rsp+120h+pCertContext]; struct _CERT_CONTEXT **
0x180002cca  mov     rcx, r12; hCertStore
0x180002ccd  call    ?_TpmGetCertificateFromStoreMatchingEkPub@@YAJPEAXPEAPEBU_CERT_CONTEXT@@@Z; _TpmGetCertificateFromStoreMatchingEkPub(void *,_CERT_CONTEXT const * *)
0x180002cd2  mov     ebx, eax
0x180002cd4  cmp     eax, 80070490h
0x180002cd9  jnz     short loc_180002CE9
0x180002cdb  mov     ecx, 5BB12C2h
0x180002ce0  lea     r8, aTraceTpmgetcer_2; "TRACE: _TpmGetCertificateFromStoreMatch"...
0x180002ce7  jmp     short loc_180002CFD
0x180002ce9  test    ebx, ebx
0x180002ceb  jnz     loc_180002DEA
0x180002cf1  mov     ecx, 5C012C2h; unsigned int
0x180002cf6  lea     r8, aTraceTpmgetcer_1; "TRACE: _TpmGetCertificateFromStoreMatch"...
0x180002cfd  mov     edx, 1; unsigned int
0x180002d02  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002d07  mov     r14, [rsp+120h+pCertContext]
0x180002d0c  test    r14, r14
0x180002d0f  jz      short loc_180002D3C
0x180002d11  mov     rcx, r14; pCertContext
0x180002d14  mov     dword ptr [rsp+120h+var_C8], 2
0x180002d1c  call    ?_GetVolatileCertIdString@@YAPEAGPEBU_CERT_CONTEXT@@@Z; _GetVolatileCertIdString(_CERT_CONTEXT const *)
0x180002d21  mov     r9, rax
0x180002d24  lea     r8, aTraceOnemanufa; "TRACE: OneManufacturerCert: %ws\n"
0x180002d2b  mov     edx, 2; unsigned int
0x180002d30  mov     ecx, 5CC12C2h; unsigned int
0x180002d35  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002d3a  jmp     short loc_180002D5D
0x180002d3c  mov     r9d, ebx
0x180002d3f  mov     dword ptr [rsp+120h+var_C8], 3
0x180002d47  lea     r8, aErrorTpmendors_0; "ERROR: _TpmEndorsementKeyGetEkCertifica"...
0x180002d4e  mov     edx, 1; unsigned int
0x180002d53  mov     ecx, 5D012C2h; unsigned int
0x180002d58  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002d5d  xor     edx, edx; pPrevCertContext
0x180002d5f  mov     rcx, r15; hCertStore
0x180002d62  call    cs:__imp_CertEnumCertificatesInStore
0x180002d68  mov     [rsp+120h+pCertContext], rax
0x180002d6d  test    rax, rax
0x180002d70  jz      short loc_180002DCB
0x180002d72  mov     ebx, edi
0x180002d74  cmp     edi, dword ptr [rsp+120h+var_C8]
0x180002d78  jnb     short loc_180002DCD
0x180002d7a  mov     rcx, rax; pCertContext
0x180002d7d  call    ?_GetVolatileCertIdString@@YAPEAGPEBU_CERT_CONTEXT@@@Z; _GetVolatileCertIdString(_CERT_CONTEXT const *)
0x180002d82  mov     r9, rax
0x180002d85  lea     r8, aTraceOthercert; "TRACE: OtherCert: %ws\n"
0x180002d8c  mov     edx, 2; unsigned int
0x180002d91  mov     ecx, 5E212C2h; unsigned int
0x180002d96  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002d9b  mov     rcx, [rsp+120h+pCertContext]; pCertContext
0x180002da0  call    cs:__imp_CertDuplicateCertificateContext
0x180002da6  mov     rdx, [rsp+120h+pCertContext]; pPrevCertContext
0x180002dab  mov     ecx, edi
0x180002dad  inc     edi
0x180002daf  mov     ebx, edi
0x180002db1  mov     [rbp+rcx*8+3Fh+var_60], rax
0x180002db6  mov     rcx, r15; hCertStore
0x180002db9  call    cs:__imp_CertEnumCertificatesInStore
0x180002dbf  mov     [rsp+120h+pCertContext], rax
0x180002dc4  test    rax, rax
0x180002dc7  jnz     short loc_180002D72
0x180002dc9  jmp     short loc_180002DCD
0x180002dcb  xor     ebx, ebx
0x180002dcd  mov     r9d, ebx
0x180002dd0  lea     r8, aTraceOtherekce; "TRACE: OtherEkCertificates. Count=%d\n"
0x180002dd7  mov     edx, 2; unsigned int
0x180002ddc  mov     ecx, 5E912C2h; unsigned int
0x180002de1  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002de6  xor     ebx, ebx
0x180002de8  jmp     short loc_180002E08
0x180002dea  mov     r9d, ebx
0x180002ded  lea     r8, aErrorTpmgetcer; "ERROR: _TpmGetCertificateFromStoreMatch"...
0x180002df4  mov     edx, 1; unsigned int
0x180002df9  mov     ecx, 5C512C2h; unsigned int
0x180002dfe  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002e03  mov     r14, [rsp+120h+pCertContext]
0x180002e08  test    r12, r12
0x180002e0b  jz      short loc_180002E18
0x180002e0d  xor     edx, edx; dwFlags
0x180002e0f  mov     rcx, r12; hCertStore
0x180002e12  call    cs:__imp_CertCloseStore
0x180002e18  test    r15, r15
0x180002e1b  jz      short loc_180002E28
0x180002e1d  xor     edx, edx; dwFlags
0x180002e1f  mov     rcx, r15; hCertStore
0x180002e22  call    cs:__imp_CertCloseStore
0x180002e28  lea     r8, aTraceTpmendors_2; "TRACE: _TpmEndorsementKeyGetEkCertifica"...
0x180002e2f  mov     edx, 2; unsigned int
0x180002e34  mov     ecx, 5F712C2h; unsigned int
0x180002e39  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002e3e  test    ebx, ebx
0x180002e40  jz      short loc_180002E64
0x180002e42  mov     r9d, ebx
0x180002e45  lea     r8, aErrorTpmendors_1; "ERROR: _TpmEndorsementKeyGetEkCertifica"...
0x180002e4c  mov     edx, 1; unsigned int
0x180002e51  mov     ecx, 0E5C12C2h; unsigned int
0x180002e56  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002e5b  mov     r12, [rbp+3Fh+var_80]
0x180002e5f  jmp     loc_18000303C
0x180002e64  mov     r12, [rbp+3Fh+var_68]
0x180002e68  mov     r15, [rbp+3Fh+var_70]
0x180002e6c  test    r14, r14
0x180002e6f  jz      short loc_180002ED2
0x180002e71  mov     rax, [rbp+3Fh+var_98]
0x180002e75  lea     r8, [rbp+3Fh+var_A0]; unsigned __int16 **
0x180002e79  mov     [rsp+120h+var_E8], rax; unsigned __int8 **
0x180002e7e  lea     rdx, [rbp+3Fh+var_A8]; unsigned __int16 **
0x180002e82  mov     rax, [rbp+3Fh+var_90]
0x180002e86  mov     r9, r15; enum EKCAIdType *
0x180002e89  mov     [rsp+120h+var_F0], rax; unsigned int *
0x180002e8e  mov     rcx, r14; pCertContext
0x180002e91  mov     rax, [rbp+3Fh+var_88]
0x180002e95  mov     [rsp+120h+var_F8], r12; unsigned __int8 **
0x180002e9a  mov     [rsp+120h+var_100], rax; unsigned int *
0x180002e9f  call    ?_GetManufacturerInfoFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAG1PEAW4EKCAIdType@@PEAKPEAPEAE34@Z; _GetManufacturerInfoFromCert(_CERT_CONTEXT const *,ushort * *,ushort * *,EKCAIdType *,ulong *,uchar * *,ulong *,uchar * *)
0x180002ea4  test    eax, eax
0x180002ea6  jz      loc_180002F59
0x180002eac  mov     r9d, eax
0x180002eaf  lea     r8, aErrorGetmanufa; "ERROR: _GetManufacturerInfoFromCert. Re"...
0x180002eb6  mov     edx, 1; unsigned int
0x180002ebb  mov     ecx, 0E7112C2h; unsigned int
0x180002ec0  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002ec5  mov     rax, [rbp+3Fh+var_A0]
0x180002ec9  mov     rsi, [rbp+3Fh+var_A8]
0x180002ecd  mov     [rsp+120h+var_D8], rax
0x180002ed2  mov     r9d, edi
0x180002ed5  lea     r8, aTraceManufactu; "TRACE: ManufacturerCert not found. Numb"...
0x180002edc  mov     edx, 2; unsigned int
0x180002ee1  mov     ecx, 0E7C12C2h; unsigned int
0x180002ee6  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002eeb  xor     ebx, ebx
0x180002eed  cmp     ebx, edi
0x180002eef  jnb     loc_180002FF3
0x180002ef5  mov     rcx, [rbp+rbx*8+3Fh+var_60]; pCertContext
0x180002efa  test    rcx, rcx
0x180002efd  jz      loc_180002FCE
0x180002f03  mov     rax, [rbp+3Fh+var_98]
0x180002f07  lea     r8, [rsp+120h+var_C0]; unsigned __int16 **
0x180002f0c  mov     [rsp+120h+var_E8], rax; unsigned __int8 **
0x180002f11  lea     rdx, [rbp+3Fh+var_B0]; unsigned __int16 **
0x180002f15  mov     rax, [rbp+3Fh+var_90]
0x180002f19  mov     r9, r15; enum EKCAIdType *
0x180002f1c  mov     [rsp+120h+var_F0], rax; unsigned int *
0x180002f21  mov     rax, [rbp+3Fh+var_88]
0x180002f25  mov     [rsp+120h+var_F8], r12; unsigned __int8 **
0x180002f2a  mov     [rsp+120h+var_100], rax; unsigned int *
0x180002f2f  call    ?_GetManufacturerInfoFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAG1PEAW4EKCAIdType@@PEAKPEAPEAE34@Z; _GetManufacturerInfoFromCert(_CERT_CONTEXT const *,ushort * *,ushort * *,EKCAIdType *,ulong *,uchar * *,ulong *,uchar * *)
0x180002f34  test    rsi, rsi
0x180002f37  jnz     short loc_180002F74
0x180002f39  mov     rsi, [rbp+3Fh+var_B0]
0x180002f3d  xor     edx, edx
0x180002f3f  mov     rcx, [rsp+120h+var_C0]
0x180002f44  mov     [rbp+3Fh+hMem], rdx
0x180002f48  test    rsi, rsi
0x180002f4b  jnz     short loc_180002F81
0x180002f4d  mov     [rsp+120h+var_D8], rcx
0x180002f52  mov     [rsp+120h+var_D0], rdx
0x180002f57  jmp     short loc_180002F86
0x180002f59  mov     rax, [rbp+3Fh+var_A0]
0x180002f5d  lea     r8, aTraceManufactu_0; "TRACE: ManufacturerInfo found. _TpmEndo"...
0x180002f64  mov     rsi, [rbp+3Fh+var_A8]
0x180002f68  mov     ecx, 0E7512C2h
0x180002f6d  mov     [rsp+120h+var_D8], rax
0x180002f72  jmp     short loc_180002FE1
0x180002f74  mov     rcx, [rbp+3Fh+var_B0]
0x180002f78  mov     [rbp+3Fh+hMem], rcx
0x180002f7c  mov     rcx, [rsp+120h+var_C0]
0x180002f81  mov     [rsp+120h+var_D0], rcx
0x180002f86  test    eax, eax
0x180002f88  jz      short loc_180002FD5
0x180002f8a  mov     r9d, eax
0x180002f8d  lea     r8, aErrorGetmanufa; "ERROR: _GetManufacturerInfoFromCert. Re"...
0x180002f94  mov     edx, 1; unsigned int
0x180002f99  mov     ecx, 0E9E12C2h; unsigned int
0x180002f9e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002fa3  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180002fa7  call    cs:__imp_LocalFree
0x180002fad  mov     rcx, [rsp+120h+var_D0]; hMem
0x180002fb2  xor     eax, eax
0x180002fb4  mov     [rbp+3Fh+hMem], rax
0x180002fb8  mov     [rbp+3Fh+var_B0], rax
0x180002fbc  call    cs:__imp_LocalFree
0x180002fc2  xor     eax, eax
0x180002fc4  mov     [rsp+120h+var_D0], rax
0x180002fc9  mov     [rsp+120h+var_C0], rax
0x180002fce  inc     ebx
0x180002fd0  jmp     loc_180002EED
0x180002fd5  mov     ecx, 0E9A12C2h; unsigned int
0x180002fda  lea     r8, aTraceManufactu_1; "TRACE: ManufacturerCert found from rgEK"...
0x180002fe1  mov     edx, 2; unsigned int
0x180002fe6  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002feb  mov     r12, [rbp+3Fh+var_80]
  ... truncated ...
```
