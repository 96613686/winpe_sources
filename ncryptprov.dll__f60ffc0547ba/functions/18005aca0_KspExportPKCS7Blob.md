# KspExportPKCS7Blob

- ea: `0x18005aca0`
- end: `0x18005b330`
- name: `KspExportPKCS7Blob`
- size: `1680`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180029600`

## callees

- `0x1800086d0`
- `0x18000af80`
- `0x180038970`
- `0x18005a2e4`
- `0x18005aca0`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005af59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005af59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b212`
- `CRYPT32!CertCloseStore` at `0x18005b2d9`
- `CRYPT32!CertCloseStore` at `0x18005b2d9`
- `CRYPT32!CertOpenStore` at `0x18005af45`
- `CRYPT32!CertOpenStore` at `0x18005af45`
- `CRYPT32!CertFreeCertificateContext` at `0x18005b241`
- `CRYPT32!CertFreeCertificateContext` at `0x18005b241`
- `CRYPT32!CryptEncryptMessage` at `0x18005b185`
- `CRYPT32!CryptEncryptMessage` at `0x18005b202`
- `CRYPT32!CryptEncryptMessage` at `0x18005b185`
- `CRYPT32!CryptEncryptMessage` at `0x18005b202`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005af8f`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005afb0`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005b093`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005af8f`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005afb0`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18005b093`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005b0aa`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005b0aa`

## string_xrefs

- `0x18005aefc`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005af6b`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b0d7`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b1a9`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b287`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`
- `0x18005b2f7`: `onecore\ds\security\cryptoapi\ncrypt\storage\deprecate.c`

## pseudocode

```c
__int64 __fastcall KspExportPKCS7Blob(__int64 a1, int a2, BYTE *a3, DWORD a4, DWORD *a5, int a6)
{
  __int64 v6; // r12
  bool v9; // zf
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  const wchar_t *v13; // rdi
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned __int64 v17; // rbx
  DWORD *p_cbToBeEncrypted; // rsi
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  DWORD *v24; // rax
  unsigned int v25; // eax
  void *v26; // r13
  HCERTSTORE v27; // rax
  DWORD LastError; // eax
  const CERT_CONTEXT *v29; // r14
  __int64 v30; // rdx
  unsigned __int64 v31; // rbx
  DWORD *v32; // rdi
  unsigned __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  void *v36; // rsp
  void *v37; // rsp
  DWORD *v38; // rax
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 i; // rbx
  const CERT_CONTEXT *v42; // rax
  PCCERT_CONTEXT v43; // rax
  DWORD v44; // eax
  __int64 v45; // r9
  BYTE *v46; // rdx
  CHAR *v47; // r8
  DWORD v48; // ecx
  DWORD v49; // eax
  __int64 v50; // r9
  DWORD v51; // eax
  __int64 v52; // r15
  const CERT_CONTEXT *v53; // rcx
  __int64 v54; // rax
  DWORD *v55; // rcx
  _BYTE v57[32]; // [rsp+0h] [rbp-40h] BYREF
  DWORD cbToBeEncrypted; // [rsp+40h] [rbp+0h] BYREF
  DWORD pcbEncryptedBlob; // [rsp+44h] [rbp+4h] BYREF
  DWORD v60; // [rsp+48h] [rbp+8h] BYREF
  __int64 v61; // [rsp+50h] [rbp+10h] BYREF
  __int64 v62; // [rsp+58h] [rbp+18h] BYREF
  __int64 v63; // [rsp+60h] [rbp+20h] BYREF
  __int128 pvPara; // [rsp+68h] [rbp+28h] BYREF
  _CRYPT_ENCRYPT_MESSAGE_PARA pEncryptPara; // [rsp+80h] [rbp+40h] BYREF
  __int128 v66; // [rsp+B8h] [rbp+78h]

  LODWORD(v6) = 0;
  v60 = a4;
  v62 = 0;
  v63 = 0;
  v61 = 0;
  *(_QWORD *)((char *)&pvPara + 4) = 0;
  cbToBeEncrypted = 0;
  v9 = (*(_BYTE *)(a1 + 36) & 5) == 0;
  *(_QWORD *)&pvPara = 0;
  memset(&pEncryptPara, 0, sizeof(pEncryptPara));
  pcbEncryptedBlob = 0;
  if ( v9 )
  {
    v10 = -2146893783;
    v11 = 1368;
    v12 = 2148073513LL;
LABEL_87:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v11);
    return v10;
  }
  if ( (a6 & 0xFFFFF7FF) != 0 )
  {
    v10 = -2146893815;
    v11 = 1375;
    v12 = 2148073481LL;
    goto LABEL_87;
  }
  if ( !(unsigned int)CheckPKCS7BlobArgs(a2, (unsigned int)&v61, (unsigned int)&v62, (unsigned int)&v63, 0, 0) )
  {
    v10 = -2146893785;
    v11 = 1390;
    v12 = 2148073511LL;
    goto LABEL_87;
  }
  if ( (a6 & 0x800) != 0 )
  {
    v14 = *(_QWORD *)(a1 + 64);
    switch ( *(_DWORD *)(v14 + 32) )
    {
      case 0x30001:
        v13 = L"CAPIPRIVATEBLOB";
        break;
      case 0x30003:
        v13 = L"CAPIDSAPRIVATEBLOB";
        break;
      case 0x30002:
        v13 = L"CAPIDHPRIVATEBLOB";
        break;
      default:
        v10 = -2146893814;
        v11 = 1420;
        v12 = 2148073482LL;
        goto LABEL_87;
    }
  }
  else
  {
    v13 = L"PRIVATEBLOB";
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD, DWORD, DWORD *, _DWORD))(*(_QWORD *)(a1 + 168) + 120LL))(
          *(_QWORD *)(a1 + 112),
          0,
          v13,
          0,
          cbToBeEncrypted,
          &cbToBeEncrypted,
          0);
  v10 = v15;
  if ( v15 )
  {
    v11 = 1436;
    v12 = v15;
    goto LABEL_87;
  }
  v17 = cbToBeEncrypted;
  p_cbToBeEncrypted = 0;
  if ( !cbToBeEncrypted )
    goto LABEL_91;
  if ( cbToBeEncrypted > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_91;
  v19 = cbToBeEncrypted + g_ulAdditionalProbeSize + 8;
  if ( v19 < cbToBeEncrypted || !(unsigned int)VerifyStackAvailable(v19, v16) )
    goto LABEL_91;
  v20 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v20 = 0xFFFFFFFFFFFFFF0LL;
  v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
  v22 = alloca(v21);
  v23 = alloca(v21);
  p_cbToBeEncrypted = &cbToBeEncrypted;
  if ( v57 == (_BYTE *)-64LL || (cbToBeEncrypted = 1801679955, (p_cbToBeEncrypted = &v60) == 0) )
  {
LABEL_91:
    if ( v17 + 8 >= v17 )
    {
      v24 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_cbToBeEncrypted = v24;
      if ( v24 )
      {
        *v24 = 1885431112;
        p_cbToBeEncrypted = v24 + 2;
      }
    }
  }
  if ( !p_cbToBeEncrypted )
  {
    v10 = 8;
    v11 = 1445;
    v12 = 8;
    goto LABEL_87;
  }
  v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, DWORD *, DWORD, DWORD *, _DWORD))(*(_QWORD *)(a1 + 168) + 120LL))(
          *(_QWORD *)(a1 + 112),
          0,
          v13,
          p_cbToBeEncrypted,
          cbToBeEncrypted,
          &cbToBeEncrypted,
          0);
  v10 = v25;
  if ( !v25 )
  {
    *((_QWORD *)&pvPara + 1) = *(_QWORD *)(v61 + 8);
    LODWORD(pvPara) = *(_DWORD *)v61;
    v27 = CertOpenStore((LPCSTR)6, 0x10001u, 0, 0x2000u, &pvPara);
    v26 = v27;
    if ( !v27 )
    {
      LastError = GetLastError();
      DebugTraceError(
        LastError,
        "GetLastError()",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c",
        1474);
      v10 = -2146893785;
      goto LABEL_80;
    }
    v29 = CertEnumCertificatesInStore(v27, 0);
    if ( !v29 )
      goto LABEL_78;
    do
    {
      v6 = (unsigned int)(v6 + 1);
      v29 = CertEnumCertificatesInStore(v26, v29);
    }
    while ( v29 );
    if ( !(_DWORD)v6 )
    {
LABEL_78:
      v10 = -2146893785;
      v39 = 1494;
      v40 = 2148073511LL;
      goto LABEL_79;
    }
    v31 = 8LL * (unsigned int)v6;
    v32 = 0;
    if ( !v31 )
      goto LABEL_92;
    if ( v31 > g_ulMaxStackAllocSize )
      goto LABEL_92;
    v33 = v31 + g_ulAdditionalProbeSize + 8;
    if ( v33 < v31 || !(unsigned int)VerifyStackAvailable(v33, v30) )
      goto LABEL_92;
    v34 = v31 + 23;
    if ( v31 + 23 <= v31 + 8 )
      v34 = 0xFFFFFFFFFFFFFF0LL;
    v35 = v34 & 0xFFFFFFFFFFFFFFF0uLL;
    v36 = alloca(v35);
    v37 = alloca(v35);
    v32 = &cbToBeEncrypted;
    if ( v57 == (_BYTE *)-64LL || (cbToBeEncrypted = 1801679955, (v32 = &v60) == 0) )
    {
LABEL_92:
      if ( v31 + 8 >= v31 )
      {
        v38 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v32 = v38;
        if ( v38 )
        {
          *v38 = 1885431112;
          v32 = v38 + 2;
        }
      }
    }
    if ( !v32 )
    {
      v10 = 8;
      v39 = 1504;
      v40 = 8;
LABEL_79:
      DebugTraceError(v40, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v39);
      goto LABEL_80;
    }
    memset_0(v32, 0, 8 * v6);
    for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
    {
      v42 = CertEnumCertificatesInStore(v26, v29);
      v29 = v42;
      if ( !v42 )
      {
        v44 = GetLastError();
        v45 = 1519;
        goto LABEL_56;
      }
      v43 = CertDuplicateCertificateContext(v42);
      *(_QWORD *)&v32[2 * i] = v43;
      if ( !v43 )
      {
        v44 = GetLastError();
        v45 = 1531;
LABEL_56:
        DebugTraceError(v44, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v45);
        v10 = -2146893792;
        goto LABEL_71;
      }
    }
    v46 = 0;
    v66 = 0;
    v47 = *(CHAR **)(v62 + 8);
    if ( v63 )
    {
      v48 = *(_DWORD *)v63;
      v46 = *(BYTE **)(v63 + 8);
    }
    else
    {
      v48 = DWORD2(v66);
    }
    *(&pEncryptPara.ContentEncryptionAlgorithm.Parameters.cbData + 1) = HIDWORD(v66);
    pEncryptPara.ContentEncryptionAlgorithm.pszObjId = v47;
    pEncryptPara.ContentEncryptionAlgorithm.Parameters.cbData = v48;
    pEncryptPara.ContentEncryptionAlgorithm.Parameters.pbData = v46;
    *(_OWORD *)&pEncryptPara.pvEncryptionAuxInfo = 0;
    pEncryptPara.cbSize = 56;
    pEncryptPara.dwMsgEncodingType = 0x10000;
    pEncryptPara.hCryptProv = 0;
    if ( !CryptEncryptMessage(
            &pEncryptPara,
            v6,
            (PCCERT_CONTEXT *)v32,
            (const BYTE *)p_cbToBeEncrypted,
            cbToBeEncrypted,
            0,
            &pcbEncryptedBlob) )
    {
      v49 = GetLastError();
      v50 = 1564;
LABEL_63:
      DebugTraceError(v49, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", v50);
      v10 = -2146893785;
      goto LABEL_71;
    }
    v51 = pcbEncryptedBlob;
    *a5 = pcbEncryptedBlob;
    if ( a3 )
    {
      if ( v60 < v51 )
      {
        v10 = -2146893784;
        goto LABEL_71;
      }
      if ( !CryptEncryptMessage(
              &pEncryptPara,
              v6,
              (PCCERT_CONTEXT *)v32,
              (const BYTE *)p_cbToBeEncrypted,
              cbToBeEncrypted,
              a3,
              &pcbEncryptedBlob) )
      {
        v49 = GetLastError();
        v50 = 1595;
        goto LABEL_63;
      }
      *a5 = pcbEncryptedBlob;
    }
    v10 = 0;
LABEL_71:
    v52 = 0;
    do
    {
      v53 = *(const CERT_CONTEXT **)&v32[2 * v52];
      if ( v53 )
        CertFreeCertificateContext(v53);
      v52 = (unsigned int)(v52 + 1);
    }
    while ( (unsigned int)v52 < (unsigned int)v6 );
    if ( *(v32 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_80;
  }
  v26 = 0;
  DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\deprecate.c", 1458);
LABEL_80:
  v54 = cbToBeEncrypted;
  v55 = p_cbToBeEncrypted;
  if ( cbToBeEncrypted )
  {
    do
    {
      *(_BYTE *)v55 = 0;
      v55 = (DWORD *)((char *)v55 + 1);
      --v54;
    }
    while ( v54 );
  }
  if ( *(p_cbToBeEncrypted - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v26 )
    CertCloseStore(v26, 1u);
  return v10;
}

```

## disassembly

```asm
0x18005aca0  push    rbp
0x18005aca2  push    rbx
0x18005aca3  push    rsi
0x18005aca4  push    rdi
0x18005aca5  push    r12
0x18005aca7  push    r13
0x18005aca9  push    r14
0x18005acab  push    r15
0x18005acad  sub     rsp, 0E8h
0x18005acb4  lea     rbp, [rsp+40h]
0x18005acb9  mov     rax, cs:__security_cookie
0x18005acc0  xor     rax, rbp
0x18005acc3  mov     [rbp+0E0h+var_50], rax
0x18005acca  xor     r12d, r12d
0x18005accd  mov     [rbp+0E0h+var_D8], r9d
0x18005acd1  xorps   xmm0, xmm0
0x18005acd4  mov     [rbp+0E0h+var_C8], r12
0x18005acd8  mov     r14, rcx
0x18005acdb  mov     [rbp+0E0h+var_C0], r12
0x18005acdf  xor     ecx, ecx
0x18005ace1  mov     [rbp+0E0h+var_D0], r12
0x18005ace5  mov     [rbp+0E0h+var_B4], rcx
0x18005ace9  mov     r15, r8
0x18005acec  mov     rax, rdx
0x18005acef  mov     [rbp+0E0h+cbToBeEncrypted], r12d
0x18005acf3  test    byte ptr [r14+24h], 5
0x18005acf8  mov     [rbp+28h], rcx
0x18005acfc  movups  xmmword ptr [rbp+0E0h+pEncryptPara.cbSize], xmm0
0x18005ad00  mov     qword ptr [rbp+0E0h+pEncryptPara.dwFlags], rcx
0x18005ad04  movups  xmmword ptr [rbp+0E0h+pEncryptPara.ContentEncryptionAlgorithm.pszObjId], xmm0
0x18005ad08  mov     [rbp+0E0h+var_DC], r12d
0x18005ad0c  movups  xmmword ptr [rbp+0E0h+pEncryptPara.ContentEncryptionAlgorithm.Parameters.pbData], xmm0
0x18005ad10  jnz     short loc_18005AD27
0x18005ad12  mov     ebx, 80090029h
0x18005ad17  mov     r9d, 558h
0x18005ad1d  mov     ecx, 80090029h
0x18005ad22  jmp     loc_18005B2F7
0x18005ad27  test    [rbp+0E0h+arg_28], 0FFFFF7FFh
0x18005ad31  jz      short loc_18005AD48
0x18005ad33  mov     ebx, 80090009h
0x18005ad38  mov     r9d, 55Fh
0x18005ad3e  mov     ecx, 80090009h
0x18005ad43  jmp     loc_18005B2F7
0x18005ad48  mov     dword ptr [rsp+120h+pbEncryptedBlob], r12d
0x18005ad4d  lea     r9, [rbp+0E0h+var_C0]
0x18005ad51  lea     r8, [rbp+0E0h+var_C8]
0x18005ad55  mov     [rsp+120h+pvPara], r12
0x18005ad5a  lea     rdx, [rbp+0E0h+var_D0]
0x18005ad5e  mov     rcx, rax
0x18005ad61  call    CheckPKCS7BlobArgs
0x18005ad66  test    eax, eax
0x18005ad68  jnz     short loc_18005AD7F
0x18005ad6a  mov     ebx, 80090027h
0x18005ad6f  mov     r9d, 56Eh
0x18005ad75  mov     ecx, 80090027h
0x18005ad7a  jmp     loc_18005B2F7
0x18005ad7f  test    [rbp+0E0h+arg_28], 800h
0x18005ad89  jnz     short loc_18005AD94
0x18005ad8b  lea     rdi, aPrivateblob; "PRIVATEBLOB"
0x18005ad92  jmp     short loc_18005ADD0
0x18005ad94  mov     rax, [r14+40h]
0x18005ad98  cmp     dword ptr [rax+20h], 30001h
0x18005ad9f  jnz     short loc_18005ADAA
0x18005ada1  lea     rdi, aCapiprivateblo; "CAPIPRIVATEBLOB"
0x18005ada8  jmp     short loc_18005ADD0
0x18005adaa  cmp     dword ptr [rax+20h], 30003h
0x18005adb1  jnz     short loc_18005ADBC
0x18005adb3  lea     rdi, aCapidsaprivate; "CAPIDSAPRIVATEBLOB"
0x18005adba  jmp     short loc_18005ADD0
0x18005adbc  cmp     dword ptr [rax+20h], 30002h
0x18005adc3  jnz     loc_18005B2E7
0x18005adc9  lea     rdi, aCapidhprivateb; "CAPIDHPRIVATEBLOB"
0x18005add0  mov     rax, [r14+0A8h]
0x18005add7  lea     rcx, [rbp+0E0h+cbToBeEncrypted]
0x18005addb  mov     dword ptr [rsp+120h+pcbEncryptedBlob], r12d
0x18005ade0  xor     r9d, r9d
0x18005ade3  mov     [rsp+120h+pbEncryptedBlob], rcx
0x18005ade8  mov     r8, rdi
0x18005adeb  mov     ecx, [rbp+0E0h+cbToBeEncrypted]
0x18005adee  xor     edx, edx
0x18005adf0  mov     rax, [rax+78h]
0x18005adf4  mov     dword ptr [rsp+120h+pvPara], ecx
0x18005adf8  mov     rcx, [r14+70h]
0x18005adfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae01  mov     ebx, eax
0x18005ae03  test    eax, eax
0x18005ae05  jz      short loc_18005AE14
0x18005ae07  mov     r9d, 59Ch
0x18005ae0d  mov     ecx, eax
0x18005ae0f  jmp     loc_18005B2F7
0x18005ae14  mov     ebx, [rbp+0E0h+cbToBeEncrypted]
0x18005ae17  mov     rsi, r12
0x18005ae1a  mov     r13, 0FFFFFFFFFFFFFF0h
0x18005ae24  test    rbx, rbx
0x18005ae27  jz      short loc_18005AE83
0x18005ae29  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005ae30  ja      short loc_18005AE83
0x18005ae32  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005ae39  add     rcx, 8
0x18005ae3d  add     rcx, rbx
0x18005ae40  cmp     rcx, rbx
0x18005ae43  jb      short loc_18005AE83
0x18005ae45  call    VerifyStackAvailable
0x18005ae4a  test    eax, eax
0x18005ae4c  jz      short loc_18005AE83
0x18005ae4e  lea     rax, [rbx+8]
0x18005ae52  lea     rcx, [rax+0Fh]
0x18005ae56  cmp     rcx, rax
0x18005ae59  ja      short loc_18005AE5E
0x18005ae5b  mov     rcx, r13
0x18005ae5e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005ae62  mov     rax, rcx
0x18005ae65  call    _alloca_probe
0x18005ae6a  sub     rsp, rcx
0x18005ae6d  lea     rsi, [rsp+120h+cbToBeEncrypted]
0x18005ae72  test    rsi, rsi
0x18005ae75  jz      short loc_18005AE83
0x18005ae77  mov     dword ptr [rsi], 6B637453h
0x18005ae7d  add     rsi, 8
0x18005ae81  jnz     short loc_18005AEAA
0x18005ae83  lea     rcx, [rbx+8]
0x18005ae87  cmp     rcx, rbx
0x18005ae8a  jb      short loc_18005AEAA
0x18005ae8c  mov     rax, cs:g_pfnAllocate
0x18005ae93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ae98  mov     rsi, rax
0x18005ae9b  test    rax, rax
0x18005ae9e  jz      short loc_18005AEAA
0x18005aea0  mov     dword ptr [rax], 70616548h
0x18005aea6  add     rsi, 8
0x18005aeaa  test    rsi, rsi
0x18005aead  jnz     short loc_18005AEBF
0x18005aeaf  lea     ebx, [rsi+8]
0x18005aeb2  mov     r9d, 5A5h
0x18005aeb8  mov     ecx, ebx
0x18005aeba  jmp     loc_18005B2F7
0x18005aebf  mov     rax, [r14+0A8h]
0x18005aec6  lea     rcx, [rbp+0E0h+cbToBeEncrypted]
0x18005aeca  mov     dword ptr [rsp+120h+pcbEncryptedBlob], r12d
0x18005aecf  mov     r9, rsi
0x18005aed2  mov     [rsp+120h+pbEncryptedBlob], rcx
0x18005aed7  mov     r8, rdi
0x18005aeda  mov     ecx, [rbp+0E0h+cbToBeEncrypted]
0x18005aedd  xor     edx, edx
0x18005aedf  mov     rax, [rax+78h]
0x18005aee3  mov     dword ptr [rsp+120h+pvPara], ecx
0x18005aee7  mov     rcx, [r14+70h]
0x18005aeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aef0  mov     ebx, eax
0x18005aef2  test    eax, eax
0x18005aef4  jz      short loc_18005AF19
0x18005aef6  mov     r9d, 5B2h
0x18005aefc  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005af03  lea     rdx, aStatus; "Status"
0x18005af0a  mov     ecx, eax
0x18005af0c  mov     r13, r12
0x18005af0f  call    DebugTraceError
0x18005af14  jmp     loc_18005B29D
0x18005af19  mov     rcx, [rbp+0E0h+var_D0]
0x18005af1d  xor     r8d, r8d; hCryptProv
0x18005af20  mov     r9d, 2000h; dwFlags
0x18005af26  mov     edx, 10001h; dwEncodingType
0x18005af2b  mov     rax, [rcx+8]
0x18005af2f  mov     [rbp+0E0h+var_B4+4], rax
0x18005af33  mov     eax, [rcx]
0x18005af35  lea     ecx, [r8+6]; lpszStoreProvider
0x18005af39  mov     [rbp+0E0h+var_B8], eax
0x18005af3c  lea     rax, [rbp+0E0h+var_B8]
0x18005af40  mov     [rsp+120h+pvPara], rax; pvPara
0x18005af45  call    cs:__imp_CertOpenStore
0x18005af4c  nop     dword ptr [rax+rax+00h]
0x18005af51  mov     r13, rax
0x18005af54  test    rax, rax
0x18005af57  jnz     short loc_18005AF8A
0x18005af59  call    cs:__imp_GetLastError
0x18005af60  nop     dword ptr [rax+rax+00h]
0x18005af65  mov     r9d, 5C2h
0x18005af6b  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005af72  mov     ecx, eax
0x18005af74  lea     rdx, aGetlasterror; "GetLastError()"
0x18005af7b  call    DebugTraceError
0x18005af80  mov     ebx, 80090027h
0x18005af85  jmp     loc_18005B29D
0x18005af8a  xor     edx, edx; pPrevCertContext
0x18005af8c  mov     rcx, r13; hCertStore
0x18005af8f  call    cs:__imp_CertEnumCertificatesInStore
0x18005af96  nop     dword ptr [rax+rax+00h]
0x18005af9b  mov     r14, rax
0x18005af9e  test    rax, rax
0x18005afa1  jz      loc_18005B277
0x18005afa7  mov     rdx, r14; pPrevCertContext
0x18005afaa  mov     rcx, r13; hCertStore
0x18005afad  inc     r12d
0x18005afb0  call    cs:__imp_CertEnumCertificatesInStore
0x18005afb7  nop     dword ptr [rax+rax+00h]
0x18005afbc  mov     r14, rax
0x18005afbf  test    rax, rax
0x18005afc2  jnz     short loc_18005AFA7
0x18005afc4  test    r12d, r12d
0x18005afc7  jz      loc_18005B277
0x18005afcd  lea     rbx, ds:0[r12*8]
0x18005afd5  xor     edi, edi
0x18005afd7  test    rbx, rbx
0x18005afda  jz      short loc_18005B03D
0x18005afdc  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005afe3  ja      short loc_18005B03D
0x18005afe5  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005afec  add     rcx, 8
0x18005aff0  add     rcx, rbx
0x18005aff3  cmp     rcx, rbx
0x18005aff6  jb      short loc_18005B03D
0x18005aff8  call    VerifyStackAvailable
0x18005affd  test    eax, eax
0x18005afff  jz      short loc_18005B03D
0x18005b001  lea     rax, [rbx+8]
0x18005b005  lea     rcx, [rax+0Fh]
0x18005b009  cmp     rcx, rax
0x18005b00c  ja      short loc_18005B018
0x18005b00e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005b018  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005b01c  mov     rax, rcx
0x18005b01f  call    _alloca_probe
0x18005b024  sub     rsp, rcx
0x18005b027  lea     rdi, [rsp+120h+cbToBeEncrypted]
0x18005b02c  test    rdi, rdi
0x18005b02f  jz      short loc_18005B03D
0x18005b031  mov     dword ptr [rdi], 6B637453h
0x18005b037  add     rdi, 8
0x18005b03b  jnz     short loc_18005B064
0x18005b03d  lea     rcx, [rbx+8]
0x18005b041  cmp     rcx, rbx
0x18005b044  jb      short loc_18005B064
0x18005b046  mov     rax, cs:g_pfnAllocate
0x18005b04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b052  mov     rdi, rax
0x18005b055  test    rax, rax
0x18005b058  jz      short loc_18005B064
0x18005b05a  mov     dword ptr [rax], 70616548h
0x18005b060  add     rdi, 8
0x18005b064  test    rdi, rdi
0x18005b067  jnz     short loc_18005B079
0x18005b069  lea     ebx, [rdi+8]
0x18005b06c  mov     r9d, 5E0h
0x18005b072  mov     ecx, ebx
0x18005b074  jmp     loc_18005B287
0x18005b079  mov     r8, rbx; Size
0x18005b07c  xor     edx, edx; Val
0x18005b07e  mov     rcx, rdi; void *
0x18005b081  call    memset_0
0x18005b086  xor     ebx, ebx
0x18005b088  cmp     ebx, r12d
0x18005b08b  jnb     short loc_18005B108
0x18005b08d  mov     rdx, r14; pPrevCertContext
0x18005b090  mov     rcx, r13; hCertStore
0x18005b093  call    cs:__imp_CertEnumCertificatesInStore
0x18005b09a  nop     dword ptr [rax+rax+00h]
0x18005b09f  mov     r14, rax
0x18005b0a2  test    rax, rax
0x18005b0a5  jz      short loc_18005B0F4
0x18005b0a7  mov     rcx, rax; pCertContext
0x18005b0aa  call    cs:__imp_CertDuplicateCertificateContext
0x18005b0b1  nop     dword ptr [rax+rax+00h]
0x18005b0b6  mov     [rdi+rbx*8], rax
0x18005b0ba  test    rax, rax
0x18005b0bd  jz      short loc_18005B0C3
0x18005b0bf  inc     ebx
0x18005b0c1  jmp     short loc_18005B088
0x18005b0c3  call    cs:__imp_GetLastError
0x18005b0ca  nop     dword ptr [rax+rax+00h]
0x18005b0cf  mov     r9d, 5FBh
0x18005b0d5  mov     ecx, eax
0x18005b0d7  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b0de  lea     rdx, aGetlasterror; "GetLastError()"
0x18005b0e5  call    DebugTraceError
0x18005b0ea  mov     ebx, 80090020h
0x18005b0ef  jmp     loc_18005B22D
0x18005b0f4  call    cs:__imp_GetLastError
0x18005b0fb  nop     dword ptr [rax+rax+00h]
0x18005b100  mov     r9d, 5EFh
0x18005b106  jmp     short loc_18005B0D5
0x18005b108  mov     rax, [rbp+0E0h+var_C8]
0x18005b10c  xor     edx, edx
0x18005b10e  xorps   xmm0, xmm0
0x18005b111  movups  [rbp+0E0h+var_68], xmm0
0x18005b115  mov     r8, [rax+8]
0x18005b119  mov     rax, [rbp+0E0h+var_C0]
0x18005b11d  test    rax, rax
0x18005b120  jz      short loc_18005B12A
0x18005b122  mov     ecx, [rax]
0x18005b124  mov     rdx, [rax+8]
0x18005b128  jmp     short loc_18005B130
0x18005b12a  mov     ecx, dword ptr [rbp+0E0h+var_68+8]
0x18005b130  mov     eax, dword ptr [rbp+0E0h+var_68+0Ch]
0x18005b136  mov     r9, rsi; pbToBeEncrypted
0x18005b139  mov     dword ptr [rbp+0E0h+pEncryptPara.ContentEncryptionAlgorithm.Parameters+4], eax
0x18005b13c  lea     rax, [rbp+0E0h+var_DC]
0x18005b140  mov     [rsp+120h+pcbEncryptedBlob], rax; pcbEncryptedBlob
0x18005b145  mov     eax, [rbp+0E0h+cbToBeEncrypted]
0x18005b148  mov     [rbp+0E0h+pEncryptPara.ContentEncryptionAlgorithm.pszObjId], r8
0x18005b14c  mov     r8, rdi; rgpRecipientCert
  ... truncated ...
```
