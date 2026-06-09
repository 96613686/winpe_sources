# _GetIssuerId(_CERT_CONTEXT const *,EKCAIdType *,uchar * *,ulong *)

- ea: `0x180002310`
- end: `0x180002845`
- name: `?_GetIssuerId@@YAKPEBU_CERT_CONTEXT@@PEAW4EKCAIdType@@PEAPEAEPEAK@Z`
- size: `1333`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, enum EKCAIdType *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800030f0`

## callees

- `0x180001060`
- `0x180002310`
- `0x180003750`
- `0x180003ab0`
- `0x180005998`
- `0x180005a20`
- `0x180005ac0`
- `0x18000a7c2`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18000280c`
- `CRYPT32!CertFreeCertificateContext` at `0x180002828`
- `CRYPT32!CertFreeCertificateContext` at `0x18000280c`
- `CRYPT32!CertFreeCertificateContext` at `0x180002828`
- `CRYPT32!CertGetCertificateChain` at `0x1800023e0`
- `CRYPT32!CertGetCertificateChain` at `0x1800023e0`
- `CRYPT32!CertFindExtension` at `0x180002459`
- `CRYPT32!CertFindExtension` at `0x180002459`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000249c`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000249c`
- `CRYPT32!CertCloseStore` at `0x1800027fe`
- `CRYPT32!CertCloseStore` at `0x1800027fe`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180002383`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180002383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000271d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000276c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000281a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000271d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000276c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000281a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002795`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024bf`

## pseudocode

```c
__int64 __fastcall _GetIssuerId(
        PCCERT_CONTEXT pCertContext,
        enum EKCAIdType *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  BYTE *v4; // r12
  const CERT_CONTEXT *v6; // rbx
  HCERTSTORE v7; // rsi
  unsigned int IntermediateCertificateStore; // eax
  HCERTSTORE v9; // rdi
  __int64 LastError; // r13
  const CERT_CONTEXT *v11; // r14
  PCCERT_CONTEXT v12; // rax
  void *v13; // r9
  DWORD v14; // r15d
  void *v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  DWORD v21; // eax
  HCERTSTORE v22; // rcx
  DWORD v23; // edx
  unsigned __int16 *VolatileHexString; // rax
  enum EKCAIdType *v25; // r13
  PCERT_INFO pCertInfo; // rcx
  unsigned int v27; // eax
  unsigned __int16 *v28; // rax
  const char *v29; // r8
  unsigned int v30; // ecx
  const struct _CERT_CONTEXT *HighestCertInChainAlsoInStore; // rax
  unsigned int KeyIdentifierFromCertificate; // eax
  unsigned int v33; // ecx
  HLOCAL v34; // r15
  void *v35; // rcx
  unsigned __int16 *v36; // rax
  HLOCAL v37; // rax
  void *v38; // rcx
  HLOCAL v39; // r15
  unsigned __int16 *v40; // rax
  unsigned __int8 *v41; // rax
  HLOCAL hMem; // [rsp+40h] [rbp-79h] BYREF
  DWORD pcbStructInfo; // [rsp+48h] [rbp-71h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v46; // [rsp+58h] [rbp-61h]
  PCCERT_CHAIN_CONTEXT ppChainContext; // [rsp+60h] [rbp-59h] BYREF
  HLOCAL v48; // [rsp+68h] [rbp-51h]
  _BYTE pChainPara[36]; // [rsp+70h] [rbp-49h] BYREF
  __int128 v50; // [rsp+94h] [rbp-25h]
  __int128 v51; // [rsp+A4h] [rbp-15h]
  _BYTE v52[28]; // [rsp+B4h] [rbp-5h] BYREF

  v4 = 0;
  v6 = 0;
  *a3 = 0;
  hMem = 0;
  v7 = 0;
  hCertStore = 0;
  IntermediateCertificateStore = _TpmEndorsementKeyGetIntermediateCertificateStore(&hCertStore);
  v9 = hCertStore;
  LODWORD(LastError) = IntermediateCertificateStore;
  if ( IntermediateCertificateStore )
  {
    v11 = 0;
    ekTraceFmt(
      0xC6E12C2u,
      1,
      "ERROR: _TpmEndorsementKeyGetIntermediateCertificateStore. Return=%d\n",
      IntermediateCertificateStore);
    goto LABEL_57;
  }
  v12 = CertEnumCertificatesInStore(hCertStore, 0);
  ppChainContext = 0;
  *(_DWORD *)pChainPara = 96;
  v11 = v12;
  v13 = 0;
  if ( v12 )
    v13 = v9;
  memset(v52, 0, sizeof(v52));
  memset(&pChainPara[4], 0, 32);
  v50 = 0;
  v51 = 0;
  if ( !CertGetCertificateChain(0, pCertContext, 0, v13, (PCERT_CHAIN_PARA)pChainPara, 0, 0, &ppChainContext) )
  {
    LastError = GetLastError();
    ekTraceFmt(0xC8612C2u, 1, "ERROR: CertGetCertificateChain. Return=%d\n", LastError);
    goto LABEL_57;
  }
  v14 = 0;
  if ( ppChainContext->cChain )
  {
    v15 = *ppChainContext->rgpChain;
    v16 = 0;
    v48 = v15;
    while ( 1 )
    {
      v46 = v16;
      if ( v16 >= *((_DWORD *)v15 + 3) )
        goto LABEL_24;
      LODWORD(LastError) = 0;
      v17 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v15 + 2) + 8LL * v16) + 8LL) + 24LL);
      Extension = CertFindExtension("1.3.6.1.4.1.311.21.43", *(_DWORD *)(v17 + 192), *(CERT_EXTENSION **)(v17 + 200));
      if ( !Extension )
        goto LABEL_14;
      cbData = Extension->Value.cbData;
      pbData = Extension->Value.pbData;
      hCertStore = 0;
      pcbStructInfo = 0;
      if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x19, pbData, cbData, 0x8001u, 0, &hCertStore, &pcbStructInfo) )
        break;
      if ( hCertStore )
      {
        v4 = (BYTE *)*((_QWORD *)hCertStore + 1);
        v7 = hCertStore;
        v14 = *(_DWORD *)hCertStore;
        v23 = *(_DWORD *)hCertStore;
        *(_DWORD *)a2 = 3;
        VolatileHexString = _GetVolatileHexString(v4, v23);
        ekTraceFmt(0xCB112C2u, 2, "TRACE: EKCAKeyId: %ws\n", VolatileHexString);
        if ( !v14 || !v4 )
          goto LABEL_24;
        goto LABEL_19;
      }
LABEL_15:
      v15 = v48;
      v16 = v46 + 1;
    }
    ekTraceFmt(0xC1012C2u, 1, "ERROR: CryptDecodeObjectEx. Return=%d\n", 0);
    v21 = GetLastError();
    v22 = hCertStore;
    LODWORD(LastError) = v21;
    hCertStore = 0;
    if ( v22 )
      LocalFree(v22);
LABEL_14:
    if ( (_DWORD)LastError )
    {
      v29 = "ERROR: _GetKeyIdentifierFromCertificate. Return=%d\n";
      v30 = 212210370;
      goto LABEL_56;
    }
    goto LABEL_15;
  }
LABEL_24:
  if ( !v11
    || (HighestCertInChainAlsoInStore = _GetHighestCertInChainAlsoInStore(ppChainContext, v9),
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
          &hMem,
          HighestCertInChainAlsoInStore),
        (v6 = (const CERT_CONTEXT *)hMem) == 0) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
      &hMem,
      pCertContext);
    v6 = (const CERT_CONTEXT *)hMem;
  }
  if ( v14 && v4 )
    goto LABEL_19;
  hMem = 0;
  KeyIdentifierFromCertificate = _GetKeyIdentifierFromCertificate(
                                   v6,
                                   "2.5.29.35",
                                   (const char *)0x1F,
                                   (struct _CRYPTOAPI_BLOB **)&hMem);
  LODWORD(LastError) = KeyIdentifierFromCertificate;
  if ( KeyIdentifierFromCertificate )
  {
    v33 = 215880386;
    goto LABEL_31;
  }
  if ( hMem )
  {
    v34 = hMem;
    v35 = v7;
    v7 = hMem;
    if ( v35 )
      LocalFree(v35);
    v4 = (BYTE *)*((_QWORD *)v34 + 1);
    v14 = *(_DWORD *)v34;
    *(_DWORD *)a2 = 2;
    v36 = _GetVolatileHexString(v4, v14);
    ekTraceFmt(0xCE912C2u, 2, "TRACE: KeyId2: %ws\n", v36);
  }
  if ( v14 && v4 )
  {
LABEL_19:
    v25 = a2;
LABEL_20:
    if ( v4 )
    {
LABEL_52:
      v41 = (unsigned __int8 *)LocalAlloc(0x40u, v14);
      *a3 = v41;
      if ( v41 )
      {
        memcpy_0(v41, v4, v14);
        LODWORD(LastError) = 0;
        *a4 = v14;
        goto LABEL_57;
      }
      LODWORD(LastError) = 14;
      v29 = "ERROR: MIDL_user_allocate. Return=%d\n";
      v30 = 221123266;
      goto LABEL_56;
    }
LABEL_21:
    pCertInfo = v6->pCertInfo;
    v27 = pCertInfo->Issuer.cbData;
    if ( v27 <= 2 )
    {
      if ( !v14 )
        goto LABEL_55;
    }
    else
    {
      v4 = pCertInfo->Issuer.pbData;
      *(_DWORD *)v25 = 1;
      v14 = v27;
      ekTraceFmt(0xD1912C2u, 2, "TRACE: NameId\n");
      v28 = _GetVolatileHexString(v4, v14);
      ekTraceFmt(0xD1B12C2u, 2, "TRACE: NameId: %ws\n", v28);
    }
    if ( v4 )
      goto LABEL_52;
LABEL_55:
    LODWORD(LastError) = -2146889715;
    v29 = "ERROR: No AKI. Return=%d\n";
    v30 = 220664514;
LABEL_56:
    ekTraceFmt(v30, 1, v29, (unsigned int)LastError);
    goto LABEL_57;
  }
  hMem = 0;
  KeyIdentifierFromCertificate = _GetKeyIdentifierFromCertificate(
                                   v6,
                                   "2.5.29.1",
                                   (const char *)9,
                                   (struct _CRYPTOAPI_BLOB **)&hMem);
  LODWORD(LastError) = KeyIdentifierFromCertificate;
  if ( !KeyIdentifierFromCertificate )
  {
    v37 = hMem;
    if ( hMem )
    {
      v38 = v7;
      v48 = 0;
      v39 = hMem;
      v7 = hMem;
      if ( v38 )
        LocalFree(v38);
      v4 = (BYTE *)*((_QWORD *)v39 + 1);
      v14 = *(_DWORD *)v39;
      v25 = a2;
      *(_DWORD *)a2 = 2;
      v40 = _GetVolatileHexString(v4, v14);
      ekTraceFmt(0xD0912C2u, 2, "TRACE: KeyId: %ws\n", v40);
      v37 = v48;
    }
    else
    {
      v25 = a2;
    }
    if ( v37 )
      LocalFree(v37);
    if ( !v14 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v33 = 217977538;
LABEL_31:
  ekTraceFmt(v33, 1, "ERROR: _GetKeyIdentifierFromCertificate. Return=%d\n", KeyIdentifierFromCertificate);
  if ( hMem )
    LocalFree(hMem);
LABEL_57:
  if ( v9 )
    CertCloseStore(v9, 0);
  if ( v11 )
    CertFreeCertificateContext(v11);
  if ( v7 )
    LocalFree(v7);
  if ( v6 )
    CertFreeCertificateContext(v6);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180002310  mov     [rsp-8+arg_18], r9
0x180002315  mov     [rsp-8+arg_10], r8
0x18000231a  mov     [rsp-8+arg_8], rdx
0x18000231f  mov     [rsp-8+arg_0], rcx
0x180002324  push    rbp
0x180002325  push    rbx
0x180002326  push    rsi
0x180002327  push    rdi
0x180002328  push    r12
0x18000232a  push    r13
0x18000232c  push    r14
0x18000232e  push    r15
0x180002330  lea     rbp, [rsp-1Fh]
0x180002335  sub     rsp, 0D8h
0x18000233c  xor     r12d, r12d
0x18000233f  mov     r15, rcx
0x180002342  mov     ebx, r12d
0x180002345  mov     [r8], r12
0x180002348  lea     rcx, [rbp+57h+hCertStore]; void **
0x18000234c  mov     [rbp+57h+hMem], rbx
0x180002350  mov     esi, r12d
0x180002353  mov     [rbp+57h+hCertStore], r12
0x180002357  call    ?_TpmEndorsementKeyGetIntermediateCertificateStore@@YAJPEAPEAX@Z; _TpmEndorsementKeyGetIntermediateCertificateStore(void * *)
0x18000235c  mov     rdi, [rbp+57h+hCertStore]
0x180002360  mov     r13d, eax
0x180002363  test    eax, eax
0x180002365  jz      short loc_18000237E
0x180002367  mov     r14d, r12d
0x18000236a  lea     r8, aErrorTpmendors; "ERROR: _TpmEndorsementKeyGetIntermediat"...
0x180002371  mov     r9d, eax
0x180002374  mov     ecx, 0C6E12C2h
0x180002379  jmp     loc_1800027EA
0x18000237e  xor     edx, edx; pPrevCertContext
0x180002380  mov     rcx, rdi; hCertStore
0x180002383  call    cs:__imp_CertEnumCertificatesInStore
0x180002389  xorps   xmm0, xmm0
0x18000238c  mov     [rbp+57h+var_B0], r12
0x180002390  test    rax, rax
0x180002393  mov     dword ptr [rbp+57h+var_A0], 60h ; '`'
0x18000239a  mov     r14, rax
0x18000239d  mov     r9, r12
0x1800023a0  cmovnz  r9, rdi; hAdditionalStore
0x1800023a4  lea     rax, [rbp+57h+var_B0]
0x1800023a8  mov     [rsp+110h+ppChainContext], rax; ppChainContext
0x1800023ad  xor     r8d, r8d; pTime
0x1800023b0  mov     [rsp+110h+pvReserved], r12; pvReserved
0x1800023b5  lea     rax, [rbp+57h+var_A0]
0x1800023b9  movups  xmmword ptr [rbp+57h+var_5C], xmm0
0x1800023bd  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x1800023c2  mov     rdx, r15; pCertContext
0x1800023c5  xor     ecx, ecx; hChainEngine
0x1800023c7  mov     [rsp+110h+pChainPara], rax; pChainPara
0x1800023cc  movups  xmmword ptr [rbp+57h+var_A0+4], xmm0
0x1800023d0  movups  xmmword ptr [rbp+57h+var_A0+14h], xmm0
0x1800023d4  movups  [rbp+57h+var_7C], xmm0
0x1800023d8  movups  [rbp+57h+var_6C], xmm0
0x1800023dc  movups  xmmword ptr [rbp+57h+var_5C+0Ch], xmm0
0x1800023e0  call    cs:__imp_CertGetCertificateChain
0x1800023e6  test    eax, eax
0x1800023e8  jnz     short loc_180002407
0x1800023ea  call    cs:__imp_GetLastError
0x1800023f0  lea     r8, aErrorCertgetce_0; "ERROR: CertGetCertificateChain. Return="...
0x1800023f7  mov     ecx, 0C8612C2h
0x1800023fc  mov     r13d, eax
0x1800023ff  mov     r9d, eax
0x180002402  jmp     loc_1800027EA
0x180002407  mov     rax, [rbp+57h+var_B0]
0x18000240b  xor     r15d, r15d
0x18000240e  cmp     [rax+0Ch], ebx
0x180002411  jbe     loc_1800025BD
0x180002417  mov     rax, [rax+10h]
0x18000241b  mov     rdx, [rax]
0x18000241e  xor     eax, eax
0x180002420  mov     [rbp+57h+var_A8], rdx
0x180002424  mov     [rbp+57h+var_B8], eax
0x180002427  cmp     eax, [rdx+0Ch]
0x18000242a  jnb     loc_1800025BD
0x180002430  mov     ecx, eax
0x180002432  xor     r13d, r13d
0x180002435  mov     rax, [rdx+10h]
0x180002439  mov     rcx, [rax+rcx*8]
0x18000243d  mov     rax, [rcx+8]
0x180002441  lea     rcx, pszObjId; "1.3.6.1.4.1.311.21.43"
0x180002448  mov     rdx, [rax+18h]
0x18000244c  mov     r8, [rdx+0C8h]; rgExtensions
0x180002453  mov     edx, [rdx+0C0h]; cExtensions
0x180002459  call    cs:__imp_CertFindExtension
0x18000245f  test    rax, rax
0x180002462  jz      short loc_1800024DB
0x180002464  mov     r9d, [rax+10h]; cbEncoded
0x180002468  lea     rcx, [rbp+57h+pcbStructInfo]
0x18000246c  mov     r8, [rax+18h]; pbEncoded
0x180002470  mov     edx, 19h; lpszStructType
0x180002475  mov     [rsp+110h+ppChainContext], rcx; pcbStructInfo
0x18000247a  lea     rcx, [rbp+57h+hCertStore]
0x18000247e  mov     [rsp+110h+pvReserved], rcx; pvStructInfo
0x180002483  mov     ecx, 1; dwCertEncodingType
0x180002488  mov     qword ptr [rsp+110h+dwFlags], rbx; pDecodePara
0x18000248d  mov     dword ptr [rsp+110h+pChainPara], 8001h; dwFlags
0x180002495  mov     [rbp+57h+hCertStore], rbx
0x180002499  mov     [rbp+57h+pcbStructInfo], ebx
0x18000249c  call    cs:__imp_CryptDecodeObjectEx
0x1800024a2  test    eax, eax
0x1800024a4  jnz     short loc_1800024F2
0x1800024a6  xor     r9d, r9d
0x1800024a9  lea     r8, aErrorCryptdeco_0; "ERROR: CryptDecodeObjectEx. Return=%d\n"
0x1800024b0  mov     edx, 1; unsigned int
0x1800024b5  mov     ecx, 0C1012C2h; unsigned int
0x1800024ba  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800024bf  call    cs:__imp_GetLastError
0x1800024c5  mov     rcx, [rbp+57h+hCertStore]; hMem
0x1800024c9  mov     r13d, eax
0x1800024cc  mov     [rbp+57h+hCertStore], rbx
0x1800024d0  test    rcx, rcx
0x1800024d3  jz      short loc_1800024DB
0x1800024d5  call    cs:__imp_LocalFree
0x1800024db  test    r13d, r13d
0x1800024de  jnz     loc_1800025AC
0x1800024e4  mov     eax, [rbp+57h+var_B8]
0x1800024e7  mov     rdx, [rbp+57h+var_A8]
0x1800024eb  inc     eax
0x1800024ed  jmp     loc_180002424
0x1800024f2  mov     rax, [rbp+57h+hCertStore]
0x1800024f6  test    rax, rax
0x1800024f9  jz      short loc_1800024E4
0x1800024fb  mov     r12, [rax+8]
0x1800024ff  mov     rsi, rax
0x180002502  mov     r15d, [rax]
0x180002505  mov     rcx, r12; pbBinary
0x180002508  mov     rax, [rbp+57h+arg_8]
0x18000250c  mov     edx, r15d; cbBinary
0x18000250f  mov     dword ptr [rax], 3
0x180002515  call    ?_GetVolatileHexString@@YAPEAGPEBEK@Z; _GetVolatileHexString(uchar const *,ulong)
0x18000251a  mov     r9, rax
0x18000251d  lea     r8, aTraceEkcakeyid; "TRACE: EKCAKeyId: %ws\n"
0x180002524  mov     edx, 2; unsigned int
0x180002529  mov     ecx, 0CB112C2h; unsigned int
0x18000252e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002533  test    r15d, r15d
0x180002536  jz      loc_1800025BD
0x18000253c  test    r12, r12
0x18000253f  jz      short loc_1800025BD
0x180002541  mov     r13, [rbp+57h+arg_8]
0x180002545  test    r12, r12
0x180002548  jnz     loc_18000278A
0x18000254e  mov     rcx, [rbx+18h]
0x180002552  mov     eax, [rcx+30h]
0x180002555  cmp     eax, 2
0x180002558  jbe     loc_180002780
0x18000255e  mov     r12, [rcx+38h]
0x180002562  lea     r8, aTraceNameid; "TRACE: NameId\n"
0x180002569  mov     ecx, 0D1912C2h; unsigned int
0x18000256e  mov     dword ptr [r13+0], 1
0x180002576  mov     edx, 2; unsigned int
0x18000257b  mov     r15d, eax
0x18000257e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002583  mov     edx, r15d; cbBinary
0x180002586  mov     rcx, r12; pbBinary
0x180002589  call    ?_GetVolatileHexString@@YAPEAGPEBEK@Z; _GetVolatileHexString(uchar const *,ulong)
0x18000258e  mov     r9, rax
0x180002591  lea     r8, aTraceNameidWs; "TRACE: NameId: %ws\n"
0x180002598  mov     edx, 2; unsigned int
0x18000259d  mov     ecx, 0D1B12C2h; unsigned int
0x1800025a2  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800025a7  jmp     loc_180002785
0x1800025ac  lea     r8, aErrorGetkeyide; "ERROR: _GetKeyIdentifierFromCertificate"...
0x1800025b3  mov     ecx, 0CA612C2h
0x1800025b8  jmp     loc_1800027E7
0x1800025bd  test    r14, r14
0x1800025c0  jz      short loc_1800025E3
0x1800025c2  mov     rcx, [rbp+57h+var_B0]; struct _CERT_CHAIN_CONTEXT *
0x1800025c6  mov     rdx, rdi; void *
0x1800025c9  call    ?_GetHighestCertInChainAlsoInStore@@YAPEBU_CERT_CONTEXT@@PEBU_CERT_CHAIN_CONTEXT@@PEAX@Z; _GetHighestCertInChainAlsoInStore(_CERT_CHAIN_CONTEXT const *,void *)
0x1800025ce  mov     rdx, rax
0x1800025d1  lea     rcx, [rbp+57h+hMem]
0x1800025d5  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x1800025da  mov     rbx, [rbp+57h+hMem]
0x1800025de  test    rbx, rbx
0x1800025e1  jnz     short loc_1800025F4
0x1800025e3  mov     rdx, [rbp+57h+arg_0]
0x1800025e7  lea     rcx, [rbp+57h+hMem]
0x1800025eb  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x1800025f0  mov     rbx, [rbp+57h+hMem]
0x1800025f4  test    r15d, r15d
0x1800025f7  jz      short loc_180002602
0x1800025f9  test    r12, r12
0x1800025fc  jnz     loc_180002541
0x180002602  lea     r9, [rbp+57h+hMem]; struct _CRYPTOAPI_BLOB **
0x180002606  mov     [rbp+57h+hMem], 0
0x18000260e  mov     r8d, 1Fh; char *
0x180002614  lea     rdx, a252935; "2.5.29.35"
0x18000261b  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18000261e  call    ?_GetKeyIdentifierFromCertificate@@YAKPEBU_CERT_CONTEXT@@PEBD1PEAPEAU_CRYPTOAPI_BLOB@@@Z; _GetKeyIdentifierFromCertificate(_CERT_CONTEXT const *,char const *,char const *,_CRYPTOAPI_BLOB * *)
0x180002623  mov     r13d, eax
0x180002626  test    eax, eax
0x180002628  jz      short loc_18000265B
0x18000262a  mov     ecx, 0CDE12C2h; unsigned int
0x18000262f  mov     edx, 1; unsigned int
0x180002634  lea     r8, aErrorGetkeyide; "ERROR: _GetKeyIdentifierFromCertificate"...
0x18000263b  mov     r9d, eax
0x18000263e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002643  mov     rcx, [rbp+57h+hMem]; hMem
0x180002647  test    rcx, rcx
0x18000264a  jz      loc_1800027F4
0x180002650  call    cs:__imp_LocalFree
0x180002656  jmp     loc_1800027F4
0x18000265b  mov     r13, [rbp+57h+hMem]
0x18000265f  test    r13, r13
0x180002662  jz      short loc_1800026BE
0x180002664  mov     r15, r13
0x180002667  mov     rcx, rsi; hMem
0x18000266a  xor     r13d, r13d
0x18000266d  mov     rsi, r15
0x180002670  test    rcx, rcx
0x180002673  jz      short loc_18000267B
0x180002675  call    cs:__imp_LocalFree
0x18000267b  mov     r12, [r15+8]
0x18000267f  mov     r15d, [r15]
0x180002682  mov     rcx, r12; pbBinary
0x180002685  mov     rax, [rbp+57h+arg_8]
0x180002689  mov     edx, r15d; cbBinary
0x18000268c  mov     dword ptr [rax], 2
0x180002692  call    ?_GetVolatileHexString@@YAPEAGPEBEK@Z; _GetVolatileHexString(uchar const *,ulong)
0x180002697  mov     r9, rax
0x18000269a  lea     r8, aTraceKeyid2Ws; "TRACE: KeyId2: %ws\n"
0x1800026a1  mov     edx, 2; unsigned int
0x1800026a6  mov     ecx, 0CE912C2h; unsigned int
0x1800026ab  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800026b0  test    r13, r13
0x1800026b3  jz      short loc_1800026BE
0x1800026b5  mov     rcx, r13; hMem
0x1800026b8  call    cs:__imp_LocalFree
0x1800026be  test    r15d, r15d
0x1800026c1  jz      short loc_1800026CC
0x1800026c3  test    r12, r12
0x1800026c6  jnz     loc_180002541
0x1800026cc  lea     r9, [rbp+57h+hMem]; struct _CRYPTOAPI_BLOB **
0x1800026d0  mov     [rbp+57h+hMem], 0
0x1800026d8  mov     r8d, 9; char *
0x1800026de  lea     rdx, a25291; "2.5.29.1"
0x1800026e5  mov     rcx, rbx; struct _CERT_CONTEXT *
0x1800026e8  call    ?_GetKeyIdentifierFromCertificate@@YAKPEBU_CERT_CONTEXT@@PEBD1PEAPEAU_CRYPTOAPI_BLOB@@@Z; _GetKeyIdentifierFromCertificate(_CERT_CONTEXT const *,char const *,char const *,_CRYPTOAPI_BLOB * *)
0x1800026ed  mov     r13d, eax
0x1800026f0  test    eax, eax
0x1800026f2  jz      short loc_1800026FE
0x1800026f4  mov     ecx, 0CFE12C2h
0x1800026f9  jmp     loc_18000262F
0x1800026fe  mov     rax, [rbp+57h+hMem]
0x180002702  test    rax, rax
0x180002705  jz      short loc_180002760
0x180002707  mov     rcx, rsi; hMem
0x18000270a  mov     [rbp+57h+var_A8], 0
0x180002712  mov     r15, rax
0x180002715  mov     rsi, rax
0x180002718  test    rcx, rcx
0x18000271b  jz      short loc_180002723
0x18000271d  call    cs:__imp_LocalFree
0x180002723  mov     r12, [r15+8]
0x180002727  mov     r15d, [r15]
0x18000272a  mov     rcx, r12; pbBinary
0x18000272d  mov     r13, [rbp+57h+arg_8]
0x180002731  mov     edx, r15d; cbBinary
0x180002734  mov     dword ptr [r13+0], 2
0x18000273c  call    ?_GetVolatileHexString@@YAPEAGPEBEK@Z; _GetVolatileHexString(uchar const *,ulong)
0x180002741  mov     r9, rax
0x180002744  lea     r8, aTraceKeyidWs; "TRACE: KeyId: %ws\n"
0x18000274b  mov     edx, 2; unsigned int
0x180002750  mov     ecx, 0D0912C2h; unsigned int
0x180002755  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000275a  mov     rax, [rbp+57h+var_A8]
0x18000275e  jmp     short loc_180002764
0x180002760  mov     r13, [rbp+57h+arg_8]
0x180002764  test    rax, rax
0x180002767  jz      short loc_180002772
0x180002769  mov     rcx, rax; hMem
0x18000276c  call    cs:__imp_LocalFree
0x180002772  test    r15d, r15d
0x180002775  jz      loc_18000254E
0x18000277b  jmp     loc_180002545
0x180002780  test    r15d, r15d
0x180002783  jz      short loc_1800027D5
0x180002785  test    r12, r12
0x180002788  jz      short loc_1800027D5
0x18000278a  mov     edx, r15d; uBytes
0x18000278d  mov     ecx, 40h ; '@'; uFlags
0x180002792  mov     r13d, r15d
0x180002795  call    cs:__imp_LocalAlloc
0x18000279b  mov     rcx, [rbp+57h+arg_10]
0x18000279f  mov     [rcx], rax
0x1800027a2  test    rax, rax
0x1800027a5  jnz     short loc_1800027BB
0x1800027a7  mov     r13d, 0Eh
0x1800027ad  lea     r8, aErrorMidlUserA_0; "ERROR: MIDL_user_allocate. Return=%d\n"
0x1800027b4  mov     ecx, 0D2E12C2h
0x1800027b9  jmp     short loc_1800027E7
0x1800027bb  mov     r8, r13; Size
0x1800027be  mov     rdx, r12; Src
0x1800027c1  mov     rcx, rax; void *
0x1800027c4  call    memcpy_0
0x1800027c9  mov     rax, [rbp+57h+arg_18]
  ... truncated ...
```
