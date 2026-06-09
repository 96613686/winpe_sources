# GetValidCertFromSCard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x180073538`
- end: `0x180074316`
- name: `?GetValidCertFromSCard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU4@@Z`
- size: `3550`
- prototype: `unsigned int __fastcall(int, unsigned int, struct _EAPTLS_CONN_PROPERTIES_V1 *, HWND, int, struct _EAPTLS_FILTER_PROP *, const struct _CERT_CONTEXT **, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18006f550`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180035680`
- `0x180036254`
- `0x18004acb8`
- `0x180066818`
- `0x180066c18`
- `0x180069408`
- `0x180069e80`
- `0x18006c948`
- `0x18006d510`
- `0x18007042c`
- `0x1800718ac`
- `0x180071f5c`
- `0x1800725a4`
- `0x180072fe4`
- `0x180073538`
- `0x180074744`
- `0x1800747d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007412b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007412b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073d9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800739f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180074106`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800739f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180074106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073752`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007375c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073fab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800740e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073752`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007375c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073fab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800740e6`
- `CRYPT32!CertCloseStore` at `0x18007372a`
- `CRYPT32!CertCloseStore` at `0x18007373a`
- `CRYPT32!CertCloseStore` at `0x180074158`
- `CRYPT32!CertCloseStore` at `0x18007372a`
- `CRYPT32!CertCloseStore` at `0x18007373a`
- `CRYPT32!CertCloseStore` at `0x180074158`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180073f2c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18007413c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180073f2c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18007413c`
- `CRYPT32!CertFreeCertificateContext` at `0x180073f69`
- `CRYPT32!CertFreeCertificateContext` at `0x180073f79`
- `CRYPT32!CertFreeCertificateContext` at `0x1800740ac`
- `CRYPT32!CertFreeCertificateContext` at `0x1800742dd`
- `CRYPT32!CertFreeCertificateContext` at `0x180073f69`
- `CRYPT32!CertFreeCertificateContext` at `0x180073f79`
- `CRYPT32!CertFreeCertificateContext` at `0x1800740ac`
- `CRYPT32!CertFreeCertificateContext` at `0x1800742dd`
- `CRYPT32!CertOpenStore` at `0x18007369c`
- `CRYPT32!CertOpenStore` at `0x1800737a1`
- `CRYPT32!CertOpenStore` at `0x18007369c`
- `CRYPT32!CertOpenStore` at `0x1800737a1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180073914`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180074044`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800740b5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180073914`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180074044`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800740b5`
- `CRYPT32!CertFindChainInStore` at `0x18007383d`
- `CRYPT32!CertFindChainInStore` at `0x18007383d`
- `CRYPT32!CertFreeCertificateChain` at `0x180073749`
- `CRYPT32!CertFreeCertificateChain` at `0x180073749`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x180073d6b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x180073d6b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180073cc4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180073cc4`
- `ncrypt!NCryptOpenStorageProvider` at `0x180073e15`
- `ncrypt!NCryptOpenStorageProvider` at `0x180073e15`
- `ncrypt!NCryptGetProperty` at `0x180073eeb`
- `ncrypt!NCryptGetProperty` at `0x180073eeb`
- `ncrypt!NCryptSetProperty` at `0x180073e84`
- `ncrypt!NCryptSetProperty` at `0x180073e84`
- `ncrypt!NCryptFreeObject` at `0x180073ebd`
- `ncrypt!NCryptFreeObject` at `0x180073ef7`
- `ncrypt!NCryptFreeObject` at `0x180073ebd`
- `ncrypt!NCryptFreeObject` at `0x180073ef7`
- `CRYPTSP!CryptReleaseContext` at `0x180073d79`
- `CRYPTSP!CryptReleaseContext` at `0x180073d79`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x18007426e`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x18007426e`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x18007395b`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x18007395b`
- `ext-ms-win-security-winscard-l1-1-0!SCardListCardsW` at `0x180073b55`
- `ext-ms-win-security-winscard-l1-1-0!SCardListCardsW` at `0x180073b55`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x18007397a`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x18007397a`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetStatusChangeW` at `0x180073a94`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetStatusChangeW` at `0x180073a94`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180073c0d`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180073c62`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180073c0d`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180073c62`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x1800736f5`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x18007370a`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180073be6`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180073d3f`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x1800736f5`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x18007370a`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180073be6`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180073d3f`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x18007371a`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x18007371a`

## string_xrefs

- `0x180073e79`: `SmartCardReader`

## pseudocode

```c
__int64 __fastcall GetValidCertFromSCard(
        __int64 a1,
        unsigned int a2,
        struct _EAPTLS_CONN_PROPERTIES_V1 *a3,
        HWND a4,
        int a5,
        struct _CERT_CONTEXT *a6,
        const struct _CERT_CONTEXT **a7)
{
  PCCERT_CHAIN_CONTEXT pPrevChainContext; // r15
  const CERT_CONTEXT *v8; // r12
  PCCERT_CONTEXT v9; // r13
  unsigned int v10; // esi
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v11; // r14
  int v12; // edi
  unsigned int v13; // eax
  void *v14; // rsi
  unsigned int LastError; // ebx
  void *v16; // r13
  DWORD v18; // eax
  const struct _CERT_CONTEXT *pCertContext; // rbx
  _WORD *v20; // rax
  DWORD v21; // edi
  __int64 v22; // rcx
  const WCHAR *v23; // rcx
  unsigned int v24; // edx
  unsigned __int64 v25; // rax
  __int64 v26; // rax
  struct _EAPTLS_CONTROL_BLOCK *v27; // rcx
  DWORD v28; // ebx
  unsigned int v29; // r14d
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v30; // r9
  __int64 v31; // rax
  __int64 v32; // r15
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v33; // rdx
  unsigned int v34; // eax
  struct _EAPTLS_CONTROL_BLOCK **v35; // rdx
  int v36; // r8d
  const WCHAR *v37; // rdi
  unsigned int CardTypeProviderNameW; // eax
  unsigned int v39; // eax
  unsigned int FormattedCardName; // eax
  struct _EAPTLS_CONTROL_BLOCK *v41; // rcx
  __int64 v42; // rdx
  BOOL v43; // ebx
  DWORD v44; // eax
  __int64 v45; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v46; // rcx
  __int64 v47; // r9
  __int64 v48; // rax
  BOOL ProvParam; // ebx
  __int64 v50; // r9
  BYTE *v51; // r8
  DWORD v52; // ebx
  unsigned int v53; // eax
  unsigned int Property; // ebx
  unsigned __int8 v55; // r8
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v56; // r14
  unsigned int valid; // ebx
  int v58; // ebx
  int v59; // eax
  int v60; // eax
  __int64 v61; // rdx
  HLOCAL v62; // rax
  __int64 v63; // rdx
  HCERTSTORE hCertStore; // [rsp+40h] [rbp-C0h]
  unsigned int v65; // [rsp+48h] [rbp-B8h] BYREF
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v66; // [rsp+50h] [rbp-B0h]
  HCERTSTORE v67; // [rsp+58h] [rbp-A8h]
  SCARDCONTEXT hContext; // [rsp+60h] [rbp-A0h] BYREF
  int v69; // [rsp+68h] [rbp-98h]
  DWORD pdwDataLen; // [rsp+6Ch] [rbp-94h] BYREF
  LPCVOID v71; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR szContainer; // [rsp+78h] [rbp-88h] BYREF
  BYTE pbData[8]; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcchProvider; // [rsp+88h] [rbp-78h] BYREF
  DWORD dwFlags; // [rsp+8Ch] [rbp-74h]
  unsigned int v76; // [rsp+90h] [rbp-70h]
  int v77; // [rsp+94h] [rbp-6Ch] BYREF
  int v78; // [rsp+98h] [rbp-68h] BYREF
  DWORD v79; // [rsp+9Ch] [rbp-64h]
  DWORD v80; // [rsp+A0h] [rbp-60h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+A8h] [rbp-58h] BYREF
  struct _CERT_CONTEXT *v82; // [rsp+B0h] [rbp-50h] BYREF
  LPCVOID pvMem; // [rsp+B8h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+C0h] [rbp-40h]
  DWORD pcchReaders; // [rsp+C8h] [rbp-38h] BYREF
  DWORD pcchCards; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v87; // [rsp+D0h] [rbp-30h]
  unsigned int v88; // [rsp+D4h] [rbp-2Ch]
  HCRYPTPROV phProv; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL v90; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR mszCards[4]; // [rsp+E8h] [rbp-18h] BYREF
  struct _EAPTLS_CONN_PROPERTIES_V1 *v92; // [rsp+F0h] [rbp-10h]
  __int64 v93; // [rsp+F8h] [rbp-8h]
  const CERT_CHAIN_CONTEXT *v94; // [rsp+100h] [rbp+0h]
  const struct _CERT_CONTEXT **v95; // [rsp+108h] [rbp+8h]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+110h] [rbp+10h]
  unsigned __int64 v97; // [rsp+118h] [rbp+18h] BYREF
  HWND hwnd; // [rsp+120h] [rbp+20h]
  _OWORD pvFindPara[3]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v100; // [rsp+158h] [rbp+58h]
  __int128 v101; // [rsp+160h] [rbp+60h] BYREF
  __int64 v102; // [rsp+170h] [rbp+70h]
  _BYTE v103[64]; // [rsp+180h] [rbp+80h] BYREF
  FILETIME NotBefore; // [rsp+1C0h] [rbp+C0h]
  unsigned __int16 CertWeight; // [rsp+1C8h] [rbp+C8h]
  _BYTE v106[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  FILETIME v107; // [rsp+220h] [rbp+120h]
  unsigned __int16 v108; // [rsp+228h] [rbp+128h]

  pPrevChainContext = 0;
  v82 = a6;
  v92 = a3;
  v76 = a2;
  v8 = 0;
  hwnd = a4;
  v95 = a7;
  v9 = 0;
  hContext = 0;
  phProvider = 0;
  phProv = 0;
  *(_QWORD *)pbData = 0;
  hCertStore = 0;
  pdwDataLen = 0;
  v90 = 0;
  v101 = 0;
  v102 = 0;
  v77 = 0;
  memset_0(v106, 0, 0x58u);
  memset_0(v103, 0, 0x58u);
  v65 = 0;
  pvMem = 0;
  pcchReaders = -1;
  v100 = 0;
  v10 = 0;
  v71 = 0;
  v11 = 0;
  hMem = 0;
  v12 = 0;
  v67 = 0;
  v69 = 0;
  pChainContext = 0;
  v78 = 0;
  v97 = 0;
  memset(&pvFindPara[1], 0, 32);
  pvFindPara[0] = 0x38u;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
  v13 = v76 & 2;
  *a7 = 0;
  v88 = v13;
  dwFlags = v13 != 0 ? 0x40 : 0;
  if ( !a5 )
  {
    hCertStore = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0, 0);
    v14 = hCertStore;
    if ( !hCertStore )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, LastError);
      v16 = 0;
      goto LABEL_8;
    }
    v67 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x18000u, L"MY");
    v16 = v67;
    if ( !v67 )
    {
      LastError = -2143158256;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v18 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v18);
      }
      goto LABEL_8;
    }
LABEL_24:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
    while ( 1 )
    {
      pChainContext = CertFindChainInStore(v16, 0x10001u, 0, 1u, pvFindPara, pPrevChainContext);
      pPrevChainContext = pChainContext;
      if ( !pChainContext )
        break;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
      pCertContext = (*(*pPrevChainContext->rgpChain)->rgpElement)->pCertContext;
      if ( (unsigned int)FCheckTimeValidity(pCertContext) )
      {
        if ( (unsigned int)IsCertNGC(pCertContext) == 1 )
        {
          if ( !v12 )
            v12 = 1;
          v69 = v12;
          if ( (unsigned int)AddCertificateToStore(
                               hCertStore,
                               pCertContext,
                               ((*((_DWORD *)v92 + 2) >> 10) & 1) == 0,
                               0,
                               &v65) )
          {
            v8 = CertDuplicateCertificateContext(pCertContext);
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
            pPrevChainContext = 0;
            goto LABEL_39;
          }
        }
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
        goto LABEL_24;
      }
    }
    pPrevChainContext = 0;
    if ( !v12 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
LABEL_39:
    v10 = v65;
    v9 = 0;
  }
  LastError = SCardEstablishContext(0, 0, 0, &hContext);
  if ( LastError )
    goto LABEL_51;
  LastError = SCardListReadersW(hContext, 0, (LPWSTR)&pvMem, &pcchReaders);
  if ( LastError )
    goto LABEL_51;
  v20 = pvMem;
  v21 = 0;
  v79 = 0;
  if ( *(_WORD *)pvMem )
  {
    do
    {
      ++v21;
      v22 = -1;
      do
        ++v22;
      while ( v20[v22] );
      v20 += v22 + 1;
    }
    while ( *v20 );
    v79 = v21;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v21);
  v66 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)LocalAlloc(0x40u, (unsigned __int64)v21 << 6);
  v11 = v66;
  if ( !v66 )
  {
    LastError = GetLastError();
    goto LABEL_51;
  }
  v23 = (const WCHAR *)pvMem;
  v24 = 0;
  while ( *v23 )
  {
    v25 = (unsigned __int64)v24 << 6;
    *(LPCWSTR *)((char *)&v11->szReader + v25) = v23;
    *(DWORD *)((char *)&v11->dwCurrentState + v25) = 0;
    v26 = -1;
    do
      ++v26;
    while ( v23[v26] );
    v23 += v26 + 1;
    ++v24;
  }
  LastError = SCardGetStatusChangeW(hContext, 0, v11, v21);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, LastError);
    goto LABEL_51;
  }
  v27 = WPP_GLOBAL_Control;
  v94 = 0;
  v28 = 0;
  v80 = 0;
  v29 = 0;
  if ( !v21 )
    goto LABEL_148;
  v30 = v66;
  v31 = 0;
  v93 = 0;
  do
  {
    *(_QWORD *)mszCards = 0;
    v32 = v31 << 6;
    pcchCards = -1;
    v33 = &v30[v31];
    if ( (v33->dwEventState & 0xA0) != 0x20 || !v33->cbAtr )
    {
      if ( v27 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_SDd(
          *((_QWORD *)v27 + 2),
          (_DWORD)v33,
          v30[v31].dwEventState,
          *(LPCWSTR *)((char *)&v30->szReader + v32),
          v30[v31].dwEventState,
          v33->cbAtr);
        goto LABEL_144;
      }
      goto LABEL_146;
    }
    v34 = SCardListCardsW(hContext, &v30->rgbAtr[v32], 0, 0, mszCards, &pcchCards);
    if ( v34 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v34);
        goto LABEL_144;
      }
      goto LABEL_145;
    }
    v37 = *(const WCHAR **)mszCards;
    if ( !**(_WORD **)mszCards )
      goto LABEL_92;
    do
    {
      ++v29;
      pcchProvider = -1;
      v87 = v29;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v35, v36, v29, (__int64)v37);
      if ( v71 )
      {
        SCardFreeMemory(hContext, v71);
        v71 = 0;
      }
      CardTypeProviderNameW = SCardGetCardTypeProviderNameW(hContext, v37, 3u, (WCHAR *)&v71, &pcchProvider);
      if ( CardTypeProviderNameW )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            72,
            &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids,
            CardTypeProviderNameW);
        v39 = SCardGetCardTypeProviderNameW(hContext, v37, 2u, (WCHAR *)&v71, &pcchProvider);
        if ( v39 )
        {
          v35 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v39);
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
          }
          goto LABEL_88;
        }
        szContainer = 0;
        FormattedCardName = GetFormattedCardName(
                              *(const unsigned __int16 **)((char *)&v66->szReader + v32),
                              (unsigned __int16 **)&szContainer);
        if ( FormattedCardName )
        {
          v41 = WPP_GLOBAL_Control;
          v35 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_88;
          v42 = 78;
LABEL_102:
          WPP_SF_d(*((_QWORD *)v41 + 2), v42, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, FormattedCardName);
          goto LABEL_88;
        }
        v43 = CryptAcquireContextW(&phProv, szContainer, (LPCWSTR)v71, 1u, dwFlags);
        LocalFree((HLOCAL)szContainer);
        if ( !v43 )
        {
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_88;
          v44 = GetLastError();
          v45 = 79;
          goto LABEL_86;
        }
        pdwDataLen = 8;
        ProvParam = CryptGetProvParam(phProv, 0x2Au, pbData, &pdwDataLen, 0);
        CryptReleaseContext(phProv, 0);
        if ( !ProvParam )
        {
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_88;
          v44 = GetLastError();
          v45 = 80;
LABEL_86:
          v46 = WPP_GLOBAL_Control;
          v47 = v44;
LABEL_87:
          WPP_SF_d(*((_QWORD *)v46 + 2), v45, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v47);
          goto LABEL_88;
        }
      }
      else
      {
        FormattedCardName = NCryptOpenStorageProvider(&phProvider, (LPCWSTR)v71, 0);
        if ( FormattedCardName )
        {
          v41 = WPP_GLOBAL_Control;
          v35 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_88;
          v42 = 75;
          goto LABEL_102;
        }
        v50 = -1;
        v51 = *(BYTE **)((char *)&v66->szReader + v32);
        do
          ++v50;
        while ( *(_WORD *)&v51[2 * v50] );
        v52 = dwFlags;
        v53 = NCryptSetProperty(phProvider, L"SmartCardReader", v51, 2 * v50 + 2, dwFlags);
        if ( v53 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v53);
          NCryptFreeObject(phProvider);
          goto LABEL_88;
        }
        Property = NCryptGetProperty(phProvider, L"SmartCardUserCertStore", pbData, 8u, &pdwDataLen, v52);
        NCryptFreeObject(phProvider);
        if ( Property )
        {
          v46 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_88;
          v45 = 77;
          v47 = Property;
          goto LABEL_87;
        }
      }
      v9 = CertEnumCertificatesInStore(*(HCERTSTORE *)pbData, v9);
      if ( !v9 )
        goto LABEL_141;
      v56 = v66;
      do
      {
        szContainer = 0;
        if ( (unsigned int)CheckForCertificateRenewal(
                             *(HCERTSTORE *)pbData,
                             v9,
                             v55,
                             (const struct _CERT_CONTEXT **)&szContainer)
          && v9 != (PCCERT_CONTEXT)szContainer )
        {
          CertFreeCertificateContext((PCCERT_CONTEXT)szContainer);
          goto LABEL_139;
        }
        if ( szContainer )
          CertFreeCertificateContext((PCCERT_CONTEXT)szContainer);
        valid = isValidSCardCert(
                  v9,
                  (struct _EAPTLS_FILTER_PROP *)v82,
                  v76,
                  (struct _EAPTLS_HASH *)&v101,
                  (unsigned __int16 **)&v90,
                  &v77);
        LocalFree(v90);
        v90 = 0;
        if ( !valid )
        {
          v58 = 0;
          if ( v77 )
          {
            if ( !WiFiCredRequireNgc(v9, &v78, &v97) && v78 == 1 )
            {
              v59 = v69;
              v58 = 1;
              if ( !v69 )
                v59 = 1;
              v69 = v59;
            }
            if ( a5
              || (v60 = AddCertificateToStore(hCertStore, v9, ((*((_DWORD *)v92 + 2) >> 10) & 1) == 0, v58, &v65),
                  v10 = v65,
                  v60) )
            {
              if ( v8 )
              {
                if ( !a5 )
                  goto LABEL_139;
              }
              else
              {
                v8 = CertDuplicateCertificateContext(v9);
                if ( !a5 )
                  goto LABEL_139;
                v10 = 1;
                v65 = 1;
              }
              CertWeight = GetCertWeight(v9);
              NotBefore = v9->pCertInfo->NotBefore;
              if ( (int)CompareCertWeight((struct _EAPTLS_CERT_NODE *)v106, (struct _EAPTLS_CERT_NODE *)v103) < 0 )
              {
                CertFreeCertificateContext(v8);
                v8 = CertDuplicateCertificateContext(v9);
                v108 = CertWeight;
                v107 = NotBefore;
                v94 = *(const CERT_CHAIN_CONTEXT **)((char *)&v56->szReader + v32);
                LocalFree(hMem);
                v61 = -1;
                do
                  ++v61;
                while ( v37[v61] );
                v62 = LocalAlloc(0x40u, 2 * v61 + 2);
                hMem = v62;
                if ( v62 )
                {
                  v63 = -1;
                  do
                    ++v63;
                  while ( v37[v63] );
                  _o_wcscpy_s(v62, v63 + 1, v37);
                }
              }
            }
          }
        }
LABEL_139:
        v9 = CertEnumCertificatesInStore(*(HCERTSTORE *)pbData, v9);
      }
      while ( v9 );
      v29 = v87;
LABEL_141:
      CertCloseStore(*(HCERTSTORE *)pbData, 0);
LABEL_88:
      v48 = -1;
      do
        ++v48;
      while ( v37[v48] );
      v37 += v48 + 1;
    }
    while ( *v37 );
    v37 = *(const WCHAR **)mszCards;
    v28 = v80;
LABEL_92:
    SCardFreeMemory(hContext, v37);
    v21 = v79;
LABEL_144:
    v27 = WPP_GLOBAL_Control;
LABEL_145:
    v30 = v66;
LABEL_146:
    ++v28;
    v31 = v93 + 1;
    v80 = v28;
    ++v93;
  }
  while ( v28 < v21 );
  pPrevChainContext = v94;
LABEL_148:
  if ( v27 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_dd(*((_QWORD *)v27 + 2), 81, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v29, v10);
  if ( !v10 )
  {
    LastError = v29 != 0 ? 798 : -2146435060;
    goto LABEL_152;
  }
  LastError = 0;
  if ( v10 != 1 || v69 != 1 )
  {
    if ( a5 )
    {
      v82 = 0;
      if ( !ExtractCAPICert(
              hContext,
              (const unsigned __int16 *)pPrevChainContext,
              (LPCWSTR)hMem,
              v8,
              (const struct _CERT_CONTEXT **)&v82) )
      {
        CertFreeCertificateContext(v8);
        v8 = v82;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
      }
    }
    else
    {
      if ( v82 )
        SQMCertSelectData(0, v10 > 1);
      if ( v10 > 1 )
      {
        v14 = hCertStore;
        if ( v88 )
        {
          LastError = 703;
LABEL_165:
          v11 = v66;
          goto LABEL_52;
        }
        v8 = CryptUIDlgSelectCertificateFromStore(hCertStore, hwnd, 0, 0, 0, 0, 0);
        if ( !v8 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids);
          LastError = 1223;
          goto LABEL_165;
        }
LABEL_171:
        *v95 = v8;
        goto LABEL_165;
      }
    }
    v14 = hCertStore;
    goto LABEL_171;
  }
  *v95 = v8;
LABEL_152:
  v11 = v66;
LABEL_51:
  v14 = hCertStore;
LABEL_52:
  v16 = v67;
LABEL_8:
  if ( pvMem )
    SCardFreeMemory(hContext, pvMem);
  if ( v71 )
    SCardFreeMemory(hContext, v71);
  if ( hContext )
    SCardReleaseContext(hContext);
  if ( v14 )
    CertCloseStore(v14, 0);
  if ( v16 )
    CertCloseStore(v16, 0);
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  LocalFree(v11);
  LocalFree(hMem);
  return LastError;
}

```

## disassembly

```asm
0x180073538  push    rbp
0x18007353a  push    rbx
0x18007353b  push    rsi
0x18007353c  push    rdi
0x18007353d  push    r12
0x18007353f  push    r13
0x180073541  push    r14
0x180073543  push    r15
0x180073545  lea     rbp, [rsp-158h]
0x18007354d  sub     rsp, 258h
0x180073554  mov     rax, cs:__security_cookie
0x18007355b  xor     rax, rsp
0x18007355e  mov     [rbp+190h+var_50], rax
0x180073565  mov     rax, [rbp+190h+arg_28]
0x18007356c  lea     rcx, [rbp+190h+var_B0]; void *
0x180073573  mov     rbx, [rbp+190h+arg_30]
0x18007357a  xor     r15d, r15d
0x18007357d  mov     [rbp+190h+var_1E0], rax
0x180073581  xorps   xmm0, xmm0
0x180073584  xor     eax, eax
0x180073586  mov     [rbp+190h+var_1A0], r8
0x18007358a  mov     [rbp+190h+var_200], edx
0x18007358d  mov     r12d, r15d
0x180073590  xor     edx, edx; Val
0x180073592  mov     [rbp+190h+hwnd], r9
0x180073596  mov     [rbp+190h+var_188], rbx
0x18007359a  mov     r13d, r15d
0x18007359d  lea     edi, [rax+58h]
0x1800735a0  mov     [rsp+290h+hContext], r15
0x1800735a5  mov     r8d, edi; Size
0x1800735a8  mov     [rbp+190h+phProvider], r15
0x1800735ac  mov     [rbp+190h+phProv], r15
0x1800735b0  mov     qword ptr [rbp+190h+pbData], r15
0x1800735b4  mov     [rsp+290h+hCertStore], r15
0x1800735b9  mov     [rsp+290h+pdwDataLen], r15d
0x1800735be  mov     [rbp+190h+var_1B0], r15
0x1800735c2  movups  [rbp+190h+var_130], xmm0
0x1800735c6  mov     [rbp+190h+var_120], rax
0x1800735ca  mov     [rbp+190h+var_1FC], r15d
0x1800735ce  call    memset_0
0x1800735d3  mov     r8d, edi; Size
0x1800735d6  lea     rcx, [rbp+190h+var_110]; void *
0x1800735dd  xor     edx, edx; Val
0x1800735df  call    memset_0
0x1800735e4  xor     edx, edx
0x1800735e6  mov     [rsp+290h+var_248], r15d
0x1800735eb  xorps   xmm0, xmm0
0x1800735ee  mov     [rbp+190h+pvMem], r15
0x1800735f2  movups  [rbp+190h+pvFindPara], xmm0
0x1800735f6  xor     eax, eax
0x1800735f8  mov     [rbp+190h+pcchReaders], 0FFFFFFFFh
0x1800735ff  mov     [rbp+190h+var_138], rax
0x180073603  mov     esi, r15d
0x180073606  mov     [rsp+290h+var_220], r15
0x18007360b  mov     r14d, r15d
0x18007360e  mov     [rbp+190h+hMem], r15
0x180073612  mov     edi, r15d
0x180073615  mov     [rsp+290h+var_238], r15
0x18007361a  mov     [rsp+290h+var_228], r15d
0x18007361f  mov     [rbp+190h+pChainContext], r15
0x180073623  mov     [rbp+190h+var_1F8], edx
0x180073626  mov     [rbp+190h+var_178], rdx
0x18007362a  movups  [rbp+190h+var_158], xmm0
0x18007362e  mov     dword ptr [rbp+190h+pvFindPara], 38h ; '8'
0x180073635  movups  [rbp+190h+var_148], xmm0
0x180073639  mov     qword ptr [rbp+190h+pvFindPara+8], rdx
0x18007363d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073644  lea     rax, WPP_GLOBAL_Control
0x18007364b  cmp     rcx, rax
0x18007364e  jz      short loc_180073666
0x180073650  mov     rcx, [rcx+10h]
0x180073654  lea     edx, [r15+3Bh]
0x180073658  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x18007365f  call    WPP_SF_
0x180073664  xor     edx, edx
0x180073666  mov     eax, [rbp+190h+var_200]
0x180073669  and     eax, 2
0x18007366c  mov     [rbx], rdx
0x18007366f  mov     [rbp+190h+var_1BC], eax
0x180073672  neg     eax
0x180073674  sbb     eax, eax
0x180073676  and     eax, 40h
0x180073679  mov     [rbp+190h+dwFlags], eax
0x18007367c  cmp     [rbp+190h+arg_20], edx
0x180073682  jnz     loc_18007394F
0x180073688  xor     r9d, r9d; dwFlags
0x18007368b  mov     [rsp+290h+pvPara], rdx; pvPara
0x180073690  xor     r8d, r8d; hCryptProv
0x180073693  mov     edx, 10001h; dwEncodingType
0x180073698  lea     ecx, [r9+2]; lpszStoreProvider
0x18007369c  call    cs:__imp_CertOpenStore
0x1800736a2  mov     [rsp+290h+hCertStore], rax
0x1800736a7  mov     rsi, rax
0x1800736aa  test    rax, rax
0x1800736ad  jnz     loc_180073787
0x1800736b3  call    cs:__imp_GetLastError
0x1800736b9  mov     ebx, eax
0x1800736bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736c2  lea     rax, WPP_GLOBAL_Control
0x1800736c9  cmp     rcx, rax
0x1800736cc  jz      short loc_1800736E4
0x1800736ce  mov     rcx, [rcx+10h]
0x1800736d2  lea     edx, [rsi+3Ch]
0x1800736d5  mov     r9d, ebx
0x1800736d8  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800736df  call    WPP_SF_d
0x1800736e4  mov     r13, rdi
0x1800736e7  mov     rdx, [rbp+190h+pvMem]; pvMem
0x1800736eb  test    rdx, rdx
0x1800736ee  jz      short loc_1800736FB
0x1800736f0  mov     rcx, [rsp+290h+hContext]; hContext
0x1800736f5  call    cs:__imp_SCardFreeMemory
0x1800736fb  mov     rdx, [rsp+290h+var_220]; pvMem
0x180073700  test    rdx, rdx
0x180073703  jz      short loc_180073710
0x180073705  mov     rcx, [rsp+290h+hContext]; hContext
0x18007370a  call    cs:__imp_SCardFreeMemory
0x180073710  mov     rcx, [rsp+290h+hContext]; hContext
0x180073715  test    rcx, rcx
0x180073718  jz      short loc_180073720
0x18007371a  call    cs:__imp_SCardReleaseContext
0x180073720  test    rsi, rsi
0x180073723  jz      short loc_180073730
0x180073725  xor     edx, edx; dwFlags
0x180073727  mov     rcx, rsi; hCertStore
0x18007372a  call    cs:__imp_CertCloseStore
0x180073730  test    r13, r13
0x180073733  jz      short loc_180073740
0x180073735  xor     edx, edx; dwFlags
0x180073737  mov     rcx, r13; hCertStore
0x18007373a  call    cs:__imp_CertCloseStore
0x180073740  mov     rcx, [rbp+190h+pChainContext]; pChainContext
0x180073744  test    rcx, rcx
0x180073747  jz      short loc_18007374F
0x180073749  call    cs:__imp_CertFreeCertificateChain
0x18007374f  mov     rcx, r14; hMem
0x180073752  call    cs:__imp_LocalFree
0x180073758  mov     rcx, [rbp+190h+hMem]; hMem
0x18007375c  call    cs:__imp_LocalFree
0x180073762  mov     eax, ebx
0x180073764  mov     rcx, [rbp+190h+var_50]
0x18007376b  xor     rcx, rsp; StackCookie
0x18007376e  call    __security_check_cookie
0x180073773  add     rsp, 258h
0x18007377a  pop     r15
0x18007377c  pop     r14
0x18007377e  pop     r13
0x180073780  pop     r12
0x180073782  pop     rdi
0x180073783  pop     rsi
0x180073784  pop     rbx
0x180073785  pop     rbp
0x180073786  retn
0x180073787  xor     edx, edx; dwEncodingType
0x180073789  lea     rax, aMy_1; "MY"
0x180073790  mov     r9d, 18000h; dwFlags
0x180073796  mov     [rsp+290h+pvPara], rax; pvPara
0x18007379b  xor     r8d, r8d; hCryptProv
0x18007379e  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800737a1  call    cs:__imp_CertOpenStore
0x1800737a7  mov     [rsp+290h+var_238], rax
0x1800737ac  mov     r13, rax
0x1800737af  test    rax, rax
0x1800737b2  jnz     short loc_1800737F6
0x1800737b4  mov     ebx, 80420010h
0x1800737b9  lea     rax, WPP_GLOBAL_Control
0x1800737c0  cmp     cs:WPP_GLOBAL_Control, rax
0x1800737c7  jz      loc_1800736E7
0x1800737cd  call    cs:__imp_GetLastError
0x1800737d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800737da  lea     edx, [r13+3Dh]
0x1800737de  mov     r9d, eax
0x1800737e1  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800737e8  mov     rcx, [rcx+10h]
0x1800737ec  call    WPP_SF_d
0x1800737f1  jmp     loc_1800736E7
0x1800737f6  lea     rbx, WPP_GLOBAL_Control
0x1800737fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180073804  cmp     rcx, rbx
0x180073807  jz      short loc_18007381E
0x180073809  mov     rcx, [rcx+10h]
0x18007380d  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180073814  mov     edx, 3Eh ; '>'
0x180073819  call    WPP_SF_
0x18007381e  lea     rax, [rbp+190h+pvFindPara]
0x180073822  mov     [rsp+290h+pPrevChainContext], r15; pPrevChainContext
0x180073827  mov     r9d, 1; dwFindType
0x18007382d  mov     [rsp+290h+pvPara], rax; pvFindPara
0x180073832  xor     r8d, r8d; dwFindFlags
0x180073835  mov     edx, 10001h; dwCertEncodingType
0x18007383a  mov     rcx, r13; hCertStore
0x18007383d  call    cs:__imp_CertFindChainInStore
0x180073843  mov     [rbp+190h+pChainContext], rax
0x180073847  mov     r15, rax
0x18007384a  test    rax, rax
0x18007384d  jz      loc_180073A1F
0x180073853  mov     rcx, cs:WPP_GLOBAL_Control
0x18007385a  cmp     rcx, rbx
0x18007385d  jz      short loc_180073874
0x18007385f  mov     rcx, [rcx+10h]
0x180073863  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x18007386a  mov     edx, 40h ; '@'
0x18007386f  call    WPP_SF_
0x180073874  mov     rax, [r15+10h]
0x180073878  mov     rcx, [rax]
0x18007387b  mov     rax, [rcx+10h]
0x18007387f  mov     rcx, [rax]
0x180073882  mov     rbx, [rcx+8]
0x180073886  mov     rcx, rbx; struct _CERT_CONTEXT *
0x180073889  call    ?FCheckTimeValidity@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckTimeValidity(_CERT_CONTEXT const *)
0x18007388e  test    eax, eax
0x180073890  jnz     short loc_1800738C1
0x180073892  mov     rcx, cs:WPP_GLOBAL_Control
0x180073899  lea     rbx, WPP_GLOBAL_Control
0x1800738a0  cmp     rcx, rbx
0x1800738a3  jz      loc_18007381E
0x1800738a9  mov     rcx, [rcx+10h]
0x1800738ad  lea     edx, [rax+41h]
0x1800738b0  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800738b7  call    WPP_SF_
0x1800738bc  jmp     loc_1800737FD
0x1800738c1  mov     rcx, rbx; pCertContext
0x1800738c4  call    ?IsCertNGC@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertNGC(_CERT_CONTEXT const *)
0x1800738c9  mov     ecx, 1
0x1800738ce  cmp     eax, ecx
0x1800738d0  jnz     loc_1800737F6
0x1800738d6  mov     rax, [rbp+190h+var_1A0]
0x1800738da  test    edi, edi
0x1800738dc  mov     rdx, rbx; pCertContext
0x1800738df  cmovz   edi, ecx
0x1800738e2  xor     r9d, r9d; int
0x1800738e5  mov     [rsp+290h+var_228], edi
0x1800738e9  mov     r8d, [rax+8]
0x1800738ed  lea     rax, [rsp+290h+var_248]
0x1800738f2  shr     r8d, 0Ah
0x1800738f6  not     r8d
0x1800738f9  mov     [rsp+290h+pvPara], rax; unsigned int *
0x1800738fe  and     r8d, ecx; int
0x180073901  mov     rcx, rsi; hCertStore
0x180073904  call    ?AddCertificateToStore@@YAHPEAXPEBU_CERT_CONTEXT@@HHPEAK@Z; AddCertificateToStore(void *,_CERT_CONTEXT const *,int,int,ulong *)
0x180073909  test    eax, eax
0x18007390b  jz      loc_1800737F6
0x180073911  mov     rcx, rbx; pCertContext
0x180073914  call    cs:__imp_CertDuplicateCertificateContext
0x18007391a  mov     r12, rax
0x18007391d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073924  lea     rax, WPP_GLOBAL_Control
0x18007392b  cmp     rcx, rax
0x18007392e  jz      short loc_180073945
0x180073930  mov     rcx, [rcx+10h]
0x180073934  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x18007393b  mov     edx, 42h ; 'B'
0x180073940  call    WPP_SF_
0x180073945  xor     r15d, r15d
0x180073948  mov     esi, [rsp+290h+var_248]
0x18007394c  mov     r13, r15
0x18007394f  lea     r9, [rsp+290h+hContext]; phContext
0x180073954  xor     r8d, r8d; pvReserved2
0x180073957  xor     edx, edx; pvReserved1
0x180073959  xor     ecx, ecx; dwScope
0x18007395b  call    cs:__imp_SCardEstablishContext
0x180073961  mov     ebx, eax
0x180073963  test    eax, eax
0x180073965  jnz     loc_180073A10
0x18007396b  mov     rcx, [rsp+290h+hContext]; hContext
0x180073970  lea     r9, [rbp+190h+pcchReaders]; pcchReaders
0x180073974  lea     r8, [rbp+190h+pvMem]; mszReaders
0x180073978  xor     edx, edx; mszGroups
0x18007397a  call    cs:__imp_SCardListReadersW
0x180073980  mov     ebx, eax
0x180073982  test    eax, eax
0x180073984  jnz     loc_180073A10
0x18007398a  mov     rax, [rbp+190h+pvMem]
0x18007398e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180073992  mov     edi, r15d
0x180073995  mov     [rbp+190h+var_1F4], r15d
0x180073999  cmp     [rax], r15w
0x18007399d  jz      short loc_1800739BF
0x18007399f  inc     edi
0x1800739a1  mov     rcx, rbx
0x1800739a4  inc     rcx
0x1800739a7  cmp     [rax+rcx*2], r15w
0x1800739ac  jnz     short loc_1800739A4
0x1800739ae  lea     rax, [rax+rcx*2]
0x1800739b2  add     rax, 2
0x1800739b6  cmp     [rax], r15w
0x1800739ba  jnz     short loc_18007399F
0x1800739bc  mov     [rbp+190h+var_1F4], edi
0x1800739bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800739c6  lea     rax, WPP_GLOBAL_Control
0x1800739cd  cmp     rcx, rax
0x1800739d0  jz      short loc_1800739EA
0x1800739d2  mov     rcx, [rcx+10h]
0x1800739d6  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800739dd  mov     edx, 43h ; 'C'
0x1800739e2  mov     r9d, edi
0x1800739e5  call    WPP_SF_d
0x1800739ea  mov     edx, edi
0x1800739ec  mov     ecx, 40h ; '@'; uFlags
0x1800739f1  shl     rdx, 6; uBytes
  ... truncated ...
```
