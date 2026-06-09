# InetSendReceiveUrlRequest

- ea: `0x180003ef0`
- end: `0x180004b2d`
- name: `InetSendReceiveUrlRequest`
- size: `3133`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, int, __int64, _DWORD *, _QWORD *, _QWORD *, struct _CRYPT_RETRIEVE_AUX_INFO *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006420`

## callees

- `0x180001154`
- `0x1800013fc`
- `0x180001808`
- `0x180002c40`
- `0x180002d24`
- `0x180003104`
- `0x1800031e8`
- `0x18000335c`
- `0x1800036dc`
- `0x180003b40`
- `0x180003ef0`
- `0x180004b40`
- `0x180005940`
- `0x180006290`
- `0x180007c00`
- `0x18000a990`
- `0x18000bb78`
- `0x180018c28`
- `0x180019220`
- `0x180026552`
- `0x18002656a`
- `0x1800265b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004213`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000427f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000460e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004622`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000473e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004876`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004213`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000427f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000460e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004622`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000473e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004644`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004597`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004a2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004597`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004a2b`
- `CRYPT32!I_CryptGetTls` at `0x18000440d`
- `CRYPT32!I_CryptGetTls` at `0x18000440d`
- `CRYPT32!I_CertDiagControl` at `0x180004a82`
- `CRYPT32!I_CertDiagControl` at `0x180004a82`
- `CRYPT32!CryptMemRealloc` at `0x1800047d4`
- `CRYPT32!CryptMemRealloc` at `0x1800047d4`
- `CRYPT32!CryptQueryObject` at `0x180004af0`
- `CRYPT32!CryptQueryObject` at `0x180004af0`
- `CRYPT32!CryptMemAlloc` at `0x1800043f2`
- `CRYPT32!CryptMemAlloc` at `0x1800043f2`
- `CRYPT32!CryptMemFree` at `0x18000474c`
- `CRYPT32!CryptMemFree` at `0x180004aa7`
- `CRYPT32!CryptMemFree` at `0x180004b22`
- `CRYPT32!CryptMemFree` at `0x18000474c`
- `CRYPT32!CryptMemFree` at `0x180004aa7`
- `CRYPT32!CryptMemFree` at `0x180004b22`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800049d1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800049d1`
- `CRYPTBASE!SystemFunction036` at `0x1800042c1`
- `CRYPTBASE!SystemFunction036` at `0x1800042c1`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180004720`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180004998`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180004720`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180004998`
- `WINHTTP!WinHttpOpenRequest` at `0x18000416c`
- `WINHTTP!WinHttpOpenRequest` at `0x18000416c`
- `WINHTTP!WinHttpConnect` at `0x180004114`
- `WINHTTP!WinHttpConnect` at `0x180004114`
- `WINHTTP!WinHttpCrackUrl` at `0x180004028`
- `WINHTTP!WinHttpCrackUrl` at `0x180004028`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180004433`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180004433`
- `WINHTTP!WinHttpReadData` at `0x18000447e`
- `WINHTTP!WinHttpReadData` at `0x18000447e`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800043cf`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800043cf`
- `WINHTTP!WinHttpCloseHandle` at `0x18000423a`
- `WINHTTP!WinHttpCloseHandle` at `0x180004244`
- `WINHTTP!WinHttpCloseHandle` at `0x18000423a`
- `WINHTTP!WinHttpCloseHandle` at `0x180004244`
- `WINHTTP!WinHttpSetOption` at `0x1800046fe`
- `WINHTTP!WinHttpSetOption` at `0x1800048ee`
- `WINHTTP!WinHttpSetOption` at `0x180004916`
- `WINHTTP!WinHttpSetOption` at `0x180004955`
- `WINHTTP!WinHttpSetOption` at `0x180004976`
- `WINHTTP!WinHttpSetOption` at `0x1800046fe`
- `WINHTTP!WinHttpSetOption` at `0x1800048ee`
- `WINHTTP!WinHttpSetOption` at `0x180004916`
- `WINHTTP!WinHttpSetOption` at `0x180004955`
- `WINHTTP!WinHttpSetOption` at `0x180004976`

## string_xrefs

- `0x180004776`: `Call_WinHttpReadData`
- `0x1800048c9`: `Call_WinHttpOpenRequest`
- `0x180004a8c`: `CRYPTNET.DLL --> Exceeded MaxUrlRetrievalByteCount for: %S\n`
- `0x180004b0e`: `CRYPTNET.DLL --> Invalid AIA content, no caching: %S\n`

## pseudocode

```c
__int64 __fastcall InetSendReceiveUrlRequest(
        void *a1,
        unsigned __int16 *a2,
        int a3,
        __int64 a4,
        _DWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        struct _CRYPT_RETRIEVE_AUX_INFO *a8)
{
  struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *v10; // r12
  void *v11; // r13
  char *v12; // r15
  void *v13; // rsi
  const WCHAR *v14; // rcx
  void *v15; // r14
  __int64 v16; // rax
  void *v17; // rcx
  void *v18; // rax
  unsigned int v19; // r14d
  const WCHAR *v20; // rdx
  void *v21; // rax
  const unsigned __int16 *v22; // r8
  int v23; // r13d
  unsigned int v24; // esi
  const unsigned __int16 *v25; // r9
  int v26; // esi
  struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *ResponseInfo; // rax
  __int64 v28; // rdx
  PCRYPTNET_URL_CACHE_RESPONSE_INFO *ppResponseInfo; // r12
  DWORD LastError; // ebx
  __int64 v32; // rax
  int v33; // edx
  ULONG v34; // esi
  unsigned int v35; // esi
  __int64 Tls; // rax
  DWORD v37; // r8d
  FILETIME *v38; // rax
  int v39; // r9d
  unsigned __int8 *v40; // r8
  int v41; // edx
  _DWORD *v42; // rsi
  struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *v43; // rdi
  struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *v44; // rsi
  int updated; // ecx
  int v46; // r13d
  _DWORD *v47; // r8
  unsigned int cbSize; // eax
  struct _FILETIME *pLastSyncTime; // rcx
  DWORD v50; // ecx
  FILETIME *p_pv; // rdx
  const wchar_t *v52; // rcx
  void *v53; // rax
  PCRYPTNET_URL_CACHE_RESPONSE_INFO v54; // rcx
  DWORD dwMaxAge; // eax
  struct _FILETIME *v56; // rcx
  LPCWSTR pwszReferrer; // [rsp+20h] [rbp-E0h]
  unsigned int dwFlags; // [rsp+30h] [rbp-D0h]
  struct _CRYPT_CREDENTIALS *pdwFormatType; // [rsp+38h] [rbp-C8h]
  struct _CRYPTNET_URL_CACHE_RESPONSE_INFO *v60; // [rsp+60h] [rbp-A0h]
  void *RandomBuffer; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v62; // [rsp+70h] [rbp-90h]
  HLOCAL v63; // [rsp+78h] [rbp-88h]
  DWORD dwIndex; // [rsp+80h] [rbp-80h] BYREF
  HINTERNET hInternet; // [rsp+88h] [rbp-78h] BYREF
  HINTERNET hSession; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  __int64 Buffer; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v69; // [rsp+A8h] [rbp-58h]
  unsigned int dwMaxUrlRetrievalByteCount; // [rsp+B0h] [rbp-50h]
  DWORD dwErrCode; // [rsp+B4h] [rbp-4Ch] BYREF
  FILETIME FileTime2; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD *v73; // [rsp+C0h] [rbp-40h]
  HLOCAL hMem; // [rsp+C8h] [rbp-38h] BYREF
  HLOCAL v75; // [rsp+D0h] [rbp-30h] BYREF
  HINTERNET *p_hInternet; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v77; // [rsp+E0h] [rbp-20h]
  _QWORD *v78; // [rsp+E8h] [rbp-18h]
  HINTERNET v79; // [rsp+F0h] [rbp-10h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v81; // [rsp+170h] [rbp+70h] BYREF
  FILETIME *lpFileTime1; // [rsp+178h] [rbp+78h]
  __int128 v83; // [rsp+180h] [rbp+80h]
  __int128 v84; // [rsp+190h] [rbp+90h]
  __int64 v85; // [rsp+1A8h] [rbp+A8h]
  LPCWSTR ppwszAcceptTypes[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v87[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v88; // [rsp+1F0h] [rbp+F0h]
  int v89; // [rsp+200h] [rbp+100h]

  v73 = a5;
  v10 = 0;
  v77 = a6;
  v69 = a2;
  hSession = a1;
  v78 = a7;
  v79 = 0;
  hInternet = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  ppwszAcceptTypes[1] = 0;
  hMem = 0;
  ppwszAcceptTypes[0] = L"*/*";
  v11 = 0;
  v63 = 0;
  v89 = 0;
  v12 = 0;
  p_hInternet = 0;
  v13 = 0;
  *(_OWORD *)v87 = 0;
  pv = 0;
  v88 = 0;
  v75 = 0;
  dwIndex = 0;
  LODWORD(Buffer) = 0;
  FileTime2 = 0;
  v60 = 0;
  dwErrCode = 0;
  if ( !(unsigned int)I_CryptNetGetConnectivity() )
  {
    SetLastError(0x8CAu);
    goto LABEL_37;
  }
  dwMaxUrlRetrievalByteCount = 0;
  if ( a8 && a8->cbSize > 0x10 )
    dwMaxUrlRetrievalByteCount = a8->dwMaxUrlRetrievalByteCount;
  v14 = a2;
  if ( (a3 & 0x100000) != 0 )
  {
    if ( !(unsigned int)InetParseSpecialPostUrl(
                          a2,
                          (unsigned __int16 **)&hMem,
                          (unsigned __int16 **)&pv,
                          (unsigned __int8 **)&v75,
                          &dwIndex) )
    {
      v13 = pv;
      goto LABEL_37;
    }
    a3 &= ~0x200000u;
    v14 = (const WCHAR *)hMem;
    v63 = pv;
  }
  pv = 0;
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  UrlComponents.dwExtraInfoLength = -1;
  if ( !WinHttpCrackUrl(v14, 0, 0, &UrlComponents) )
  {
    v52 = L"Call_WinHttpCrackUrl";
LABEL_119:
    CryptDiagAddActionWithWinHttpLastError(v52);
    goto LABEL_102;
  }
  v62 = 0;
  if ( UrlComponents.nScheme == INTERNET_SCHEME_GOPHER )
  {
    if ( (a3 & 0x80000) != 0 )
    {
      SetLastError(0x32u);
      goto LABEL_36;
    }
    LODWORD(v13) = 0x800000;
    a3 &= ~0x200000u;
    v62 = 0x800000;
  }
  if ( !UrlComponents.lpszHostName )
  {
    UrlComponents.dwHostNameLength = 0;
    UrlComponents.lpszHostName = (LPSTR)&pszUrl;
  }
  if ( !UrlComponents.lpszUrlPath )
  {
    UrlComponents.dwUrlPathLength = 0;
    UrlComponents.lpszUrlPath = (LPSTR)&pszUrl;
  }
  if ( !UrlComponents.lpszExtraInfo )
  {
    UrlComponents.dwExtraInfoLength = 0;
    UrlComponents.lpszExtraInfo = (LPSTR)&pszUrl;
  }
  if ( (a3 & 0x4000000) != 0 )
  {
    RandomBuffer = 0;
    if ( SystemFunction036(&RandomBuffer, 8u) )
    {
      LODWORD(pwszReferrer) = HIDWORD(RandomBuffer);
      if ( (int)StringCchPrintfW(v87, 0x12u, L"?%08x%08x", (unsigned int)RandomBuffer, pwszReferrer) >= 0 )
      {
        v32 = -1;
        do
          ++v32;
        while ( v87[v32] );
        UrlComponents.dwExtraInfoLength = v32;
        UrlComponents.lpszExtraInfo = (LPSTR)v87;
      }
    }
  }
  v15 = (void *)PkiNonzeroAlloc(2LL * (UrlComponents.dwHostNameLength + 1));
  RandomBuffer = v15;
  v16 = PkiNonzeroAlloc(2LL * (UrlComponents.dwExtraInfoLength + 1 + UrlComponents.dwUrlPathLength));
  v12 = (char *)v16;
  if ( !v15 || !v16 )
  {
LABEL_100:
    v50 = -2147024882;
LABEL_101:
    SetLastError(v50);
    v11 = RandomBuffer;
LABEL_102:
    if ( pv )
      CryptMemFree(pv);
    v10 = v60;
    goto LABEL_36;
  }
  memcpy_0(v15, UrlComponents.lpszHostName, 2LL * UrlComponents.dwHostNameLength);
  *((_WORD *)v15 + UrlComponents.dwHostNameLength) = 0;
  memcpy_0(v12, UrlComponents.lpszUrlPath, 2LL * UrlComponents.dwUrlPathLength);
  memcpy_0(&v12[2 * UrlComponents.dwUrlPathLength], UrlComponents.lpszExtraInfo, 2LL * UrlComponents.dwExtraInfoLength);
  v17 = hSession;
  *(_WORD *)&v12[2 * (UrlComponents.dwExtraInfoLength + UrlComponents.dwUrlPathLength)] = 0;
  v18 = WinHttpConnect(v17, (LPCWSTR)v15, UrlComponents.nPort, 0);
  v79 = v18;
  if ( !v18 )
  {
    v52 = L"Call_WinHttpConnect";
    v11 = v15;
    goto LABEL_119;
  }
  v19 = 1;
  if ( (a3 & 0x280000) != 0 )
  {
    if ( a8 && a8->cbSize > 0x40 )
      a8->fProxyCacheRetrieval = 1;
  }
  else
  {
    LODWORD(v13) = (unsigned int)v13 | 0x100;
    v62 = (unsigned int)v13;
  }
  if ( (a3 & 0x100000) != 0 )
    v20 = L"POST";
  else
    v20 = 0;
  v21 = WinHttpOpenRequest(v18, v20, (LPCWSTR)v12, 0, 0, ppwszAcceptTypes, (DWORD)v13);
  hInternet = v21;
  if ( !v21 )
  {
    v52 = L"Call_WinHttpOpenRequest";
LABEL_118:
    v11 = RandomBuffer;
    goto LABEL_119;
  }
  v23 = a3 & 0x80000;
  if ( (a3 & 0x80000) != 0 )
  {
    p_hInternet = &hInternet;
    if ( !WinHttpSetOption(v21, 0x2Du, &p_hInternet, 8u)
      || WinHttpSetStatusCallback(hInternet, AiaUrlRedirectCallBack, 0x4000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      goto LABEL_34;
    }
    v21 = hInternet;
  }
  if ( (a3 & 0x20000) != 0 )
  {
    LODWORD(hSession) = 2;
    if ( !WinHttpSetOption(v21, 0x4Du, &hSession, 4u) )
      goto LABEL_34;
    LODWORD(hSession) = 4;
    if ( !WinHttpSetOption(hInternet, 0x3Fu, &hSession, 4u) )
      goto LABEL_34;
    v21 = hInternet;
  }
  v24 = (unsigned int)v13 & 0x800000;
  if ( v24 && (a3 & 0x800000) != 0 )
  {
    LODWORD(hSession) = 1;
    pv = &dwErrCode;
    if ( !WinHttpSetOption(v21, 0x4Fu, &hSession, 4u)
      || !WinHttpSetOption(hInternet, 0x2Du, &pv, 8u)
      || WinHttpSetStatusCallback(hInternet, RevErrorCallBack, 0x10000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      goto LABEL_34;
    }
    v21 = hInternet;
  }
  v25 = (const unsigned __int16 *)v63;
  if ( !v63 && !v24 )
  {
    if ( (v62 & 0x100) != 0 || (v33 = 1, (a3 & 0x4000000) != 0) )
      v33 = 0;
    v63 = InetCreateRequestHeaders(v69, v33, a8, (int *)&Buffer, &FileTime2);
    v21 = hInternet;
    v25 = (const unsigned __int16 *)v63;
  }
  v26 = InetSendAuthenticatedRequestAndReceiveResponse(
          v75,
          v21,
          v22,
          v25,
          (const unsigned __int8 *)v75,
          dwIndex,
          dwFlags,
          pdwFormatType,
          a8);
  if ( v26 < 0 )
    goto LABEL_34;
  ResponseInfo = InetCreateResponseInfo(hInternet);
  v60 = ResponseInfo;
  v10 = ResponseInfo;
  if ( !ResponseInfo )
  {
LABEL_35:
    v11 = RandomBuffer;
LABEL_36:
    v13 = v63;
LABEL_37:
    LastError = dwErrCode;
    if ( !dwErrCode )
      LastError = GetLastError();
    v19 = 0;
    goto LABEL_40;
  }
  ppResponseInfo = 0;
  if ( a8 && a8->cbSize > 0x28 && a8->ppResponseInfo )
    ppResponseInfo = a8->ppResponseInfo;
  if ( !v26 )
  {
    if ( (_DWORD)Buffer )
    {
      v44 = ResponseInfo;
      if ( (a3 & 8) != 0 )
      {
        updated = 0;
        v46 = 0;
      }
      else
      {
        v46 = 1;
        updated = SchemeUpdateCacheResponseInfo(v69, v28, &FileTime2, ResponseInfo, a8);
      }
      if ( (a3 & 0x400000) != 0 )
      {
        v47 = v73;
        *v73 = 0;
        *((_QWORD *)v47 + 1) = 0;
        if ( a8 )
        {
          cbSize = a8->cbSize;
          if ( a8->cbSize > 0x44 )
            a8->dwHttpStatusCode = 304;
          if ( !updated && cbSize > 8 )
          {
            pLastSyncTime = a8->pLastSyncTime;
            if ( pLastSyncTime )
              GetSystemTimeAsFileTime(pLastSyncTime);
          }
          if ( ppResponseInfo )
          {
            v11 = RandomBuffer;
            *ppResponseInfo = v44;
            v10 = 0;
            v13 = v63;
            LastError = 0;
            goto LABEL_40;
          }
        }
      }
      else
      {
        memset_0((char *)&v81 + 4, 0, 0x54u);
        pv = 0;
        if ( a8 )
        {
          LODWORD(v81) = 88;
          I_UrlCacheCopyCbSizeStruct(a8, &v81);
        }
        else
        {
          memset_0(&v81, 0, 0x58u);
          LODWORD(v81) = 88;
        }
        v85 = 0;
        if ( !v46 )
        {
          p_pv = (FILETIME *)&pv;
          if ( lpFileTime1 )
            p_pv = lpFileTime1;
          lpFileTime1 = p_pv;
        }
        if ( !(unsigned int)SchemeRetrieveCachedCryptBlobArray(
                              (_DWORD)v69,
                              (_DWORD)p_pv,
                              (_DWORD)v73,
                              (_DWORD)v77,
                              (__int64)v78,
                              (__int64)&v81) )
          goto LABEL_34;
        if ( !v46 && !CompareFileTime(lpFileTime1, &FileTime2) )
        {
          if ( ppResponseInfo )
          {
            v54 = *ppResponseInfo;
            v10 = v60;
            if ( v54 )
            {
              dwMaxAge = v60->dwMaxAge;
              if ( dwMaxAge )
                v54->dwMaxAge = dwMaxAge;
              if ( v60->LastModifiedTime.dwLowDateTime || v60->LastModifiedTime.dwHighDateTime )
                v54->LastModifiedTime = v60->LastModifiedTime;
            }
          }
          else
          {
            v10 = v60;
          }
          if ( a8 )
          {
            if ( a8->cbSize > 8 )
            {
              v56 = a8->pLastSyncTime;
              if ( v56 )
                GetSystemTimeAsFileTime(v56);
            }
          }
          goto LABEL_97;
        }
      }
LABEL_110:
      v10 = v60;
      goto LABEL_97;
    }
    SetLastError(0xDu);
LABEL_34:
    v10 = v60;
    goto LABEL_35;
  }
  v34 = 4096;
  v62 = 4096;
  if ( !v23 )
  {
    LODWORD(Buffer) = 0;
    LODWORD(hSession) = 4;
    dwIndex = 0;
    if ( WinHttpQueryHeaders(hInternet, 0x20000005u, 0, &Buffer, (LPDWORD)&hSession, &dwIndex) )
    {
      if ( (unsigned int)Buffer > 0x7270E00 )
      {
        v34 = 120000000;
      }
      else if ( (unsigned int)Buffer > 0x1000 )
      {
        v34 = Buffer;
      }
      v62 = v34;
    }
  }
  pv = CryptMemAlloc(v34);
  if ( !pv )
    goto LABEL_100;
  v35 = 0;
  Tls = I_CryptGetTls((unsigned int)hCryptNetCancelTls);
  for ( Buffer = Tls; ; Tls = Buffer )
  {
    LODWORD(hSession) = 0;
    dwIndex = 0;
    if ( Tls && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))Tls)(0, *(_QWORD *)(Tls + 8)) )
    {
      v50 = 1223;
      goto LABEL_101;
    }
    LODWORD(hSession) = 0;
    if ( !WinHttpQueryDataAvailable(hInternet, (LPDWORD)&hSession) )
      break;
    v37 = (unsigned int)hSession;
    if ( !(_DWORD)hSession )
      break;
    if ( dwMaxUrlRetrievalByteCount && (unsigned int)hSession + v35 > dwMaxUrlRetrievalByteCount )
    {
      lpFileTime1 = (FILETIME *)0x30000000DLL;
      v81 = L"CheckMaxUrlRetrievalByteCount";
      v83 = 0;
      v84 = 0;
      I_CertDiagControl(11, &v81, 0);
      I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> Exceeded MaxUrlRetrievalByteCount for: %S\n", v69);
      v50 = 13;
      goto LABEL_101;
    }
    if ( v62 < (unsigned int)hSession + v35 )
    {
      v53 = CryptMemRealloc(pv, (unsigned int)hSession + v62 + 4096);
      if ( !v53 )
        goto LABEL_100;
      v37 = (unsigned int)hSession;
      pv = v53;
      v62 += (_DWORD)hSession + 4096;
    }
    dwIndex = 0;
    if ( !WinHttpReadData(hInternet, (char *)pv + v35, v37, &dwIndex) )
    {
      v52 = L"Call_WinHttpReadData";
      goto LABEL_118;
    }
    v35 += dwIndex;
  }
  if ( !v35 )
  {
    CryptMemFree(v60);
    v60 = 0;
  }
  DWORD1(v83) = 1;
  LODWORD(v81) = 0;
  v38 = (FILETIME *)operator new(0x10u);
  lpFileTime1 = v38;
  if ( !v38 )
  {
    SetLastError(0x8007000E);
    goto LABEL_99;
  }
  v40 = (unsigned __int8 *)pv;
  LODWORD(v83) = 1;
  *(_OWORD *)&v38->dwLowDateTime = 0;
  if ( !(unsigned int)CCryptBlobArray::AddBlob((CCryptBlobArray *)&v81, v35, v40, v39) )
  {
LABEL_99:
    operator delete(lpFileTime1);
    goto LABEL_100;
  }
  v42 = v73;
  *v73 = (_DWORD)v81;
  *((_QWORD *)v42 + 1) = lpFileTime1;
  *v77 = LdapFreeEncodedObject;
  *v78 = 0;
  if ( (a3 & 8) != 0 )
    goto LABEL_77;
  if ( !v23 || CryptQueryObject(2u, *((const void **)v42 + 1), 0x2102u, 0xEu, 0, 0, 0, 0, 0, 0, 0) )
  {
    v43 = v60;
    if ( !(unsigned int)SchemeCacheCryptBlobArray((_DWORD)v69, v41, (_DWORD)v42, (_DWORD)a8, (__int64)v60) )
      goto LABEL_78;
  }
  else
  {
    CryptDiagAddActionWithLastError(L"CanDecodeRetrievedIssuerCertificate");
    I_CryptNetDebugErrorPrintfA("CRYPTNET.DLL --> Invalid AIA content, no caching: %S\n", v69);
LABEL_77:
    v43 = v60;
LABEL_78:
    SchemeRetrieveUncachedAuxInfo(a8);
  }
  if ( !ppResponseInfo )
    goto LABEL_110;
  *ppResponseInfo = v43;
  v10 = 0;
LABEL_97:
  v13 = v63;
  LastError = 0;
  v11 = RandomBuffer;
LABEL_40:
  WinHttpCloseHandle(hInternet);
  WinHttpCloseHandle(v79);
  operator delete(v11);
  operator delete(v12);
  operator delete(hMem);
  operator delete(v13);
  operator delete(v75);
  if ( v10 )
    CryptMemFree(v10);
  SetLastError(LastError);
  return v19;
}

```

## disassembly

```asm
0x180003ef0  mov     [rsp-8+arg_10], rbx
0x180003ef5  push    rbp
0x180003ef6  push    rsi
0x180003ef7  push    rdi
0x180003ef8  push    r12
0x180003efa  push    r13
0x180003efc  push    r14
0x180003efe  push    r15
0x180003f00  lea     rbp, [rsp-110h]
0x180003f08  sub     rsp, 210h
0x180003f0f  mov     rax, cs:__security_cookie
0x180003f16  xor     rax, rsp
0x180003f19  mov     [rbp+140h+var_38], rax
0x180003f20  mov     rax, [rbp+140h+arg_20]
0x180003f27  mov     edi, r8d
0x180003f2a  mov     rbx, [rbp+140h+arg_38]
0x180003f31  mov     r14, rdx
0x180003f34  mov     [rbp+140h+var_180], rax
0x180003f38  xor     r12d, r12d
0x180003f3b  mov     rax, [rbp+140h+arg_28]
0x180003f42  mov     r8d, 68h ; 'h'; Size
0x180003f48  mov     [rbp+140h+var_160], rax
0x180003f4c  mov     rax, [rbp+140h+arg_30]
0x180003f53  mov     [rbp+140h+var_198], rdx
0x180003f57  xor     edx, edx; Val
0x180003f59  mov     [rbp+140h+hSession], rcx
0x180003f5d  lea     rcx, [rbp+140h+UrlComponents]; void *
0x180003f61  mov     [rbp+140h+var_158], rax
0x180003f65  mov     [rbp+140h+var_150], r12
0x180003f69  mov     [rbp+140h+hInternet], r12
0x180003f6d  call    memset_0
0x180003f72  xorps   xmm0, xmm0
0x180003f75  mov     [rbp+140h+var_68], r12
0x180003f7c  lea     rax, asc_1800296A8; "*/*"
0x180003f83  mov     [rbp+140h+hMem], r12
0x180003f87  mov     [rbp+140h+var_70], rax
0x180003f8e  mov     r13d, r12d
0x180003f91  xor     eax, eax
0x180003f93  mov     [rsp+240h+var_1C8], r12
0x180003f98  mov     [rbp+140h+var_40], eax
0x180003f9e  mov     r15d, r12d
0x180003fa1  mov     [rbp+140h+var_168], rax
0x180003fa5  mov     esi, r12d
0x180003fa8  movups  xmmword ptr [rbp+140h+var_60], xmm0
0x180003faf  mov     [rbp+140h+pv], r12
0x180003fb3  movups  [rbp+140h+var_50], xmm0
0x180003fba  mov     [rbp+140h+var_170], r12
0x180003fbe  mov     [rbp+140h+dwIndex], r12d
0x180003fc2  mov     dword ptr [rbp+140h+Buffer], r12d
0x180003fc6  mov     qword ptr [rbp+140h+FileTime2.dwLowDateTime], r12
0x180003fca  mov     [rsp+240h+var_1E0], r12
0x180003fcf  call    I_CryptNetGetConnectivity
0x180003fd4  mov     [rbp+140h+dwErrCode], esi
0x180003fd7  test    eax, eax
0x180003fd9  jz      loc_180004739
0x180003fdf  mov     [rbp+140h+var_190], esi
0x180003fe2  test    rbx, rbx
0x180003fe5  jz      short loc_180003FF2
0x180003fe7  cmp     dword ptr [rbx], 10h
0x180003fea  jbe     short loc_180003FF2
0x180003fec  mov     eax, [rbx+10h]
0x180003fef  mov     [rbp+140h+var_190], eax
0x180003ff2  mov     rcx, r14; unsigned __int16 *
0x180003ff5  bt      edi, 14h
0x180003ff9  jb      loc_180004822
0x180003fff  lea     r9, [rbp+140h+UrlComponents]; lpUrlComponents
0x180004003  mov     [rbp+140h+pv], rsi
0x180004007  xor     r8d, r8d; dwFlags
0x18000400a  mov     [rbp+140h+UrlComponents.dwStructSize], 68h ; 'h'
0x180004011  xor     edx, edx; dwUrlLength
0x180004013  mov     [rbp+140h+UrlComponents.dwHostNameLength], 0FFFFFFFFh
0x18000401a  mov     [rbp+140h+UrlComponents.dwUrlPathLength], 0FFFFFFFFh
0x180004021  mov     [rbp+140h+UrlComponents.dwExtraInfoLength], 0FFFFFFFFh
0x180004028  call    cs:__imp_WinHttpCrackUrl
0x18000402e  test    eax, eax
0x180004030  jz      loc_18000485F
0x180004036  cmp     [rbp+140h+UrlComponents.nScheme], 2
0x18000403a  mov     [rsp+240h+var_1D0], esi
0x18000403e  jz      loc_18000486B
0x180004044  lea     rax, pszUrl
0x18000404b  cmp     [rbp+140h+UrlComponents.lpszHostName], r12
0x18000404f  jz      loc_180004893
0x180004055  cmp     [rbp+140h+UrlComponents.lpszUrlPath], r12
0x180004059  jz      loc_1800048A0
0x18000405f  cmp     [rbp+140h+UrlComponents.lpszExtraInfo], r12
0x180004063  jz      loc_1800048AD
0x180004069  mov     r12d, edi
0x18000406c  and     r12d, 4000000h
0x180004073  jnz     loc_1800042B2
0x180004079  mov     ecx, [rbp+140h+UrlComponents.dwHostNameLength]
0x18000407c  inc     ecx
0x18000407e  add     rcx, rcx; uBytes
0x180004081  call    PkiNonzeroAlloc
0x180004086  mov     ecx, [rbp+140h+UrlComponents.dwUrlPathLength]
0x180004089  mov     r14, rax
0x18000408c  mov     [rsp+240h+RandomBuffer], rax
0x180004091  mov     eax, [rbp+140h+UrlComponents.dwExtraInfoLength]
0x180004094  inc     eax
0x180004096  add     ecx, eax
0x180004098  add     rcx, rcx; uBytes
0x18000409b  call    PkiNonzeroAlloc
0x1800040a0  mov     r15, rax
0x1800040a3  test    r14, r14
0x1800040a6  jz      loc_18000461D
0x1800040ac  test    rax, rax
0x1800040af  jz      loc_18000461D
0x1800040b5  mov     r8d, [rbp+140h+UrlComponents.dwHostNameLength]
0x1800040b9  mov     rcx, r14; void *
0x1800040bc  mov     rdx, [rbp+140h+UrlComponents.lpszHostName]; Src
0x1800040c0  add     r8, r8; Size
0x1800040c3  call    memcpy_0
0x1800040c8  mov     ecx, [rbp+140h+UrlComponents.dwHostNameLength]
0x1800040cb  mov     [r14+rcx*2], r13w
0x1800040d0  mov     rcx, r15; void *
0x1800040d3  mov     r8d, [rbp+140h+UrlComponents.dwUrlPathLength]
0x1800040d7  mov     rdx, [rbp+140h+UrlComponents.lpszUrlPath]; Src
0x1800040db  add     r8, r8; Size
0x1800040de  call    memcpy_0
0x1800040e3  mov     eax, [rbp+140h+UrlComponents.dwUrlPathLength]
0x1800040e6  mov     r8d, [rbp+140h+UrlComponents.dwExtraInfoLength]
0x1800040ea  mov     rdx, [rbp+140h+UrlComponents.lpszExtraInfo]; Src
0x1800040ee  add     r8, r8; Size
0x1800040f1  lea     rcx, [r15+rax*2]; void *
0x1800040f5  call    memcpy_0
0x1800040fa  mov     edx, [rbp+140h+UrlComponents.dwUrlPathLength]
0x1800040fd  xor     r9d, r9d; dwReserved
0x180004100  add     edx, [rbp+140h+UrlComponents.dwExtraInfoLength]
0x180004103  mov     rcx, [rbp+140h+hSession]; hSession
0x180004107  mov     [r15+rdx*2], r13w
0x18000410c  mov     rdx, r14; pswzServerName
0x18000410f  movzx   r8d, [rbp+140h+UrlComponents.nPort]; nServerPort
0x180004114  call    cs:__imp_WinHttpConnect
0x18000411a  mov     [rbp+140h+var_150], rax
0x18000411e  test    rax, rax
0x180004121  jz      loc_1800048BA
0x180004127  mov     r14d, 1
0x18000412d  test    edi, 280000h
0x180004133  jnz     loc_18000432D
0x180004139  bts     esi, 8
0x18000413d  mov     [rsp+240h+var_1D0], esi
0x180004141  bt      edi, 14h
0x180004145  jb      loc_1800046D8
0x18000414b  mov     rdx, r13; pwszVerb
0x18000414e  lea     rcx, [rbp+140h+var_70]
0x180004155  mov     [rsp+240h+dwFlags], esi; unsigned int
0x180004159  mov     [rsp+240h+ppwszAcceptTypes], rcx; ppwszAcceptTypes
0x18000415e  xor     r9d, r9d; pwszVersion
0x180004161  mov     rcx, rax; hConnect
0x180004164  mov     [rsp+240h+pwszReferrer], r13; pwszReferrer
0x180004169  mov     r8, r15; pwszObjectName
0x18000416c  call    cs:__imp_WinHttpOpenRequest
0x180004172  mov     [rbp+140h+hInternet], rax
0x180004176  test    rax, rax
0x180004179  jz      loc_1800048C9
0x18000417f  mov     r13d, edi
0x180004182  and     r13d, 80000h
0x180004189  jnz     loc_1800046E4
0x18000418f  bt      edi, 11h
0x180004193  jb      loc_1800048D5
0x180004199  and     esi, 800000h
0x18000419f  jnz     loc_18000492D
0x1800041a5  mov     r9, [rsp+240h+var_1C8]; unsigned __int16 *
0x1800041aa  test    r9, r9
0x1800041ad  jz      loc_180004348
0x1800041b3  mov     ecx, [rbp+140h+dwIndex]
0x1800041b6  mov     rdx, rax; void *
0x1800041b9  mov     [rsp+240h+phCertStore], rbx; struct _CRYPT_RETRIEVE_AUX_INFO *
0x1800041be  mov     dword ptr [rsp+240h+ppwszAcceptTypes], ecx; DWORD
0x1800041c2  mov     rcx, [rbp+140h+var_170]; void *
0x1800041c6  mov     [rsp+240h+pwszReferrer], rcx; unsigned __int8 *
0x1800041cb  call    ?InetSendAuthenticatedRequestAndReceiveResponse@@YAJPEAX0PEBG1PEBEKKPEAU_CRYPT_CREDENTIALS@@PEAU_CRYPT_RETRIEVE_AUX_INFO@@@Z; InetSendAuthenticatedRequestAndReceiveResponse(void *,void *,ushort const *,ushort const *,uchar const *,ulong,ulong,_CRYPT_CREDENTIALS *,_CRYPT_RETRIEVE_AUX_INFO *)
0x1800041d0  mov     esi, eax
0x1800041d2  test    eax, eax
0x1800041d4  js      short loc_180004219
0x1800041d6  mov     rcx, [rbp+140h+hInternet]; void *
0x1800041da  call    ?InetCreateResponseInfo@@YAPEAU_CRYPTNET_URL_CACHE_RESPONSE_INFO@@PEAX@Z; InetCreateResponseInfo(void *)
0x1800041df  mov     [rsp+240h+var_1E0], rax
0x1800041e4  mov     r12, rax
0x1800041e7  test    rax, rax
0x1800041ea  jz      short loc_18000421E
0x1800041ec  xor     r12d, r12d
0x1800041ef  test    rbx, rbx
0x1800041f2  jz      short loc_1800041FD
0x1800041f4  cmp     dword ptr [rbx], 28h ; '('
0x1800041f7  ja      loc_18000452A
0x1800041fd  test    esi, esi
0x1800041ff  jnz     loc_180004390
0x180004205  cmp     dword ptr [rbp+140h+Buffer], esi
0x180004208  jnz     loc_18000453F
0x18000420e  mov     ecx, 0Dh; dwErrCode
0x180004213  call    cs:__imp_SetLastError
0x180004219  mov     r12, [rsp+240h+var_1E0]
0x18000421e  mov     r13, [rsp+240h+RandomBuffer]
0x180004223  mov     rsi, [rsp+240h+var_1C8]
0x180004228  mov     ebx, [rbp+140h+dwErrCode]
0x18000422b  test    ebx, ebx
0x18000422d  jz      loc_180004644
0x180004233  xor     r14d, r14d
0x180004236  mov     rcx, [rbp+140h+hInternet]; hInternet
0x18000423a  call    cs:__imp_WinHttpCloseHandle
0x180004240  mov     rcx, [rbp+140h+var_150]; hInternet
0x180004244  call    cs:__imp_WinHttpCloseHandle
0x18000424a  mov     rcx, r13; hMem
0x18000424d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004252  mov     rcx, r15; hMem
0x180004255  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000425a  mov     rcx, [rbp+140h+hMem]; hMem
0x18000425e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004263  mov     rcx, rsi; hMem
0x180004266  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000426b  mov     rcx, [rbp+140h+var_170]; hMem
0x18000426f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004274  test    r12, r12
0x180004277  jnz     loc_180004749
0x18000427d  mov     ecx, ebx; dwErrCode
0x18000427f  call    cs:__imp_SetLastError
0x180004285  mov     eax, r14d
0x180004288  mov     rcx, [rbp+140h+var_38]
0x18000428f  xor     rcx, rsp; StackCookie
0x180004292  call    __security_check_cookie
0x180004297  mov     rbx, [rsp+240h+arg_10]
0x18000429f  add     rsp, 210h
0x1800042a6  pop     r15
0x1800042a8  pop     r14
0x1800042aa  pop     r13
0x1800042ac  pop     r12
0x1800042ae  pop     rdi
0x1800042af  pop     rsi
0x1800042b0  pop     rbp
0x1800042b1  retn
0x1800042b2  mov     edx, 8; RandomBufferLength
0x1800042b7  mov     [rsp+240h+RandomBuffer], r13
0x1800042bc  lea     rcx, [rsp+240h+RandomBuffer]; RandomBuffer
0x1800042c1  call    cs:__imp_SystemFunction036
0x1800042c7  test    al, al
0x1800042c9  jz      loc_180004079
0x1800042cf  mov     eax, dword ptr [rsp+240h+RandomBuffer+4]
0x1800042d3  lea     r8, a08x08x; "?%08x%08x"
0x1800042da  mov     r9d, dword ptr [rsp+240h+RandomBuffer]
0x1800042df  lea     rcx, [rbp+140h+var_60]; unsigned __int16 *
0x1800042e6  mov     edx, 12h; unsigned __int64
0x1800042eb  mov     dword ptr [rsp+240h+pwszReferrer], eax
0x1800042ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800042f4  test    eax, eax
0x1800042f6  js      loc_180004079
0x1800042fc  lea     rcx, [rbp+140h+var_60]
0x180004303  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000430a  nop     word ptr [rax+rax+00h]
0x180004310  inc     rax
0x180004313  cmp     [rcx+rax*2], r15w
0x180004318  jnz     short loc_180004310
0x18000431a  mov     [rbp+140h+UrlComponents.dwExtraInfoLength], eax
0x18000431d  lea     rax, [rbp+140h+var_60]
0x180004324  mov     [rbp+140h+UrlComponents.lpszExtraInfo], rax
0x180004328  jmp     loc_180004079
0x18000432d  test    rbx, rbx
0x180004330  jz      loc_180004141
0x180004336  cmp     dword ptr [rbx], 40h ; '@'
0x180004339  jbe     loc_180004141
0x18000433f  mov     [rbx+40h], r14d
0x180004343  jmp     loc_180004141
0x180004348  test    esi, esi
0x18000434a  jnz     loc_1800041B3
0x180004350  test    [rsp+240h+var_1D0], 100h
0x180004358  jnz     short loc_180004362
0x18000435a  mov     edx, r14d
0x18000435d  test    r12d, r12d
0x180004360  jz      short loc_180004364
0x180004362  xor     edx, edx; int
0x180004364  mov     rcx, [rbp+140h+var_198]; unsigned __int16 *
0x180004368  lea     rax, [rbp+140h+FileTime2]
0x18000436c  lea     r9, [rbp+140h+Buffer]; int *
0x180004370  mov     [rsp+240h+pwszReferrer], rax; struct _FILETIME *
0x180004375  mov     r8, rbx; struct _CRYPT_RETRIEVE_AUX_INFO *
0x180004378  call    ?InetCreateRequestHeaders@@YAPEAGPEBGHPEAU_CRYPT_RETRIEVE_AUX_INFO@@PEAHPEAU_FILETIME@@@Z; InetCreateRequestHeaders(ushort const *,int,_CRYPT_RETRIEVE_AUX_INFO *,int *,_FILETIME *)
0x18000437d  mov     [rsp+240h+var_1C8], rax
0x180004382  mov     rax, [rbp+140h+hInternet]
0x180004386  mov     r9, [rsp+240h+var_1C8]
0x18000438b  jmp     loc_1800041B3
0x180004390  mov     esi, 1000h
0x180004395  mov     [rsp+240h+var_1D0], esi
0x180004399  test    r13d, r13d
0x18000439c  jnz     short loc_1800043F0
0x18000439e  mov     rcx, [rbp+140h+hInternet]; hRequest
0x1800043a2  lea     rax, [rbp+140h+dwIndex]
0x1800043a6  mov     [rsp+240h+ppwszAcceptTypes], rax; lpdwIndex
0x1800043ab  lea     r9, [rbp+140h+Buffer]; lpBuffer
0x1800043af  lea     rax, [rbp+140h+hSession]
0x1800043b3  mov     dword ptr [rbp+140h+Buffer], r13d
0x1800043b7  xor     r8d, r8d; pwszName
0x1800043ba  mov     [rsp+240h+pwszReferrer], rax; lpdwBufferLength
0x1800043bf  mov     edx, 20000005h; dwInfoLevel
0x1800043c4  mov     dword ptr [rbp+140h+hSession], 4
0x1800043cb  mov     [rbp+140h+dwIndex], r13d
0x1800043cf  call    cs:__imp_WinHttpQueryHeaders
0x1800043d5  test    eax, eax
0x1800043d7  jz      short loc_1800043F0
0x1800043d9  mov     eax, dword ptr [rbp+140h+Buffer]
0x1800043dc  cmp     eax, 7270E00h
0x1800043e1  ja      loc_180004A36
  ... truncated ...
```
