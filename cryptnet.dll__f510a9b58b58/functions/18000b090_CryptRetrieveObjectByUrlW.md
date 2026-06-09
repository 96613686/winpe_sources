# CryptRetrieveObjectByUrlW

- ea: `0x18000b090`
- end: `0x18000ba7c`
- name: `CryptRetrieveObjectByUrlW`
- size: `2540`
- prototype: `BOOL __stdcall(LPCWSTR pszUrl, LPCSTR pszObjectOid, DWORD dwRetrievalFlags, DWORD dwTimeout, LPVOID *ppvObject, HCRYPTASYNC hAsyncRetrieve, PCRYPT_CREDENTIALS pCredentials, LPVOID pvVerify, PCRYPT_RETRIEVE_AUX_INFO pAuxInfo)`
- caller_count: `4`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a9d0`
- `0x18000c620`
- `0x18001dc80`
- `0x18001f61c`

## callees

- `0x1800012c4`
- `0x1800013fc`
- `0x1800015bc`
- `0x18000b090`
- `0x18000ba90`
- `0x18000bb78`
- `0x18000bc60`
- `0x18000d5d0`
- `0x1800171e4`
- `0x180017f70`
- `0x180018b30`
- `0x1800194ec`
- `0x180020140`
- `0x180026546`
- `0x180026552`
- `0x18002656a`
- `0x1800265b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b412`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b6d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b869`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b971`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b412`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b6d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b869`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b971`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b957`
- `CRYPT32!I_CryptGetTls` at `0x18000b8f1`
- `CRYPT32!I_CryptGetTls` at `0x18000b8f1`
- `CRYPT32!I_CertDiagControl` at `0x18000b14d`
- `CRYPT32!I_CertDiagControl` at `0x18000b48c`
- `CRYPT32!I_CertDiagControl` at `0x18000b6c8`
- `CRYPT32!I_CertDiagControl` at `0x18000b14d`
- `CRYPT32!I_CertDiagControl` at `0x18000b48c`
- `CRYPT32!I_CertDiagControl` at `0x18000b6c8`
- `CRYPT32!CryptMemAlloc` at `0x18000b828`
- `CRYPT32!CryptMemAlloc` at `0x18000b828`
- `CRYPT32!CryptMemFree` at `0x18000b5ef`
- `CRYPT32!CryptMemFree` at `0x18000b97c`
- `CRYPT32!CryptMemFree` at `0x18000ba71`
- `CRYPT32!CryptMemFree` at `0x18000b5ef`
- `CRYPT32!CryptMemFree` at `0x18000b97c`
- `CRYPT32!CryptMemFree` at `0x18000ba71`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000b3af`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000b3c8`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000b3af`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000b3c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b615`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b615`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b193`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b193`

## string_xrefs

- `0x18000b16e`: `CRYPTNET.DLL --> %s URL to retrieve: %S\n`
- `0x18000b160`: `Cached`
- `0x18000b3fa`: `CRYPTNET.DLL --> %s URL to retrieve: %S, failed: %d (0x%x)\n`
- `0x18000b99a`: `CRYPTNET.DLL --> CryptRetrieveObjectByUrl, already pending for : %S\n`

## pseudocode

```c
BOOL __stdcall CryptRetrieveObjectByUrlW(
        LPCWSTR pszUrl,
        LPCSTR pszObjectOid,
        DWORD dwRetrievalFlags,
        DWORD dwTimeout,
        LPVOID *ppvObject,
        HCRYPTASYNC hAsyncRetrieve,
        PCRYPT_CREDENTIALS pCredentials,
        LPVOID pvVerify,
        PCRYPT_RETRIEVE_AUX_INFO pAuxInfo)
{
  DWORD v9; // ebx
  const char *v11; // r13
  const char *v13; // rax
  CObjectRetrievalManager *v14; // rax
  CObjectRetrievalManager *v15; // rbx
  LPWSTR pwszCacheFileNamePrefix; // r14
  DWORD cbSize; // ecx
  LPFILETIME pftCacheResync; // rax
  unsigned int *v19; // r8
  int Providers; // r14d
  DWORD v21; // r13d
  DWORD v22; // edi
  int v23; // eax
  void *v24; // rcx
  void *v25; // rcx
  DWORD v26; // edi
  PCRYPT_RETRIEVE_AUX_INFO v28; // rbx
  FILETIME *pLastSyncTime; // rcx
  PCRYPTNET_URL_CACHE_PRE_FETCH_INFO pPreFetchInfo; // rdi
  __int64 v31; // rbx
  unsigned int v32; // r15d
  PCRYPTNET_URL_CACHE_FLUSH_INFO pFlushInfo; // rbx
  __int64 v34; // rdi
  unsigned int v35; // r15d
  PCRYPTNET_URL_CACHE_RESPONSE_INFO *ppResponseInfo; // rcx
  LPWSTR *ppwszErrorResponseHeaders; // rcx
  PCRYPT_DATA_BLOB *v38; // rcx
  DWORD v39; // ecx
  __int64 v40; // rdi
  unsigned int v42; // r14d
  struct _OFFLINE_URL_CACHE_ENTRY *v43; // rdi
  int v44; // eax
  int v45; // ecx
  __int64 v46; // rdi
  void (__fastcall *v47)(char *, __int64 *, __int64); // r13
  PCRYPT_DATA_BLOB *ppErrorContentBlob; // rax
  int v49; // eax
  struct _CRYPTOAPI_BLOB *v50; // rax
  DWORD v51; // edx
  DWORD LastError; // edi
  DWORD dwErrCode; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Size; // [rsp+64h] [rbp-9Ch]
  DWORD Size_4; // [rsp+68h] [rbp-98h]
  char *v56; // [rsp+70h] [rbp-90h]
  PCRYPT_RETRIEVE_AUX_INFO v57; // [rsp+78h] [rbp-88h]
  struct _CRYPT_BLOB_ARRAY **v58; // [rsp+80h] [rbp-80h]
  __int64 v59; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+90h] [rbp-70h]
  struct _CERT_CONTEXT *v61; // [rsp+98h] [rbp-68h]
  void *v62; // [rsp+A0h] [rbp-60h] BYREF
  PCRYPT_CREDENTIALS v63; // [rsp+A8h] [rbp-58h] BYREF
  struct _CRYPTOAPI_BLOB *v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-40h] BYREF
  void (__fastcall *v67)(char *, __int64 *, __int64); // [rsp+C8h] [rbp-38h] BYREF
  const char *v68; // [rsp+D0h] [rbp-30h]
  int v69; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  void *v73; // [rsp+F0h] [rbp-10h] BYREF
  int v74; // [rsp+F8h] [rbp-8h]
  int v75; // [rsp+FCh] [rbp-4h]
  LPCWSTR v76; // [rsp+100h] [rbp+0h]
  const char *v77; // [rsp+108h] [rbp+8h]
  DWORD v78; // [rsp+110h] [rbp+10h]
  DWORD v79; // [rsp+114h] [rbp+14h]
  struct _CRYPT_BLOB_ARRAY *v80; // [rsp+118h] [rbp+18h]
  PCRYPT_RETRIEVE_AUX_INFO v81; // [rsp+120h] [rbp+20h]
  _BYTE v82[40]; // [rsp+130h] [rbp+30h] BYREF
  int v83; // [rsp+158h] [rbp+58h] BYREF
  FILETIME *v84; // [rsp+160h] [rbp+60h]
  DWORD dwMaxUrlRetrievalByteCount; // [rsp+168h] [rbp+68h]
  unsigned int *v86; // [rsp+170h] [rbp+70h]
  unsigned int *v87; // [rsp+178h] [rbp+78h]
  LPVOID *v88; // [rsp+180h] [rbp+80h]
  LPWSTR v89; // [rsp+188h] [rbp+88h]
  struct _FILETIME *v90; // [rsp+190h] [rbp+90h]
  BOOL v91; // [rsp+198h] [rbp+98h]
  DWORD v92; // [rsp+19Ch] [rbp+9Ch]
  LPVOID *v93; // [rsp+1A0h] [rbp+A0h]
  LPVOID *p_pv; // [rsp+1A8h] [rbp+A8h]
  FILETIME v95; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v96; // [rsp+1B8h] [rbp+B8h] BYREF
  char Src[36]; // [rsp+1BCh] [rbp+BCh] BYREF
  unsigned int v98; // [rsp+1E0h] [rbp+E0h] BYREF
  char v99[12]; // [rsp+1E4h] [rbp+E4h] BYREF
  LPVOID v100; // [rsp+1F0h] [rbp+F0h] BYREF
  LPVOID v101; // [rsp+1F8h] [rbp+F8h] BYREF
  LPVOID pv; // [rsp+200h] [rbp+100h] BYREF
  struct _FILETIME v103; // [rsp+208h] [rbp+108h] BYREF

  v9 = dwTimeout;
  v11 = pszObjectOid;
  v63 = pCredentials;
  v56 = (char *)pszObjectOid;
  v61 = (struct _CERT_CONTEXT *)pvVerify;
  Size_4 = dwTimeout;
  v58 = (struct _CRYPT_BLOB_ARRAY **)ppvObject;
  v64 = (struct _CRYPTOAPI_BLOB *)hAsyncRetrieve;
  memset_0(v82, 0, 0x120u);
  for ( *ppvObject = 0; *pszUrl == 32; ++pszUrl )
    ;
  if ( (dwRetrievalFlags & 0x10000000) != 0 )
    return SchemeCreateNewFlushEntry(pszUrl, v61);
  v62 = 0;
  dwErrCode = dwRetrievalFlags;
  I_CertDiagControl(7, &dwErrCode, &v62);
  v13 = "Cached";
  if ( (dwRetrievalFlags & 2) == 0 )
    v13 = "Wire";
  v68 = v13;
  I_CryptNetDebugTracePrintfA("CRYPTNET.DLL --> %s URL to retrieve: %S\n", v13, pszUrl);
  if ( v9
    && (dwRetrievalFlags & 2) == 0
    && (unsigned __int64)v11 <= 0xFFFF
    && !hAsyncRetrieve
    && !v63
    && !v61
    && !I_CryptGetTls((unsigned int)hCryptNetCancelTls) )
  {
    if ( !(unsigned int)IsPendingCryptRetrieveObjectByUrl(pszUrl) )
      return CryptRetrieveObjectByUrlWithTimeout(pszUrl, v11, dwRetrievalFlags, v9, (void **)v58, pAuxInfo, v62);
    I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> CryptRetrieveObjectByUrl, already pending for : %S\n", pszUrl);
    SetLastError(0x3Au);
    CryptDiagAddActionWithLastError(L"IsPendingNetworkRetrieval");
    goto LABEL_138;
  }
  v14 = (CObjectRetrievalManager *)LocalAlloc(0x40u, 0x30u);
  v15 = v14;
  if ( v14 )
  {
    *(_QWORD *)v14 = &CObjectRetrievalManager::`vftable';
    dwErrCode = 1;
    *((_DWORD *)v14 + 2) = 1;
    *((_QWORD *)v14 + 2) = 0;
    *((_QWORD *)v14 + 3) = 0;
    *((_QWORD *)v14 + 4) = 0;
    *((_QWORD *)v14 + 5) = 0;
    if ( v62 )
    {
      if ( !pAuxInfo || pAuxInfo->cbSize <= 0x30 || (pwszCacheFileNamePrefix = pAuxInfo->pwszCacheFileNamePrefix) == 0 )
        pwszCacheFileNamePrefix = 0;
      memset_0(v82, 0, 0x120u);
      v83 = 88;
      v84 = &v95;
      v86 = &v96;
      v87 = &v98;
      v88 = &v100;
      v93 = &v101;
      p_pv = &pv;
      v96 = 40;
      v98 = 16;
      v89 = pwszCacheFileNamePrefix;
      if ( pAuxInfo )
      {
        cbSize = pAuxInfo->cbSize;
        if ( pAuxInfo->cbSize > 0x10 )
          dwMaxUrlRetrievalByteCount = pAuxInfo->dwMaxUrlRetrievalByteCount;
        if ( cbSize > 0x38 )
        {
          pftCacheResync = pAuxInfo->pftCacheResync;
          if ( pftCacheResync )
          {
            v90 = &v103;
            v103 = *pftCacheResync;
          }
        }
      }
      v57 = (PCRYPT_RETRIEVE_AUX_INFO)&v83;
    }
    else
    {
      v57 = pAuxInfo;
    }
    v60 = 0;
    v67 = 0;
    v66 = 0;
    v59 = 0;
    SetLastError(0x80070057);
    if ( (dwRetrievalFlags & 0x10) == 0 )
    {
      Size = dwRetrievalFlags & 4;
      if ( (dwRetrievalFlags & 4) == 0 || (dwRetrievalFlags & 2) == 0 )
      {
        if ( (dwRetrievalFlags & 0x40) != 0 )
        {
          SetLastError(0x80004001);
        }
        else if ( (dwRetrievalFlags & 0x60) != 0x60
               && ((dwRetrievalFlags & 0x60) == 0 || v61 && (dwRetrievalFlags & 1) == 0) )
        {
          SetLastError(0);
          Providers = CObjectRetrievalManager::LoadProviders(v15, pszUrl, v11);
          if ( Providers == 1 )
          {
            v65 = 0;
            v21 = dwRetrievalFlags & 0x4002;
            if ( v21 == 0x4000 )
            {
              v40 = -1;
              while ( pszUrl[++v40] != 0 )
                ;
              EnterCriticalSection(&OfflineUrlCacheCriticalSection);
              v42 = 2 * v40;
              v43 = pOfflineUrlCacheHead;
              v44 = 0x10000;
              if ( (unsigned int)v56 <= 0xFFFF )
                v44 = (int)v56;
              v45 = v44 | 0x20000;
              if ( !Size )
                v45 = v44;
              Size = v45;
              while ( v43 )
              {
                if ( *((_DWORD *)v43 + 8) == v45 && *(_DWORD *)v43 == v42 && !*((_DWORD *)v43 + 4) )
                {
                  if ( !v42 || !memcmp_0(*((const void **)v43 + 1), pszUrl, v42) )
                  {
                    dwErrCode = GetOfflineUrlTimeStatus((struct _OFFLINE_URL_CACHE_ENTRY *)((char *)v43 + 36));
                    if ( (int)dwErrCode <= 0 )
                      v65 = *((_QWORD *)v43 + 5);
                    break;
                  }
                  v45 = Size;
                }
                v43 = (struct _OFFLINE_URL_CACHE_ENTRY *)*((_QWORD *)v43 + 6);
              }
              LeaveCriticalSection(&OfflineUrlCacheCriticalSection);
              v22 = dwErrCode;
              if ( (dwErrCode & 0x80000000) != 0 )
              {
                v63 = (PCRYPT_CREDENTIALS)&v65;
                I_CertDiagControl(10, &v63, 0);
                SetLastError(0x8CAu);
                CryptDiagAddActionWithLastError(L"CanRetrieveFromNetwork");
                Providers = 0;
                goto LABEL_30;
              }
            }
            else
            {
              v22 = 1;
            }
            v23 = (*((__int64 (__fastcall **)(LPCWSTR, char *, _QWORD, _QWORD, __int64 *, void (__fastcall **)(char *, __int64 *, __int64), __int64 *, struct _CRYPTOAPI_BLOB *, PCRYPT_CREDENTIALS, PCRYPT_RETRIEVE_AUX_INFO))v15
                   + 3))(
                    pszUrl,
                    v56,
                    dwRetrievalFlags,
                    Size_4,
                    &v59,
                    &v67,
                    &v66,
                    v64,
                    v63,
                    v57);
            Providers = v23;
            if ( v21 == 0x4000 )
            {
              if ( v23 == 1 )
              {
                if ( !v22 )
                  SetOnlineUrlW(pszUrl, v56, dwRetrievalFlags);
                goto LABEL_97;
              }
              LastError = GetLastError();
              SetOfflineUrlW(pszUrl, v56, dwRetrievalFlags);
              SetLastError(LastError);
            }
          }
          if ( !Providers )
          {
LABEL_30:
            v24 = (void *)*((_QWORD *)v15 + 2);
            if ( v24 )
            {
              CryptFreeOIDFunctionAddress(v24, 0);
              *((_QWORD *)v15 + 2) = 0;
            }
            v25 = (void *)*((_QWORD *)v15 + 4);
            if ( v25 )
            {
              CryptFreeOIDFunctionAddress(v25, 0);
              *((_QWORD *)v15 + 4) = 0;
            }
            if ( Providers )
            {
              (*(void (__fastcall **)(CObjectRetrievalManager *))(*(_QWORD *)v15 + 8LL))(v15);
            }
            else
            {
              v26 = GetLastError();
              (*(void (__fastcall **)(CObjectRetrievalManager *))(*(_QWORD *)v15 + 8LL))(v15);
              I_CryptNetDebugErrorPrintfA(
                "CRYPTNET.DLL --> %s URL to retrieve: %S, failed: %d (0x%x)\n",
                v68,
                pszUrl,
                v26,
                v26);
              SetLastError(v26);
            }
            v9 = Size_4;
            v11 = v56;
            goto LABEL_37;
          }
LABEL_97:
          if ( !(_DWORD)v59 )
          {
            if ( (dwRetrievalFlags & 0x400000) == 0 )
            {
              Providers = 0;
              SetLastError(0x8000FFFF);
            }
            goto LABEL_30;
          }
          v46 = v66;
          v47 = v67;
          if ( !v56 || v56 == (char *)6 )
          {
            v70 = v60;
            v72 = 0;
            v69 = v59;
            v71 = v59;
            Providers = CCryptBlobArray::GetArrayInSingleBufferEncodedForm((CCryptBlobArray *)&v69, v58, v19);
LABEL_101:
            v47(v56, &v59, v46);
            goto LABEL_30;
          }
          Providers = (*((__int64 (__fastcall **)(char *, _QWORD, __int64 *, struct _CRYPT_BLOB_ARRAY **))v15 + 5))(
                        v56,
                        dwRetrievalFlags,
                        &v59,
                        v58);
          if ( Providers == 1 )
          {
            if ( (dwRetrievalFlags & 0x20) == 0 )
              goto LABEL_101;
            Providers = ObjectContextVerifySignature(v56, *v58, v61);
          }
          else
          {
            CryptDiagAddActionWithLastError(L"Call_CryptQueryObject");
          }
          if ( !Providers )
          {
            if ( v57 )
            {
              if ( v57->cbSize > 0x50 )
              {
                ppErrorContentBlob = v57->ppErrorContentBlob;
                if ( ppErrorContentBlob )
                {
                  if ( !*ppErrorContentBlob && (_DWORD)v59 && *(_DWORD *)v60 )
                  {
                    dwErrCode = GetLastError();
                    v49 = 4096;
                    if ( *(_DWORD *)v60 < 0x1000u )
                      v49 = *(_DWORD *)v60;
                    Size = v49;
                    v50 = (struct _CRYPTOAPI_BLOB *)CryptMemAlloc(v49 + 16);
                    v64 = v50;
                    if ( v50 )
                    {
                      v51 = Size;
                      v50->pbData = (BYTE *)&v50[1];
                      v50->cbData = v51;
                      memcpy_0(&v50[1], *(const void **)(v60 + 8), v51);
                      *v57->ppErrorContentBlob = v64;
                    }
                    SetLastError(dwErrCode);
                  }
                }
              }
            }
          }
          goto LABEL_101;
        }
      }
    }
    Providers = 0;
    goto LABEL_30;
  }
  SetLastError(0x8007000E);
  SetLastError(8u);
  SetLastError(0x8007000E);
  v9 = Size_4;
LABEL_138:
  v57 = 0;
  Providers = 0;
LABEL_37:
  if ( v62 )
  {
    v73 = v62;
    v79 = v9;
    v28 = v57;
    v75 = 0;
    v74 = Providers;
    v76 = pszUrl;
    v77 = v11;
    v80 = *v58;
    v78 = dwRetrievalFlags;
    v81 = v57;
    I_CertDiagControl(8, &v73, 0);
    if ( v28 )
    {
      if ( pAuxInfo )
      {
        if ( pAuxInfo->cbSize > 8 )
        {
          pLastSyncTime = pAuxInfo->pLastSyncTime;
          if ( pLastSyncTime )
            *pLastSyncTime = v95;
        }
        if ( pAuxInfo->cbSize > 0x18 )
        {
          pPreFetchInfo = pAuxInfo->pPreFetchInfo;
          if ( pPreFetchInfo )
          {
            v31 = v96;
            v32 = pPreFetchInfo->cbSize;
            if ( v96 >= pPreFetchInfo->cbSize )
              v31 = v32;
            if ( (unsigned int)v31 > 4 )
            {
              memcpy_0(&pPreFetchInfo->dwObjectType, Src, v31 - 4);
              if ( v32 > (unsigned int)v31 )
                memset_0((char *)pPreFetchInfo + v31, 0, v32 - (unsigned int)v31);
            }
          }
        }
        if ( pAuxInfo->cbSize > 0x20 )
        {
          pFlushInfo = pAuxInfo->pFlushInfo;
          if ( pFlushInfo )
          {
            v34 = v98;
            v35 = pFlushInfo->cbSize;
            if ( v98 >= pFlushInfo->cbSize )
              v34 = v35;
            if ( (unsigned int)v34 > 4 )
            {
              memcpy_0(&pFlushInfo->dwExemptSeconds, v99, v34 - 4);
              if ( v35 > (unsigned int)v34 )
                memset_0((char *)pFlushInfo + v34, 0, v35 - (unsigned int)v34);
            }
          }
        }
        if ( pAuxInfo->cbSize > 0x28 )
        {
          ppResponseInfo = pAuxInfo->ppResponseInfo;
          if ( ppResponseInfo )
          {
            *ppResponseInfo = (PCRYPTNET_URL_CACHE_RESPONSE_INFO)v100;
            v100 = 0;
          }
        }
        if ( pAuxInfo->cbSize > 0x48 )
        {
          ppwszErrorResponseHeaders = pAuxInfo->ppwszErrorResponseHeaders;
          if ( ppwszErrorResponseHeaders )
          {
            *ppwszErrorResponseHeaders = (LPWSTR)v101;
            v101 = 0;
          }
        }
        if ( pAuxInfo->cbSize > 0x50 )
        {
          v38 = pAuxInfo->ppErrorContentBlob;
          if ( v38 )
          {
            *v38 = (PCRYPT_DATA_BLOB)pv;
            pv = 0;
          }
        }
        v39 = pAuxInfo->cbSize;
        if ( pAuxInfo->cbSize > 0x40 )
          pAuxInfo->fProxyCacheRetrieval = v91;
        if ( v39 > 0x44 )
          pAuxInfo->dwHttpStatusCode = v92;
      }
      if ( v100 )
        CryptMemFree(v100);
      if ( v101 )
        CryptMemFree(v101);
      if ( pv )
        CryptMemFree(pv);
    }
  }
  return Providers;
}

```

## disassembly

```asm
0x18000b090  push    rbp
0x18000b092  push    rbx
0x18000b093  push    rsi
0x18000b094  push    rdi
0x18000b095  push    r12
0x18000b097  push    r13
0x18000b099  push    r14
0x18000b09b  push    r15
0x18000b09d  lea     rbp, [rsp-168h]
0x18000b0a5  sub     rsp, 268h
0x18000b0ac  mov     rax, cs:__security_cookie
0x18000b0b3  xor     rax, rsp
0x18000b0b6  mov     [rbp+1A0h+var_50], rax
0x18000b0bd  mov     rax, [rbp+1A0h+pCredentials]
0x18000b0c4  mov     ebx, r9d
0x18000b0c7  mov     rdi, [rbp+1A0h+ppvObject]
0x18000b0ce  mov     r15d, r8d
0x18000b0d1  mov     r14, [rbp+1A0h+hAsyncRetrieve]
0x18000b0d8  mov     r13, rdx
0x18000b0db  mov     rsi, [rbp+1A0h+pAuxInfo]
0x18000b0e2  mov     r12, rcx
0x18000b0e5  mov     [rbp+1A0h+var_1F8], rax
0x18000b0e9  lea     rcx, [rbp+1A0h+var_170]; void *
0x18000b0ed  mov     rax, [rbp+1A0h+pvVerify]
0x18000b0f4  mov     r8d, 120h; Size
0x18000b0fa  mov     [rsp+2A0h+var_230], rdx
0x18000b0ff  xor     edx, edx; Val
0x18000b101  mov     [rbp+1A0h+var_208], rax
0x18000b105  mov     dword ptr [rsp+2A0h+Size+4], ebx
0x18000b109  mov     [rbp+1A0h+var_220], rdi
0x18000b10d  mov     [rbp+1A0h+var_1F0], r14
0x18000b111  call    memset_0
0x18000b116  xor     eax, eax
0x18000b118  mov     ecx, 20h ; ' '
0x18000b11d  mov     [rdi], rax
0x18000b120  cmp     cx, [r12]
0x18000b125  jz      loc_18000B987
0x18000b12b  bt      r15d, 1Ch
0x18000b130  jb      loc_18000B93D
0x18000b136  lea     r8, [rbp+1A0h+var_200]
0x18000b13a  mov     [rbp+1A0h+var_200], rax
0x18000b13e  lea     rdx, [rsp+2A0h+dwErrCode]
0x18000b143  mov     [rsp+2A0h+dwErrCode], r15d
0x18000b148  mov     ecx, 7
0x18000b14d  call    cs:__imp_I_CertDiagControl
0x18000b153  lea     rcx, aWire; "Wire"
0x18000b15a  mov     edi, r15d
0x18000b15d  and     edi, 2
0x18000b160  lea     rax, aCached; "Cached"
0x18000b167  mov     r8, r12
0x18000b16a  cmovz   rax, rcx
0x18000b16e  lea     rcx, aCryptnetDllSUr_0; "CRYPTNET.DLL --> %s URL to retrieve: %S"...
0x18000b175  mov     rdx, rax
0x18000b178  mov     [rbp+1A0h+var_1D0], rax
0x18000b17c  call    ?I_CryptNetDebugTracePrintfA@@YAXPEBDZZ; I_CryptNetDebugTracePrintfA(char const *,...)
0x18000b181  test    ebx, ebx
0x18000b183  jnz     loc_18000B8B9
0x18000b189  mov     edx, 30h ; '0'; uBytes
0x18000b18e  mov     ecx, 40h ; '@'; uFlags
0x18000b193  call    cs:__imp_LocalAlloc
0x18000b199  mov     rbx, rax
0x18000b19c  test    rax, rax
0x18000b19f  jz      loc_18000B9BF
0x18000b1a5  xor     ecx, ecx
0x18000b1a7  lea     rax, ??_7CObjectRetrievalManager@@6B@; const CObjectRetrievalManager::`vftable'
0x18000b1ae  mov     [rbx], rax
0x18000b1b1  mov     eax, 1
0x18000b1b6  mov     [rsp+2A0h+dwErrCode], eax
0x18000b1ba  mov     [rbx+8], eax
0x18000b1bd  mov     [rbx+10h], rcx
0x18000b1c1  mov     [rbx+18h], rcx
0x18000b1c5  mov     [rbx+20h], rcx
0x18000b1c9  mov     [rbx+28h], rcx
0x18000b1cd  cmp     [rbp+1A0h+var_200], rcx
0x18000b1d1  jz      loc_18000B9F3
0x18000b1d7  test    rsi, rsi
0x18000b1da  jz      short loc_18000B1EA
0x18000b1dc  cmp     dword ptr [rsi], 30h ; '0'
0x18000b1df  jbe     short loc_18000B1EA
0x18000b1e1  mov     r14, [rsi+30h]
0x18000b1e5  test    r14, r14
0x18000b1e8  jnz     short loc_18000B1ED
0x18000b1ea  mov     r14, rcx
0x18000b1ed  xor     edx, edx; Val
0x18000b1ef  lea     rcx, [rbp+1A0h+var_170]; void *
0x18000b1f3  mov     r8d, 120h; Size
0x18000b1f9  call    memset_0
0x18000b1fe  mov     [rbp+1A0h+var_148], 58h ; 'X'
0x18000b205  lea     rax, [rbp+1A0h+var_F0]
0x18000b20c  mov     [rbp+1A0h+var_140], rax
0x18000b210  lea     rax, [rbp+1A0h+var_E8]
0x18000b217  mov     [rbp+1A0h+var_130], rax
0x18000b21b  lea     rax, [rbp+1A0h+var_C0]
0x18000b222  mov     [rbp+1A0h+var_128], rax
0x18000b226  lea     rax, [rbp+1A0h+var_B0]
0x18000b22d  mov     [rbp+1A0h+var_120], rax
0x18000b234  lea     rax, [rbp+1A0h+var_A8]
0x18000b23b  mov     [rbp+1A0h+var_100], rax
0x18000b242  lea     rax, [rbp+1A0h+pv]
0x18000b249  mov     [rbp+1A0h+var_F8], rax
0x18000b250  mov     [rbp+1A0h+var_E8], 28h ; '('
0x18000b25a  mov     [rbp+1A0h+var_C0], 10h
0x18000b264  mov     [rbp+1A0h+var_118], r14
0x18000b26b  test    rsi, rsi
0x18000b26e  jz      short loc_18000B28F
0x18000b270  mov     ecx, [rsi]
0x18000b272  cmp     ecx, 10h
0x18000b275  jbe     short loc_18000B27D
0x18000b277  mov     eax, [rsi+10h]
0x18000b27a  mov     [rbp+1A0h+var_138], eax
0x18000b27d  cmp     ecx, 38h ; '8'
0x18000b280  jbe     short loc_18000B28F
0x18000b282  mov     rax, [rsi+38h]
0x18000b286  test    rax, rax
0x18000b289  jnz     loc_18000B75F
0x18000b28f  lea     r14, [rbp+1A0h+var_148]
0x18000b293  xor     ecx, ecx
0x18000b295  mov     [rsp+2A0h+var_228], r14
0x18000b29a  mov     [rbp+1A0h+var_210], rcx
0x18000b29e  mov     [rbp+1A0h+var_1D8], rcx
0x18000b2a2  mov     [rbp+1A0h+var_1E0], rcx
0x18000b2a6  mov     ecx, 80070057h; dwErrCode
0x18000b2ab  mov     [rbp+1A0h+var_218], 0
0x18000b2b3  call    cs:__imp_SetLastError
0x18000b2b9  test    r15b, 10h
0x18000b2bd  jnz     loc_18000B787
0x18000b2c3  mov     eax, r15d
0x18000b2c6  and     eax, 4
0x18000b2c9  mov     dword ptr [rsp+2A0h+Size], eax
0x18000b2cd  jz      short loc_18000B2D7
0x18000b2cf  test    edi, edi
0x18000b2d1  jnz     loc_18000B787
0x18000b2d7  test    r15b, 40h
0x18000b2db  jnz     loc_18000B9FD
0x18000b2e1  mov     eax, r15d
0x18000b2e4  and     eax, 60h
0x18000b2e7  cmp     eax, 60h ; '`'
0x18000b2ea  jz      loc_18000B787
0x18000b2f0  test    eax, eax
0x18000b2f2  jnz     loc_18000B77C
0x18000b2f8  xor     ecx, ecx; dwErrCode
0x18000b2fa  call    cs:__imp_SetLastError
0x18000b300  mov     r8, r13; char *
0x18000b303  mov     rdx, r12; unsigned __int16 *
0x18000b306  mov     rcx, rbx; this
0x18000b309  call    ?LoadProviders@CObjectRetrievalManager@@AEAAHPEBGPEBD@Z; CObjectRetrievalManager::LoadProviders(ushort const *,char const *)
0x18000b30e  mov     r14d, eax
0x18000b311  cmp     eax, 1
0x18000b314  jnz     loc_18000B39B
0x18000b31a  mov     r13d, r15d
0x18000b31d  mov     [rbp+1A0h+var_1E8], 0
0x18000b325  and     r13d, 4002h
0x18000b32c  cmp     r13d, 4000h
0x18000b333  jz      loc_18000B5FA
0x18000b339  mov     edi, eax
0x18000b33b  mov     rax, [rsp+2A0h+var_228]
0x18000b340  mov     r8d, r15d
0x18000b343  mov     r9d, dword ptr [rsp+2A0h+Size+4]
0x18000b348  mov     rcx, r12
0x18000b34b  mov     rdx, [rsp+2A0h+var_230]
0x18000b350  mov     [rsp+2A0h+var_258], rax
0x18000b355  mov     rax, [rbp+1A0h+var_1F8]
0x18000b359  mov     [rsp+2A0h+var_260], rax
0x18000b35e  mov     rax, [rbp+1A0h+var_1F0]
0x18000b362  mov     [rsp+2A0h+var_268], rax
0x18000b367  lea     rax, [rbp+1A0h+var_1E0]
0x18000b36b  mov     [rsp+2A0h+var_270], rax
0x18000b370  lea     rax, [rbp+1A0h+var_1D8]
0x18000b374  mov     [rsp+2A0h+var_278], rax
0x18000b379  lea     rax, [rbp+1A0h+var_218]
0x18000b37d  mov     [rsp+2A0h+var_280], rax
0x18000b382  mov     rax, [rbx+18h]
0x18000b386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b38b  mov     r14d, eax
0x18000b38e  cmp     r13d, 4000h
0x18000b395  jz      loc_18000B94E
0x18000b39b  test    r14d, r14d
0x18000b39e  jnz     loc_18000B6F5
0x18000b3a4  mov     rcx, [rbx+10h]; hFuncAddr
0x18000b3a8  test    rcx, rcx
0x18000b3ab  jz      short loc_18000B3BD
0x18000b3ad  xor     edx, edx; dwFlags
0x18000b3af  call    cs:__imp_CryptFreeOIDFunctionAddress
0x18000b3b5  mov     qword ptr [rbx+10h], 0
0x18000b3bd  mov     rcx, [rbx+20h]; hFuncAddr
0x18000b3c1  test    rcx, rcx
0x18000b3c4  jz      short loc_18000B3D6
0x18000b3c6  xor     edx, edx; dwFlags
0x18000b3c8  call    cs:__imp_CryptFreeOIDFunctionAddress
0x18000b3ce  mov     qword ptr [rbx+20h], 0
0x18000b3d6  test    r14d, r14d
0x18000b3d9  jnz     loc_18000BA31
0x18000b3df  call    cs:__imp_GetLastError
0x18000b3e5  mov     rcx, [rbx]
0x18000b3e8  mov     edi, eax
0x18000b3ea  mov     rax, [rcx+8]
0x18000b3ee  mov     rcx, rbx
0x18000b3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3f6  mov     rdx, [rbp+1A0h+var_1D0]
0x18000b3fa  lea     rcx, aCryptnetDllSUr; "CRYPTNET.DLL --> %s URL to retrieve: %S"...
0x18000b401  mov     r9d, edi
0x18000b404  mov     dword ptr [rsp+2A0h+var_280], edi
0x18000b408  mov     r8, r12
0x18000b40b  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x18000b410  mov     ecx, edi; dwErrCode
0x18000b412  call    cs:__imp_SetLastError
0x18000b418  mov     ebx, dword ptr [rsp+2A0h+Size+4]
0x18000b41c  mov     r13, [rsp+2A0h+var_230]
0x18000b421  mov     rax, [rbp+1A0h+var_200]
0x18000b425  test    rax, rax
0x18000b428  jnz     short loc_18000B450
0x18000b42a  mov     eax, r14d
0x18000b42d  mov     rcx, [rbp+1A0h+var_50]
0x18000b434  xor     rcx, rsp; StackCookie
0x18000b437  call    __security_check_cookie
0x18000b43c  add     rsp, 268h
0x18000b443  pop     r15
0x18000b445  pop     r14
0x18000b447  pop     r13
0x18000b449  pop     r12
0x18000b44b  pop     rdi
0x18000b44c  pop     rsi
0x18000b44d  pop     rbx
0x18000b44e  pop     rbp
0x18000b44f  retn
0x18000b450  mov     [rbp+1A0h+var_1B0], rax
0x18000b454  lea     rdx, [rbp+1A0h+var_1B0]
0x18000b458  xor     eax, eax
0x18000b45a  mov     [rbp+1A0h+var_18C], ebx
0x18000b45d  mov     rbx, [rsp+2A0h+var_228]
0x18000b462  xor     r8d, r8d
0x18000b465  mov     [rbp+1A0h+var_1A4], eax
0x18000b468  mov     ecx, 8
0x18000b46d  mov     rax, [rbp+1A0h+var_220]
0x18000b471  mov     [rbp+1A0h+var_1A8], r14d
0x18000b475  mov     [rbp+1A0h+var_1A0], r12
0x18000b479  mov     [rbp+1A0h+var_198], r13
0x18000b47d  mov     rax, [rax]
0x18000b480  mov     [rbp+1A0h+var_188], rax
0x18000b484  mov     [rbp+1A0h+var_190], r15d
0x18000b488  mov     [rbp+1A0h+var_180], rbx
0x18000b48c  call    cs:__imp_I_CertDiagControl
0x18000b492  test    rbx, rbx
0x18000b495  jz      short loc_18000B42A
0x18000b497  test    rsi, rsi
0x18000b49a  jz      loc_18000B5BF
0x18000b4a0  cmp     dword ptr [rsi], 8
0x18000b4a3  jbe     short loc_18000B4B8
0x18000b4a5  mov     rcx, [rsi+8]
0x18000b4a9  test    rcx, rcx
0x18000b4ac  jz      short loc_18000B4B8
0x18000b4ae  mov     rax, [rbp+1A0h+var_F0]
0x18000b4b5  mov     [rcx], rax
0x18000b4b8  cmp     dword ptr [rsi], 18h
0x18000b4bb  jbe     short loc_18000B4F8
0x18000b4bd  mov     rdi, [rsi+18h]
0x18000b4c1  test    rdi, rdi
0x18000b4c4  jz      short loc_18000B4F8
0x18000b4c6  mov     ebx, [rbp+1A0h+var_E8]
0x18000b4cc  mov     r15d, [rdi]
0x18000b4cf  cmp     ebx, r15d
0x18000b4d2  cmovnb  ebx, r15d
0x18000b4d6  cmp     ebx, 4
0x18000b4d9  jbe     short loc_18000B4F8
0x18000b4db  lea     r8, [rbx-4]; Size
0x18000b4df  lea     rcx, [rdi+4]; void *
0x18000b4e3  lea     rdx, [rbp+1A0h+Src]; Src
0x18000b4ea  call    memcpy_0
0x18000b4ef  cmp     r15d, ebx
0x18000b4f2  ja      loc_18000BA45
0x18000b4f8  cmp     dword ptr [rsi], 20h ; ' '
0x18000b4fb  jbe     short loc_18000B538
0x18000b4fd  mov     rbx, [rsi+20h]
0x18000b501  test    rbx, rbx
0x18000b504  jz      short loc_18000B538
0x18000b506  mov     edi, [rbp+1A0h+var_C0]
0x18000b50c  mov     r15d, [rbx]
0x18000b50f  cmp     edi, r15d
0x18000b512  cmovnb  edi, r15d
0x18000b516  cmp     edi, 4
0x18000b519  jbe     short loc_18000B538
0x18000b51b  lea     r8, [rdi-4]; Size
0x18000b51f  lea     rcx, [rbx+4]; void *
0x18000b523  lea     rdx, [rbp+1A0h+var_BC]; Src
0x18000b52a  call    memcpy_0
0x18000b52f  cmp     r15d, edi
0x18000b532  ja      loc_18000BA5B
0x18000b538  cmp     dword ptr [rsi], 28h ; '('
0x18000b53b  jbe     short loc_18000B55B
0x18000b53d  mov     rcx, [rsi+28h]
0x18000b541  test    rcx, rcx
0x18000b544  jz      short loc_18000B55B
0x18000b546  mov     rax, [rbp+1A0h+var_B0]
0x18000b54d  mov     [rcx], rax
0x18000b550  mov     [rbp+1A0h+var_B0], 0
0x18000b55b  cmp     dword ptr [rsi], 48h ; 'H'
0x18000b55e  jbe     short loc_18000B57E
0x18000b560  mov     rcx, [rsi+48h]
0x18000b564  test    rcx, rcx
0x18000b567  jz      short loc_18000B57E
  ... truncated ...
```
