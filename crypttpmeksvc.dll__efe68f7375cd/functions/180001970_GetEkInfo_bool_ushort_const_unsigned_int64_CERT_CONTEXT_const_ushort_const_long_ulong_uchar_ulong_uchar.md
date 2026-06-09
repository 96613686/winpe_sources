# _GetEkInfo(bool,ushort const *,unsigned __int64,_CERT_CONTEXT const *,ushort const *,long,ulong *,uchar * *,ulong *,uchar * *)

- ea: `0x180001970`
- end: `0x18000230a`
- name: `?_GetEkInfo@@YAK_NPEBG_KPEBU_CERT_CONTEXT@@1JPEAKPEAPEAE45@Z`
- size: `2458`
- prototype: `__int64 __fastcall(char, const unsigned __int16 *, void *, const struct _CERT_CONTEXT *, char *pvKey, unsigned int, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180001850`
- `0x180009150`
- `0x1800092a0`

## callees

- `0x180001140`
- `0x180001480`
- `0x180001970`
- `0x180002850`
- `0x180003750`
- `0x180004790`
- `0x1800049f0`
- `0x180005680`
- `0x180007d80`
- `0x180008b50`
- `0x180008ca4`
- `0x180008e84`
- `0x18000a800`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001a4d`
- `msvcrt!_wcsicmp` at `0x180001a68`
- `msvcrt!_wcsicmp` at `0x180001a4d`
- `msvcrt!_wcsicmp` at `0x180001a68`
- `CRYPT32!CryptFindOIDInfo` at `0x180001ad7`
- `CRYPT32!CryptFindOIDInfo` at `0x180001ad7`
- `CRYPT32!CryptEncryptMessage` at `0x18000212f`
- `CRYPT32!CryptEncryptMessage` at `0x1800021ce`
- `CRYPT32!CryptEncryptMessage` at `0x18000212f`
- `CRYPT32!CryptEncryptMessage` at `0x1800021ce`
- `CRYPT32!CertFreeCertificateContext` at `0x1800022a7`
- `CRYPT32!CertFreeCertificateContext` at `0x1800022c6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800022dc`
- `CRYPT32!CertFreeCertificateContext` at `0x1800022a7`
- `CRYPT32!CertFreeCertificateContext` at `0x1800022c6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800022dc`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180001cfa`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180001cfa`
- `CRYPT32!CryptEncodeObjectEx` at `0x180001f09`
- `CRYPT32!CryptEncodeObjectEx` at `0x180002010`
- `CRYPT32!CryptEncodeObjectEx` at `0x180001f09`
- `CRYPT32!CryptEncodeObjectEx` at `0x180002010`
- `CRYPT32!CertCloseStore` at `0x180001d70`
- `CRYPT32!CertCloseStore` at `0x180001d85`
- `CRYPT32!CertCloseStore` at `0x180001d70`
- `CRYPT32!CertCloseStore` at `0x180001d85`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180001cbc`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180001d15`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180001cbc`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180001d15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000204d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000207a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000227b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000204d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000207a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000227b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002175`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000201a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000201a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021d8`

## pseudocode

```c
__int64 __fastcall _GetEkInfo(
        char a1,
        const unsigned __int16 *a2,
        void *a3,
        const struct _CERT_CONTEXT *a4,
        char *pvKey,
        unsigned int a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        unsigned int *a9,
        unsigned __int8 **a10)
{
  PCCERT_CONTEXT v11; // rdi
  struct _CERT_CONTEXT **v12; // r15
  unsigned int v13; // ebx
  PCCRYPT_OID_INFO OIDInfo; // r14
  unsigned int v15; // eax
  unsigned int EkPub; // eax
  DWORD v17; // esi
  unsigned int EkCertificateStores; // eax
  unsigned int CertificateFromStoreMatchingEkPub; // eax
  unsigned __int16 *VolatileCertIdString; // rax
  const CERT_CONTEXT *v21; // rax
  DWORD v22; // ebx
  unsigned __int16 *v23; // rax
  const CERT_CONTEXT *v24; // rax
  const CERT_CONTEXT *v25; // rdx
  __int64 v26; // rcx
  unsigned int PublicKeyInfo; // eax
  unsigned int KeyCertificate; // eax
  PCCERT_CONTEXT *v29; // r15
  unsigned int KeyCertChain; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  signed int v33; // eax
  unsigned int v34; // ecx
  int cbCertEncoded; // ecx
  int v36; // eax
  HCERTSTORE *pbCertEncoded; // rdx
  unsigned int v38; // r8d
  DWORD i; // r10d
  __int64 v40; // rax
  __int64 v41; // rdx
  PCCERT_CONTEXT v42; // rcx
  signed int LastError; // eax
  DWORD v44; // ebx
  CHAR *pszOID; // rax
  BYTE *v46; // r14
  signed int v47; // eax
  unsigned __int8 *v48; // r14
  signed int v49; // eax
  DWORD v50; // eax
  unsigned int v51; // r14d
  __int64 j; // r12
  const CERT_CONTEXT *v53; // rcx
  __int64 k; // rdi
  const CERT_CONTEXT *v55; // rcx
  const CERT_CHAIN_CONTEXT *pEncodePara; // [rsp+20h] [rbp-E0h]
  PCRYPT_ENCODE_PARA pEncodeParaa; // [rsp+20h] [rbp-E0h]
  DWORD pcbEncryptedBlob; // [rsp+40h] [rbp-C0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-B8h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbToBeEncrypted; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v63; // [rsp+5Ch] [rbp-A4h] BYREF
  HCERTSTORE v64; // [rsp+60h] [rbp-A0h] BYREF
  PCCERT_CONTEXT rgpRecipientCert; // [rsp+68h] [rbp-98h] BYREF
  void *pvStructInfo; // [rsp+70h] [rbp-90h] BYREF
  BYTE *pbToBeEncrypted; // [rsp+78h] [rbp-88h] BYREF
  BYTE *v68[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _CERT_CONTEXT **v69; // [rsp+90h] [rbp-70h] BYREF
  char *v70[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v71; // [rsp+A8h] [rbp-58h]
  PCCERT_CONTEXT v72[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v73; // [rsp+C0h] [rbp-40h]
  _CRYPT_ENCRYPT_MESSAGE_PARA pEncryptPara; // [rsp+D0h] [rbp-30h] BYREF

  LOBYTE(hCertStore) = a1;
  v64 = a3;
  rgpRecipientCert = a4;
  v11 = 0;
  v70[0] = pvKey;
  v12 = 0;
  *a9 = 0;
  *a10 = 0;
  v71 = a9;
  v68[0] = (BYTE *)a10;
  pvStructInfo = 0;
  pCertContext = 0;
  pbToBeEncrypted = 0;
  cbToBeEncrypted = 0;
  v69 = 0;
  v63 = 0;
  *(_OWORD *)v72 = 0;
  v73 = 0;
  if ( !a2 || !a4 || !a8 || !a7 )
  {
    v13 = 160;
    ekTraceFmt(0x98012C2u, 1, "ERROR: Arguments. Return=%d\n", 160);
    goto LABEL_87;
  }
  *a8 = 0;
  *a7 = 0;
  if ( !_wcsicmp(a2, L"Microsoft Platform Crypto Provider")
    || v64 && !_wcsicmp(a2, L"Microsoft Smart Card Key Storage Provider") )
  {
    if ( a6 > 0xFFF )
    {
      ekTraceFmt(0x3E712C2u, 1, "ERROR: dwCngKeySize=%d Hr=%d\n", a6, -2147024809);
LABEL_13:
      v13 = -2146889726;
      LODWORD(pEncodeParaa) = a6;
      ekTraceFmt(
        0x99B12C2u,
        1,
        "ERROR: _FindOidInfo AlgorithmName=%ws EncryptionStrength=%d Hr=%d\n",
        v70[0],
        pEncodeParaa,
        -2146889726);
      goto LABEL_87;
    }
    OIDInfo = CryptFindOIDInfo(5u, pvKey, (a6 << 16) | 2);
    if ( !OIDInfo )
    {
      ekTraceFmt(0x3F312C2u, 1, "ERROR: CNG Algorithm Not Found. Algorithm=%ws, KeySize=%d\n", pvKey, a6);
      goto LABEL_13;
    }
    v70[0] = "1.3.6.1.4.1.311.21.5";
    v70[1] = "1.3.6.1.4.1.311.21.36";
    v15 = _VerifyCertContext((char)hCertStore, rgpRecipientCert, 2u, v70, pEncodePara, 0);
    v13 = v15;
    if ( v15 )
    {
      ekTraceFmt(0x22912C3u, 1, "ERROR: _VerifyCertContext. Hr=%x\n", v15);
      ekTraceFmt(0x9A912C2u, 1, "ERROR: _ValidateCaExchangeCertificate. Return=%x\n", v13);
      goto LABEL_87;
    }
    if ( v64 )
    {
      PublicKeyInfo = _GetPublicKeyInfo(
                        (HCRYPTPROV_OR_NCRYPT_KEY_HANDLE)v64,
                        (struct _CERT_PUBLIC_KEY_INFO **)&pvStructInfo);
      v13 = PublicKeyInfo;
      if ( PublicKeyInfo )
      {
        ekTraceFmt(0x9DA12C2u, 1, "ERROR: _GetPublicKeyInfo. Return=%d\n", PublicKeyInfo);
        goto LABEL_87;
      }
      KeyCertificate = _GetKeyCertificate((unsigned __int64)v64, &pCertContext);
      if ( KeyCertificate )
        ekTraceFmt(0x9E412C2u, 1, "ERROR: _GetKeyCertificate. Return=%d\n", KeyCertificate);
      v11 = pCertContext;
      v17 = 0;
LABEL_46:
      v29 = &v72[v17];
      *v29 = v11;
      KeyCertChain = _GetKeyCertChain(v72, v17 + (v11 != 0) != 0, (const struct _CERT_CONTEXT ***)&v69, &v63);
      v13 = KeyCertChain;
      if ( KeyCertChain )
      {
        ekTraceFmt(0x9F212C2u, 1, "ERROR: _GetKeyCertChain. Return=%d\n", KeyCertChain);
        v12 = v69;
        goto LABEL_88;
      }
      v31 = v63;
      *v29 = 0;
      v12 = v69;
      if ( v31 )
      {
        v32 = _EncodeKeyCertChain((const struct _CERT_CONTEXT **)v69, v31, (unsigned __int8 **)v68[0], v71);
        v13 = v32;
        if ( v32 )
        {
          ekTraceFmt(0xA0212C2u, 1, "ERROR: _EncodeKeyCertChain. Return=%d\n", v32);
          goto LABEL_88;
        }
      }
      pCertContext = 0;
      LOWORD(hCertStore) = 5;
      *(_OWORD *)v68 = 0;
      pbToBeEncrypted = 0;
      cbToBeEncrypted = 0;
      pcbEncryptedBlob = 0;
      if ( CryptEncodeObjectEx(1u, (LPCSTR)8, pvStructInfo, 0x8000u, 0, &pCertContext, &pcbEncryptedBlob) )
      {
        v68[1] = (BYTE *)&pEncryptPara;
        pEncryptPara.hCryptProv = (HCRYPTPROV_LEGACY)pCertContext;
        pEncryptPara.cbSize = pcbEncryptedBlob;
        if ( v11 )
        {
          cbCertEncoded = v11->cbCertEncoded;
          v36 = 1;
          pbCertEncoded = (HCERTSTORE *)v11->pbCertEncoded;
        }
        else
        {
          v36 = 0;
          pbCertEncoded = &hCertStore;
          cbCertEncoded = 2;
        }
        *(_QWORD *)&pEncryptPara.ContentEncryptionAlgorithm.Parameters.cbData = pbCertEncoded;
        LODWORD(pEncryptPara.ContentEncryptionAlgorithm.pszObjId) = cbCertEncoded;
        v38 = 2;
        LODWORD(v68[0]) = 2;
        if ( v17 + v36 > 3 )
        {
          v13 = -2147024736;
          ekTraceFmt(0x36D12C2u, 1, "ERROR: EKCERTMAX. Hr=%x\n", -2147024736);
          LocalFree((HLOCAL)pCertContext);
LABEL_67:
          ekTraceFmt(0xA1512C2u, 1, "ERROR: _EncodeEkInfo. Return=%d\n", v13);
          goto LABEL_88;
        }
        for ( i = 0; i < v17; LODWORD(v68[0]) = v38 )
        {
          v40 = i++;
          v41 = v38++;
          v41 *= 2;
          v42 = v72[v40];
          *(&pEncryptPara.hCryptProv + v41) = (HCRYPTPROV_LEGACY)v42->pbCertEncoded;
          *(&pEncryptPara.cbSize + 2 * v41) = v42->cbCertEncoded;
        }
        if ( CryptEncodeObjectEx(1u, (LPCSTR)0x22, v68, 0x8000u, 0, &pbToBeEncrypted, &cbToBeEncrypted) )
        {
          LocalFree((HLOCAL)pCertContext);
          goto LABEL_69;
        }
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        v34 = 59183810;
      }
      else
      {
        v33 = GetLastError();
        v13 = v33;
        if ( v33 > 0 )
          v13 = (unsigned __int16)v33 | 0x80070000;
        v34 = 55251650;
      }
      ekTraceFmt(v34, 1, "ERROR: CryptEncodeObjectEx. Hr=%x\n", v13);
      LocalFree((HLOCAL)pCertContext);
      if ( v13 )
        goto LABEL_67;
LABEL_69:
      v44 = cbToBeEncrypted;
      pszOID = (CHAR *)OIDInfo->pszOID;
      v46 = pbToBeEncrypted;
      *a8 = 0;
      *a7 = 0;
      pcbEncryptedBlob = 0;
      pEncryptPara.hCryptProv = 0;
      v68[0] = v46;
      memset(&pEncryptPara.ContentEncryptionAlgorithm.Parameters, 0, 32);
      pEncryptPara.cbSize = 56;
      pEncryptPara.dwMsgEncodingType = 65537;
      pEncryptPara.ContentEncryptionAlgorithm.pszObjId = pszOID;
      ekTraceFmt(0x41C12C2u, 2, "TRACE: cemp.dwMsgEncodingType=%d\n", 65537);
      ekTraceFmt(
        0x41D12C2u,
        2,
        "TRACE: cemp.ContentEncryptionAlgorithm.pszObjId=%hs\n",
        pEncryptPara.ContentEncryptionAlgorithm.pszObjId);
      pcbEncryptedBlob = 0;
      if ( CryptEncryptMessage(&pEncryptPara, 1u, &rgpRecipientCert, v46, v44, 0, &pcbEncryptedBlob) )
      {
        v48 = (unsigned __int8 *)LocalAlloc(0x40u, pcbEncryptedBlob);
        if ( !v48 )
        {
          v13 = -2147024882;
          ekTraceFmt(0x43212C2u, 1, "ERROR: MIDL_user_allocate. Hr=%x\n", -2147024882);
LABEL_83:
          ekTraceFmt(0xA2612C2u, 1, "ERROR: _EncryptContent. Return=%d\n", v13);
          goto LABEL_88;
        }
        LODWORD(hCertStore) = pcbEncryptedBlob;
        if ( CryptEncryptMessage(&pEncryptPara, 1u, &rgpRecipientCert, v68[0], v44, v48, (DWORD *)&hCertStore) )
        {
          v50 = pcbEncryptedBlob;
          if ( pcbEncryptedBlob == (_DWORD)hCertStore )
          {
            *a8 = v48;
            *a7 = v50;
            goto LABEL_85;
          }
          v13 = -2147024736;
          ekTraceFmt(0x44712C2u, 1, "ERROR: cbEnveloped != cbEnvelopedT. Hr=%x\n", 2147942560LL);
        }
        else
        {
          v49 = GetLastError();
          v13 = v49;
          if ( v49 > 0 )
            v13 = (unsigned __int16)v49 | 0x80070000;
          ekTraceFmt(0x44112C2u, 1, "ERROR: CryptEncryptMessage. Hr=%x\n", v13);
        }
        MIDL_user_free(v48);
      }
      else
      {
        v47 = GetLastError();
        v13 = v47;
        if ( v47 > 0 )
          v13 = (unsigned __int16)v47 | 0x80070000;
        ekTraceFmt(0x42A12C2u, 1, "ERROR: CryptEncryptMessage. Hr=%x\n", v13);
      }
      if ( v13 )
        goto LABEL_83;
LABEL_85:
      v13 = 0;
      goto LABEL_88;
    }
    EkPub = _TpmEndorsementKeyGetEkPub((struct _CERT_PUBLIC_KEY_INFO **)&pvStructInfo);
    v13 = EkPub;
    if ( EkPub )
    {
      ekTraceFmt(0x9C412C2u, 1, "ERROR: _TpmEndorsementKeyGetEkPub. Return=%d\n", EkPub);
      goto LABEL_87;
    }
    ekTraceFmt(0x5A012C2u, 2, "TRACE: _TpmEndorsementKeyGetEkCertificates start.\n");
    v64 = 0;
    hCertStore = 0;
    v17 = 0;
    EkCertificateStores = _TpmEndorsementKeyGetEkCertificateStores(&v64, &hCertStore);
    v13 = EkCertificateStores;
    if ( EkCertificateStores )
    {
      ekTraceFmt(0x5B012C2u, 1, "ERROR: _TpmEndorsementKeyGetEkCertificateStores. Hr=%x\n", EkCertificateStores);
      goto LABEL_35;
    }
    CertificateFromStoreMatchingEkPub = _TpmGetCertificateFromStoreMatchingEkPub(v64, &pCertContext);
    v13 = CertificateFromStoreMatchingEkPub;
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
        v11 = pCertContext;
        goto LABEL_35;
      }
      ekTraceFmt(
        0x5C012C2u,
        1,
        "TRACE: _TpmGetCertificateFromStoreMatchingEkPub succeeded. A certificate in the NV EK Certificate store matched the EK pub.\n");
    }
    v11 = pCertContext;
    if ( pCertContext )
    {
      pcbEncryptedBlob = 2;
      VolatileCertIdString = _GetVolatileCertIdString(pCertContext);
      ekTraceFmt(0x5CC12C2u, 2, "TRACE: OneManufacturerCert: %ws\n", VolatileCertIdString);
    }
    else
    {
      pcbEncryptedBlob = 3;
      ekTraceFmt(0x5D012C2u, 1, "ERROR: _TpmEndorsementKeyGetEkCertificateByIndex. Hr=%x\n", v13);
    }
    v21 = CertEnumCertificatesInStore(hCertStore, 0);
    pCertContext = v21;
    if ( v21 )
    {
      do
      {
        v22 = v17;
        if ( v17 >= pcbEncryptedBlob )
          break;
        v23 = _GetVolatileCertIdString(v21);
        ekTraceFmt(0x5E212C2u, 2, "TRACE: OtherCert: %ws\n", v23);
        v24 = CertDuplicateCertificateContext(pCertContext);
        v25 = pCertContext;
        v26 = v17++;
        v22 = v17;
        v72[v26] = v24;
        v21 = CertEnumCertificatesInStore(hCertStore, v25);
        pCertContext = v21;
      }
      while ( v21 );
    }
    else
    {
      v22 = 0;
    }
    ekTraceFmt(0x5E912C2u, 2, "TRACE: OtherEkCertificates. Count=%d\n", v22);
    v13 = 0;
LABEL_35:
    if ( v64 )
      CertCloseStore(v64, 0);
    if ( hCertStore )
      CertCloseStore(hCertStore, 0);
    ekTraceFmt(0x5F712C2u, 2, "TRACE: _TpmEndorsementKeyGetEkCertificates end.\n");
    if ( v13 )
    {
      ekTraceFmt(0x9D012C2u, 1, "ERROR: _TpmEndorsementKeyGetEkCertificates. Return=%d\n", v13);
      goto LABEL_88;
    }
    goto LABEL_46;
  }
  v13 = 160;
  ekTraceFmt(0x99012C2u, 1, "ERROR: Invalid KSP.Ksp=%ws Return=%d\n", a2, 160);
LABEL_87:
  v17 = 0;
LABEL_88:
  LocalFree(pvStructInfo);
  LocalFree(pbToBeEncrypted);
  if ( v12 )
  {
    v51 = v63;
    for ( j = 0; (unsigned int)j < v51; j = (unsigned int)(j + 1) )
    {
      v53 = v12[j];
      if ( v53 )
        CertFreeCertificateContext(v53);
    }
    LocalFree(v12);
  }
  if ( v11 )
    CertFreeCertificateContext(v11);
  for ( k = 0; (unsigned int)k < v17; k = (unsigned int)(k + 1) )
  {
    v55 = v72[k];
    if ( v55 )
      CertFreeCertificateContext(v55);
  }
  return v13;
}

```

## disassembly

```asm
0x180001970  push    rbp
0x180001972  push    rbx
0x180001973  push    rsi
0x180001974  push    rdi
0x180001975  push    r12
0x180001977  push    r13
0x180001979  push    r14
0x18000197b  push    r15
0x18000197d  lea     rbp, [rsp-38h]
0x180001982  sub     rsp, 138h
0x180001989  mov     rax, cs:__security_cookie
0x180001990  xor     rax, rsp
0x180001993  mov     [rbp+70h+var_50], rax
0x180001997  mov     rbx, [rbp+70h+pvKey]
0x18000199e  mov     r14, rdx
0x1800019a1  mov     rdx, [rbp+70h+arg_48]
0x1800019a8  xorps   xmm0, xmm0
0x1800019ab  mov     esi, [rbp+70h+arg_28]
0x1800019b1  mov     rax, r9
0x1800019b4  mov     r12, [rbp+70h+arg_30]
0x1800019bb  mov     r13, [rbp+70h+arg_38]
0x1800019c2  mov     byte ptr [rsp+170h+hCertStore], cl
0x1800019c6  mov     rcx, [rbp+70h+arg_40]
0x1800019cd  mov     [rsp+170h+var_110], r8
0x1800019d2  xor     r8d, r8d
0x1800019d5  mov     [rsp+170h+rgpRecipientCert], rax
0x1800019da  mov     edi, r8d
0x1800019dd  mov     [rbp+70h+var_D8], rbx
0x1800019e1  mov     r15d, r8d
0x1800019e4  mov     [rcx], r8d
0x1800019e7  mov     [rdx], r8
0x1800019ea  mov     [rbp+70h+var_C8], rcx
0x1800019ee  mov     [rbp+70h+var_F0], rdx
0x1800019f2  mov     [rsp+170h+pvStructInfo], r8
0x1800019f7  mov     [rsp+170h+pCertContext], r8
0x1800019fc  mov     [rsp+170h+pbToBeEncrypted], r8
0x180001a01  mov     [rsp+170h+cbToBeEncrypted], r8d
0x180001a06  mov     [rbp+70h+var_E0], r8
0x180001a0a  mov     [rsp+170h+var_114], r8d
0x180001a0f  movups  xmmword ptr [rbp+70h+var_C0], xmm0
0x180001a13  movups  [rbp+70h+var_B0], xmm0
0x180001a17  test    r14, r14
0x180001a1a  jz      loc_180002256
0x180001a20  test    rax, rax
0x180001a23  jz      loc_180002256
0x180001a29  test    r13, r13
0x180001a2c  jz      loc_180002256
0x180001a32  test    r12, r12
0x180001a35  jz      loc_180002256
0x180001a3b  mov     [r13+0], r8
0x180001a3f  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180001a46  mov     rcx, r14; String1
0x180001a49  mov     [r12], r8d
0x180001a4d  call    cs:__imp__wcsicmp
0x180001a53  test    eax, eax
0x180001a55  jz      short loc_180001A99
0x180001a57  cmp     [rsp+170h+var_110], r15
0x180001a5c  jz      short loc_180001A72
0x180001a5e  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x180001a65  mov     rcx, r14; String1
0x180001a68  call    cs:__imp__wcsicmp
0x180001a6e  test    eax, eax
0x180001a70  jz      short loc_180001A99
0x180001a72  mov     ebx, 0A0h
0x180001a77  lea     r8, aErrorInvalidKs; "ERROR: Invalid KSP.Ksp=%ws Return=%d\n"
0x180001a7e  mov     r9, r14
0x180001a81  mov     dword ptr [rsp+170h+pEncodePara], ebx
0x180001a85  mov     edx, 1; unsigned int
0x180001a8a  mov     ecx, 99012C2h; unsigned int
0x180001a8f  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001a94  jmp     loc_180002274
0x180001a99  cmp     esi, 0FFFh
0x180001a9f  jbe     short loc_180001AC4
0x180001aa1  mov     r9d, esi
0x180001aa4  mov     dword ptr [rsp+170h+pEncodePara], 80070057h
0x180001aac  lea     r8, aErrorDwcngkeys; "ERROR: dwCngKeySize=%d Hr=%d\n"
0x180001ab3  mov     edx, 1; unsigned int
0x180001ab8  mov     ecx, 3E712C2h; unsigned int
0x180001abd  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001ac2  jmp     short loc_180001B02
0x180001ac4  mov     r8d, esi
0x180001ac7  mov     rdx, rbx; pvKey
0x180001aca  shl     r8d, 10h
0x180001ace  mov     ecx, 5; dwKeyType
0x180001ad3  or      r8d, 2; dwGroupId
0x180001ad7  call    cs:__imp_CryptFindOIDInfo
0x180001add  mov     r14, rax
0x180001ae0  test    rax, rax
0x180001ae3  jnz     short loc_180001B2E
0x180001ae5  mov     r9, rbx
0x180001ae8  mov     dword ptr [rsp+170h+pEncodePara], esi
0x180001aec  lea     r8, aErrorCngAlgori; "ERROR: CNG Algorithm Not Found. Algorit"...
0x180001af3  mov     edx, 1; unsigned int
0x180001af8  mov     ecx, 3F312C2h; unsigned int
0x180001afd  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001b02  mov     r9, [rbp+70h+var_D8]
0x180001b06  lea     r8, aErrorFindoidin; "ERROR: _FindOidInfo AlgorithmName=%ws E"...
0x180001b0d  mov     ebx, 80091002h
0x180001b12  mov     edx, 1; unsigned int
0x180001b17  mov     dword ptr [rsp+170h+pvEncoded], ebx
0x180001b1b  mov     ecx, 99B12C2h; unsigned int
0x180001b20  mov     dword ptr [rsp+170h+pEncodePara], esi
0x180001b24  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001b29  jmp     loc_180002274
0x180001b2e  mov     rdx, [rsp+170h+rgpRecipientCert]; struct _CERT_CONTEXT *
0x180001b33  lea     rax, a136141311215; "1.3.6.1.4.1.311.21.5"
0x180001b3a  movzx   ecx, byte ptr [rsp+170h+hCertStore]; bool
0x180001b3f  lea     r9, [rbp+70h+var_D8]; char **
0x180001b43  mov     [rbp+70h+var_D8], rax
0x180001b47  mov     r8d, 2; unsigned int
0x180001b4d  lea     rax, a1361413112136; "1.3.6.1.4.1.311.21.36"
0x180001b54  mov     [rsp+170h+pvEncoded], rdi; void *
0x180001b59  mov     [rbp+70h+var_D0], rax
0x180001b5d  call    ?_VerifyCertContext@@YAJ_NPEBU_CERT_CONTEXT@@KPEBQEBDPEAX3@Z; _VerifyCertContext(bool,_CERT_CONTEXT const *,ulong,char const * const *,void *,void *)
0x180001b62  mov     ebx, eax
0x180001b64  test    eax, eax
0x180001b66  jz      short loc_180001B92
0x180001b68  mov     r9d, eax
0x180001b6b  lea     r8, aErrorVerifycer; "ERROR: _VerifyCertContext. Hr=%x\n"
0x180001b72  mov     edx, 1; unsigned int
0x180001b77  mov     ecx, 22912C3h; unsigned int
0x180001b7c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001b81  lea     r8, aErrorValidatec; "ERROR: _ValidateCaExchangeCertificate. "...
0x180001b88  mov     ecx, 9A912C2h
0x180001b8d  jmp     loc_180002267
0x180001b92  mov     rsi, [rsp+170h+var_110]
0x180001b97  test    rsi, rsi
0x180001b9a  jnz     loc_180001DC3
0x180001ba0  lea     rcx, [rsp+170h+pvStructInfo]; struct _CERT_PUBLIC_KEY_INFO **
0x180001ba5  call    ?_TpmEndorsementKeyGetEkPub@@YAKPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z; _TpmEndorsementKeyGetEkPub(_CERT_PUBLIC_KEY_INFO * *)
0x180001baa  mov     ebx, eax
0x180001bac  test    eax, eax
0x180001bae  jz      short loc_180001BC4
0x180001bb0  mov     r9d, eax
0x180001bb3  lea     r8, aErrorTpmendors_2; "ERROR: _TpmEndorsementKeyGetEkPub. Retu"...
0x180001bba  mov     ecx, 9C412C2h
0x180001bbf  jmp     loc_18000226A
0x180001bc4  lea     r8, aTraceTpmendors_1; "TRACE: _TpmEndorsementKeyGetEkCertifica"...
0x180001bcb  mov     edx, 2; unsigned int
0x180001bd0  mov     ecx, 5A012C2h; unsigned int
0x180001bd5  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001bda  xor     eax, eax
0x180001bdc  lea     rdx, [rsp+170h+hCertStore]; void **
0x180001be1  lea     rcx, [rsp+170h+var_110]; void **
0x180001be6  mov     [rsp+170h+var_110], rax
0x180001beb  mov     [rsp+170h+hCertStore], rax
0x180001bf0  mov     esi, eax
0x180001bf2  call    ?_TpmEndorsementKeyGetEkCertificateStores@@YAJPEAPEAX0@Z; _TpmEndorsementKeyGetEkCertificateStores(void * *,void * *)
0x180001bf7  mov     ebx, eax
0x180001bf9  test    eax, eax
0x180001bfb  jz      short loc_180001C1B
0x180001bfd  mov     r9d, eax
0x180001c00  lea     r8, aErrorTpmendors_3; "ERROR: _TpmEndorsementKeyGetEkCertifica"...
0x180001c07  mov     edx, 1; unsigned int
0x180001c0c  mov     ecx, 5B012C2h; unsigned int
0x180001c11  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001c16  jmp     loc_180001D64
0x180001c1b  mov     rcx, [rsp+170h+var_110]; hCertStore
0x180001c20  lea     rdx, [rsp+170h+pCertContext]; struct _CERT_CONTEXT **
0x180001c25  call    ?_TpmGetCertificateFromStoreMatchingEkPub@@YAJPEAXPEAPEBU_CERT_CONTEXT@@@Z; _TpmGetCertificateFromStoreMatchingEkPub(void *,_CERT_CONTEXT const * *)
0x180001c2a  mov     ebx, eax
0x180001c2c  cmp     eax, 80070490h
0x180001c31  jnz     short loc_180001C41
0x180001c33  mov     ecx, 5BB12C2h
0x180001c38  lea     r8, aTraceTpmgetcer_2; "TRACE: _TpmGetCertificateFromStoreMatch"...
0x180001c3f  jmp     short loc_180001C55
0x180001c41  test    ebx, ebx
0x180001c43  jnz     loc_180001D46
0x180001c49  mov     ecx, 5C012C2h; unsigned int
0x180001c4e  lea     r8, aTraceTpmgetcer_1; "TRACE: _TpmGetCertificateFromStoreMatch"...
0x180001c55  mov     edx, 1; unsigned int
0x180001c5a  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001c5f  mov     rdi, [rsp+170h+pCertContext]
0x180001c64  test    rdi, rdi
0x180001c67  jz      short loc_180001C94
0x180001c69  mov     rcx, rdi; pCertContext
0x180001c6c  mov     [rsp+170h+pcbEncryptedBlob], 2
0x180001c74  call    ?_GetVolatileCertIdString@@YAPEAGPEBU_CERT_CONTEXT@@@Z; _GetVolatileCertIdString(_CERT_CONTEXT const *)
0x180001c79  mov     r9, rax
0x180001c7c  lea     r8, aTraceOnemanufa; "TRACE: OneManufacturerCert: %ws\n"
0x180001c83  mov     edx, 2; unsigned int
0x180001c88  mov     ecx, 5CC12C2h; unsigned int
0x180001c8d  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001c92  jmp     short loc_180001CB5
0x180001c94  mov     r9d, ebx
0x180001c97  mov     [rsp+170h+pcbEncryptedBlob], 3
0x180001c9f  lea     r8, aErrorTpmendors_0; "ERROR: _TpmEndorsementKeyGetEkCertifica"...
0x180001ca6  mov     edx, 1; unsigned int
0x180001cab  mov     ecx, 5D012C2h; unsigned int
0x180001cb0  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001cb5  mov     rcx, [rsp+170h+hCertStore]; hCertStore
0x180001cba  xor     edx, edx; pPrevCertContext
0x180001cbc  call    cs:__imp_CertEnumCertificatesInStore
0x180001cc2  mov     [rsp+170h+pCertContext], rax
0x180001cc7  test    rax, rax
0x180001cca  jz      short loc_180001D27
0x180001ccc  mov     ebx, esi
0x180001cce  cmp     esi, [rsp+170h+pcbEncryptedBlob]
0x180001cd2  jnb     short loc_180001D29
0x180001cd4  mov     rcx, rax; pCertContext
0x180001cd7  call    ?_GetVolatileCertIdString@@YAPEAGPEBU_CERT_CONTEXT@@@Z; _GetVolatileCertIdString(_CERT_CONTEXT const *)
0x180001cdc  mov     r9, rax
0x180001cdf  lea     r8, aTraceOthercert; "TRACE: OtherCert: %ws\n"
0x180001ce6  mov     edx, 2; unsigned int
0x180001ceb  mov     ecx, 5E212C2h; unsigned int
0x180001cf0  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001cf5  mov     rcx, [rsp+170h+pCertContext]; pCertContext
0x180001cfa  call    cs:__imp_CertDuplicateCertificateContext
0x180001d00  mov     rdx, [rsp+170h+pCertContext]; pPrevCertContext
0x180001d05  mov     ecx, esi
0x180001d07  inc     esi
0x180001d09  mov     ebx, esi
0x180001d0b  mov     [rbp+rcx*8+70h+var_C0], rax
0x180001d10  mov     rcx, [rsp+170h+hCertStore]; hCertStore
0x180001d15  call    cs:__imp_CertEnumCertificatesInStore
0x180001d1b  mov     [rsp+170h+pCertContext], rax
0x180001d20  test    rax, rax
0x180001d23  jnz     short loc_180001CCC
0x180001d25  jmp     short loc_180001D29
0x180001d27  xor     ebx, ebx
0x180001d29  mov     r9d, ebx
0x180001d2c  lea     r8, aTraceOtherekce; "TRACE: OtherEkCertificates. Count=%d\n"
0x180001d33  mov     edx, 2; unsigned int
0x180001d38  mov     ecx, 5E912C2h; unsigned int
0x180001d3d  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001d42  xor     ebx, ebx
0x180001d44  jmp     short loc_180001D64
0x180001d46  mov     r9d, ebx
0x180001d49  lea     r8, aErrorTpmgetcer; "ERROR: _TpmGetCertificateFromStoreMatch"...
0x180001d50  mov     edx, 1; unsigned int
0x180001d55  mov     ecx, 5C512C2h; unsigned int
0x180001d5a  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001d5f  mov     rdi, [rsp+170h+pCertContext]
0x180001d64  mov     rcx, [rsp+170h+var_110]; hCertStore
0x180001d69  test    rcx, rcx
0x180001d6c  jz      short loc_180001D76
0x180001d6e  xor     edx, edx; dwFlags
0x180001d70  call    cs:__imp_CertCloseStore
0x180001d76  mov     rax, [rsp+170h+hCertStore]
0x180001d7b  test    rax, rax
0x180001d7e  jz      short loc_180001D8B
0x180001d80  xor     edx, edx; dwFlags
0x180001d82  mov     rcx, rax; hCertStore
0x180001d85  call    cs:__imp_CertCloseStore
0x180001d8b  lea     r8, aTraceTpmendors_2; "TRACE: _TpmEndorsementKeyGetEkCertifica"...
0x180001d92  mov     edx, 2; unsigned int
0x180001d97  mov     ecx, 5F712C2h; unsigned int
0x180001d9c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001da1  test    ebx, ebx
0x180001da3  jz      short loc_180001E1C
0x180001da5  mov     r9d, ebx
0x180001da8  lea     r8, aErrorTpmendors_1; "ERROR: _TpmEndorsementKeyGetEkCertifica"...
0x180001daf  mov     edx, 1; unsigned int
0x180001db4  mov     ecx, 9D012C2h; unsigned int
0x180001db9  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001dbe  jmp     loc_180002276
0x180001dc3  lea     rdx, [rsp+170h+pvStructInfo]; struct _CERT_PUBLIC_KEY_INFO **
0x180001dc8  mov     rcx, rsi; hCryptProvOrNCryptKey
0x180001dcb  call    ?_GetPublicKeyInfo@@YAK_KPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z; _GetPublicKeyInfo(unsigned __int64,_CERT_PUBLIC_KEY_INFO * *)
0x180001dd0  mov     ebx, eax
0x180001dd2  test    eax, eax
0x180001dd4  jz      short loc_180001DEA
0x180001dd6  mov     r9d, eax
0x180001dd9  lea     r8, aErrorGetpublic; "ERROR: _GetPublicKeyInfo. Return=%d\n"
0x180001de0  mov     ecx, 9DA12C2h
0x180001de5  jmp     loc_18000226A
0x180001dea  lea     rdx, [rsp+170h+pCertContext]; struct _CERT_CONTEXT **
0x180001def  mov     rcx, rsi; unsigned __int64
0x180001df2  call    ?_GetKeyCertificate@@YAK_KPEAPEBU_CERT_CONTEXT@@@Z; _GetKeyCertificate(unsigned __int64,_CERT_CONTEXT const * *)
0x180001df7  test    eax, eax
0x180001df9  jz      short loc_180001E14
0x180001dfb  mov     r9d, eax
0x180001dfe  lea     r8, aErrorGetkeycer_0; "ERROR: _GetKeyCertificate. Return=%d\n"
0x180001e05  mov     edx, 1; unsigned int
0x180001e0a  mov     ecx, 9E412C2h; unsigned int
0x180001e0f  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180001e14  mov     rdi, [rsp+170h+pCertContext]
0x180001e19  mov     esi, r15d
0x180001e1c  mov     eax, esi
0x180001e1e  lea     r15, [rbp+70h+var_C0]
0x180001e22  lea     r15, [r15+rax*8]
0x180001e26  xor     eax, eax
0x180001e28  lea     r9, [rsp+170h+var_114]; unsigned int *
0x180001e2d  mov     [r15], rdi
0x180001e30  test    rdi, rdi
0x180001e33  lea     r8, [rbp+70h+var_E0]; struct _CERT_CONTEXT ***
0x180001e37  lea     rcx, [rbp+70h+var_C0]; struct _CERT_CONTEXT **
0x180001e3b  setnz   al
0x180001e3e  xor     edx, edx
0x180001e40  add     eax, esi
0x180001e42  setnz   dl; unsigned int
0x180001e45  call    ?_GetKeyCertChain@@YAKPEAPEBU_CERT_CONTEXT@@KPEAPEAPEBU1@PEAK@Z; _GetKeyCertChain(_CERT_CONTEXT const * *,ulong,_CERT_CONTEXT const * * *,ulong *)
0x180001e4a  mov     ebx, eax
0x180001e4c  test    eax, eax
0x180001e4e  jz      short loc_180001E72
0x180001e50  mov     r9d, eax
0x180001e53  lea     r8, aErrorGetkeycer; "ERROR: _GetKeyCertChain. Return=%d\n"
0x180001e5a  mov     edx, 1; unsigned int
0x180001e5f  mov     ecx, 9F212C2h; unsigned int
0x180001e64  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
  ... truncated ...
```
