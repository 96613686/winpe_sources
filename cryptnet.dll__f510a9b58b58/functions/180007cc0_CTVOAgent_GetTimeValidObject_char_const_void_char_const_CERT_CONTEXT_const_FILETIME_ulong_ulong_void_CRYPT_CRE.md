# CTVOAgent::GetTimeValidObject(char const *,void *,char const *,_CERT_CONTEXT const *,_FILETIME *,ulong,ulong,void * *,_CRYPT_CREDENTIALS *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)

- ea: `0x180007cc0`
- end: `0x180008a2a`
- name: `?GetTimeValidObject@CTVOAgent@@QEAAHPEBDPEAX0PEBU_CERT_CONTEXT@@PEAU_FILETIME@@KKPEAPEAXPEAU_CRYPT_CREDENTIALS@@PEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@@Z`
- size: `3434`
- prototype: `__int64 __fastcall(CTVOAgent *this, char *, const CERT_CONTEXT *, char *, struct _CERT_CONTEXT *, struct _FILETIME *, unsigned int, unsigned int, void **, struct _CRYPT_CREDENTIALS *, struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *Src)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180007c50`
- `0x18001e0b0`
- `0x18001e150`

## callees

- `0x180003b40`
- `0x180005f10`
- `0x180007c00`
- `0x180007cc0`
- `0x180008a30`
- `0x180008f80`
- `0x180009df0`
- `0x18000a990`
- `0x180010e80`
- `0x18001254c`
- `0x1800171e4`
- `0x180017270`
- `0x180017d7c`
- `0x180018ff8`
- `0x180019334`
- `0x1800258a4`
- `0x180026552`
- `0x1800265b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000827f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008432`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000852a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000874e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008780`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008858`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000897e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000827f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008432`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000852a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000874e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008780`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008858`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000897e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800089dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000831a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000841f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000831a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000841f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007fc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007fc7`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180008615`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x1800086b8`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180008615`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x1800086b8`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000808a`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x1800084bb`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000808a`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x1800084bb`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180008053`
- `CRYPT32!I_CryptGetLruEntryData` at `0x18000847b`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180008053`
- `CRYPT32!I_CryptGetLruEntryData` at `0x18000847b`
- `CRYPT32!I_CryptFindLruEntry` at `0x180007f22`
- `CRYPT32!I_CryptFindLruEntry` at `0x1800080e9`
- `CRYPT32!I_CryptFindLruEntry` at `0x180007f22`
- `CRYPT32!I_CryptFindLruEntry` at `0x1800080e9`
- `CRYPT32!I_CryptTouchLruEntry` at `0x180007fe9`
- `CRYPT32!I_CryptTouchLruEntry` at `0x180007fe9`
- `CRYPT32!I_CertDiagControl` at `0x180007f66`
- `CRYPT32!I_CertDiagControl` at `0x180008743`
- `CRYPT32!I_CertDiagControl` at `0x180007f66`
- `CRYPT32!I_CertDiagControl` at `0x180008743`
- `CRYPT32!CertDuplicateCTLContext` at `0x1800088d9`
- `CRYPT32!CertDuplicateCTLContext` at `0x1800088d9`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800087d2`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800087d2`
- `CRYPT32!CertDuplicateCRLContext` at `0x18000801e`
- `CRYPT32!CertDuplicateCRLContext` at `0x18000801e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180007eed`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180007eed`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x180008079`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x1800084aa`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x180008079`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x1800084aa`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180008228`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x1800082d7`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180008228`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x1800082d7`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180008277`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180008328`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180008277`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180008328`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007f9a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007fd5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008884`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000889b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007f9a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180007fd5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008884`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000889b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ebf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ebf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000838b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008775`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000838b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800086e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008775`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000842a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000842a`
- `bcrypt!BCryptHashData` at `0x180007e2e`
- `bcrypt!BCryptHashData` at `0x180007e4b`
- `bcrypt!BCryptHashData` at `0x180007e6b`
- `bcrypt!BCryptHashData` at `0x180007e2e`
- `bcrypt!BCryptHashData` at `0x180007e4b`
- `bcrypt!BCryptHashData` at `0x180007e6b`
- `bcrypt!BCryptDestroyHash` at `0x180007ea4`
- `bcrypt!BCryptDestroyHash` at `0x180007ea4`
- `bcrypt!BCryptFinishHash` at `0x180007e8d`
- `bcrypt!BCryptFinishHash` at `0x180007e8d`
- `bcrypt!BCryptCreateHash` at `0x180007e04`
- `bcrypt!BCryptCreateHash` at `0x180007e04`

## string_xrefs

- `0x180007f56`: `TvoCache`
- `0x18000870a`: `CanCheckServerForUpdatedCrl`

## pseudocode

```c
__int64 __fastcall CTVOAgent::GetTimeValidObject(
        CTVOAgent *this,
        char *a2,
        const CERT_CONTEXT *a3,
        char *a4,
        struct _CERT_CONTEXT *a5,
        struct _FILETIME *a6,
        unsigned int a7,
        unsigned int a8,
        void **a9,
        struct _CRYPT_CREDENTIALS *a10,
        struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *Src)
{
  struct _CRYPT_URL_ARRAY *v11; // r12
  struct _CERT_CONTEXT *v12; // rcx
  LPCRITICAL_SECTION v13; // r14
  char *v15; // r10
  CERT_CONTEXT *v16; // r9
  LPFILETIME pLastSyncTime; // rax
  int v18; // esi
  CERT_CONTEXT *v19; // r13
  PCERT_INFO pCertInfo; // rbx
  PCERT_INFO v21; // rdi
  NTSTATUS v22; // eax
  __int64 v23; // rbx
  unsigned int v24; // edi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  __int64 i; // rax
  __int64 v27; // rdi
  unsigned int v28; // r15d
  void **v29; // rdi
  __int64 v30; // rax
  const CERT_CONTEXT *v31; // rcx
  void *v32; // rax
  __int64 LruEntryData; // rax
  size_t cbSize; // r8
  PRTL_CRITICAL_SECTION_DEBUG v36; // rcx
  __int64 j; // rax
  __int64 v38; // rsi
  char *v39; // rsi
  int started; // eax
  char *v41; // rax
  PCCERT_CONTEXT v42; // rsi
  unsigned int OcspCrlUrlOrder; // eax
  unsigned int v44; // edi
  int v45; // esi
  DWORD LastError; // edi
  struct _CRYPT_URL_ARRAY *v47; // rdi
  LPCSTR v48; // rsi
  __int64 v49; // r8
  unsigned int TimeValidObjectByUrl; // esi
  DWORD v51; // edi
  bool v52; // zf
  int v53; // edx
  unsigned int v54; // edi
  unsigned int v55; // eax
  unsigned int v56; // ebx
  DWORD v57; // ebx
  unsigned int *v58; // rdi
  _DWORD *v59; // rax
  DWORD v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  int v63; // eax
  unsigned int k; // eax
  LPWSTR v65; // rax
  __int64 v66; // rcx
  unsigned int NextUpdateUrl; // eax
  struct _CRYPT_URL_ARRAY *v68; // rax
  DWORD v69; // ebx
  int v70; // [rsp+80h] [rbp-80h]
  int v71; // [rsp+80h] [rbp-80h]
  UCHAR pbInput[4]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v73; // [rsp+88h] [rbp-78h] BYREF
  DWORD pcbData; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v75; // [rsp+90h] [rbp-70h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+98h] [rbp-68h] BYREF
  SIZE_T uBytes; // [rsp+A0h] [rbp-60h]
  PCCERT_CONTEXT pCertContext; // [rsp+A8h] [rbp-58h]
  LPCSTR pszOID; // [rsp+B0h] [rbp-50h]
  void *ppvFuncAddr; // [rsp+B8h] [rbp-48h] BYREF
  char *v81; // [rsp+C0h] [rbp-40h]
  HCRYPTOIDFUNCADDR phFuncAddr; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v83; // [rsp+D0h] [rbp-30h]
  int v84; // [rsp+D4h] [rbp-2Ch]
  int v85; // [rsp+D8h] [rbp-28h] BYREF
  char *v86; // [rsp+E0h] [rbp-20h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v88; // [rsp+F0h] [rbp-10h]
  void **v89; // [rsp+F8h] [rbp-8h]
  FILETIME *lpFileTime1; // [rsp+100h] [rbp+0h]
  struct _CERT_CONTEXT *v91; // [rsp+108h] [rbp+8h]
  HLOCAL hMem[2]; // [rsp+110h] [rbp+10h] BYREF
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO lpFileTime2; // [rsp+120h] [rbp+20h] BYREF
  __int64 v94; // [rsp+150h] [rbp+50h] BYREF
  __int64 v95; // [rsp+158h] [rbp+58h] BYREF
  struct _CRYPT_CREDENTIALS *v96; // [rsp+160h] [rbp+60h]
  _QWORD v97[2]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v98[6]; // [rsp+178h] [rbp+78h] BYREF
  UCHAR pbOutput[16]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v100; // [rsp+1B8h] [rbp+B8h]
  _OWORD pvData[2]; // [rsp+1C8h] [rbp+C8h] BYREF

  v11 = 0;
  v12 = a5;
  v13 = g_pProcessTVOAgent;
  lpFileTime1 = a6;
  v15 = a4;
  v89 = a9;
  v81 = a2;
  v96 = a10;
  v86 = a4;
  v16 = (CERT_CONTEXT *)a3;
  v83 = 0;
  LODWORD(ppvFuncAddr) = 0;
  pCertContext = a3;
  v91 = a5;
  v85 = 0;
  v94 = 0;
  v95 = 0;
  memset(&lpFileTime2, 0, sizeof(lpFileTime2));
  if ( Src )
  {
    if ( Src->cbSize < 0x30 )
      cbSize = Src->cbSize;
    else
      cbSize = 48;
    memcpy_0(&lpFileTime2, Src, cbSize);
    v16 = (CERT_CONTEXT *)pCertContext;
    v12 = v91;
    v15 = v86;
  }
  pLastSyncTime = lpFileTime2.pLastSyncTime;
  lpFileTime2.cbSize = 48;
  if ( !lpFileTime2.pLastSyncTime )
  {
    pLastSyncTime = (LPFILETIME)&v94;
    lpFileTime2.pLastSyncTime = (LPFILETIME)&v94;
  }
  if ( !lpFileTime2.pMaxAgeTime )
    lpFileTime2.pMaxAgeTime = (LPFILETIME)&v95;
  *pLastSyncTime = 0;
  *lpFileTime2.pMaxAgeTime = 0;
  if ( a2 == (char *)3 )
  {
    v18 = 0;
    pszOID = (LPCSTR)10;
    v19 = v16;
    goto LABEL_8;
  }
  if ( a2 == (char *)4 )
  {
    pszOID = (LPCSTR)6;
    v19 = v16;
LABEL_144:
    v18 = 1;
LABEL_8:
    pCertInfo = v12->pCertInfo;
    v21 = v19->pCertInfo;
    v70 = 1;
    pbInput[0] = 0;
    phHash = 0;
    v22 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
    if ( v22 )
      goto LABEL_91;
    if ( v18 )
      LOBYTE(v22) = 1;
    pbInput[0] = v22;
    if ( BCryptHashData(phHash, pbInput, 1u, 0)
      || BCryptHashData(phHash, v21->Issuer.pbData, v21->Issuer.cbData, 0)
      || BCryptHashData(
           phHash,
           pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
           pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
           0)
      || BCryptFinishHash(phHash, pbOutput, 0x20u, 0) )
    {
LABEL_91:
      *(_OWORD *)pbOutput = 0;
      v100 = 0;
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
    goto LABEL_17;
  }
  if ( a2 == (char *)5 )
  {
    v19 = *(CERT_CONTEXT **)&v16->dwCertEncodingType;
    pszOID = (LPCSTR)7;
    goto LABEL_144;
  }
  v70 = 0;
  pszOID = 0;
  v19 = 0;
  if ( !ObjectContextGetOriginIdentifier(v15, v16, v12, (unsigned int)v16, pbOutput) )
    return 0;
LABEL_17:
  v75 = 0;
  v23 = 0;
  v73 = 0;
  v24 = 0;
  phFuncAddr = 0;
  EnterCriticalSection(v13);
  ++LODWORD(v13[1].LockSemaphore);
  if ( a2 == (char *)3 )
  {
    pcbData = 32;
    if ( CertGetCertificateContextProperty(v19, 0x6Bu, pvData, &pcbData) )
    {
      if ( pcbData == 32 )
      {
        DebugInfo = v13[1].DebugInfo;
        hMem[1] = pvData;
        hMem[0] = (HLOCAL)32;
        for ( i = I_CryptFindLruEntry(DebugInfo, hMem); ; i = I_CryptEnumMatchingLruEntries(v27) )
        {
          v27 = i;
          v23 = 0;
          if ( !i )
            break;
          LruEntryData = I_CryptGetLruEntryData(i);
          v23 = LruEntryData;
          if ( *(_QWORD *)(LruEntryData + 32) == 2
            && (!v19 || CertIsValidCRLForCertificate(v19, *(PCCRL_CONTEXT *)(LruEntryData + 40), 0, 0)) )
          {
            I_CryptReleaseLruEntry(v27);
            break;
          }
        }
        if ( v23 )
        {
          v28 = a7;
          goto LABEL_24;
        }
        v24 = v75;
      }
      else
      {
        SetLastError(0xDu);
      }
    }
  }
  else
  {
    memset(pvData, 0, sizeof(pvData));
  }
  v28 = a7;
  if ( (a7 & 0x1000000) == 0 )
  {
    v36 = v13[1].DebugInfo;
    v97[1] = pbOutput;
    v97[0] = 32;
    for ( j = I_CryptFindLruEntry(v36, v97); ; j = I_CryptEnumMatchingLruEntries(v38) )
    {
      v23 = 0;
      v38 = j;
      if ( !j )
        break;
      v23 = I_CryptGetLruEntryData(j);
      if ( v86 == *(char **)(v23 + 32)
        && (v86 != (char *)2 || !v19 || CertIsValidCRLForCertificate(v19, *(PCCRL_CONTEXT *)(v23 + 40), 0, 0)) )
      {
        I_CryptReleaseLruEntry(v38);
        break;
      }
    }
    if ( v23 )
    {
LABEL_24:
      SystemTimeAsFileTime = *(struct _FILETIME *)(v23 + 40);
      v88 = L"TvoCache";
      I_CertDiagControl(2, &SystemTimeAsFileTime, 0);
      if ( (v28 & 4) != 0 )
        goto LABEL_87;
      if ( (v28 & 0x200) == 0 )
      {
        if ( lpFileTime1 )
        {
          if ( (v28 & 0x400) != 0 )
          {
            if ( CompareFileTime(lpFileTime1, (const FILETIME *)(v23 + 84)) > 0 )
              goto LABEL_87;
          }
          else if ( CompareFileTime(lpFileTime1, (const FILETIME *)(v23 + 92)) > 0
                 && (*(_DWORD *)(v23 + 92) || *(_DWORD *)(v23 + 96)) )
          {
            goto LABEL_87;
          }
        }
        if ( lpFileTime2.pftCacheResync
          && CompareFileTime((const FILETIME *)(v23 + 100), lpFileTime2.pftCacheResync) < 0 )
        {
          if ( *(_QWORD *)(v23 + 32) == 2 )
            v66 = *(_QWORD *)(v23 + 40);
          else
            LODWORD(v66) = 0;
          CertDiagRejectCrl(v66, (unsigned int)L"IsCrlRetrievedBeforeResyncTime", 0, 0, 0, 0);
          goto LABEL_87;
        }
        if ( *(_DWORD *)(v23 + 108) || *(_DWORD *)(v23 + 112) )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)(v23 + 108)) > 0 )
          {
LABEL_87:
            if ( (v28 & 2) != 0 )
            {
LABEL_88:
              phHash = *(BCRYPT_HASH_HANDLE *)(v23 + 72);
              if ( phHash )
              {
                v59 = (_DWORD *)(v23 + 68);
                v58 = (unsigned int *)(v23 + 80);
              }
              else
              {
                v58 = (unsigned int *)(v23 + 64);
                phHash = *(BCRYPT_HASH_HANDLE *)(v23 + 56);
                v59 = (_DWORD *)(v23 + 48);
              }
              v24 = *v58;
              LODWORD(uBytes) = *v59;
              v75 = v24;
              v73 = v24;
              goto LABEL_52;
            }
            if ( (int)GetOfflineUrlTimeStatus((struct _OFFLINE_URL_TIME_INFO *)(v23 + 128)) >= 0 )
            {
              pcbData = 0;
              if ( (unsigned int)I_CryptNetGetConnectivity() )
                goto LABEL_88;
            }
            else
            {
              pcbData = 1;
            }
            if ( (v28 & 4) != 0 )
            {
              LeaveCriticalSection(v13);
              if ( *(_QWORD *)(v23 + 32) == 2 && pcbData )
              {
                v98[0] = *(_QWORD *)(v23 + 40);
                v98[2] = 0;
                v98[1] = L"CanCheckServerForUpdatedCrl";
                v98[4] = 0;
                v98[5] = 0;
                v98[3] = v23 + 132;
                I_CertDiagControl(5, v98, 0);
              }
              SetLastError(0x8CAu);
              return 0;
            }
            v28 |= 2u;
            goto LABEL_88;
          }
        }
      }
      I_CryptTouchLruEntry(*(_QWORD *)(v23 + 120), 0);
      v29 = v89;
      if ( v89 )
      {
        v30 = *(_QWORD *)(v23 + 32);
        v31 = *(const CERT_CONTEXT **)(v23 + 40);
        switch ( v30 )
        {
          case 1LL:
            v32 = (void *)CertDuplicateCertificateContext(v31);
            break;
          case 3LL:
            v32 = (void *)CertDuplicateCTLContext((PCCTL_CONTEXT)v31);
            break;
          case 2LL:
            v32 = (void *)CertDuplicateCRLContext((PCCRL_CONTEXT)v31);
            break;
          default:
            SetLastError(0x80070057);
            v32 = 0;
            break;
        }
        *v29 = v32;
      }
      *lpFileTime2.pLastSyncTime = *(struct _FILETIME *)(v23 + 100);
      *lpFileTime2.pMaxAgeTime = *(struct _FILETIME *)(v23 + 108);
      LeaveCriticalSection(v13);
      return 1;
    }
  }
  LODWORD(uBytes) = 0;
  phHash = 0;
  if ( (a7 & 2) == 0 && !(unsigned int)I_CryptNetGetConnectivity() )
  {
    if ( (a7 & 4) != 0 )
    {
      LeaveCriticalSection(v13);
      SetLastError(0x8CAu);
      return 0;
    }
    v28 = a7 | 2;
  }
LABEL_52:
  SystemTimeAsFileTime = 0;
  v39 = v81;
  started = CTVOAgent::StartActiveRetrieval(
              (CTVOAgent *)v13,
              v81,
              v86,
              v19,
              lpFileTime1,
              v28,
              v89,
              &lpFileTime2,
              pbOutput,
              (unsigned __int8 *const)pvData,
              (struct _TVO_ACTIVE_ENTRY **)&SystemTimeAsFileTime);
  if ( started != 1 )
  {
    if ( started != -1 )
    {
      if ( started )
      {
        LODWORD(uBytes) = 0;
        v75 = 0;
        v23 = 0;
        v73 = 0;
        phHash = 0;
        goto LABEL_54;
      }
      return 1;
    }
    return 0;
  }
  if ( !v23 )
  {
LABEL_54:
    LeaveCriticalSection(v13);
    v41 = 0;
    v84 = 0;
    goto LABEL_55;
  }
  v84 = 1;
  v41 = *(char **)(*((_QWORD *)phHash + 1) + 8LL * v24);
LABEL_55:
  v81 = v41;
  if ( v70 )
  {
    pcbData = 0;
    v71 = 0;
    if ( pszOID != (LPCSTR)10 )
      goto LABEL_60;
    v42 = pCertContext;
    if ( (v28 & 0x1000000) != 0 )
    {
      v71 = 1;
    }
    else
    {
      OcspCrlUrlOrder = CertificateGetOcspCrlUrlOrder(pCertContext, v28);
      v71 = OcspCrlUrlOrder;
      v44 = OcspCrlUrlOrder;
      if ( OcspCrlUrlOrder == 3 )
      {
        if ( v81 && !(unsigned int)IsOcspUrl((const unsigned __int16 *)v81, (const char *)2, (void *)pCertContext) )
          v81 = 0;
        goto LABEL_60;
      }
      v71 = OcspCrlUrlOrder;
      v61 = OcspCrlUrlOrder - 1;
      if ( v61 )
      {
        v62 = v61 - 1;
        if ( !v62 )
        {
          pszOID = (LPCSTR)2;
          v71 = v44;
          goto LABEL_61;
        }
        if ( v62 != 2 )
        {
LABEL_61:
          phFuncAddr = 0;
          ppvFuncAddr = 0;
          if ( CryptGetOIDFunctionAddress(hGetObjectUrlFuncSet, 1u, pszOID, 0, &ppvFuncAddr, &phFuncAddr) )
          {
            v45 = ((__int64 (__fastcall *)(LPCSTR, PCCERT_CONTEXT, __int64, _QWORD, DWORD *, _QWORD, _QWORD, _QWORD))ppvFuncAddr)(
                    pszOID,
                    v42,
                    15,
                    0,
                    &pcbData,
                    0,
                    0,
                    0);
            LastError = GetLastError();
            CryptFreeOIDFunctionAddress(phFuncAddr, 0);
            SetLastError(LastError);
            if ( v45 )
            {
              hMem[0] = operator new(pcbData);
              v47 = (struct _CRYPT_URL_ARRAY *)hMem[0];
              if ( hMem[0] )
              {
                v48 = pszOID;
                ppvFuncAddr = 0;
                phFuncAddr = 0;
                if ( CryptGetOIDFunctionAddress(hGetObjectUrlFuncSet, 1u, pszOID, 0, &phFuncAddr, &ppvFuncAddr) )
                {
                  TimeValidObjectByUrl = ((__int64 (__fastcall *)(LPCSTR, PCCERT_CONTEXT, __int64, struct _CRYPT_URL_ARRAY *, DWORD *, _QWORD, _QWORD, _QWORD))phFuncAddr)(
                                           v48,
                                           pCertContext,
                                           15,
                                           v47,
                                           &pcbData,
                                           0,
                                           0,
                                           0);
                  v51 = GetLastError();
                  CryptFreeOIDFunctionAddress(ppvFuncAddr, 0);
                  SetLastError(v51);
                  v47 = (struct _CRYPT_URL_ARRAY *)hMem[0];
                }
                else
                {
                  TimeValidObjectByUrl = 0;
                }
                if ( TimeValidObjectByUrl )
                {
                  v11 = v47;
                  v83 = pcbData;
                  if ( v81 )
                  {
                    GetUrlArrayIndex(v47, v81, v49, &v73);
LABEL_111:
                    v75 = v73;
                  }
                  else
                  {
                    v52 = v47->cUrl == 1;
                    v75 = 0;
                    if ( !v52 )
                    {
                      v53 = v71;
                      if ( ((v71 - 1) & 0xFFFFFFFD) != 0 )
                      {
                        for ( k = 0; ; k = v73 + 1 )
                        {
                          v73 = k;
                          if ( k >= v47->cUrl )
                            break;
                          v65 = v47->rgwszUrl[k];
                          hMem[0] = v65;
                          if ( v53 == 4 )
                          {
                            if ( (unsigned int)IsOcspUrl(v65, (const char *)2, (void *)pCertContext) )
                              break;
                            v65 = (LPWSTR)hMem[0];
                          }
                          if ( (unsigned int)SchemeHasCacheMetaData(v65) )
                            goto LABEL_111;
                          v53 = v71;
                        }
                      }
                    }
                  }
                  v54 = v75;
                  v55 = v83;
                  goto LABEL_71;
                }
                operator delete(v47);
LABEL_94:
                v60 = GetLastError();
                CertDiagRejectCrl(0, (unsigned int)L"GetCrlOrOcspUrls", v60, 0, 0, 0);
                v55 = v83;
                v54 = v75;
                goto LABEL_71;
              }
              SetLastError(0x8007000E);
            }
          }
          TimeValidObjectByUrl = 0;
          goto LABEL_94;
        }
        pszOID = (LPCSTR)11;
        if ( v81 )
        {
          v63 = IsOcspUrl((const unsigned __int16 *)v81, (const char *)2, (void *)pCertContext);
          v42 = pCertContext;
          v71 = v44;
          if ( v63 )
            v81 = 0;
          goto LABEL_61;
        }
        v71 = v44;
LABEL_60:
        v42 = pCertContext;
        goto LABEL_61;
      }
    }
    pszOID = (LPCSTR)13;
    goto LABEL_61;
  }
  if ( v39 != (char *)1 )
  {
    SetLastError(0x80092004);
    TimeValidObjectByUrl = 0;
    v54 = v75;
LABEL_169:
    if ( v23 )
    {
      v56 = uBytes;
      v68 = (struct _CRYPT_URL_ARRAY *)operator new((unsigned int)uBytes);
      v11 = v68;
      if ( v68 )
      {
        if ( (unsigned int)CopyUrlArray(v68, phHash, v56) )
        {
          TimeValidObjectByUrl = 1;
        }
        else
        {
          operator delete(v11);
          v11 = 0;
          SetLastError(0x80070057);
        }
      }
      else
      {
        SetLastError(0x8007000E);
      }
    }
    else
    {
      v56 = uBytes;
    }
    goto LABEL_73;
  }
  NextUpdateUrl = ObjectContextGetNextUpdateUrl(
                    v86,
                    (void *)pCertContext,
                    v91,
                    (unsigned __int16 *)v41,
                    (struct _CRYPT_URL_ARRAY **)&phFuncAddr,
                    (unsigned int *)&ppvFuncAddr,
                    &v73);
  v54 = v73;
  TimeValidObjectByUrl = NextUpdateUrl;
  v55 = (unsigned int)ppvFuncAddr;
  v11 = (struct _CRYPT_URL_ARRAY *)phFuncAddr;
LABEL_71:
  if ( TimeValidObjectByUrl != 1 )
    goto LABEL_169;
  v56 = v55;
LABEL_73:
  if ( v84 )
    LeaveCriticalSection(v13);
  if ( TimeValidObjectByUrl == 1 )
  {
    TimeValidObjectByUrl = CTVOAgent::GetTimeValidObjectByUrl(
                             v13,
                             v56,
                             v11,
                             v54,
                             v86,
                             v91,
                             v19,
                             pbOutput,
                             lpFileTime1,
                             v28,
                             a8,
                             v89,
                             v96,
                             &v85,
                             &lpFileTime2,
                             *(struct _TVO_ACTIVE_ENTRY **)&SystemTimeAsFileTime);
  }
  else
  {
    v69 = GetLastError();
    if ( !v69 )
      v69 = -2147418113;
    CTVOAgent::CompleteActiveRetrieval(v13, *(HLOCAL *)&SystemTimeAsFileTime, v69, 0, 0);
    SetLastError(v69);
  }
  if ( !v85 && v11 )
  {
    v57 = GetLastError();
    LocalFree(v11);
    SetLastError(v57);
  }
  return TimeValidObjectByUrl;
}

```

## disassembly

```asm
0x180007cc0  push    rbp
0x180007cc2  push    r12
0x180007cc4  push    r14
0x180007cc6  push    r15
0x180007cc8  lea     rbp, [rsp-108h]
0x180007cd0  sub     rsp, 208h
0x180007cd7  mov     rax, cs:__security_cookie
0x180007cde  xor     rax, rsp
0x180007ce1  mov     [rbp+120h+var_38], rax
0x180007ce8  mov     rax, [rbp+120h+arg_28]
0x180007cef  xor     r12d, r12d
0x180007cf2  mov     rcx, [rbp+120h+arg_20]
0x180007cf9  xorps   xmm0, xmm0
0x180007cfc  mov     r14, cs:?g_pProcessTVOAgent@@3PEAVCTVOAgent@@EA; CTVOAgent * g_pProcessTVOAgent
0x180007d03  mov     r15, rdx
0x180007d06  mov     [rbp+120h+lpFileTime1], rax
0x180007d0a  mov     r10, r9
0x180007d0d  mov     rax, [rbp+120h+arg_40]
0x180007d14  mov     [rbp+120h+var_128], rax
0x180007d18  mov     rax, [rbp+120h+arg_48]
0x180007d1f  mov     [rbp+120h+var_160], rdx
0x180007d23  mov     rdx, [rbp+120h+Src]; Src
0x180007d2a  mov     [rbp+120h+var_C0], rax
0x180007d2e  mov     eax, r12d
0x180007d31  mov     [rbp+120h+var_140], r9
0x180007d35  mov     r9, r8; unsigned int
0x180007d38  mov     [rbp+120h+var_150], eax
0x180007d3b  mov     dword ptr [rbp+120h+ppvFuncAddr], eax
0x180007d3e  mov     [rbp+120h+pCertContext], r8
0x180007d42  mov     [rbp+120h+var_118], rcx
0x180007d46  mov     [rbp+120h+var_148], r12d
0x180007d4a  mov     [rbp+120h+var_D0], r12
0x180007d4e  mov     [rbp+120h+var_C8], r12
0x180007d52  movups  xmmword ptr [rbp+120h+lpFileTime2], xmm0
0x180007d56  movups  [rbp+120h+var_F0], xmm0
0x180007d5a  movups  [rbp+120h+var_E0], xmm0
0x180007d5e  test    rdx, rdx
0x180007d61  jnz     loc_180008095
0x180007d67  mov     rax, qword ptr [rbp+120h+var_F0]
0x180007d6b  mov     dword ptr [rbp+120h+lpFileTime2], 30h ; '0'
0x180007d72  test    rax, rax
0x180007d75  jnz     short loc_180007D7F
0x180007d77  lea     rax, [rbp+120h+var_D0]
0x180007d7b  mov     qword ptr [rbp+120h+var_F0], rax
0x180007d7f  cmp     qword ptr [rbp+120h+var_F0+8], r12
0x180007d83  jnz     short loc_180007D8D
0x180007d85  lea     rdx, [rbp+120h+var_C8]
0x180007d89  mov     qword ptr [rbp+120h+var_F0+8], rdx
0x180007d8d  mov     [rsp+220h+arg_0], rbx
0x180007d95  mov     [rax], r12
0x180007d98  mov     rax, qword ptr [rbp+120h+var_F0+8]
0x180007d9c  mov     [rsp+220h+var_20], rsi
0x180007da4  mov     [rsp+220h+var_28], rdi
0x180007dac  mov     [rsp+220h+var_30], r13
0x180007db4  mov     [rax], r12
0x180007db7  cmp     r15, 3
0x180007dbb  jnz     loc_1800087EC
0x180007dc1  mov     esi, r12d
0x180007dc4  mov     [rbp+120h+pszOID], 0Ah
0x180007dcc  mov     r13, r9
0x180007dcf  mov     rbx, [rcx+18h]
0x180007dd3  lea     rdx, [rbp+120h+phHash]; phHash
0x180007dd7  mov     rdi, [r13+18h]
0x180007ddb  mov     ecx, 41h ; 'A'; hAlgorithm
0x180007de0  mov     [rsp+220h+dwFlags], r12d; dwFlags
0x180007de5  xor     r9d, r9d; cbHashObject
0x180007de8  mov     [rsp+220h+cbSecret], r12d; cbSecret
0x180007ded  xor     r8d, r8d; pbHashObject
0x180007df0  mov     [rsp+220h+pbSecret], r12; pbSecret
0x180007df5  mov     [rbp+120h+var_1A0], 1
0x180007dfc  mov     [rbp+120h+pbInput], r12b
0x180007e00  mov     [rbp+120h+phHash], r12
0x180007e04  call    cs:__imp_BCryptCreateHash
0x180007e0a  test    eax, eax
0x180007e0c  jnz     loc_18000850F
0x180007e12  test    esi, esi
0x180007e14  jnz     loc_18000881A
0x180007e1a  mov     rcx, [rbp+120h+phHash]; hHash
0x180007e1e  lea     rdx, [rbp+120h+pbInput]; pbInput
0x180007e22  xor     r9d, r9d; dwFlags
0x180007e25  mov     [rbp+120h+pbInput], al
0x180007e28  mov     r8d, 1; cbInput
0x180007e2e  call    cs:__imp_BCryptHashData
0x180007e34  test    eax, eax
0x180007e36  jnz     loc_18000850F
0x180007e3c  mov     r8d, [rdi+30h]; cbInput
0x180007e40  xor     r9d, r9d; dwFlags
0x180007e43  mov     rdx, [rdi+38h]; pbInput
0x180007e47  mov     rcx, [rbp+120h+phHash]; hHash
0x180007e4b  call    cs:__imp_BCryptHashData
0x180007e51  test    eax, eax
0x180007e53  jnz     loc_18000850F
0x180007e59  mov     r8d, [rbx+78h]; cbInput
0x180007e5d  xor     r9d, r9d; dwFlags
0x180007e60  mov     rdx, [rbx+80h]; pbInput
0x180007e67  mov     rcx, [rbp+120h+phHash]; hHash
0x180007e6b  call    cs:__imp_BCryptHashData
0x180007e71  test    eax, eax
0x180007e73  jnz     loc_18000850F
0x180007e79  mov     rcx, [rbp+120h+phHash]; hHash
0x180007e7d  lea     rdx, [rbp+120h+pbOutput]; pbOutput
0x180007e84  xor     r9d, r9d; dwFlags
0x180007e87  mov     r8d, 20h ; ' '; cbOutput
0x180007e8d  call    cs:__imp_BCryptFinishHash
0x180007e93  test    eax, eax
0x180007e95  jnz     loc_18000850F
0x180007e9b  mov     rcx, [rbp+120h+phHash]; hHash
0x180007e9f  test    rcx, rcx
0x180007ea2  jz      short loc_180007EAA
0x180007ea4  call    cs:__imp_BCryptDestroyHash
0x180007eaa  mov     rcx, r14; lpCriticalSection
0x180007ead  mov     [rbp+120h+var_190], r12d
0x180007eb1  mov     rbx, r12
0x180007eb4  mov     [rbp+120h+var_198], r12d
0x180007eb8  mov     edi, r12d
0x180007ebb  mov     [rbp+120h+phFuncAddr], r12
0x180007ebf  call    cs:__imp_EnterCriticalSection
0x180007ec5  inc     dword ptr [r14+40h]
0x180007ec9  cmp     r15, 3
0x180007ecd  jnz     loc_180008868
0x180007ed3  lea     r9, [rbp+120h+pcbData]; pcbData
0x180007ed7  mov     [rbp+120h+pcbData], 20h ; ' '
0x180007ede  lea     r8, [rbp+120h+pvData]; pvData
0x180007ee5  mov     edx, 6Bh ; 'k'; dwPropId
0x180007eea  mov     rcx, r13; pCertContext
0x180007eed  call    cs:__imp_CertGetCertificateContextProperty
0x180007ef3  test    eax, eax
0x180007ef5  jz      loc_180008879
0x180007efb  cmp     [rbp+120h+pcbData], 20h ; ' '
0x180007eff  jnz     loc_180008853
0x180007f05  mov     rcx, [r14+28h]
0x180007f09  lea     rax, [rbp+120h+pvData]
0x180007f10  xor     esi, esi
0x180007f12  mov     [rbp+120h+var_108], rax
0x180007f16  lea     rdx, [rbp+120h+hMem]
0x180007f1a  mov     [rbp+120h+hMem], 20h ; ' '
0x180007f22  call    cs:__imp_I_CryptFindLruEntry
0x180007f28  mov     rdi, rax
0x180007f2b  mov     rbx, rsi
0x180007f2e  test    rax, rax
0x180007f31  jnz     loc_180008050
0x180007f37  test    rbx, rbx
0x180007f3a  jz      loc_180008860
0x180007f40  mov     r15d, [rbp+120h+arg_30]
0x180007f47  mov     rax, [rbx+28h]
0x180007f4b  lea     rdx, [rbp+120h+SystemTimeAsFileTime]
0x180007f4f  mov     qword ptr [rbp+120h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007f53  xor     r8d, r8d
0x180007f56  lea     rax, aTvocache; "TvoCache"
0x180007f5d  mov     ecx, 2
0x180007f62  mov     [rbp+120h+var_130], rax
0x180007f66  call    cs:__imp_I_CertDiagControl
0x180007f6c  mov     esi, r15d
0x180007f6f  and     esi, 4
0x180007f72  jnz     loc_1800084D0
0x180007f78  bt      r15d, 9
0x180007f7d  jb      short loc_180007FE3
0x180007f7f  mov     rax, [rbp+120h+lpFileTime1]
0x180007f83  test    rax, rax
0x180007f86  jz      short loc_180007FA8
0x180007f88  mov     rcx, rax; lpFileTime1
0x180007f8b  bt      r15d, 0Ah
0x180007f90  jb      loc_180008880
0x180007f96  lea     rdx, [rbx+5Ch]; lpFileTime2
0x180007f9a  call    cs:__imp_CompareFileTime
0x180007fa0  test    eax, eax
0x180007fa2  jg      loc_1800084C6
0x180007fa8  mov     rdx, [rbp+120h+lpFileTime2+8]; lpFileTime2
0x180007fac  test    rdx, rdx
0x180007faf  jnz     loc_180008897
0x180007fb5  cmp     [rbx+6Ch], r12d
0x180007fb9  jz      loc_18000858B
0x180007fbf  lea     rcx, [rbp+120h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007fc3  mov     qword ptr [rbp+120h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180007fc7  call    cs:__imp_GetSystemTimeAsFileTime
0x180007fcd  lea     rdx, [rbx+6Ch]; lpFileTime2
0x180007fd1  lea     rcx, [rbp+120h+SystemTimeAsFileTime]; lpFileTime1
0x180007fd5  call    cs:__imp_CompareFileTime
0x180007fdb  test    eax, eax
0x180007fdd  jg      loc_1800084D0
0x180007fe3  mov     rcx, [rbx+78h]
0x180007fe7  xor     edx, edx
0x180007fe9  call    cs:__imp_I_CryptTouchLruEntry
0x180007fef  mov     rdi, [rbp+120h+var_128]
0x180007ff3  test    rdi, rdi
0x180007ff6  jz      short loc_180008027
0x180007ff8  mov     rax, [rbx+20h]
0x180007ffc  mov     rcx, [rbx+28h]; pCtlContext
0x180008000  cmp     rax, 1
0x180008004  jz      loc_1800087D2
0x18000800a  cmp     rax, 3
0x18000800e  jz      loc_1800088D9
0x180008014  cmp     rax, 2
0x180008018  jnz     loc_1800088E4
0x18000801e  call    cs:__imp_CertDuplicateCRLContext
0x180008024  mov     [rdi], rax
0x180008027  mov     rdx, qword ptr [rbp+120h+var_F0]
0x18000802b  mov     rcx, r14; lpCriticalSection
0x18000802e  mov     r8, [rbx+64h]
0x180008032  mov     [rdx], r8
0x180008035  mov     rdx, qword ptr [rbp+120h+var_F0+8]
0x180008039  mov     r8, [rbx+6Ch]
0x18000803d  mov     [rdx], r8
0x180008040  call    cs:__imp_LeaveCriticalSection
0x180008046  mov     eax, 1
0x18000804b  jmp     loc_18000843A
0x180008050  mov     rcx, rdi
0x180008053  call    cs:__imp_I_CryptGetLruEntryData
0x180008059  mov     rbx, rax
0x18000805c  cmp     qword ptr [rax+20h], 2
0x180008061  jnz     loc_180008612
0x180008067  test    r13, r13
0x18000806a  jz      short loc_180008087
0x18000806c  mov     rdx, [rax+28h]; pCrl
0x180008070  xor     r9d, r9d; pvReserved
0x180008073  xor     r8d, r8d; dwFlags
0x180008076  mov     rcx, r13; pCert
0x180008079  call    cs:__imp_CertIsValidCRLForCertificate
0x18000807f  test    eax, eax
0x180008081  jz      loc_180008612
0x180008087  mov     rcx, rdi
0x18000808a  call    cs:__imp_I_CryptReleaseLruEntry
0x180008090  jmp     loc_180007F37
0x180008095  mov     eax, [rdx]
0x180008097  cmp     eax, 30h ; '0'
0x18000809a  jb      loc_1800087DD
0x1800080a0  mov     r8d, 30h ; '0'; Size
0x1800080a6  lea     rcx, [rbp+120h+lpFileTime2]; void *
0x1800080aa  call    memcpy_0
0x1800080af  mov     r9, [rbp+120h+pCertContext]
0x1800080b3  mov     rcx, [rbp+120h+var_118]
0x1800080b7  mov     r10, [rbp+120h+var_140]
0x1800080bb  jmp     loc_180007D67
0x1800080c0  mov     r15d, [rbp+120h+arg_30]
0x1800080c7  bt      r15d, 18h
0x1800080cc  jb      short loc_180008108
0x1800080ce  mov     rcx, [r14+28h]
0x1800080d2  lea     rax, [rbp+120h+pbOutput]
0x1800080d9  lea     rdx, [rbp+120h+var_B8]
0x1800080dd  mov     [rbp+120h+var_B0], rax
0x1800080e1  mov     [rbp+120h+var_B8], 20h ; ' '
0x1800080e9  call    cs:__imp_I_CryptFindLruEntry
0x1800080ef  xor     ebx, ebx
0x1800080f1  mov     rsi, rax
0x1800080f4  test    rax, rax
0x1800080f7  jnz     loc_180008478
0x1800080fd  test    rbx, rbx
0x180008100  jnz     loc_180007F47
0x180008106  xor     esi, esi
0x180008108  mov     dword ptr [rbp+120h+uBytes], esi
0x18000810b  mov     [rbp+120h+phHash], rsi
0x18000810f  test    r15b, 2
0x180008113  jz      loc_18000875B
0x180008119  mov     r8, [rbp+120h+var_140]; char *
0x18000811d  lea     rax, [rbp+120h+SystemTimeAsFileTime]
0x180008121  mov     [rsp+220h+var_1D0], rax; struct _TVO_ACTIVE_ENTRY **
0x180008126  mov     r9, r13; void *
0x180008129  lea     rax, [rbp+120h+pvData]
0x180008130  mov     qword ptr [rbp+120h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180008134  mov     rsi, [rbp+120h+var_160]
0x180008138  mov     rcx, r14; this
0x18000813b  mov     [rsp+220h+var_1D8], rax; unsigned __int8 *
0x180008140  mov     rdx, rsi; char *
0x180008143  lea     rax, [rbp+120h+pbOutput]
0x18000814a  mov     [rsp+220h+Buf2], rax; Buf2
0x18000814f  lea     rax, [rbp+120h+lpFileTime2]
0x180008153  mov     [rsp+220h+var_1E8], rax; struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *
0x180008158  mov     rax, [rbp+120h+var_128]
0x18000815c  mov     qword ptr [rsp+220h+dwFlags], rax; void **
0x180008161  mov     rax, [rbp+120h+lpFileTime1]
0x180008165  mov     [rsp+220h+cbSecret], r15d; unsigned int
0x18000816a  mov     [rsp+220h+pbSecret], rax; struct _FILETIME *
0x18000816f  call    ?StartActiveRetrieval@CTVOAgent@@QEAAJPEBD0PEAXPEAU_FILETIME@@KPEAPEAXPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@QEAE5PEAPEAU_TVO_ACTIVE_ENTRY@@@Z; CTVOAgent::StartActiveRetrieval(char const *,char const *,void *,_FILETIME *,ulong,void * *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *,uchar * const,uchar * const,_TVO_ACTIVE_ENTRY * *)
0x180008174  cmp     eax, 1
0x180008177  jnz     loc_180008562
0x18000817d  test    rbx, rbx
0x180008180  jnz     loc_1800085F6
0x180008186  mov     rdi, [rbp+120h+phHash]
0x18000818a  mov     eax, dword ptr [rbp+120h+uBytes]
0x18000818d  mov     [rbp+120h+phHash], rdi
0x180008191  xor     edi, edi
0x180008193  mov     dword ptr [rbp+120h+uBytes], eax
0x180008196  mov     rcx, r14; lpCriticalSection
0x180008199  call    cs:__imp_LeaveCriticalSection
0x18000819f  mov     rax, rdi
0x1800081a2  mov     [rbp+120h+var_14C], edi
0x1800081a5  mov     [rbp+120h+var_160], rax
0x1800081a9  cmp     [rbp+120h+var_1A0], r12d
0x1800081ad  jz      loc_180008933
0x1800081b3  cmp     [rbp+120h+pszOID], 0Ah
0x1800081b8  mov     [rbp+120h+pcbData], edi
0x1800081bb  mov     [rbp+120h+var_1A0], edi
0x1800081be  jnz     short loc_1800081F5
0x1800081c0  mov     rsi, [rbp+120h+pCertContext]
0x1800081c4  bt      r15d, 18h
0x1800081c9  jb      loc_180008908
0x1800081cf  mov     edx, r15d; unsigned int
0x1800081d2  mov     rcx, rsi; pCertContext
0x1800081d5  call    ?CertificateGetOcspCrlUrlOrder@@YAKPEBU_CERT_CONTEXT@@K@Z; CertificateGetOcspCrlUrlOrder(_CERT_CONTEXT const *,ulong)
0x1800081da  mov     [rbp+120h+var_1A0], eax
  ... truncated ...
```
