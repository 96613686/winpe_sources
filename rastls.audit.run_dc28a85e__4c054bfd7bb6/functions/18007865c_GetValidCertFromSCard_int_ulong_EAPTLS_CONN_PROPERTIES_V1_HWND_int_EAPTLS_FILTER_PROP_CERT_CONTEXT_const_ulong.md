# GetValidCertFromSCard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x18007865c`
- end: `0x180079565`
- name: `?GetValidCertFromSCard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU4@@Z`
- size: `3849`
- prototype: `unsigned int __fastcall(int, unsigned int, struct _EAPTLS_CONN_PROPERTIES_V1 *, HWND, int, struct _EAPTLS_FILTER_PROP *, const struct _CERT_CONTEXT **, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180074168`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038270`
- `0x180038e64`
- `0x18004d58c`
- `0x18006a5dc`
- `0x18006aa70`
- `0x18006d744`
- `0x18006e2e0`
- `0x180071118`
- `0x180071dd4`
- `0x18007510c`
- `0x180076704`
- `0x180076e20`
- `0x180077514`
- `0x180078070`
- `0x18007865c`
- `0x180079a0c`
- `0x180079aa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007935c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007935c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800787dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078f72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078b7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180079331`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078b7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180079331`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800788a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800788b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800791b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007930b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800788a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800788b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078e8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800791b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007930b`
- `CRYPT32!CertCloseStore` at `0x18007886c`
- `CRYPT32!CertCloseStore` at `0x180078882`
- `CRYPT32!CertCloseStore` at `0x180079395`
- `CRYPT32!CertCloseStore` at `0x18007886c`
- `CRYPT32!CertCloseStore` at `0x180078882`
- `CRYPT32!CertCloseStore` at `0x180079395`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180079127`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180079373`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180079127`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180079373`
- `CRYPT32!CertFreeCertificateContext` at `0x18007916a`
- `CRYPT32!CertFreeCertificateContext` at `0x180079180`
- `CRYPT32!CertFreeCertificateContext` at `0x1800792c5`
- `CRYPT32!CertFreeCertificateContext` at `0x180079526`
- `CRYPT32!CertFreeCertificateContext` at `0x18007916a`
- `CRYPT32!CertFreeCertificateContext` at `0x180079180`
- `CRYPT32!CertFreeCertificateContext` at `0x1800792c5`
- `CRYPT32!CertFreeCertificateContext` at `0x180079526`
- `CRYPT32!CertOpenStore` at `0x1800787c0`
- `CRYPT32!CertOpenStore` at `0x180078902`
- `CRYPT32!CertOpenStore` at `0x1800787c0`
- `CRYPT32!CertOpenStore` at `0x180078902`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180078a87`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180079257`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800792d4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180078a87`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180079257`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800792d4`
- `CRYPT32!CertFindChainInStore` at `0x1800789aa`
- `CRYPT32!CertFindChainInStore` at `0x1800789aa`
- `CRYPT32!CertFreeCertificateChain` at `0x180078897`
- `CRYPT32!CertFreeCertificateChain` at `0x180078897`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x180078f36`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x180078f36`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180078e77`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180078e77`
- `ncrypt!NCryptOpenStorageProvider` at `0x180078ff2`
- `ncrypt!NCryptOpenStorageProvider` at `0x180078ff2`
- `ncrypt!NCryptGetProperty` at `0x1800790da`
- `ncrypt!NCryptGetProperty` at `0x1800790da`
- `ncrypt!NCryptSetProperty` at `0x180079067`
- `ncrypt!NCryptSetProperty` at `0x180079067`
- `ncrypt!NCryptFreeObject` at `0x1800790a6`
- `ncrypt!NCryptFreeObject` at `0x1800790ec`
- `ncrypt!NCryptFreeObject` at `0x1800790a6`
- `ncrypt!NCryptFreeObject` at `0x1800790ec`
- `CRYPTSP!CryptReleaseContext` at `0x180078f4a`
- `CRYPTSP!CryptReleaseContext` at `0x180078f4a`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x1800794b1`
- `ext-ms-win-security-cryptui-l1-1-0!CryptUIDlgSelectCertificateFromStore` at `0x1800794b1`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x180078ad4`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x180078ad4`
- `ext-ms-win-security-winscard-l1-1-0!SCardListCardsW` at `0x180078cec`
- `ext-ms-win-security-winscard-l1-1-0!SCardListCardsW` at `0x180078cec`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x180078af9`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x180078af9`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetStatusChangeW` at `0x180078c25`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetStatusChangeW` at `0x180078c25`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180078db0`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180078e0b`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180078db0`
- `ext-ms-win-security-winscard-l1-1-0!SCardGetCardTypeProviderNameW` at `0x180078e0b`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078825`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078840`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078d83`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078f04`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078825`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078840`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078d83`
- `ext-ms-win-security-winscard-l1-1-0!SCardFreeMemory` at `0x180078f04`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x180078856`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x180078856`

## string_xrefs

- `0x18007905c`: `SmartCardReader`

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
    WPP_SF_DD(*((_QWORD *)v27 + 2), 81, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v29, v10);
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
0x18007865c  push    rbp
0x18007865e  push    rbx
0x18007865f  push    rsi
0x180078660  push    rdi
0x180078661  push    r12
0x180078663  push    r13
0x180078665  push    r14
0x180078667  push    r15
0x180078669  lea     rbp, [rsp-158h]
0x180078671  sub     rsp, 258h
0x180078678  mov     rax, cs:__security_cookie
0x18007867f  xor     rax, rsp
0x180078682  mov     [rbp+190h+var_50], rax
0x180078689  mov     rax, [rbp+190h+arg_28]
0x180078690  lea     rcx, [rbp+190h+var_B0]; void *
0x180078697  mov     rbx, [rbp+190h+arg_30]
0x18007869e  xor     r15d, r15d
0x1800786a1  mov     [rbp+190h+var_1E0], rax
0x1800786a5  xorps   xmm0, xmm0
0x1800786a8  xor     eax, eax
0x1800786aa  mov     [rbp+190h+var_1A0], r8
0x1800786ae  mov     [rbp+190h+var_200], edx
0x1800786b1  mov     r12d, r15d
0x1800786b4  xor     edx, edx; Val
0x1800786b6  mov     [rbp+190h+hwnd], r9
0x1800786ba  mov     [rbp+190h+var_188], rbx
0x1800786be  mov     r13d, r15d
0x1800786c1  lea     edi, [rax+58h]
0x1800786c4  mov     [rsp+290h+hContext], r15
0x1800786c9  mov     r8d, edi; Size
0x1800786cc  mov     [rbp+190h+phProvider], r15
0x1800786d0  mov     [rbp+190h+phProv], r15
0x1800786d4  mov     qword ptr [rbp+190h+pbData], r15
0x1800786d8  mov     [rsp+290h+hCertStore], r15
0x1800786dd  mov     [rsp+290h+pdwDataLen], r15d
0x1800786e2  mov     [rbp+190h+var_1B0], r15
0x1800786e6  movups  [rbp+190h+var_130], xmm0
0x1800786ea  mov     [rbp+190h+var_120], rax
0x1800786ee  mov     [rbp+190h+var_1FC], r15d
0x1800786f2  call    memset_0
0x1800786f7  mov     r8d, edi; Size
0x1800786fa  lea     rcx, [rbp+190h+var_110]; void *
0x180078701  xor     edx, edx; Val
0x180078703  call    memset_0
0x180078708  xor     edx, edx
0x18007870a  mov     [rsp+290h+var_248], r15d
0x18007870f  xorps   xmm0, xmm0
0x180078712  mov     [rbp+190h+pvMem], r15
0x180078716  movups  [rbp+190h+pvFindPara], xmm0
0x18007871a  xor     eax, eax
0x18007871c  mov     [rbp+190h+pcchReaders], 0FFFFFFFFh
0x180078723  mov     [rbp+190h+var_138], rax
0x180078727  mov     esi, r15d
0x18007872a  mov     [rsp+290h+var_220], r15
0x18007872f  mov     r14d, r15d
0x180078732  mov     [rbp+190h+hMem], r15
0x180078736  mov     edi, r15d
0x180078739  mov     [rsp+290h+var_238], r15
0x18007873e  mov     [rsp+290h+var_228], r15d
0x180078743  mov     [rbp+190h+pChainContext], r15
0x180078747  mov     [rbp+190h+var_1F8], edx
0x18007874a  mov     [rbp+190h+var_178], rdx
0x18007874e  movups  [rbp+190h+var_158], xmm0
0x180078752  mov     dword ptr [rbp+190h+pvFindPara], 38h ; '8'
0x180078759  movups  [rbp+190h+var_148], xmm0
0x18007875d  mov     qword ptr [rbp+190h+pvFindPara+8], rdx
0x180078761  mov     rcx, cs:WPP_GLOBAL_Control
0x180078768  lea     rax, WPP_GLOBAL_Control
0x18007876f  cmp     rcx, rax
0x180078772  jz      short loc_18007878A
0x180078774  mov     rcx, [rcx+10h]
0x180078778  lea     edx, [r15+3Bh]
0x18007877c  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180078783  call    WPP_SF_
0x180078788  xor     edx, edx
0x18007878a  mov     eax, [rbp+190h+var_200]
0x18007878d  and     eax, 2
0x180078790  mov     [rbx], rdx
0x180078793  mov     [rbp+190h+var_1BC], eax
0x180078796  neg     eax
0x180078798  sbb     eax, eax
0x18007879a  and     eax, 40h
0x18007879d  mov     [rbp+190h+dwFlags], eax
0x1800787a0  cmp     [rbp+190h+arg_20], edx
0x1800787a6  jnz     loc_180078AC8
0x1800787ac  xor     r9d, r9d; dwFlags
0x1800787af  mov     [rsp+290h+pvPara], rdx; pvPara
0x1800787b4  xor     r8d, r8d; hCryptProv
0x1800787b7  mov     edx, 10001h; dwEncodingType
0x1800787bc  lea     ecx, [r9+2]; lpszStoreProvider
0x1800787c0  call    cs:__imp_CertOpenStore
0x1800787c7  nop     dword ptr [rax+rax+00h]
0x1800787cc  mov     [rsp+290h+hCertStore], rax
0x1800787d1  mov     rsi, rax
0x1800787d4  test    rax, rax
0x1800787d7  jnz     loc_1800788E8
0x1800787dd  call    cs:__imp_GetLastError
0x1800787e4  nop     dword ptr [rax+rax+00h]
0x1800787e9  mov     ebx, eax
0x1800787eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787f2  lea     rax, WPP_GLOBAL_Control
0x1800787f9  cmp     rcx, rax
0x1800787fc  jz      short loc_180078814
0x1800787fe  mov     rcx, [rcx+10h]
0x180078802  lea     edx, [rsi+3Ch]
0x180078805  mov     r9d, ebx
0x180078808  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x18007880f  call    WPP_SF_d
0x180078814  mov     r13, rdi
0x180078817  mov     rdx, [rbp+190h+pvMem]; pvMem
0x18007881b  test    rdx, rdx
0x18007881e  jz      short loc_180078831
0x180078820  mov     rcx, [rsp+290h+hContext]; hContext
0x180078825  call    cs:__imp_SCardFreeMemory
0x18007882c  nop     dword ptr [rax+rax+00h]
0x180078831  mov     rdx, [rsp+290h+var_220]; pvMem
0x180078836  test    rdx, rdx
0x180078839  jz      short loc_18007884C
0x18007883b  mov     rcx, [rsp+290h+hContext]; hContext
0x180078840  call    cs:__imp_SCardFreeMemory
0x180078847  nop     dword ptr [rax+rax+00h]
0x18007884c  mov     rcx, [rsp+290h+hContext]; hContext
0x180078851  test    rcx, rcx
0x180078854  jz      short loc_180078862
0x180078856  call    cs:__imp_SCardReleaseContext
0x18007885d  nop     dword ptr [rax+rax+00h]
0x180078862  test    rsi, rsi
0x180078865  jz      short loc_180078878
0x180078867  xor     edx, edx; dwFlags
0x180078869  mov     rcx, rsi; hCertStore
0x18007886c  call    cs:__imp_CertCloseStore
0x180078873  nop     dword ptr [rax+rax+00h]
0x180078878  test    r13, r13
0x18007887b  jz      short loc_18007888E
0x18007887d  xor     edx, edx; dwFlags
0x18007887f  mov     rcx, r13; hCertStore
0x180078882  call    cs:__imp_CertCloseStore
0x180078889  nop     dword ptr [rax+rax+00h]
0x18007888e  mov     rcx, [rbp+190h+pChainContext]; pChainContext
0x180078892  test    rcx, rcx
0x180078895  jz      short loc_1800788A3
0x180078897  call    cs:__imp_CertFreeCertificateChain
0x18007889e  nop     dword ptr [rax+rax+00h]
0x1800788a3  mov     rcx, r14; hMem
0x1800788a6  call    cs:__imp_LocalFree
0x1800788ad  nop     dword ptr [rax+rax+00h]
0x1800788b2  mov     rcx, [rbp+190h+hMem]; hMem
0x1800788b6  call    cs:__imp_LocalFree
0x1800788bd  nop     dword ptr [rax+rax+00h]
0x1800788c2  mov     eax, ebx
0x1800788c4  mov     rcx, [rbp+190h+var_50]
0x1800788cb  xor     rcx, rsp; StackCookie
0x1800788ce  call    __security_check_cookie
0x1800788d3  add     rsp, 258h
0x1800788da  pop     r15
0x1800788dc  pop     r14
0x1800788de  pop     r13
0x1800788e0  pop     r12
0x1800788e2  pop     rdi
0x1800788e3  pop     rsi
0x1800788e4  pop     rbx
0x1800788e5  pop     rbp
0x1800788e6  retn
0x1800788e8  xor     edx, edx; dwEncodingType
0x1800788ea  lea     rax, aMy_1; "MY"
0x1800788f1  mov     r9d, 18000h; dwFlags
0x1800788f7  mov     [rsp+290h+pvPara], rax; pvPara
0x1800788fc  xor     r8d, r8d; hCryptProv
0x1800788ff  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180078902  call    cs:__imp_CertOpenStore
0x180078909  nop     dword ptr [rax+rax+00h]
0x18007890e  mov     [rsp+290h+var_238], rax
0x180078913  mov     r13, rax
0x180078916  test    rax, rax
0x180078919  jnz     short loc_180078963
0x18007891b  mov     ebx, 80420010h
0x180078920  lea     rax, WPP_GLOBAL_Control
0x180078927  cmp     cs:WPP_GLOBAL_Control, rax
0x18007892e  jz      loc_180078817
0x180078934  call    cs:__imp_GetLastError
0x18007893b  nop     dword ptr [rax+rax+00h]
0x180078940  mov     rcx, cs:WPP_GLOBAL_Control
0x180078947  lea     edx, [r13+3Dh]
0x18007894b  mov     r9d, eax
0x18007894e  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180078955  mov     rcx, [rcx+10h]
0x180078959  call    WPP_SF_d
0x18007895e  jmp     loc_180078817
0x180078963  lea     rbx, WPP_GLOBAL_Control
0x18007896a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078971  cmp     rcx, rbx
0x180078974  jz      short loc_18007898B
0x180078976  mov     rcx, [rcx+10h]
0x18007897a  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180078981  mov     edx, 3Eh ; '>'
0x180078986  call    WPP_SF_
0x18007898b  lea     rax, [rbp+190h+pvFindPara]
0x18007898f  mov     [rsp+290h+pPrevChainContext], r15; pPrevChainContext
0x180078994  mov     r9d, 1; dwFindType
0x18007899a  mov     [rsp+290h+pvPara], rax; pvFindPara
0x18007899f  xor     r8d, r8d; dwFindFlags
0x1800789a2  mov     edx, 10001h; dwCertEncodingType
0x1800789a7  mov     rcx, r13; hCertStore
0x1800789aa  call    cs:__imp_CertFindChainInStore
0x1800789b1  nop     dword ptr [rax+rax+00h]
0x1800789b6  mov     [rbp+190h+pChainContext], rax
0x1800789ba  mov     r15, rax
0x1800789bd  test    rax, rax
0x1800789c0  jz      loc_180078BB0
0x1800789c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800789cd  cmp     rcx, rbx
0x1800789d0  jz      short loc_1800789E7
0x1800789d2  mov     rcx, [rcx+10h]
0x1800789d6  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800789dd  mov     edx, 40h ; '@'
0x1800789e2  call    WPP_SF_
0x1800789e7  mov     rax, [r15+10h]
0x1800789eb  mov     rcx, [rax]
0x1800789ee  mov     rax, [rcx+10h]
0x1800789f2  mov     rcx, [rax]
0x1800789f5  mov     rbx, [rcx+8]
0x1800789f9  mov     rcx, rbx; struct _CERT_CONTEXT *
0x1800789fc  call    ?FCheckTimeValidity@@YAHPEBU_CERT_CONTEXT@@@Z; FCheckTimeValidity(_CERT_CONTEXT const *)
0x180078a01  test    eax, eax
0x180078a03  jnz     short loc_180078A34
0x180078a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a0c  lea     rbx, WPP_GLOBAL_Control
0x180078a13  cmp     rcx, rbx
0x180078a16  jz      loc_18007898B
0x180078a1c  mov     rcx, [rcx+10h]
0x180078a20  lea     edx, [rax+41h]
0x180078a23  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180078a2a  call    WPP_SF_
0x180078a2f  jmp     loc_18007896A
0x180078a34  mov     rcx, rbx; pCertContext
0x180078a37  call    ?IsCertNGC@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertNGC(_CERT_CONTEXT const *)
0x180078a3c  mov     ecx, 1
0x180078a41  cmp     eax, ecx
0x180078a43  jnz     loc_180078963
0x180078a49  mov     rax, [rbp+190h+var_1A0]
0x180078a4d  test    edi, edi
0x180078a4f  mov     rdx, rbx; pCertContext
0x180078a52  cmovz   edi, ecx
0x180078a55  xor     r9d, r9d; int
0x180078a58  mov     [rsp+290h+var_228], edi
0x180078a5c  mov     r8d, [rax+8]
0x180078a60  lea     rax, [rsp+290h+var_248]
0x180078a65  shr     r8d, 0Ah
0x180078a69  not     r8d
0x180078a6c  mov     [rsp+290h+pvPara], rax; unsigned int *
0x180078a71  and     r8d, ecx; int
0x180078a74  mov     rcx, rsi; hCertStore
0x180078a77  call    ?AddCertificateToStore@@YAHPEAXPEBU_CERT_CONTEXT@@HHPEAK@Z; AddCertificateToStore(void *,_CERT_CONTEXT const *,int,int,ulong *)
0x180078a7c  test    eax, eax
0x180078a7e  jz      loc_180078963
0x180078a84  mov     rcx, rbx; pCertContext
0x180078a87  call    cs:__imp_CertDuplicateCertificateContext
0x180078a8e  nop     dword ptr [rax+rax+00h]
0x180078a93  mov     r12, rax
0x180078a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a9d  lea     rax, WPP_GLOBAL_Control
0x180078aa4  cmp     rcx, rax
0x180078aa7  jz      short loc_180078ABE
0x180078aa9  mov     rcx, [rcx+10h]
0x180078aad  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180078ab4  mov     edx, 42h ; 'B'
0x180078ab9  call    WPP_SF_
0x180078abe  xor     r15d, r15d
0x180078ac1  mov     esi, [rsp+290h+var_248]
0x180078ac5  mov     r13, r15
0x180078ac8  lea     r9, [rsp+290h+hContext]; phContext
0x180078acd  xor     r8d, r8d; pvReserved2
0x180078ad0  xor     edx, edx; pvReserved1
0x180078ad2  xor     ecx, ecx; dwScope
0x180078ad4  call    cs:__imp_SCardEstablishContext
0x180078adb  nop     dword ptr [rax+rax+00h]
0x180078ae0  mov     ebx, eax
0x180078ae2  test    eax, eax
0x180078ae4  jnz     loc_180078BA1
0x180078aea  mov     rcx, [rsp+290h+hContext]; hContext
0x180078aef  lea     r9, [rbp+190h+pcchReaders]; pcchReaders
0x180078af3  lea     r8, [rbp+190h+pvMem]; mszReaders
0x180078af7  xor     edx, edx; mszGroups
0x180078af9  call    cs:__imp_SCardListReadersW
0x180078b00  nop     dword ptr [rax+rax+00h]
0x180078b05  mov     ebx, eax
0x180078b07  test    eax, eax
0x180078b09  jnz     loc_180078BA1
0x180078b0f  mov     rax, [rbp+190h+pvMem]
0x180078b13  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180078b17  mov     edi, r15d
0x180078b1a  mov     [rbp+190h+var_1F4], r15d
0x180078b1e  cmp     [rax], r15w
0x180078b22  jz      short loc_180078B44
0x180078b24  inc     edi
0x180078b26  mov     rcx, rbx
0x180078b29  inc     rcx
0x180078b2c  cmp     [rax+rcx*2], r15w
0x180078b31  jnz     short loc_180078B29
0x180078b33  lea     rax, [rax+rcx*2]
  ... truncated ...
```
