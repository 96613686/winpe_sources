# CertCreateSelfSignCertificate

- ea: `0x180071360`
- end: `0x180071c9f`
- name: `CertCreateSelfSignCertificate`
- size: `2367`
- prototype: `PCCERT_CONTEXT __stdcall(HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey, PCERT_NAME_BLOB pSubjectIssuerBlob, DWORD dwFlags, PCRYPT_KEY_PROV_INFO pKeyProvInfo, PCRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm, PSYSTEMTIME pStartTime, PSYSTEMTIME pEndTime, PCERT_EXTENSIONS pExtensions)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009da0`
- `0x180014790`
- `0x180024a70`
- `0x180025cf0`
- `0x180028d60`
- `0x18002cb30`
- `0x180030e60`
- `0x180034270`
- `0x1800450c0`
- `0x18006dbc4`
- `0x1800701b0`
- `0x180070274`
- `0x180070750`
- `0x180071360`
- `0x1800bec20`
- `0x1800bf63c`
- `0x1800c79a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800713cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800714ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800713cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800714ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800714a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007159d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071c73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800714a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007159d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180071c73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007180f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007180f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180071821`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007185c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180071821`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007185c`
- `RPCRT4!UuidCreate` at `0x180071487`
- `RPCRT4!UuidCreate` at `0x180071746`
- `RPCRT4!UuidCreate` at `0x180071487`
- `RPCRT4!UuidCreate` at `0x180071746`
- `RPCRT4!RpcStringFreeW` at `0x180071c42`
- `RPCRT4!RpcStringFreeW` at `0x180071c42`
- `RPCRT4!UuidToStringW` at `0x180071498`
- `RPCRT4!UuidToStringW` at `0x180071498`
- `ncrypt!NCryptIsKeyHandle` at `0x1800715d9`
- `ncrypt!NCryptIsKeyHandle` at `0x1800715f9`
- `ncrypt!NCryptIsKeyHandle` at `0x1800715d9`
- `ncrypt!NCryptIsKeyHandle` at `0x1800715f9`
- `ncrypt!NCryptOpenStorageProvider` at `0x180071591`
- `ncrypt!NCryptOpenStorageProvider` at `0x180071591`
- `ncrypt!NCryptOpenKey` at `0x1800715c9`
- `ncrypt!NCryptOpenKey` at `0x1800715c9`
- `ncrypt!NCryptFreeObject` at `0x180071ac1`
- `ncrypt!NCryptFreeObject` at `0x180071c15`
- `ncrypt!NCryptFreeObject` at `0x180071ac1`
- `ncrypt!NCryptFreeObject` at `0x180071c15`
- `CRYPTSP!CryptDestroyKey` at `0x180071a9a`
- `CRYPTSP!CryptDestroyKey` at `0x180071a9a`
- `CRYPTSP!CryptGetProvParam` at `0x180071adf`
- `CRYPTSP!CryptGetProvParam` at `0x180071b18`
- `CRYPTSP!CryptGetProvParam` at `0x180071b56`
- `CRYPTSP!CryptGetProvParam` at `0x180071b8f`
- `CRYPTSP!CryptGetProvParam` at `0x180071bc8`
- `CRYPTSP!CryptGetProvParam` at `0x180071adf`
- `CRYPTSP!CryptGetProvParam` at `0x180071b18`
- `CRYPTSP!CryptGetProvParam` at `0x180071b56`
- `CRYPTSP!CryptGetProvParam` at `0x180071b8f`
- `CRYPTSP!CryptGetProvParam` at `0x180071bc8`
- `CRYPTSP!CryptGenKey` at `0x18007156f`
- `CRYPTSP!CryptGenKey` at `0x18007156f`
- `CRYPTSP!CryptGetUserKey` at `0x180071552`
- `CRYPTSP!CryptGetUserKey` at `0x180071552`
- `CRYPTSP!CryptAcquireContextW` at `0x18007150e`
- `CRYPTSP!CryptAcquireContextW` at `0x180071532`
- `CRYPTSP!CryptAcquireContextW` at `0x18007150e`
- `CRYPTSP!CryptAcquireContextW` at `0x180071532`
- `CRYPTSP!CryptReleaseContext` at `0x180071c06`
- `CRYPTSP!CryptReleaseContext` at `0x180071c06`

## pseudocode

```c
PCCERT_CONTEXT __stdcall CertCreateSelfSignCertificate(
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey,
        PCERT_NAME_BLOB pSubjectIssuerBlob,
        DWORD dwFlags,
        PCRYPT_KEY_PROV_INFO pKeyProvInfo,
        PCRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm,
        PSYSTEMTIME pStartTime,
        PSYSTEMTIME pEndTime,
        PCERT_EXTENSIONS pExtensions)
{
  PCRYPT_ALGORITHM_IDENTIFIER v8; // r12
  const CERT_CONTEXT *v10; // r13
  __int64 pInfo; // r14
  CHAR *v12; // rdi
  void *v13; // r15
  DWORD *p_dwKeySpec; // rsi
  RPC_STATUS v15; // eax
  BOOL v16; // esi
  DWORD v17; // ebx
  BYTE *v18; // r12
  BOOL v19; // eax
  DWORD dwProvType; // r9d
  SECURITY_STATUS v21; // eax
  DWORD v22; // r9d
  HCRYPTPROV v23; // r14
  DWORD v24; // r15d
  unsigned int v25; // esi
  int v26; // eax
  const char *pszOID; // rsi
  PCCRYPT_OID_INFO v28; // rax
  bool v29; // zf
  PCCRYPT_OID_INFO v30; // rax
  PCCRYPT_OID_INFO OIDInfo; // rax
  __int128 v32; // xmm0
  BYTE *v33; // xmm1_8
  __int128 v34; // xmm0
  struct _CRYPTOAPI_BLOB v35; // xmm0
  char v36; // al
  char v37; // si
  void *v38; // rax
  DWORD *v39; // rsi
  void *v40; // rax
  BYTE *v41; // rax
  BYTE *v42; // rax
  BOOL IsKeyHandle; // [rsp+50h] [rbp-B0h]
  DWORD pdwDataLen; // [rsp+54h] [rbp-ACh] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbInfo; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbCertEncoded; // [rsp+64h] [rbp-9Ch] BYREF
  PCCERT_CONTEXT ppCertContext; // [rsp+68h] [rbp-98h] BYREF
  DWORD v50; // [rsp+70h] [rbp-90h]
  DWORD LastError; // [rsp+74h] [rbp-8Ch]
  int v52; // [rsp+78h] [rbp-88h]
  RPC_WSTR StringUuid; // [rsp+80h] [rbp-80h] BYREF
  HCRYPTKEY phUserKey; // [rsp+88h] [rbp-78h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+90h] [rbp-70h] BYREF
  __int64 pvKey; // [rsp+98h] [rbp-68h] BYREF
  HCRYPTPROV v57; // [rsp+A0h] [rbp-60h]
  HLOCAL v58; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h]
  LPVOID pv[2]; // [rsp+B8h] [rbp-48h] BYREF
  BYTE pbData[16]; // [rsp+C8h] [rbp-38h] BYREF
  DWORD dwKeySpec[4]; // [rsp+D8h] [rbp-28h]
  DWORD pcbEncoded; // [rsp+F0h] [rbp-10h] BYREF
  BYTE *pbEncodedToBeSigned; // [rsp+F8h] [rbp-8h]
  struct _CRYPT_ALGORITHM_IDENTIFIER v65; // [rsp+100h] [rbp+0h] BYREF
  DWORD pcbSignature; // [rsp+118h] [rbp+18h] BYREF
  DWORD *p_pcbEncoded; // [rsp+120h] [rbp+20h]
  PCERT_NAME_BLOB v68; // [rsp+130h] [rbp+30h]
  PCERT_EXTENSIONS v69; // [rsp+138h] [rbp+38h]
  SYSTEMTIME *lpSystemTime; // [rsp+140h] [rbp+40h]
  SYSTEMTIME *v71; // [rsp+148h] [rbp+48h]
  _BYTE v72[24]; // [rsp+158h] [rbp+58h] BYREF
  _DWORD pvStructInfo[4]; // [rsp+170h] [rbp+70h] BYREF
  UUID *v74; // [rsp+180h] [rbp+80h]
  struct _CRYPT_ALGORITHM_IDENTIFIER v75; // [rsp+188h] [rbp+88h]
  struct _CRYPTOAPI_BLOB v76; // [rsp+1A0h] [rbp+A0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _FILETIME FileTime; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _CRYPTOAPI_BLOB v79; // [rsp+1C0h] [rbp+C0h]
  __int128 v80; // [rsp+1D0h] [rbp+D0h]
  __int128 v81; // [rsp+1E0h] [rbp+E0h]
  __int128 v82; // [rsp+1F0h] [rbp+F0h]
  DWORD cExtension; // [rsp+230h] [rbp+130h]
  PCERT_EXTENSION rgExtension; // [rsp+238h] [rbp+138h]
  UUID v85; // [rsp+240h] [rbp+140h] BYREF
  UUID Uuid; // [rsp+250h] [rbp+150h] BYREF

  v8 = pSignatureAlgorithm;
  v69 = pExtensions;
  v10 = 0;
  phProv = hCryptProvOrNCryptKey;
  lpSystemTime = pStartTime;
  v50 = dwFlags;
  v68 = pSubjectIssuerBlob;
  v71 = pEndTime;
  pcbInfo = 0;
  LastError = GetLastError();
  v58 = 0;
  cbCertEncoded = 0;
  pInfo = 0;
  pdwDataLen = 0;
  v12 = 0;
  hMem = 0;
  v13 = 0;
  StringUuid = 0;
  memset(v72, 0, sizeof(v72));
  phUserKey = 0;
  Uuid = 0;
  phProvider = 0;
  memset_0(pvStructInfo, 0, 0xD0u);
  v85 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)pbData = 0;
  *(_OWORD *)dwKeySpec = 0;
  memset_0(&pcbEncoded, 0, 0x40u);
  p_dwKeySpec = &pKeyProvInfo->dwKeySpec;
  if ( pKeyProvInfo )
    dwKeySpec[2] = *p_dwKeySpec;
  else
    dwKeySpec[2] = 2;
  if ( phProv )
  {
    v52 = 0;
    IsKeyHandle = NCryptIsKeyHandle(phProv);
    goto LABEL_31;
  }
  IsKeyHandle = 0;
  v52 = 1;
  if ( pKeyProvInfo )
  {
    dwProvType = pKeyProvInfo->dwProvType;
    if ( !dwProvType )
    {
      IsKeyHandle = 1;
      v21 = NCryptOpenStorageProvider(&phProvider, pKeyProvInfo->pwszProvName, 0);
      if ( v21 )
        goto LABEL_24;
      v22 = 0;
      if ( *p_dwKeySpec != -1 )
        v22 = *p_dwKeySpec;
      v21 = NCryptOpenKey(phProvider, &phProv, pKeyProvInfo->pwszContainerName, v22, pKeyProvInfo->dwFlags);
      if ( v21 )
      {
LABEL_24:
        SetLastError(v21);
        goto LABEL_25;
      }
LABEL_31:
      v23 = phProv;
      v24 = dwKeySpec[2];
      v25 = v50 & 0x3C000000;
      if ( NCryptIsKeyHandle(phProv) )
      {
        pvKey = 1;
        v57 = v23;
        v26 = I_CryptCNGExportPublicKeyInfoEx2((struct _CNG_NCRYPT_OR_BCRYPT_KEY *)&pvKey, 1u, 0, v25, 0, 0, &pcbInfo);
      }
      else
      {
        v26 = ExportCspPublicKeyInfoEx(v23, v24, 1);
      }
      if ( !v26 )
      {
        pInfo = 0;
        goto LABEL_93;
      }
      pInfo = PkiNonzeroAlloc(pcbInfo);
      if ( !pInfo
        || !CryptExportPublicKeyInfoEx(phProv, dwKeySpec[2], 1u, 0, v25, 0, (PCERT_PUBLIC_KEY_INFO)pInfo, &pcbInfo) )
      {
        goto LABEL_93;
      }
      if ( pSignatureAlgorithm )
      {
        OIDInfo = CryptFindOIDInfo(1u, pSignatureAlgorithm->pszObjId, 0x40000004u);
        if ( OIDInfo && OIDInfo->dwValue == -3 )
          *(_QWORD *)pInfo = pSignatureAlgorithm->pszObjId;
      }
      else
      {
        pszOID = "1.3.14.3.2.29";
        v28 = CryptFindOIDInfo(1u, *(void **)pInfo, 0x40000003u);
        if ( v28 )
        {
          v29 = v28->dwValue == -3;
          pvKey = (__int64)L"SHA1";
          v57 = *(_QWORD *)&v28[1].cbSize;
          if ( v29 )
          {
            pszOID = *(const char **)pInfo;
          }
          else
          {
            v30 = CryptFindOIDInfo(6u, &pvKey, 4u);
            if ( v30 )
              pszOID = v30->pszOID;
          }
        }
        *(_QWORD *)v72 = pszOID;
        *(_OWORD *)&v72[8] = 0;
        v8 = (PCRYPT_ALGORITHM_IDENTIFIER)v72;
      }
      UuidCreate(&v85);
      pvStructInfo[0] = 2;
      v80 = *(_OWORD *)pInfo;
      v81 = *(_OWORD *)(pInfo + 16);
      v32 = *(_OWORD *)(pInfo + 32);
      v74 = &v85;
      v33 = v8->Parameters.pbData;
      v82 = v32;
      v34 = *(_OWORD *)&v8->pszObjId;
      pvStructInfo[2] = 16;
      v75.Parameters.pbData = v33;
      *(_OWORD *)&v75.pszObjId = v34;
      v35 = *v68;
      v36 = v85.Data4[7] & 0x7F;
      v29 = (v85.Data4[7] & 0x7F) == 0;
      v85.Data4[7] &= ~0x80u;
      v76 = v35;
      v79 = v35;
      if ( v29 )
      {
        v85.Data4[7] = 97;
      }
      else if ( (v36 & 0xF0) == 0 )
      {
        v85.Data4[7] = v36 | 0x10;
      }
      if ( v69 )
      {
        cExtension = v69->cExtension;
        rgExtension = v69->rgExtension;
      }
      if ( lpSystemTime )
      {
        if ( !SystemTimeToFileTime(lpSystemTime, &SystemTimeAsFileTime) )
          goto LABEL_93;
      }
      else
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      }
      if ( v71 )
      {
        if ( !SystemTimeToFileTime(v71, &FileTime) )
          goto LABEL_93;
      }
      else
      {
        FileTime = (struct _FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 315576000000000LL);
      }
      if ( CryptEncodeObjectEx(1u, (LPCSTR)2, pvStructInfo, 0, 0, 0, &pcbEncoded) )
      {
        v13 = (void *)PkiNonzeroAlloc(pcbEncoded);
        if ( !v13 || !CryptEncodeObjectEx(1u, (LPCSTR)2, pvStructInfo, 0, 0, v13, &pcbEncoded) )
          goto LABEL_25;
        v37 = v50;
        v65 = v75;
        pbEncodedToBeSigned = (BYTE *)v13;
        p_pcbEncoded = &pcbEncoded;
        pcbSignature = 1;
        if ( (v50 & 1) == 0 )
        {
          if ( !CryptSignCertificate(phProv, dwKeySpec[2], 1u, (const BYTE *)v13, pcbEncoded, &v65, 0, 0, &pcbSignature) )
            goto LABEL_25;
          v38 = (void *)PkiNonzeroAlloc(pcbSignature);
          hMem = v38;
          v39 = (DWORD *)v38;
          if ( !v38
            || !CryptSignCertificate(
                  phProv,
                  dwKeySpec[2],
                  1u,
                  pbEncodedToBeSigned,
                  pcbEncoded,
                  &v65,
                  0,
                  (BYTE *)v38,
                  &pcbSignature) )
          {
            goto LABEL_25;
          }
          p_pcbEncoded = v39;
          v37 = v50;
        }
        if ( CryptEncodeObjectEx(1u, (LPCSTR)1, &pcbEncoded, 0, 0, 0, &cbCertEncoded) )
        {
          v40 = (void *)PkiNonzeroAlloc(cbCertEncoded);
          v58 = v40;
          v18 = (BYTE *)v40;
          if ( v40 )
          {
            if ( CryptEncodeObjectEx(1u, (LPCSTR)1, &pcbEncoded, 0, 0, v40, &cbCertEncoded) )
            {
              ppCertContext = 0;
              CertAddEncodedCertificateToStore(0, 1u, v18, cbCertEncoded, 4u, &ppCertContext);
              v10 = ppCertContext;
              if ( ppCertContext )
              {
                v29 = (v37 & 2) == 0;
                v16 = IsKeyHandle;
                if ( !v29 )
                  goto LABEL_75;
                if ( !pKeyProvInfo )
                {
                  if ( IsKeyHandle )
                  {
                    if ( !CryptFindCertificateKeyProvInfo(ppCertContext, 0x40000u, 0) )
                      goto LABEL_9;
LABEL_75:
                    v17 = LastError;
                    goto LABEL_76;
                  }
                  if ( !CryptGetProvParam(phProv, 4u, 0, &pdwDataLen, 0) )
                    goto LABEL_9;
                  v41 = (BYTE *)PkiNonzeroAlloc(pdwDataLen);
                  v12 = (CHAR *)v41;
                  if ( !v41 )
                    goto LABEL_9;
                  if ( !CryptGetProvParam(phProv, 4u, v41, &pdwDataLen, 0) )
                    goto LABEL_9;
                  pv[1] = (LPVOID)MkWStr(v12);
                  PkiDefaultCryptFree(v12);
                  pdwDataLen = 0;
                  v12 = 0;
                  if ( !CryptGetProvParam(phProv, 6u, 0, &pdwDataLen, 0) )
                    goto LABEL_9;
                  v42 = (BYTE *)PkiNonzeroAlloc(pdwDataLen);
                  v12 = (CHAR *)v42;
                  if ( !v42 )
                    goto LABEL_9;
                  if ( !CryptGetProvParam(phProv, 6u, v42, &pdwDataLen, 0) )
                    goto LABEL_9;
                  pv[0] = (LPVOID)MkWStr(v12);
                  pdwDataLen = 4;
                  if ( !CryptGetProvParam(phProv, 0x10u, pbData, &pdwDataLen, 0) )
                    goto LABEL_9;
                  pKeyProvInfo = (PCRYPT_KEY_PROV_INFO)pv;
                }
                if ( !CertSetCertificateContextProperty(v10, 2u, 0, pKeyProvInfo) )
                  goto LABEL_9;
                goto LABEL_75;
              }
            }
          }
        }
LABEL_25:
        v16 = IsKeyHandle;
        goto LABEL_9;
      }
LABEL_93:
      v13 = 0;
      goto LABEL_25;
    }
    if ( CryptAcquireContextW(
           &phProv,
           pKeyProvInfo->pwszContainerName,
           pKeyProvInfo->pwszProvName,
           dwProvType,
           pKeyProvInfo->dwFlags) )
    {
LABEL_20:
      if ( !CryptGetUserKey(phProv, dwKeySpec[2], &phUserKey) && !CryptGenKey(phProv, dwKeySpec[2], 0, &phUserKey) )
        goto LABEL_8;
      goto LABEL_31;
    }
    v19 = CryptAcquireContextW(
            &phProv,
            pKeyProvInfo->pwszContainerName,
            pKeyProvInfo->pwszProvName,
            pKeyProvInfo->dwProvType,
            pKeyProvInfo->dwFlags | 8);
LABEL_18:
    if ( !v19 )
    {
      phProv = 0;
      goto LABEL_8;
    }
    goto LABEL_20;
  }
  UuidCreate(&Uuid);
  v15 = UuidToStringW(&Uuid, &StringUuid);
  if ( !v15 )
  {
    v19 = CryptAcquireContextW(&phProv, StringUuid, 0, 1u, 8u);
    goto LABEL_18;
  }
  SetLastError(v15);
LABEL_8:
  v16 = 0;
LABEL_9:
  v17 = GetLastError();
  if ( !v17 )
    v17 = -2147418113;
  if ( v10 )
    CertFreeCertificateContext(v10);
  v18 = (BYTE *)v58;
  v10 = 0;
LABEL_76:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  if ( v52 && phProv )
  {
    if ( v16 )
      NCryptFreeObject(phProv);
    else
      CryptReleaseContext(phProv, 0);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( pv[1] )
    ICM_Free(pv[1]);
  if ( pv[0] )
    ICM_Free(pv[0]);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  PkiDefaultCryptFree((HLOCAL)pInfo);
  PkiDefaultCryptFree(v13);
  PkiDefaultCryptFree(hMem);
  PkiDefaultCryptFree(v18);
  PkiDefaultCryptFree(v12);
  SetLastError(v17);
  return v10;
}

```

## disassembly

```asm
0x180071360  push    rbp
0x180071362  push    rbx
0x180071363  push    rsi
0x180071364  push    rdi
0x180071365  push    r12
0x180071367  push    r13
0x180071369  push    r14
0x18007136b  push    r15
0x18007136d  lea     rbp, [rsp-178h]
0x180071375  sub     rsp, 278h
0x18007137c  mov     rax, cs:__security_cookie
0x180071383  xor     rax, rsp
0x180071386  mov     [rbp+1B0h+var_50], rax
0x18007138d  mov     rax, [rbp+1B0h+pExtensions]
0x180071394  xor     esi, esi
0x180071396  mov     r12, [rbp+1B0h+pSignatureAlgorithm]
0x18007139d  mov     rbx, r9
0x1800713a0  mov     [rbp+1B0h+var_178], rax
0x1800713a4  mov     r13d, esi
0x1800713a7  mov     rax, [rbp+1B0h+pStartTime]
0x1800713ae  mov     [rsp+2B0h+phProv], rcx
0x1800713b3  mov     rcx, [rbp+1B0h+pEndTime]
0x1800713ba  mov     [rbp+1B0h+lpSystemTime], rax
0x1800713be  mov     [rsp+2B0h+var_240], r8d
0x1800713c3  mov     [rbp+1B0h+var_180], rdx
0x1800713c7  mov     [rbp+1B0h+var_168], rcx
0x1800713cb  call    cs:__imp_GetLastError
0x1800713d1  xorps   xmm0, xmm0
0x1800713d4  mov     [rsp+2B0h+var_250], esi
0x1800713d8  mov     [rsp+2B0h+var_23C], eax
0x1800713dc  lea     rcx, [rbp+1B0h+pvStructInfo]; void *
0x1800713e0  xor     eax, eax
0x1800713e2  mov     [rbp+1B0h+var_208], rsi
0x1800713e6  xor     edx, edx; Val
0x1800713e8  mov     [rbp+1B0h+var_148], rax
0x1800713ec  mov     r8d, 0D0h; Size
0x1800713f2  mov     [rsp+2B0h+cbCertEncoded], esi
0x1800713f6  mov     r14d, esi
0x1800713f9  mov     [rsp+2B0h+pdwDataLen], esi
0x1800713fd  mov     edi, esi
0x1800713ff  mov     [rbp+1B0h+hMem], rsi
0x180071403  mov     r15d, esi
0x180071406  mov     [rbp+1B0h+StringUuid], rsi
0x18007140a  movups  [rbp+1B0h+var_158], xmm0
0x18007140e  mov     [rbp+1B0h+phUserKey], rsi
0x180071412  movups  xmmword ptr [rbp+1B0h+Uuid.Data1], xmm0
0x180071419  mov     [rbp+1B0h+phProvider], rsi
0x18007141d  call    memset_0
0x180071422  xorps   xmm1, xmm1
0x180071425  lea     r8d, [rsi+40h]; Size
0x180071429  xorps   xmm0, xmm0
0x18007142c  lea     rcx, [rbp+1B0h+pcbEncoded]; void *
0x180071430  xor     edx, edx; Val
0x180071432  movups  xmmword ptr [rbp+1B0h+var_70.Data1], xmm0
0x180071439  movups  xmmword ptr [rbp+1B0h+pv], xmm1
0x18007143d  movups  xmmword ptr [rbp+1B0h+pbData], xmm1
0x180071441  movups  xmmword ptr [rbp+1B0h+dwKeySpec], xmm1
0x180071445  call    memset_0
0x18007144a  lea     rsi, [rbx+28h]
0x18007144e  test    rbx, rbx
0x180071451  jnz     short loc_18007145C
0x180071453  mov     [rbp+1B0h+dwKeySpec+8], 2
0x18007145a  jmp     short loc_180071461
0x18007145c  mov     eax, [rsi]
0x18007145e  mov     [rbp+1B0h+dwKeySpec+8], eax
0x180071461  mov     rcx, [rsp+2B0h+phProv]; hKey
0x180071466  test    rcx, rcx
0x180071469  jnz     loc_1800715D5
0x18007146f  mov     [rsp+2B0h+var_260], edi
0x180071473  mov     [rsp+2B0h+var_238], 1
0x18007147b  test    rbx, rbx
0x18007147e  jnz     short loc_1800714EE
0x180071480  lea     rcx, [rbp+1B0h+Uuid]; Uuid
0x180071487  call    cs:__imp_UuidCreate
0x18007148d  lea     rdx, [rbp+1B0h+StringUuid]; StringUuid
0x180071491  lea     rcx, [rbp+1B0h+Uuid]; Uuid
0x180071498  call    cs:__imp_UuidToStringW
0x18007149e  test    eax, eax
0x1800714a0  jz      short loc_1800714D7
0x1800714a2  mov     ecx, eax; dwErrCode
0x1800714a4  call    cs:__imp_SetLastError
0x1800714aa  mov     esi, edi
0x1800714ac  call    cs:__imp_GetLastError
0x1800714b2  mov     ebx, eax
0x1800714b4  mov     eax, 8000FFFFh
0x1800714b9  test    ebx, ebx
0x1800714bb  cmovz   ebx, eax
0x1800714be  test    r13, r13
0x1800714c1  jz      short loc_1800714CB
0x1800714c3  mov     rcx, r13; pCertContext
0x1800714c6  call    CertFreeCertificateContext
0x1800714cb  mov     r12, [rbp+1B0h+var_208]
0x1800714cf  xor     r13d, r13d
0x1800714d2  jmp     loc_180071A91
0x1800714d7  mov     rdx, [rbp+1B0h+StringUuid]
0x1800714db  mov     r9d, 1
0x1800714e1  mov     [rsp+2B0h+dwFlags], 8
0x1800714e9  xor     r8d, r8d
0x1800714ec  jmp     short loc_18007152D
0x1800714ee  mov     r9d, [rbx+10h]; dwProvType
0x1800714f2  test    r9d, r9d
0x1800714f5  jz      loc_18007157E
0x1800714fb  mov     eax, [rbx+14h]
0x1800714fe  lea     rcx, [rsp+2B0h+phProv]; phProv
0x180071503  mov     r8, [rbx+8]; szProvider
0x180071507  mov     rdx, [rbx]; szContainer
0x18007150a  mov     [rsp+2B0h+dwFlags], eax; dwFlags
0x18007150e  call    cs:__imp_CryptAcquireContextW
0x180071514  test    eax, eax
0x180071516  jnz     short loc_180071546
0x180071518  mov     eax, [rbx+14h]
0x18007151b  mov     r9d, [rbx+10h]; dwProvType
0x18007151f  or      eax, 8
0x180071522  mov     r8, [rbx+8]; szProvider
0x180071526  mov     rdx, [rbx]; szContainer
0x180071529  mov     [rsp+2B0h+dwFlags], eax; dwFlags
0x18007152d  lea     rcx, [rsp+2B0h+phProv]; phProv
0x180071532  call    cs:__imp_CryptAcquireContextW
0x180071538  test    eax, eax
0x18007153a  jnz     short loc_180071546
0x18007153c  mov     [rsp+2B0h+phProv], rdi
0x180071541  jmp     loc_1800714AA
0x180071546  mov     edx, [rbp+1B0h+dwKeySpec+8]; dwKeySpec
0x180071549  lea     r8, [rbp+1B0h+phUserKey]; phUserKey
0x18007154d  mov     rcx, [rsp+2B0h+phProv]; hProv
0x180071552  call    cs:__imp_CryptGetUserKey
0x180071558  test    eax, eax
0x18007155a  jnz     loc_1800715E3
0x180071560  mov     edx, [rbp+1B0h+dwKeySpec+8]; Algid
0x180071563  lea     r9, [rbp+1B0h+phUserKey]; phKey
0x180071567  mov     rcx, [rsp+2B0h+phProv]; hProv
0x18007156c  xor     r8d, r8d; dwFlags
0x18007156f  call    cs:__imp_CryptGenKey
0x180071575  test    eax, eax
0x180071577  jnz     short loc_1800715E3
0x180071579  jmp     loc_1800714AA
0x18007157e  mov     rdx, [rbx+8]; pszProviderName
0x180071582  lea     rcx, [rbp+1B0h+phProvider]; phProvider
0x180071586  xor     r8d, r8d; dwFlags
0x180071589  mov     [rsp+2B0h+var_260], 1
0x180071591  call    cs:__imp_NCryptOpenStorageProvider
0x180071597  test    eax, eax
0x180071599  jz      short loc_1800715AC
0x18007159b  mov     ecx, eax; dwErrCode
0x18007159d  call    cs:__imp_SetLastError
0x1800715a3  mov     esi, [rsp+2B0h+var_260]
0x1800715a7  jmp     loc_1800714AC
0x1800715ac  mov     eax, [rbx+14h]
0x1800715af  lea     rdx, [rsp+2B0h+phProv]; phKey
0x1800715b4  mov     r8, [rbx]; pszKeyName
0x1800715b7  xor     r9d, r9d
0x1800715ba  cmp     dword ptr [rsi], 0FFFFFFFFh
0x1800715bd  mov     rcx, [rbp+1B0h+phProvider]; hProvider
0x1800715c1  cmovnz  r9d, [rsi]; dwLegacyKeySpec
0x1800715c5  mov     [rsp+2B0h+dwFlags], eax; dwFlags
0x1800715c9  call    cs:__imp_NCryptOpenKey
0x1800715cf  test    eax, eax
0x1800715d1  jz      short loc_1800715E3
0x1800715d3  jmp     short loc_18007159B
0x1800715d5  mov     [rsp+2B0h+var_238], edi
0x1800715d9  call    cs:__imp_NCryptIsKeyHandle
0x1800715df  mov     [rsp+2B0h+var_260], eax
0x1800715e3  mov     r14, [rsp+2B0h+phProv]
0x1800715e8  mov     esi, [rsp+2B0h+var_240]
0x1800715ec  mov     rcx, r14; hKey
0x1800715ef  mov     r15d, [rbp+1B0h+dwKeySpec+8]
0x1800715f3  and     esi, 3C000000h
0x1800715f9  call    cs:__imp_NCryptIsKeyHandle
0x1800715ff  test    eax, eax
0x180071601  lea     rax, [rsp+2B0h+var_250]
0x180071606  jz      short loc_18007163B
0x180071608  xor     r15d, r15d
0x18007160b  mov     [rsp+2B0h+pInfo], rax; unsigned int *
0x180071610  mov     [rsp+2B0h+pvAuxInfo], r15; struct _CERT_PUBLIC_KEY_INFO *
0x180071615  lea     rcx, [rbp+1B0h+pvKey]; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x180071619  mov     r9d, esi; unsigned int
0x18007161c  mov     [rbp+1B0h+pvKey], 1
0x180071624  xor     r8d, r8d; pvKey
0x180071627  mov     [rbp+1B0h+var_210], r14
0x18007162b  lea     edx, [r15+1]; unsigned int
0x18007162f  mov     qword ptr [rsp+2B0h+dwFlags], r15; void *
0x180071634  call    ?I_CryptCNGExportPublicKeyInfoEx2@@YAHPEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@KPEADKPEAXPEAU_CERT_PUBLIC_KEY_INFO@@PEAK@Z; I_CryptCNGExportPublicKeyInfoEx2(_CNG_NCRYPT_OR_BCRYPT_KEY *,ulong,char *,ulong,void *,_CERT_PUBLIC_KEY_INFO *,ulong *)
0x180071639  jmp     short loc_18007165A
0x18007163b  xor     r9d, r9d
0x18007163e  mov     [rsp+2B0h+pcbInfo], rax
0x180071643  mov     edx, r15d
0x180071646  mov     [rsp+2B0h+pInfo], rdi
0x18007164b  mov     rcx, r14
0x18007164e  lea     r8d, [r9+1]
0x180071652  call    ExportCspPublicKeyInfoEx
0x180071657  xor     r15d, r15d
0x18007165a  test    eax, eax
0x18007165c  jz      loc_180071BF9
0x180071662  mov     ecx, [rsp+2B0h+var_250]; uBytes
0x180071666  call    PkiNonzeroAlloc
0x18007166b  mov     r14, rax
0x18007166e  test    rax, rax
0x180071671  jz      loc_180071BFC
0x180071677  mov     edx, [rbp+1B0h+dwKeySpec+8]; dwKeySpec
0x18007167a  lea     rax, [rsp+2B0h+var_250]
0x18007167f  mov     rcx, [rsp+2B0h+phProv]; hCryptProvOrNCryptKey
0x180071684  xor     r9d, r9d; pszPublicKeyObjId
0x180071687  mov     [rsp+2B0h+pcbInfo], rax; pcbInfo
0x18007168c  mov     [rsp+2B0h+pInfo], r14; pInfo
0x180071691  mov     [rsp+2B0h+pvAuxInfo], r15; pvAuxInfo
0x180071696  lea     r8d, [r9+1]; dwCertEncodingType
0x18007169a  mov     [rsp+2B0h+dwFlags], esi; dwFlags
0x18007169e  call    CryptExportPublicKeyInfoEx
0x1800716a3  test    eax, eax
0x1800716a5  jz      loc_180071BFC
0x1800716ab  mov     ecx, 1; dwKeyType
0x1800716b0  test    r12, r12
0x1800716b3  jnz     short loc_18007171E
0x1800716b5  mov     rdx, [r14]; pvKey
0x1800716b8  lea     rsi, a13143229; "1.3.14.3.2.29"
0x1800716bf  mov     r8d, 40000003h; dwGroupId
0x1800716c5  call    CryptFindOIDInfo
0x1800716ca  mov     rcx, rax
0x1800716cd  test    rax, rax
0x1800716d0  jz      short loc_18007170C
0x1800716d2  cmp     dword ptr [rcx+1Ch], 0FFFFFFFDh
0x1800716d6  lea     rax, aSha1_0; "SHA1"
0x1800716dd  mov     [rbp+1B0h+pvKey], rax
0x1800716e1  mov     rax, [rcx+30h]
0x1800716e5  mov     [rbp+1B0h+var_210], rax
0x1800716e9  jnz     short loc_1800716F0
0x1800716eb  mov     rsi, [r14]
0x1800716ee  jmp     short loc_18007170C
0x1800716f0  mov     r8d, 4; dwGroupId
0x1800716f6  lea     rdx, [rbp+1B0h+pvKey]; pvKey
0x1800716fa  lea     ecx, [r8+2]; dwKeyType
0x1800716fe  call    CryptFindOIDInfo
0x180071703  test    rax, rax
0x180071706  jz      short loc_18007170C
0x180071708  mov     rsi, [rax+8]
0x18007170c  xorps   xmm0, xmm0
0x18007170f  mov     qword ptr [rbp+1B0h+var_158], rsi
0x180071713  movdqu  [rbp+1B0h+var_158+8], xmm0
0x180071718  lea     r12, [rbp+1B0h+var_158]
0x18007171c  jmp     short loc_18007173F
0x18007171e  mov     rdx, [r12]; pvKey
0x180071722  mov     r8d, 40000004h; dwGroupId
0x180071728  call    CryptFindOIDInfo
0x18007172d  test    rax, rax
0x180071730  jz      short loc_18007173F
0x180071732  cmp     dword ptr [rax+1Ch], 0FFFFFFFDh
0x180071736  jnz     short loc_18007173F
0x180071738  mov     rax, [r12]
0x18007173c  mov     [r14], rax
0x18007173f  lea     rcx, [rbp+1B0h+var_70]; Uuid
0x180071746  call    cs:__imp_UuidCreate
0x18007174c  lea     rax, [rbp+1B0h+var_70]
0x180071753  mov     esi, 2
0x180071758  mov     [rbp+1B0h+pvStructInfo], esi
0x18007175b  movups  xmm0, xmmword ptr [r14]
0x18007175f  movaps  [rbp+1B0h+var_E0], xmm0
0x180071766  movups  xmm1, xmmword ptr [r14+10h]
0x18007176b  movaps  [rbp+1B0h+var_D0], xmm1
0x180071772  movups  xmm0, xmmword ptr [r14+20h]
0x180071777  mov     [rbp+1B0h+var_130], rax
0x18007177e  mov     rax, [rbp+1B0h+var_180]
0x180071782  movsd   xmm1, qword ptr [r12+10h]
0x180071789  movaps  [rbp+1B0h+var_C0], xmm0
0x180071790  movups  xmm0, xmmword ptr [r12]
0x180071795  mov     [rbp+1B0h+var_138], 10h
0x18007179c  movsd   [rbp+1B0h+var_118], xmm1
0x1800717a4  movups  [rbp+1B0h+var_128], xmm0
0x1800717ab  movups  xmm0, xmmword ptr [rax]
0x1800717ae  mov     al, [rbp+1B0h+var_70.Data4+7]
0x1800717b4  and     al, 7Fh
0x1800717b6  mov     [rbp+1B0h+var_70.Data4+7], al
0x1800717bc  movdqu  [rbp+1B0h+var_110], xmm0
0x1800717c4  movdqu  [rbp+1B0h+var_F0], xmm0
0x1800717cc  jnz     short loc_1800717D7
0x1800717ce  mov     [rbp+1B0h+var_70.Data4+7], 61h ; 'a'
0x1800717d5  jmp     short loc_1800717E3
0x1800717d7  test    al, 0F0h
0x1800717d9  jnz     short loc_1800717E3
0x1800717db  or      al, 10h
0x1800717dd  mov     [rbp+1B0h+var_70.Data4+7], al
0x1800717e3  mov     rcx, [rbp+1B0h+var_178]
0x1800717e7  test    rcx, rcx
0x1800717ea  jz      short loc_1800717FF
0x1800717ec  mov     eax, [rcx]
0x1800717ee  mov     [rbp+1B0h+var_80], eax
0x1800717f4  mov     rax, [rcx+8]
0x1800717f8  mov     [rbp+1B0h+var_78], rax
0x1800717ff  mov     rax, [rbp+1B0h+lpSystemTime]
0x180071803  test    rax, rax
0x180071806  jnz     short loc_180071817
0x180071808  lea     rcx, [rbp+1B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007180f  call    cs:__imp_GetSystemTimeAsFileTime
0x180071815  jmp     short loc_18007182F
0x180071817  lea     rdx, [rbp+1B0h+SystemTimeAsFileTime]; lpFileTime
0x18007181e  mov     rcx, rax; lpSystemTime
0x180071821  call    cs:__imp_SystemTimeToFileTime
0x180071827  test    eax, eax
0x180071829  jz      loc_180071BFC
0x18007182f  mov     rax, [rbp+1B0h+var_168]
0x180071833  test    rax, rax
  ... truncated ...
```
