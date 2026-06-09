# LPA::Lpd::DownloadInstance::ValidateServerCertificate(void * const,void *)

- ea: `0x1800b8840`
- end: `0x1800b9266`
- name: `?ValidateServerCertificate@DownloadInstance@Lpd@LPA@@CAJQEAXPEAX@Z`
- size: `2598`
- prototype: `__int64 __fastcall(HINTERNET hInternet, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800010f0`
- `0x1800017c8`
- `0x18000ebd0`
- `0x18006ba8c`
- `0x1800709e4`
- `0x180071994`
- `0x1800a2ddc`
- `0x1800a7f30`
- `0x1800adc0c`
- `0x1800b8840`
- `0x1800b926c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b912e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b912e`
- `CRYPT32!CertFindExtension` at `0x1800b909c`
- `CRYPT32!CertFindExtension` at `0x1800b909c`
- `CRYPT32!CertOpenStore` at `0x1800b8939`
- `CRYPT32!CertOpenStore` at `0x1800b89a7`
- `CRYPT32!CertOpenStore` at `0x1800b8a0e`
- `CRYPT32!CertOpenStore` at `0x1800b8f18`
- `CRYPT32!CertOpenStore` at `0x1800b8f69`
- `CRYPT32!CertOpenStore` at `0x1800b8939`
- `CRYPT32!CertOpenStore` at `0x1800b89a7`
- `CRYPT32!CertOpenStore` at `0x1800b8a0e`
- `CRYPT32!CertOpenStore` at `0x1800b8f18`
- `CRYPT32!CertOpenStore` at `0x1800b8f69`
- `CRYPT32!CertAddStoreToCollection` at `0x1800b8a45`
- `CRYPT32!CertAddStoreToCollection` at `0x1800b8a61`
- `CRYPT32!CertAddStoreToCollection` at `0x1800b8a82`
- `CRYPT32!CertAddStoreToCollection` at `0x1800b8a45`
- `CRYPT32!CertAddStoreToCollection` at `0x1800b8a61`
- `CRYPT32!CertAddStoreToCollection` at `0x1800b8a82`
- `CRYPT32!CertFreeCertificateChain` at `0x1800b91eb`
- `CRYPT32!CertFreeCertificateChain` at `0x1800b91eb`
- `CRYPT32!CertCloseStore` at `0x1800b9034`
- `CRYPT32!CertCloseStore` at `0x1800b9044`
- `CRYPT32!CertCloseStore` at `0x1800b91ae`
- `CRYPT32!CertCloseStore` at `0x1800b91be`
- `CRYPT32!CertCloseStore` at `0x1800b91ce`
- `CRYPT32!CertCloseStore` at `0x1800b9034`
- `CRYPT32!CertCloseStore` at `0x1800b9044`
- `CRYPT32!CertCloseStore` at `0x1800b91ae`
- `CRYPT32!CertCloseStore` at `0x1800b91be`
- `CRYPT32!CertCloseStore` at `0x1800b91ce`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b8fa3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b91fe`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b8fa3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b91fe`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8ebd`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8eef`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8f44`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8f95`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8ebd`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8eef`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8f44`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b8f95`
- `CRYPT32!CertGetCertificateChain` at `0x1800b8adb`
- `CRYPT32!CertGetCertificateChain` at `0x1800b8adb`
- `CRYPT32!CryptHashCertificate` at `0x1800b8e21`
- `CRYPT32!CryptHashCertificate` at `0x1800b8e6a`
- `CRYPT32!CryptHashCertificate` at `0x1800b8e21`
- `CRYPT32!CryptHashCertificate` at `0x1800b8e6a`
- `CRYPT32!CertVerifyTimeValidity` at `0x1800b8bd8`
- `CRYPT32!CertVerifyTimeValidity` at `0x1800b8bd8`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x1800b8b50`
- `CRYPT32!CryptVerifyCertificateSignatureEx` at `0x1800b8b50`
- `WINHTTP!WinHttpQueryOption` at `0x1800b88f4`
- `WINHTTP!WinHttpQueryOption` at `0x1800b88f4`

## string_xrefs

- `0x1800b8873`: `LpaServiceLpd`
- `0x1800b89cf`: `LpaServiceLpd`
- `0x1800b8b81`: `LpaServiceLpd`
- `0x1800b8c09`: `LpaServiceLpd`
- `0x1800b8d2e`: `LpaServiceLpd`
- `0x1800b8fff`: `LpaServiceLpd`
- `0x1800b9175`: `LpaServiceLpd`
- `0x1800b91d4`: `LpaServiceLpd`

## pseudocode

```c
__int64 __fastcall LPA::Lpd::DownloadInstance::ValidateServerCertificate(
        HINTERNET hInternet,
        _BYTE *a2,
        int a3,
        DWORD a4)
{
  void *v5; // rbx
  signed int LastErrorToHResultAndForceFailure; // esi
  char v7; // r14
  CommonUtil *v8; // rcx
  void *v9; // rbx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  HCERTSTORE v13; // r12
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  CommonUtil *v17; // rcx
  HCERTSTORE v18; // r15
  HCERTSTORE v19; // rdx
  CommonUtil *v20; // rcx
  DWORD v21; // ebx
  CommonUtil *v22; // rcx
  int v23; // ecx
  CommonUtil *v24; // rcx
  int v25; // ecx
  PCERT_SIMPLE_CHAIN *rgpChain; // rax
  PCERT_SIMPLE_CHAIN v27; // r15
  signed int dwErrorStatus; // eax
  int v29; // ecx
  DWORD *p_cElement; // rbx
  int v31; // eax
  PCERT_CHAIN_ELEMENT v32; // rdx
  _DWORD *p_cbSize; // rcx
  PCCERT_CONTEXT pCertContext; // rax
  int v35; // eax
  PCERT_CHAIN_ELEMENT *rgpElement; // rax
  PCCERT_CONTEXT v37; // rdi
  CommonUtil *v38; // rcx
  BYTE *v39; // rbx
  CommonUtil *v40; // rcx
  HCERTSTORE v41; // rdi
  HCERTSTORE v42; // r14
  const CERT_CONTEXT *CertificateInStore; // rax
  int v44; // r8d
  int v45; // r9d
  int v46; // ecx
  _DWORD *v47; // rax
  PCERT_CHAIN_ELEMENT *v48; // rax
  unsigned int v49; // ecx
  PCCERT_CONTEXT v50; // rax
  PCERT_EXTENSION Extension; // rax
  int v52; // ecx
  char v53; // r15
  const void **v54; // r14
  _QWORD *v55; // rdi
  _QWORD *i; // rbx
  const void *v57; // rcx
  size_t v58; // r8
  HCERTSTORE hCertStore; // [rsp+40h] [rbp-39h]
  BYTE *pbComputedHash; // [rsp+48h] [rbp-31h] BYREF
  const char *v62; // [rsp+50h] [rbp-29h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+58h] [rbp-21h] BYREF
  CERT_CONTEXT *Buffer; // [rsp+60h] [rbp-19h] BYREF
  const char *v65; // [rsp+68h] [rbp-11h] BYREF
  const char *v66; // [rsp+70h] [rbp-9h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+78h] [rbp-1h] BYREF
  HCERTSTORE v68; // [rsp+98h] [rbp+1Fh]
  const char *v69; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v70; // [rsp+F0h] [rbp+77h] BYREF
  const char *dwBufferLength; // [rsp+F8h] [rbp+7Fh] BYREF

  Buffer = 0;
  pChainContext = 0;
  v5 = hInternet;
  if ( !a2 )
  {
    LastErrorToHResultAndForceFailure = -2147418113;
    goto LABEL_141;
  }
  if ( a2[120] )
  {
    LastErrorToHResultAndForceFailure = -2147467260;
LABEL_141:
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v69) = LastErrorToHResultAndForceFailure;
      v70 = "LPA::Lpd::DownloadInstance::ValidateServerCertificate";
      dwBufferLength = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)hInternet,
        (unsigned int)&word_1801322D6,
        a3,
        a4,
        (__int64)&dwBufferLength,
        (__int64)&v70,
        (__int64)&v69);
    }
    return (unsigned int)LastErrorToHResultAndForceFailure;
  }
  v7 = 1;
  LOBYTE(v69) = LPA::Lpd::DownloadInstance::m_fEnableLpaV3Support;
  LOBYTE(v70) = 1;
  std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a2 + 32, &pChainPara);
  if ( *(_QWORD *)&pChainPara.cbSize )
  {
    v7 = *(_BYTE *)(*(_QWORD *)&pChainPara.cbSize + 137LL);
    LOBYTE(v70) = *(_BYTE *)(*(_QWORD *)&pChainPara.cbSize + 136LL);
  }
  if ( *(_QWORD *)&pChainPara.RequestedUsage.dwType )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&pChainPara.RequestedUsage.dwType);
  LODWORD(dwBufferLength) = 8;
  if ( WinHttpQueryOption(v5, 0x4Eu, &Buffer, (LPDWORD)&dwBufferLength) )
  {
    LastErrorToHResultAndForceFailure = 0;
    a2[1043] = 0;
  }
  else
  {
    a2[1043] = 1;
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v8);
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_136;
  }
  hCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"eSIM Certification Authorities");
  v9 = hCertStore;
  if ( !hCertStore && (unsigned int)CallbackContext > 3 )
  {
    LODWORD(dwBufferLength) = CommonUtil::GetLastErrorToHResultAndForceFailure((CommonUtil *)(unsigned int)CallbackContext);
    pbComputedHash = (BYTE *)"LPA::Lpd::DownloadInstance::ValidateServerCertificate";
    v62 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)byte_180132505,
      v11,
      v12,
      (__int64)&v62,
      (__int64)&pbComputedHash,
      (__int64)&dwBufferLength);
  }
  v13 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"OemEsim");
  if ( !v13 && (unsigned int)CallbackContext > 3 )
  {
    LODWORD(dwBufferLength) = CommonUtil::GetLastErrorToHResultAndForceFailure((CommonUtil *)(unsigned int)CallbackContext);
    v62 = "LPA::Lpd::DownloadInstance::ValidateServerCertificate";
    pbComputedHash = (BYTE *)"LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v14,
      (unsigned int)&byte_1801324BF,
      v15,
      v16,
      (__int64)&pbComputedHash,
      (__int64)&v62,
      (__int64)&dwBufferLength);
  }
  v68 = CertOpenStore((LPCSTR)0xB, 0, 0, 0, 0);
  v18 = v68;
  if ( v68
    || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v17),
        LastErrorToHResultAndForceFailure >= 0) )
  {
    if ( hCertStore && !CertAddStoreToCollection(v18, hCertStore, 0, 0) )
      LastErrorToHResultAndForceFailure = -2147418113;
    if ( v13 && !CertAddStoreToCollection(v18, v13, 0, 0) )
      LastErrorToHResultAndForceFailure = -2147418113;
    v19 = Buffer->hCertStore;
    if ( v19 && !CertAddStoreToCollection(v18, v19, 0, 0) )
      LastErrorToHResultAndForceFailure = -2147418113;
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_130;
    memset(&pChainPara, 0, sizeof(pChainPara));
    pChainPara.cbSize = 32;
    if ( !CertGetCertificateChain((HCERTCHAINENGINE)1, Buffer, 0, v18, &pChainPara, 0x20000000u, 0, &pChainContext) )
    {
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v20);
      if ( LastErrorToHResultAndForceFailure < 0 )
        goto LABEL_130;
    }
    v21 = 1;
    if ( (*pChainContext->rgpChain)->cElement > 1 )
    {
      do
      {
        if ( CryptVerifyCertificateSignatureEx(
               0,
               1u,
               2u,
               Buffer,
               2u,
               (void *)(*pChainContext->rgpChain)->rgpElement[v21]->pCertContext,
               0,
               0) )
        {
          LastErrorToHResultAndForceFailure = 0;
          goto LABEL_41;
        }
        LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v22);
        if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(dwBufferLength) = LastErrorToHResultAndForceFailure;
          v62 = "LPA::Lpd::DownloadInstance::ValidateServerCertificate";
          pbComputedHash = (BYTE *)"LpaServiceLpd";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)word_180132482,
            a3,
            a4,
            (__int64)&pbComputedHash,
            (__int64)&v62,
            (__int64)&dwBufferLength);
        }
        ++v21;
      }
      while ( v21 < (*pChainContext->rgpChain)->cElement );
      if ( LastErrorToHResultAndForceFailure < 0 )
        goto LABEL_129;
    }
LABEL_41:
    if ( !CertVerifyTimeValidity(0, Buffer->pCertInfo) )
      goto LABEL_146;
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v24);
    if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(dwBufferLength) = LastErrorToHResultAndForceFailure;
      v62 = "LPA::Lpd::DownloadInstance::ValidateServerCertificate";
      pbComputedHash = (BYTE *)"LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v25,
        (unsigned int)&dword_180132444,
        a3,
        a4,
        (__int64)&pbComputedHash,
        (__int64)&v62,
        (__int64)&dwBufferLength);
    }
    if ( LastErrorToHResultAndForceFailure >= 0 )
    {
LABEL_146:
      if ( pChainContext->cbSize < 0x48 )
        goto LABEL_128;
      if ( pChainContext->cChain != 1 )
        goto LABEL_128;
      rgpChain = pChainContext->rgpChain;
      if ( !rgpChain )
        goto LABEL_128;
      v27 = *rgpChain;
      if ( !*rgpChain )
        goto LABEL_128;
      dwErrorStatus = pChainContext->TrustStatus.dwErrorStatus;
      v29 = 67108869;
      if ( (dwErrorStatus & 0x4000005) != 0 )
      {
        LastErrorToHResultAndForceFailure = dwErrorStatus > 0
                                          ? (unsigned __int16)dwErrorStatus | 0x80070000
                                          : pChainContext->TrustStatus.dwErrorStatus;
        v27 = 0;
        if ( LastErrorToHResultAndForceFailure < 0 )
          goto LABEL_129;
      }
      if ( v27->cbSize < 0x28 || (p_cElement = &v27->cElement, !v27->cElement) )
      {
LABEL_128:
        LastErrorToHResultAndForceFailure = -2147418113;
        goto LABEL_129;
      }
      v31 = v27->TrustStatus.dwErrorStatus;
      if ( (v31 & 0x4000005) == 0
        || (v31 > 0
          ? (LastErrorToHResultAndForceFailure = (unsigned __int16)v31 | 0x80070000)
          : (LastErrorToHResultAndForceFailure = v27->TrustStatus.dwErrorStatus),
            LastErrorToHResultAndForceFailure >= 0) )
      {
        if ( !v7
          || (_BYTE)v69
          || (LastErrorToHResultAndForceFailure = LPA::Lpd::DownloadInstance::ValidateServerCertificateExtensions((*v27->rgpElement)->pCertContext->pCertInfo),
              LastErrorToHResultAndForceFailure >= 0) )
        {
          if ( *p_cElement <= 1 )
          {
            LastErrorToHResultAndForceFailure = -2147418113;
            if ( (unsigned int)CallbackContext > 2 )
            {
              v69 = "Certificate chain length";
              v70 = "LPA::Lpd::DownloadInstance::ValidateServerCertificate";
              dwBufferLength = "LpaServiceLpd";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v29,
                (unsigned int)byte_1801323E5,
                a3,
                a4,
                (__int64)&dwBufferLength,
                (__int64)&v70,
                (__int64)&v69);
            }
            goto LABEL_129;
          }
          a4 = *p_cElement;
          if ( *p_cElement )
          {
            a3 = 0;
            while ( 1 )
            {
              if ( LastErrorToHResultAndForceFailure < 0 )
                goto LABEL_129;
              v32 = v27->rgpElement[a3];
              if ( !v32
                || v32->cbSize < 0x38
                || (p_cbSize = &v32->pRevocationInfo->cbSize) == 0
                || *p_cbSize < 0x28u
                || (pCertContext = v32->pCertContext) == 0
                || !pCertContext->pCertInfo )
              {
                LastErrorToHResultAndForceFailure = -2147418113;
                goto LABEL_85;
              }
              v35 = v32->TrustStatus.dwErrorStatus;
              if ( (v35 & 0x4000005) == 0 )
                break;
              if ( v35 > 0 )
              {
                LastErrorToHResultAndForceFailure = (unsigned __int16)v35;
LABEL_83:
                LastErrorToHResultAndForceFailure |= 0x80070000;
                goto LABEL_85;
              }
              LastErrorToHResultAndForceFailure = v32->TrustStatus.dwErrorStatus;
LABEL_85:
              if ( ++a3 >= a4 )
                goto LABEL_86;
            }
            if ( p_cbSize[1] != 4 )
              goto LABEL_85;
            LastErrorToHResultAndForceFailure = (*pChainContext->rgpChain)->TrustStatus.dwErrorStatus;
            if ( LastErrorToHResultAndForceFailure <= 0 )
              goto LABEL_85;
            LastErrorToHResultAndForceFailure = (unsigned __int16)LastErrorToHResultAndForceFailure;
            goto LABEL_83;
          }
LABEL_86:
          if ( LastErrorToHResultAndForceFailure >= 0 )
          {
            rgpElement = v27->rgpElement;
            LODWORD(dwBufferLength) = 0;
            v37 = rgpElement[a4 - 1]->pCertContext;
            if ( CryptHashCertificate(0, 0, 0, v37->pbCertEncoded, v37->cbCertEncoded, 0, (DWORD *)&dwBufferLength)
              || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v38),
                  LastErrorToHResultAndForceFailure >= 0) )
            {
              std::make_unique<unsigned char [0],0>(&pbComputedHash, (unsigned int)dwBufferLength);
              v39 = pbComputedHash;
              if ( CryptHashCertificate(
                     0,
                     0,
                     0,
                     v37->pbCertEncoded,
                     v37->cbCertEncoded,
                     pbComputedHash,
                     (DWORD *)&dwBufferLength)
                || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v40),
                    LastErrorToHResultAndForceFailure >= 0) )
              {
                v41 = 0;
                v42 = 0;
                pChainPara.cbSize = (unsigned int)dwBufferLength;
                *(_QWORD *)&pChainPara.RequestedUsage.dwType = v39;
                *(&pChainPara.cbSize + 1) = 0;
                if ( hCertStore
                  && (CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, &pChainPara, 0)) != 0
                  || v13
                  && (CertificateInStore = CertFindCertificateInStore(v13, 0x10001u, 0, 0x10000u, &pChainPara, 0)) != 0
                  || (v41 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"ROOT")) != 0
                  && (CertificateInStore = CertFindCertificateInStore(v41, 0x10001u, 0, 0x10000u, &pChainPara, 0)) != 0
                  || (v42 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"CA")) != 0
                  && (CertificateInStore = CertFindCertificateInStore(v42, 0x10001u, 0, 0x10000u, &pChainPara, 0)) != 0 )
                {
                  CertFreeCertificateContext(CertificateInStore);
                }
                else
                {
                  v46 = *((_DWORD *)a2 + 256);
                  v47 = a2 + 1028;
                  LastErrorToHResultAndForceFailure = -2147023728;
                  if ( (v46 & 1) == 0 || !*v47 )
                  {
                    v46 |= 1u;
                    *v47 = 22;
                    *((_DWORD *)a2 + 256) = v46;
                  }
                  if ( (unsigned int)CallbackContext > 2 )
                  {
                    v62 = "Certificate issuer not in store";
                    v65 = "LPA::Lpd::DownloadInstance::ValidateServerCertificate";
                    v66 = "LpaServiceLpd";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      v46,
                      (unsigned int)&byte_18013237F,
                      v44,
                      v45,
                      (__int64)&v66,
                      (__int64)&v65,
                      (__int64)&v62);
                  }
                }
                if ( v41 )
                  CertCloseStore(v41, 0);
                if ( v42 )
                  CertCloseStore(v42, 0);
              }
              std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&pbComputedHash);
              if ( LastErrorToHResultAndForceFailure >= 0 && !(_BYTE)v69 )
              {
                v48 = v27->rgpElement;
                v49 = v27->cElement - 1;
                dwBufferLength = 0;
                LODWORD(v69) = 0;
                v50 = v48[v49]->pCertContext;
                Extension = CertFindExtension("2.5.29.14", v50->pCertInfo->cExtension, v50->pCertInfo->rgExtension);
                if ( Extension )
                {
                  LastErrorToHResultAndForceFailure = LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(
                                                        (LPCSTR)0x19,
                                                        Extension->Value.pbData,
                                                        Extension->Value.cbData,
                                                        0x8001u,
                                                        (void **)&dwBufferLength,
                                                        (unsigned int *)&v69);
                  if ( LastErrorToHResultAndForceFailure >= 0 )
                  {
                    v53 = 0;
                    v54 = (const void **)dwBufferLength;
                    if ( *((_QWORD *)a2 + 105) )
                    {
                      v55 = (_QWORD *)*((_QWORD *)a2 + 104);
                      for ( i = (_QWORD *)*v55; i != v55; i = (_QWORD *)*i )
                      {
                        v57 = (const void *)i[2];
                        v58 = *(unsigned int *)v54;
                        if ( i[3] - (_QWORD)v57 == v58 && !memcmp_0(v57, v54[1], v58) )
                        {
                          v53 = 1;
                          break;
                        }
                      }
                    }
                    LocalFree(v54);
                    dwBufferLength = 0;
                    if ( v53 )
                      goto LABEL_129;
                  }
                }
                else
                {
                  LastErrorToHResultAndForceFailure = -2147023728;
                }
                if ( (_BYTE)v70 )
                {
                  if ( LastErrorToHResultAndForceFailure >= 0 )
                    goto LABEL_129;
                }
                else
                {
                  LastErrorToHResultAndForceFailure = -2147467259;
                }
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v70 = "2.5.29.14";
                  v66 = "LPA::Lpd::DownloadInstance::ValidateServerCertificate";
                  v65 = "LpaServiceLpd";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v52,
                    (unsigned int)&word_18013231E,
                    a3,
                    a4,
                    (__int64)&v65,
                    (__int64)&v66,
                    (__int64)&v70);
                }
              }
            }
          }
        }
      }
    }
LABEL_129:
    v9 = hCertStore;
LABEL_130:
    if ( v68 )
      CertCloseStore(v68, 0);
  }
  if ( v13 )
    CertCloseStore(v13, 0);
  if ( v9 )
    CertCloseStore(v9, 0);
LABEL_136:
  if ( pChainContext )
  {
    CertFreeCertificateChain(pChainContext);
    pChainContext = 0;
  }
  LODWORD(hInternet) = (_DWORD)Buffer;
  if ( Buffer )
  {
    CertFreeCertificateContext(Buffer);
    Buffer = 0;
  }
  if ( LastErrorToHResultAndForceFailure < 0 )
    goto LABEL_141;
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800b8840  mov     [rsp-8+arg_0], rbx
0x1800b8845  push    rbp
0x1800b8846  push    rsi
0x1800b8847  push    rdi
0x1800b8848  push    r12
0x1800b884a  push    r13
0x1800b884c  push    r14
0x1800b884e  push    r15
0x1800b8850  lea     rbp, [rsp-27h]
0x1800b8855  sub     rsp, 0A0h
0x1800b885c  xor     edi, edi
0x1800b885e  lea     r15, aLpaLpdDownload_3; "LPA::Lpd::DownloadInstance::ValidateSer"...
0x1800b8865  mov     [rbp+57h+Buffer], rdi
0x1800b8869  mov     r13, rdx
0x1800b886c  mov     [rbp+57h+pChainContext], rdi
0x1800b8870  mov     rbx, rcx
0x1800b8873  lea     r12, aLpaservicelpd; "LpaServiceLpd"
0x1800b887a  test    rdx, rdx
0x1800b887d  jnz     short loc_1800B8889
0x1800b887f  mov     esi, 8000FFFFh
0x1800b8884  jmp     loc_1800B920C
0x1800b8889  cmp     [rdx+78h], dil
0x1800b888d  jz      short loc_1800B8899
0x1800b888f  mov     esi, 80004004h
0x1800b8894  jmp     loc_1800B920C
0x1800b8899  mov     al, cs:?m_fEnableLpaV3Support@DownloadInstance@Lpd@LPA@@0_NA; bool LPA::Lpd::DownloadInstance::m_fEnableLpaV3Support
0x1800b889f  lea     rcx, [rdx+20h]
0x1800b88a3  mov     r14b, 1
0x1800b88a6  mov     byte ptr [rbp+57h+arg_8], al
0x1800b88a9  lea     rdx, [rbp+57h+pChainPara]
0x1800b88ad  mov     byte ptr [rbp+57h+arg_10], r14b
0x1800b88b1  call    ?lock@?$weak_ptr@VDownloadInstance@Lpd@LPA@@@std@@QEBA?AV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@2@XZ; std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(void)
0x1800b88b6  mov     rax, qword ptr [rbp+57h+pChainPara.cbSize]
0x1800b88ba  test    rax, rax
0x1800b88bd  jz      short loc_1800B88CF
0x1800b88bf  mov     r14b, [rax+89h]
0x1800b88c6  mov     al, [rax+88h]
0x1800b88cc  mov     byte ptr [rbp+57h+arg_10], al
0x1800b88cf  mov     rcx, qword ptr [rbp+57h+pChainPara.RequestedUsage.dwType]; this
0x1800b88d3  test    rcx, rcx
0x1800b88d6  jz      short loc_1800B88DD
0x1800b88d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b88dd  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800b88e1  mov     dword ptr [rbp+57h+dwBufferLength], 8
0x1800b88e8  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800b88ec  mov     edx, 4Eh ; 'N'; dwOption
0x1800b88f1  mov     rcx, rbx; hInternet
0x1800b88f4  call    cs:__imp_WinHttpQueryOption
0x1800b88fa  test    eax, eax
0x1800b88fc  jnz     short loc_1800B8916
0x1800b88fe  mov     byte ptr [r13+413h], 1
0x1800b8906  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b890b  mov     esi, eax
0x1800b890d  test    eax, eax
0x1800b890f  jns     short loc_1800B891F
0x1800b8911  jmp     loc_1800B91E2
0x1800b8916  mov     esi, edi
0x1800b8918  mov     [r13+413h], dil
0x1800b891f  xor     edx, edx; dwEncodingType
0x1800b8921  lea     rax, aEsimCertificat; "eSIM Certification Authorities"
0x1800b8928  mov     r9d, 28000h; dwFlags
0x1800b892e  mov     [rsp+0D0h+pvPara], rax; pvPara
0x1800b8933  xor     r8d, r8d; hCryptProv
0x1800b8936  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800b8939  call    cs:__imp_CertOpenStore
0x1800b893f  mov     [rbp+57h+hCertStore], rax
0x1800b8943  mov     rbx, rax
0x1800b8946  test    rax, rax
0x1800b8949  jnz     short loc_1800B898D
0x1800b894b  mov     ecx, cs:CallbackContext; this
0x1800b8951  cmp     ecx, 3
0x1800b8954  jbe     short loc_1800B898D
0x1800b8956  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b895b  mov     dword ptr [rbp+57h+dwBufferLength], eax
0x1800b895e  lea     rdx, byte_180132505
0x1800b8965  lea     rax, [rbp+57h+dwBufferLength]
0x1800b8969  mov     [rbp+57h+pbComputedHash], r15
0x1800b896d  mov     [rsp+0D0h+pvReserved], rax
0x1800b8972  lea     rax, [rbp+57h+pbComputedHash]
0x1800b8976  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800b897b  lea     rax, [rbp+57h+var_80]
0x1800b897f  mov     [rsp+0D0h+pvPara], rax
0x1800b8984  mov     [rbp+57h+var_80], r12
0x1800b8988  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b898d  xor     edx, edx; dwEncodingType
0x1800b898f  lea     rax, aOemesim; "OemEsim"
0x1800b8996  mov     r9d, 28000h; dwFlags
0x1800b899c  mov     [rsp+0D0h+pvPara], rax; pvPara
0x1800b89a1  xor     r8d, r8d; hCryptProv
0x1800b89a4  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800b89a7  call    cs:__imp_CertOpenStore
0x1800b89ad  mov     r12, rax
0x1800b89b0  test    rax, rax
0x1800b89b3  jnz     short loc_1800B89FE
0x1800b89b5  mov     ecx, cs:CallbackContext; this
0x1800b89bb  cmp     ecx, 3
0x1800b89be  jbe     short loc_1800B89FE
0x1800b89c0  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b89c5  mov     dword ptr [rbp+57h+dwBufferLength], eax
0x1800b89c8  lea     rdx, byte_1801324BF
0x1800b89cf  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b89d6  mov     [rbp+57h+var_80], r15
0x1800b89da  mov     [rbp+57h+pbComputedHash], rax
0x1800b89de  lea     rax, [rbp+57h+dwBufferLength]
0x1800b89e2  mov     [rsp+0D0h+pvReserved], rax
0x1800b89e7  lea     rax, [rbp+57h+var_80]
0x1800b89eb  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800b89f0  lea     rax, [rbp+57h+pbComputedHash]
0x1800b89f4  mov     [rsp+0D0h+pvPara], rax
0x1800b89f9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b89fe  xor     edx, edx; dwEncodingType
0x1800b8a00  mov     [rsp+0D0h+pvPara], rdi; pvPara
0x1800b8a05  xor     r9d, r9d; dwFlags
0x1800b8a08  xor     r8d, r8d; hCryptProv
0x1800b8a0b  lea     ecx, [rdx+0Bh]; lpszStoreProvider
0x1800b8a0e  call    cs:__imp_CertOpenStore
0x1800b8a14  mov     [rbp+57h+var_38], rax
0x1800b8a18  mov     r15, rax
0x1800b8a1b  test    rax, rax
0x1800b8a1e  jnz     short loc_1800B8A2F
0x1800b8a20  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b8a25  mov     esi, eax
0x1800b8a27  test    eax, eax
0x1800b8a29  js      loc_1800B91B4
0x1800b8a2f  mov     edi, 8000FFFFh
0x1800b8a34  test    rbx, rbx
0x1800b8a37  jz      short loc_1800B8A50
0x1800b8a39  xor     r9d, r9d; dwPriority
0x1800b8a3c  xor     r8d, r8d; dwUpdateFlags
0x1800b8a3f  mov     rdx, rbx; hSiblingStore
0x1800b8a42  mov     rcx, r15; hCollectionStore
0x1800b8a45  call    cs:__imp_CertAddStoreToCollection
0x1800b8a4b  test    eax, eax
0x1800b8a4d  cmovz   esi, edi
0x1800b8a50  test    r12, r12
0x1800b8a53  jz      short loc_1800B8A6C
0x1800b8a55  xor     r9d, r9d; dwPriority
0x1800b8a58  xor     r8d, r8d; dwUpdateFlags
0x1800b8a5b  mov     rdx, r12; hSiblingStore
0x1800b8a5e  mov     rcx, r15; hCollectionStore
0x1800b8a61  call    cs:__imp_CertAddStoreToCollection
0x1800b8a67  test    eax, eax
0x1800b8a69  cmovz   esi, edi
0x1800b8a6c  mov     rax, [rbp+57h+Buffer]
0x1800b8a70  mov     rdx, [rax+20h]; hSiblingStore
0x1800b8a74  test    rdx, rdx
0x1800b8a77  jz      short loc_1800B8A8D
0x1800b8a79  xor     r9d, r9d; dwPriority
0x1800b8a7c  xor     r8d, r8d; dwUpdateFlags
0x1800b8a7f  mov     rcx, r15; hCollectionStore
0x1800b8a82  call    cs:__imp_CertAddStoreToCollection
0x1800b8a88  test    eax, eax
0x1800b8a8a  cmovz   esi, edi
0x1800b8a8d  test    esi, esi
0x1800b8a8f  js      loc_1800B91A1
0x1800b8a95  mov     rdx, [rbp+57h+Buffer]; pCertContext
0x1800b8a99  lea     rax, [rbp+57h+pChainContext]
0x1800b8a9d  mov     [rsp+0D0h+ppChainContext], rax; ppChainContext
0x1800b8aa2  xorps   xmm0, xmm0
0x1800b8aa5  xor     r8d, r8d; pTime
0x1800b8aa8  mov     [rsp+0D0h+pvReserved], 0; pvReserved
0x1800b8ab1  mov     r9, r15; hAdditionalStore
0x1800b8ab4  mov     [rsp+0D0h+dwFlags], 20000000h; dwFlags
0x1800b8abc  lea     rax, [rbp+57h+pChainPara]
0x1800b8ac0  movups  xmmword ptr [rbp+57h+pChainPara.cbSize], xmm0
0x1800b8ac4  lea     r15d, [r8+1]
0x1800b8ac8  mov     [rbp+57h+pChainPara.cbSize], 20h ; ' '
0x1800b8acf  mov     ecx, r15d; hChainEngine
0x1800b8ad2  mov     [rsp+0D0h+pvPara], rax; pChainPara
0x1800b8ad7  movups  xmmword ptr [rbp+57h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1800b8adb  call    cs:__imp_CertGetCertificateChain
0x1800b8ae1  test    eax, eax
0x1800b8ae3  jnz     short loc_1800B8AF4
0x1800b8ae5  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b8aea  mov     esi, eax
0x1800b8aec  test    eax, eax
0x1800b8aee  js      loc_1800B91A1
0x1800b8af4  mov     rax, [rbp+57h+pChainContext]
0x1800b8af8  mov     ebx, r15d
0x1800b8afb  mov     rcx, [rax+10h]
0x1800b8aff  mov     rax, [rcx]
0x1800b8b02  cmp     [rax+0Ch], r15d
0x1800b8b06  jbe     loc_1800B8BCE
0x1800b8b0c  mov     rax, [rbp+57h+pChainContext]
0x1800b8b10  mov     edx, r15d; dwCertEncodingType
0x1800b8b13  mov     r9, [rbp+57h+Buffer]; pvSubject
0x1800b8b17  mov     [rsp+0D0h+ppChainContext], 0; pvExtra
0x1800b8b20  mov     dword ptr [rsp+0D0h+pvReserved], 0; dwFlags
0x1800b8b28  mov     rcx, [rax+10h]
0x1800b8b2c  mov     rax, [rcx]
0x1800b8b2f  mov     ecx, ebx
0x1800b8b31  mov     rax, [rax+10h]
0x1800b8b35  mov     rax, [rax+rcx*8]
0x1800b8b39  xor     ecx, ecx; hCryptProv
0x1800b8b3b  mov     rax, [rax+8]
0x1800b8b3f  mov     qword ptr [rsp+0D0h+dwFlags], rax; pvIssuer
0x1800b8b44  mov     eax, 2
0x1800b8b49  mov     r8d, eax; dwSubjectType
0x1800b8b4c  mov     dword ptr [rsp+0D0h+pvPara], eax; dwIssuerType
0x1800b8b50  call    cs:__imp_CryptVerifyCertificateSignatureEx
0x1800b8b56  test    eax, eax
0x1800b8b58  jnz     short loc_1800B8BCC
0x1800b8b5a  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b8b5f  mov     esi, eax
0x1800b8b61  mov     eax, cs:CallbackContext
0x1800b8b67  cmp     eax, 3
0x1800b8b6a  jbe     short loc_1800B8BAC
0x1800b8b6c  lea     rax, aLpaLpdDownload_3; "LPA::Lpd::DownloadInstance::ValidateSer"...
0x1800b8b73  mov     dword ptr [rbp+57h+dwBufferLength], esi
0x1800b8b76  mov     [rbp+57h+var_80], rax
0x1800b8b7a  lea     rdx, word_180132482
0x1800b8b81  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b8b88  mov     [rbp+57h+pbComputedHash], rax
0x1800b8b8c  lea     rax, [rbp+57h+dwBufferLength]
0x1800b8b90  mov     [rsp+0D0h+pvReserved], rax
0x1800b8b95  lea     rax, [rbp+57h+var_80]
0x1800b8b99  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800b8b9e  lea     rax, [rbp+57h+pbComputedHash]
0x1800b8ba2  mov     [rsp+0D0h+pvPara], rax
0x1800b8ba7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b8bac  mov     rax, [rbp+57h+pChainContext]
0x1800b8bb0  add     ebx, r15d
0x1800b8bb3  mov     rcx, [rax+10h]
0x1800b8bb7  mov     rax, [rcx]
0x1800b8bba  cmp     ebx, [rax+0Ch]
0x1800b8bbd  jb      loc_1800B8B0C
0x1800b8bc3  test    esi, esi
0x1800b8bc5  jns     short loc_1800B8BCE
0x1800b8bc7  jmp     loc_1800B919D
0x1800b8bcc  xor     esi, esi
0x1800b8bce  mov     rdx, [rbp+57h+Buffer]
0x1800b8bd2  xor     ecx, ecx; pTimeToVerify
0x1800b8bd4  mov     rdx, [rdx+18h]; pCertInfo
0x1800b8bd8  call    cs:__imp_CertVerifyTimeValidity
0x1800b8bde  test    eax, eax
0x1800b8be0  jz      short loc_1800B8C3C
0x1800b8be2  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b8be7  mov     esi, eax
0x1800b8be9  mov     eax, cs:CallbackContext
0x1800b8bef  cmp     eax, 3
0x1800b8bf2  jbe     short loc_1800B8C34
0x1800b8bf4  lea     rax, aLpaLpdDownload_3; "LPA::Lpd::DownloadInstance::ValidateSer"...
0x1800b8bfb  mov     dword ptr [rbp+57h+dwBufferLength], esi
0x1800b8bfe  mov     [rbp+57h+var_80], rax
0x1800b8c02  lea     rdx, dword_180132444
0x1800b8c09  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b8c10  mov     [rbp+57h+pbComputedHash], rax
0x1800b8c14  lea     rax, [rbp+57h+dwBufferLength]
0x1800b8c18  mov     [rsp+0D0h+pvReserved], rax
0x1800b8c1d  lea     rax, [rbp+57h+var_80]
0x1800b8c21  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800b8c26  lea     rax, [rbp+57h+pbComputedHash]
0x1800b8c2a  mov     [rsp+0D0h+pvPara], rax
0x1800b8c2f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b8c34  test    esi, esi
0x1800b8c36  js      loc_1800B919D
0x1800b8c3c  mov     rcx, [rbp+57h+pChainContext]
0x1800b8c40  cmp     dword ptr [rcx], 48h ; 'H'
0x1800b8c43  jb      loc_1800B919B
0x1800b8c49  cmp     [rcx+0Ch], r15d
0x1800b8c4d  jnz     loc_1800B919B
0x1800b8c53  mov     rax, [rcx+10h]
0x1800b8c57  test    rax, rax
0x1800b8c5a  jz      loc_1800B919B
0x1800b8c60  mov     r15, [rax]
0x1800b8c63  test    r15, r15
0x1800b8c66  jz      loc_1800B919B
0x1800b8c6c  mov     eax, [rcx+4]
0x1800b8c6f  mov     r11d, 80070000h
0x1800b8c75  mov     ecx, 4000005h
0x1800b8c7a  test    ecx, eax
0x1800b8c7c  jz      short loc_1800B8C97
0x1800b8c7e  test    eax, eax
0x1800b8c80  jg      short loc_1800B8C86
0x1800b8c82  mov     esi, eax
0x1800b8c84  jmp     short loc_1800B8C8C
0x1800b8c86  movzx   esi, ax
0x1800b8c89  or      esi, r11d
0x1800b8c8c  xor     r15d, r15d
0x1800b8c8f  test    esi, esi
0x1800b8c91  js      loc_1800B919D
0x1800b8c97  cmp     dword ptr [r15], 28h ; '('
0x1800b8c9b  jb      loc_1800B919B
0x1800b8ca1  lea     rbx, [r15+0Ch]
0x1800b8ca5  cmp     dword ptr [rbx], 0
0x1800b8ca8  jz      loc_1800B919B
0x1800b8cae  mov     eax, [r15+4]
0x1800b8cb2  test    ecx, eax
0x1800b8cb4  jz      short loc_1800B8CCC
0x1800b8cb6  test    eax, eax
0x1800b8cb8  jg      short loc_1800B8CBE
0x1800b8cba  mov     esi, eax
0x1800b8cbc  jmp     short loc_1800B8CC4
0x1800b8cbe  movzx   esi, ax
0x1800b8cc1  or      esi, r11d
0x1800b8cc4  test    esi, esi
0x1800b8cc6  js      loc_1800B919D
0x1800b8ccc  test    r14b, r14b
0x1800b8ccf  jz      short loc_1800B8CFB
0x1800b8cd1  cmp     byte ptr [rbp+57h+arg_8], 0
  ... truncated ...
```
