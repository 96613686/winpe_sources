# CTVOAgent::GetTimeValidObjectByUrl(ulong,_CRYPT_URL_ARRAY *,ulong,char const *,_CERT_CONTEXT const *,void *,uchar * const,_FILETIME *,ulong,ulong,void * *,_CRYPT_CREDENTIALS *,int *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *,_TVO_ACTIVE_ENTRY *)

- ea: `0x180008f80`
- end: `0x180009de4`
- name: `?GetTimeValidObjectByUrl@CTVOAgent@@QEAAHKPEAU_CRYPT_URL_ARRAY@@KPEBDPEBU_CERT_CONTEXT@@PEAXQEAEPEAU_FILETIME@@KKPEAPEAXPEAU_CRYPT_CREDENTIALS@@PEAHPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@PEAU_TVO_ACTIVE_ENTRY@@@Z`
- size: `3684`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, int, struct _CRYPT_URL_ARRAY *, unsigned int, char *, struct _CERT_CONTEXT *, CERT_CONTEXT *pCertContext, unsigned __int8 *const, struct _FILETIME *, unsigned int, unsigned int, void **, struct _CRYPT_CREDENTIALS *, int *, struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *, struct _TVO_ACTIVE_ENTRY *hMem)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180007cc0`

## callees

- `0x180007c00`
- `0x180008f80`
- `0x180009df0`
- `0x180009e30`
- `0x18000a990`
- `0x18000eb80`
- `0x180010cf4`
- `0x18001254c`
- `0x180012e1c`
- `0x180012f0c`
- `0x180012f60`
- `0x180012f9c`
- `0x180017de4`
- `0x180017e60`
- `0x180018290`
- `0x1800183a8`
- `0x180018a6c`
- `0x18001dde0`
- `0x18001e660`
- `0x18001e95c`
- `0x18001f100`
- `0x180026546`
- `0x18002656a`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009524`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800097b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009af2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ca7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009524`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800097b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009af2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ca7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009994`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009994`
- `CRYPT32!I_CryptCreateLruEntry` at `0x1800092dd`
- `CRYPT32!I_CryptCreateLruEntry` at `0x1800092dd`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x1800097a0`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180009832`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x1800097a0`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x180009832`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000960d`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x1800096d0`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000960d`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x1800096d0`
- `CRYPT32!I_CryptGetLruEntryData` at `0x1800095cd`
- `CRYPT32!I_CryptGetLruEntryData` at `0x18000969d`
- `CRYPT32!I_CryptGetLruEntryData` at `0x1800095cd`
- `CRYPT32!I_CryptGetLruEntryData` at `0x18000969d`
- `CRYPT32!I_CryptFindLruEntry` at `0x1800093db`
- `CRYPT32!I_CryptFindLruEntry` at `0x18000941a`
- `CRYPT32!I_CryptFindLruEntry` at `0x1800093db`
- `CRYPT32!I_CryptFindLruEntry` at `0x18000941a`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x180009a1b`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x180009a1b`
- `CRYPT32!I_CryptInsertLruEntry` at `0x18000966c`
- `CRYPT32!I_CryptInsertLruEntry` at `0x18000966c`
- `CRYPT32!I_CertDiagControl` at `0x18000980a`
- `CRYPT32!I_CertDiagControl` at `0x180009a98`
- `CRYPT32!I_CertDiagControl` at `0x18000980a`
- `CRYPT32!I_CertDiagControl` at `0x180009a98`
- `CRYPT32!CertDuplicateCTLContext` at `0x180009c97`
- `CRYPT32!CertDuplicateCTLContext` at `0x180009c97`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800099be`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800099be`
- `CRYPT32!CertDuplicateCRLContext` at `0x180009291`
- `CRYPT32!CertDuplicateCRLContext` at `0x180009854`
- `CRYPT32!CertDuplicateCRLContext` at `0x180009291`
- `CRYPT32!CertDuplicateCRLContext` at `0x180009854`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180009059`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180009059`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x1800095fc`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x1800096bf`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x1800095fc`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x1800096bf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009897`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800098ad`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800098e3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009897`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800098ad`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800098e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000974e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000974e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800095ba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009ab3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800095ba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009ab3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000945e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009675`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000992d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000945e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009675`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000992d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099fc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009c0b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009c0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000968f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800096db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000968f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800096db`

## pseudocode

```c
__int64 __fastcall CTVOAgent::GetTimeValidObjectByUrl(
        LPCRITICAL_SECTION lpCriticalSection,
        int a2,
        struct _CRYPT_URL_ARRAY *a3,
        unsigned int a4,
        char *a5,
        struct _CERT_CONTEXT *a6,
        CERT_CONTEXT *pCertContext,
        unsigned __int8 *const a8,
        struct _FILETIME *a9,
        unsigned int a10,
        unsigned int a11,
        void **a12,
        struct _CRYPT_CREDENTIALS *a13,
        int *a14,
        struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *a15,
        struct _TVO_ACTIVE_ENTRY *hMem)
{
  CERT_CONTEXT *v18; // r14
  unsigned int v19; // r8d
  __int64 v20; // r13
  const WCHAR *v21; // rsi
  unsigned int v22; // r9d
  const WCHAR *UrlList; // rax
  __int64 v24; // rdi
  LPWSTR **p_rgwszUrl; // r13
  unsigned __int16 *v26; // rsi
  int v27; // eax
  int v28; // r14d
  unsigned __int8 *v29; // rax
  _OWORD *v30; // rsi
  char *v31; // rax
  void *v32; // rax
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *v33; // rcx
  struct _FILETIME v34; // rax
  __int128 v35; // xmm1
  _QWORD *v36; // rax
  PCCERT_CONTEXT v37; // r12
  BYTE *NotAfter; // rcx
  int v39; // eax
  unsigned int v40; // r12d
  int *v41; // rcx
  PCCERT_CONTEXT v42; // r15
  unsigned __int8 *v43; // rsi
  DWORD LastError; // eax
  LPCRITICAL_SECTION v45; // r13
  DWORD v46; // r14d
  PRTL_CRITICAL_SECTION_DEBUG v47; // rcx
  __int64 i; // rax
  CTVOCache *v49; // rcx
  __int64 LruEntryData; // rsi
  __int64 v51; // rdi
  PRTL_CRITICAL_SECTION_DEBUG v52; // rcx
  __int64 j; // rax
  __int64 v54; // rdi
  int v55; // r15d
  __int64 v56; // rcx
  struct _TVO_ACTIVE_ENTRY **v57; // rax
  _QWORD *v58; // rdi
  _QWORD *v59; // rsi
  void *v60; // rcx
  void *v61; // rcx
  __int64 v63; // rax
  __int32 v64; // r15d
  char *v65; // r14
  struct _CRL_PRE_FETCH_ENTRY *v66; // rdi
  __int64 v67; // rax
  __int64 v68; // rdx
  struct _TVO_ACTIVE_ENTRY **v69; // rax
  _QWORD *v70; // rdi
  _QWORD *v71; // rsi
  PCCERT_CONTEXT v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  struct _FILETIME *v75; // rdi
  WCHAR *v76; // r8
  unsigned int v77; // eax
  __int64 v78; // rax
  LPWSTR *rgwszUrl; // rdx
  WCHAR *v80; // r8
  __int64 v81; // rdi
  const WCHAR *v82; // r13
  WCHAR *v83; // r12
  __int64 v84; // rsi
  const WCHAR *v85; // r12
  __int64 v86; // rax
  unsigned int v87; // edi
  struct _CRL_PRE_FETCH_ENTRY *Entry; // rax
  struct _CRYPT_CREDENTIALS *v89; // [rsp+40h] [rbp-C0h]
  BOOL v90; // [rsp+70h] [rbp-90h]
  unsigned int v91; // [rsp+74h] [rbp-8Ch]
  unsigned int valid; // [rsp+78h] [rbp-88h]
  int v93; // [rsp+78h] [rbp-88h]
  DWORD pcbData[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-78h] BYREF
  char *v96; // [rsp+90h] [rbp-70h]
  PCCERT_CONTEXT pCert; // [rsp+98h] [rbp-68h]
  HLOCAL v98; // [rsp+A0h] [rbp-60h]
  int *v99; // [rsp+A8h] [rbp-58h]
  int v100; // [rsp+B0h] [rbp-50h]
  struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *DebugInfo; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *pMaxAgeTime; // [rsp+C0h] [rbp-40h]
  void *v103; // [rsp+C8h] [rbp-38h] BYREF
  struct _FILETIME *v104; // [rsp+D0h] [rbp-30h]
  struct _TVO_CACHE_ENTRY *v105; // [rsp+D8h] [rbp-28h]
  HLOCAL v106; // [rsp+E0h] [rbp-20h]
  _QWORD v107[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v108; // [rsp+F8h] [rbp-8h] BYREF
  int v109; // [rsp+108h] [rbp+8h]
  unsigned int v110; // [rsp+10Ch] [rbp+Ch]
  struct _CERT_CONTEXT *v111; // [rsp+110h] [rbp+10h]
  PCNZWCH lpString1; // [rsp+118h] [rbp+18h]
  LPCRITICAL_SECTION lpCriticalSectiona[2]; // [rsp+120h] [rbp+20h] BYREF
  FILETIME FileTime1; // [rsp+130h] [rbp+30h] BYREF
  void **v115; // [rsp+138h] [rbp+38h]
  _BYTE pvData[32]; // [rsp+140h] [rbp+40h] BYREF

  v18 = pCertContext;
  v19 = 0;
  lpCriticalSectiona[0] = lpCriticalSection;
  v111 = a6;
  v104 = a9;
  v115 = a12;
  v99 = a14;
  v20 = a4;
  pMaxAgeTime = a8;
  v21 = 0;
  DebugInfo = a15;
  v110 = a4;
  v109 = a2;
  v96 = a5;
  pCert = pCertContext;
  v103 = 0;
  lpString1 = 0;
  FileTime1 = 0;
  if ( a5 == (char *)2 && pCertContext )
  {
    pcbData[0] = 32;
    if ( CertGetCertificateContextProperty(pCertContext, 0x6Bu, pvData, pcbData) )
    {
      if ( pcbData[0] == 32 )
      {
        v22 = a10;
        if ( (a10 & 0x1000000) == 0 )
        {
          UrlList = GetCrlPreFetchUrlList();
          v22 = a10;
          v21 = UrlList;
          lpString1 = UrlList;
        }
        v19 = 0;
        goto LABEL_8;
      }
      SetLastError(0xDu);
    }
    if ( !hMem )
    {
      ++dword_180032960;
      return 0;
    }
    ++dword_180032964;
    EnterCriticalSection(lpCriticalSection);
    v68 = *(_QWORD *)hMem;
    if ( *(struct _TVO_ACTIVE_ENTRY **)(*(_QWORD *)hMem + 8LL) == hMem )
    {
      v69 = (struct _TVO_ACTIVE_ENTRY **)*((_QWORD *)hMem + 1);
      if ( *v69 == hMem )
      {
        *v69 = (struct _TVO_ACTIVE_ENTRY *)v68;
        *(_QWORD *)(v68 + 8) = v69;
        LeaveCriticalSection(lpCriticalSection);
        v70 = (_QWORD *)((char *)hMem + 16);
        while ( 1 )
        {
          v71 = (_QWORD *)*v70;
          if ( (_QWORD *)*v70 == v70 )
          {
            FreeActiveEntry(hMem);
            return 0;
          }
          if ( (_QWORD *)v71[1] != v70 )
            break;
          v74 = *v71;
          if ( *(_QWORD **)(*v71 + 8LL) != v71 )
            break;
          *v70 = v74;
          *(_QWORD *)(v74 + 8) = v70;
          *((_DWORD *)v71 + 42) = -2147418113;
          v78 = *((_QWORD *)hMem + 20);
          if ( v78 && v71[20] )
          {
            *((_QWORD *)&v108 + 1) = v71[20];
            *(_QWORD *)&v108 = v78;
            I_CertDiagControl(26, &v108, 0);
          }
          _InterlockedExchange((volatile __int32 *)v71 + 46, 1);
          ++dword_180032968;
          SetEvent((HANDLE)v71[4]);
        }
      }
    }
    goto LABEL_123;
  }
  v22 = a10;
LABEL_8:
  valid = 0;
  v98 = 0;
  v105 = 0;
  v100 = 0;
  pcbData[0] = 0;
  v90 = 0;
  v91 = 0;
  v106 = 0;
  if ( (_DWORD)v20 )
  {
    rgwszUrl = a3->rgwszUrl;
    v80 = rgwszUrl[v20];
    rgwszUrl[v20] = *rgwszUrl;
    *a3->rgwszUrl = v80;
    v19 = 0;
  }
  if ( (v22 & 0x800) != 0 )
  {
    if ( a11 )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      LOWORD(v22) = a10;
      v19 = 0;
      FileTime1 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 10000LL * a11);
    }
    else
    {
      v22 &= ~0x800u;
      a10 = v22;
    }
  }
  if ( v21 )
  {
    v81 = 0;
    if ( a3->cUrl )
    {
      v82 = lpString1;
      do
      {
        v83 = a3->rgwszUrl[v81];
        if ( (unsigned int)IsInMultiSzList(v82, v83) )
        {
          if ( (_DWORD)v81 != v91 )
          {
            a3->rgwszUrl[v81] = a3->rgwszUrl[v91];
            a3->rgwszUrl[v91] = v83;
          }
          v19 = ++v91;
        }
        else
        {
          v19 = v91;
        }
        v81 = (unsigned int)(v81 + 1);
      }
      while ( (unsigned int)v81 < a3->cUrl );
      if ( v19 > 1 )
      {
        v84 = 0;
        v85 = v82;
        do
        {
          if ( !v85 )
            break;
          v86 = -1;
          do
            ++v86;
          while ( v85[v86] );
          if ( !(_DWORD)v86 )
            break;
          v87 = v84;
          v107[0] = (int)v86;
          while ( v87 < v19 )
          {
            SystemTimeAsFileTime = (struct _FILETIME)a3->rgwszUrl[v87];
            if ( CompareStringW(0x409u, 1u, v85, -1, *(PCNZWCH *)&SystemTimeAsFileTime, -1) == 2 )
            {
              if ( (_DWORD)v84 != v87 )
              {
                a3->rgwszUrl[v87] = a3->rgwszUrl[v84];
                a3->rgwszUrl[v84] = (LPWSTR)SystemTimeAsFileTime;
              }
              v19 = v91;
              v84 = (unsigned int)(v84 + 1);
              break;
            }
            v19 = v91;
            ++v87;
          }
          v85 += v107[0] + 1;
        }
        while ( (unsigned int)v84 < v19 - 1 );
      }
      LOWORD(v22) = a10;
    }
  }
  v24 = 0;
  v107[0] = &a3->rgwszUrl;
  p_rgwszUrl = &a3->rgwszUrl;
  while ( 1 )
  {
    if ( (unsigned int)v24 >= a3->cUrl )
      goto LABEL_103;
    if ( v19 && (unsigned int)v24 >= v19 )
    {
      p_rgwszUrl = (LPWSTR **)v107[0];
LABEL_103:
      v43 = pMaxAgeTime;
      v40 = valid;
      v42 = pCert;
      *(_QWORD *)pcbData = v103;
      goto LABEL_40;
    }
    if ( (v22 & 0x800) != 0 )
    {
      v77 = (unsigned int)I_CryptRemainingMilliseconds(&FileTime1) >> 1;
      if ( !v77 )
        v77 = 1;
      a11 = v77;
    }
    p_rgwszUrl = &a3->rgwszUrl;
    v26 = a3->rgwszUrl[v24];
    v27 = IsOcspUrl(v26, v96, v18);
    LOWORD(v22) = a10;
    v28 = v27;
    if ( v27 )
      break;
    if ( (a10 & 0x1000000) == 0 )
    {
      v100 = 1;
      goto LABEL_19;
    }
    valid = 0;
    if ( !pcbData[0] )
    {
      SetLastError(0x80092014);
LABEL_22:
      LOWORD(v22) = a10;
    }
LABEL_23:
    v18 = (CERT_CONTEXT *)pCert;
    v24 = (unsigned int)(v24 + 1);
    v19 = v91;
  }
  if ( DebugInfo->iDeltaCrlIndicator > 0 )
    goto LABEL_23;
  pcbData[0] = 1;
  v26 += 5;
LABEL_19:
  v29 = pvData;
  if ( !v28 )
    v29 = pMaxAgeTime;
  SystemTimeAsFileTime = (struct _FILETIME)v29;
  valid = RetrieveTimeValidObjectByUrl(
            v28,
            pcbData[0],
            (unsigned int)v24 < v91,
            v26,
            v96,
            v104,
            a10,
            a11,
            v89,
            v111,
            (CERT_CONTEXT *)pCert,
            v29,
            &v103,
            DebugInfo);
  if ( valid != 1 )
    goto LABEL_22;
  v108 = 0;
  v90 = v28 != 0;
  pMaxAgeTime = (unsigned __int8 *)DebugInfo->pMaxAgeTime;
  v107[0] = DebugInfo->pLastSyncTime;
  DebugInfo = (struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)lpCriticalSectiona[0][1].DebugInfo;
  v30 = operator new(0x98u);
  *(_QWORD *)pcbData = v103;
  if ( !v30 )
  {
    SetLastError(0x8007000E);
    v40 = 0;
    goto LABEL_38;
  }
  memset_0(v30, 0, 0x98u);
  v31 = v96;
  *((_QWORD *)v30 + 4) = v96;
  if ( v31 == (char *)1 )
  {
    v32 = (void *)CertDuplicateCertificateContext(*(PCCERT_CONTEXT *)pcbData);
  }
  else if ( v31 == (char *)3 )
  {
    v32 = (void *)CertDuplicateCTLContext(*(PCCTL_CONTEXT *)pcbData);
  }
  else if ( v31 == (char *)2 )
  {
    v32 = (void *)CertDuplicateCRLContext(*(PCCRL_CONTEXT *)pcbData);
  }
  else
  {
    SetLastError(0x80070057);
    v32 = 0;
  }
  v33 = DebugInfo;
  *((_QWORD *)v30 + 5) = v32;
  v34 = SystemTimeAsFileTime;
  *v30 = *(_OWORD *)*(_QWORD *)&SystemTimeAsFileTime;
  v35 = *(_OWORD *)(*(_QWORD *)&v34 + 16LL);
  v36 = (_QWORD *)v107[0];
  v30[1] = v35;
  *(_QWORD *)((char *)v30 + 100) = *v36;
  *(_QWORD *)((char *)v30 + 108) = *(_QWORD *)pMaxAgeTime;
  LODWORD(v108) = 32;
  *((_QWORD *)&v108 + 1) = v30;
  v93 = I_CryptCreateLruEntry(v33, &v108, v30, (char *)v30 + 120);
  if ( v93 != 1 )
    goto LABEL_191;
  v37 = *(PCCERT_CONTEXT *)pcbData;
  ObjectContextGetNextUpdateUrl(
    v96,
    *(void **)pcbData,
    v111,
    (*p_rgwszUrl)[v24],
    (struct _CRYPT_URL_ARRAY **)v30 + 9,
    (unsigned int *)v30 + 17,
    (unsigned int *)v30 + 20);
  if ( v96 == (char *)1 )
  {
    *(FILETIME *)((char *)v30 + 84) = v37->pCertInfo->NotBefore;
    NotAfter = (BYTE *)v37->pCertInfo->NotAfter;
LABEL_36:
    v39 = v109;
    *(_QWORD *)((char *)v30 + 92) = NotAfter;
    *((_DWORD *)v30 + 12) = v39;
    *((_QWORD *)v30 + 7) = a3;
    *((_DWORD *)v30 + 16) = v24;
    v93 = 1;
    v98 = v30;
    goto LABEL_37;
  }
  if ( v96 == (char *)3 )
  {
    *(_QWORD *)((char *)v30 + 84) = v37->pCertInfo->Issuer.pbData;
    NotAfter = (BYTE *)v37->pCertInfo->NotBefore;
    goto LABEL_36;
  }
  if ( v96 == (char *)2 )
  {
    *(_QWORD *)((char *)v30 + 84) = *(_QWORD *)&v37->pCertInfo->Issuer.cbData;
    NotAfter = v37->pCertInfo->Issuer.pbData;
    goto LABEL_36;
  }
  SetLastError(0x80070057);
  v93 = 0;
LABEL_191:
  ObjectContextFreeTVOCacheEntry(v30);
LABEL_37:
  v40 = v93;
LABEL_38:
  v41 = v99;
  v42 = pCert;
  *v99 = v40;
  if ( (unsigned int)v24 >= v91 )
  {
LABEL_39:
    v43 = (unsigned __int8 *)SystemTimeAsFileTime;
    goto LABEL_40;
  }
  if ( v40 )
  {
    if ( v28 )
      goto LABEL_39;
    Entry = CreateCrlPreFetchEntry((struct _TVO_CACHE_ENTRY *)v98, v111, v42);
    v43 = (unsigned __int8 *)SystemTimeAsFileTime;
    v106 = Entry;
LABEL_40:
    v41 = v99;
    goto LABEL_41;
  }
  v43 = (unsigned __int8 *)SystemTimeAsFileTime;
LABEL_41:
  if ( v110 && !*v41 )
  {
    v76 = (*p_rgwszUrl)[v110];
    (*p_rgwszUrl)[v110] = **p_rgwszUrl;
    **p_rgwszUrl = v76;
  }
  LastError = GetLastError();
  v45 = lpCriticalSectiona[0];
  v46 = LastError;
  EnterCriticalSection(lpCriticalSectiona[0]);
  v47 = v45[1].DebugInfo;
  v107[0] = 32;
  v107[1] = v43;
  for ( i = I_CryptFindLruEntry(v47, v107); ; i = I_CryptEnumMatchingLruEntries(v51) )
  {
    LruEntryData = 0;
    v51 = i;
    if ( !i )
      break;
    LruEntryData = I_CryptGetLruEntryData(i);
    if ( v96 == *(char **)(LruEntryData + 32)
      && (v96 != (char *)2 || !v42 || CertIsValidCRLForCertificate(v42, *(PCCRL_CONTEXT *)(LruEntryData + 40), 0, 0)) )
    {
      I_CryptReleaseLruEntry(v51);
      break;
    }
  }
  if ( v96 == (char *)2 && v42 && !v90 )
  {
    v52 = v45[1].DebugInfo;
    lpCriticalSectiona[1] = (LPCRITICAL_SECTION)pvData;
    lpCriticalSectiona[0] = (LPCRITICAL_SECTION)32;
    for ( j = I_CryptFindLruEntry(v52, lpCriticalSectiona); ; j = I_CryptEnumMatchingLruEntries(v54) )
    {
      v105 = 0;
      v54 = j;
      if ( !j )
        break;
      v67 = I_CryptGetLruEntryData(j);
      v105 = (struct _TVO_CACHE_ENTRY *)v67;
      if ( *(_QWORD *)(v67 + 32) == 2 && CertIsValidCRLForCertificate(v42, *(PCCRL_CONTEXT *)(v67 + 40), 0, 0) )
      {
        I_CryptReleaseLruEntry(v54);
        break;
      }
    }
  }
  if ( v40 )
  {
    if ( v40 != 1 || (a10 & 0x100) != 0 )
      goto LABEL_51;
    if ( v105 )
      CTVOCache::RemoveCacheEntry(v49, v105, 0);
    if ( LruEntryData )
    {
      v65 = (char *)v98;
      if ( CompareFileTime((const FILETIME *)(LruEntryData + 84), (const FILETIME *)((char *)v98 + 84)) < 0 )
      {
        RemoveCrlPreFetchEntry((struct _TVO_CACHE_ENTRY *)LruEntryData);
        I_CryptRemoveLruEntry(*(_QWORD *)(LruEntryData + 120), 0, 0);
        goto LABEL_93;
      }
      if ( CompareFileTime((const FILETIME *)(v65 + 100), (const FILETIME *)(LruEntryData + 100)) > 0
        || (unsigned int)I_CryptIsResetBackCurrentFileTime(v65 + 100, 3600, LruEntryData + 100) )
      {
        *(_QWORD *)(LruEntryData + 100) = *(_QWORD *)(v65 + 100);
      }
      if ( !*(_QWORD *)(LruEntryData + 144)
        && (CompareFileTime((const FILETIME *)(v65 + 108), (const FILETIME *)(LruEntryData + 108)) > 0
         || (unsigned int)I_CryptIsResetBackCurrentFileTime(v65 + 108, 3600, LruEntryData + 108)) )
      {
        *(_QWORD *)(LruEntryData + 108) = *(_QWORD *)(v65 + 108);
      }
      ObjectContextFree(v96, *(void **)pcbData);
      *(_QWORD *)pcbData = ObjectContextDuplicate(*(const char **)(LruEntryData + 32), *(void **)(LruEntryData + 40));
      if ( (a10 & 2) == 0 )
        *(_DWORD *)(LruEntryData + 128) = 0;
    }
    else if ( (a10 & 0x1000000) == 0 )
    {
      v65 = (char *)v98;
LABEL_93:
      v66 = (struct _CRL_PRE_FETCH_ENTRY *)v106;
      if ( v106 )
      {
        *((_QWORD *)v65 + 18) = v106;
        *(_QWORD *)(v65 + 108) = 0;
        *(_QWORD *)v66 = v65;
        ScheduleNextCrlPreFetch(v66);
        v106 = 0;
        HIDWORD(v45[1].LockSemaphore) = 1;
      }
      I_CryptInsertLruEntry(*((_QWORD *)v65 + 15), 0);
      LeaveCriticalSection(v45);
LABEL_96:
      v46 = 0;
      goto LABEL_56;
    }
    ObjectContextFreeTVOCacheEntry(v98);
    LeaveCriticalSection(v45);
    v46 = 0;
    goto LABEL_56;
  }
  if ( (a10 & 2) == 0 )
  {
    v75 = v104;
    if ( LruEntryData && (a10 & 0x1000000) == 0 )
      SetOfflineUrlTime((struct _OFFLINE_URL_TIME_INFO *)(LruEntryData + 128), v104);
    if ( v105 )
      SetOfflineUrlTime((struct _TVO_CACHE_ENTRY *)((char *)v105 + 128), v75);
  }
LABEL_51:
  if ( v98 )
    ObjectContextFreeTVOCacheEntry(v98);
  LeaveCriticalSection(v45);
  if ( v40 )
    goto LABEL_96;
  if ( !v46 )
    v46 = -2147418113;
LABEL_56:
  if ( v106 )
    FreeCrlPreFetchEntry(v106);
  if ( lpString1 )
    operator delete((HLOCAL)lpString1);
  if ( v46 && !v100 )
  {
    v55 = 1;
    v90 = 1;
  }
  else
  {
    v55 = v90;
  }
  if ( !hMem )
  {
    ++dword_180032960;
    goto LABEL_73;
  }
  ++dword_180032964;
  EnterCriticalSection(v45);
  v56 = *(_QWORD *)hMem;
  if ( *(struct _TVO_ACTIVE_ENTRY **)(*(_QWORD *)hMem + 8LL) != hMem
    || (v57 = (struct _TVO_ACTIVE_ENTRY **)*((_QWORD *)hMem + 1), *v57 != hMem) )
  {
LABEL_123:
    __fastfail(3u);
  }
  *v57 = (struct _TVO_ACTIVE_ENTRY *)v56;
  *(_QWORD *)(v56 + 8) = v57;
  LeaveCriticalSection(v45);
  v58 = (_QWORD *)((char *)hMem + 16);
  while ( 1 )
  {
    v59 = (_QWORD *)*v58;
    if ( (_QWORD *)*v58 == v58 )
      break;
    if ( (_QWORD *)v59[1] != v58 )
      goto LABEL_123;
    v63 = *v59;
    if ( *(_QWORD **)(*v59 + 8LL) != v59 )
      goto LABEL_123;
    *v58 = v63;
    *(_QWORD *)(v63 + 8) = v58;
    *((_DWORD *)v59 + 42) = v46;
    if ( v55 )
    {
      if ( memcmp_0(v59 + 15, (char *)hMem + 120, 0x20u) )
      {
        ++dword_18003296C;
        v64 = -1;
        goto LABEL_80;
      }
    }
    else
    {
      v72 = *(PCCERT_CONTEXT *)pcbData;
      if ( !*(_QWORD *)pcbData )
        goto LABEL_117;
      if ( !ObjectContextIsValidForSubject((const char *)2, *(void **)pcbData, (void *)v59[7], 0) )
      {
        ++dword_18003296C;
        v64 = -1;
        goto LABEL_80;
      }
    }
    v72 = *(PCCERT_CONTEXT *)pcbData;
LABEL_117:
    v64 = 1;
    if ( v46 )
    {
      v73 = *((_QWORD *)hMem + 20);
      if ( v73 && v59[20] )
      {
        *((_QWORD *)&v108 + 1) = v59[20];
        *(_QWORD *)&v108 = v73;
        I_CertDiagControl(26, &v108, 0);
      }
    }
    else if ( v72 )
    {
      v59[22] = CertDuplicateCRLContext((PCCRL_CONTEXT)v72);
    }
LABEL_80:
    _InterlockedExchange((volatile __int32 *)v59 + 46, v64);
    ++dword_180032968;
    SetEvent((HANDLE)v59[4]);
    v55 = v90;
  }
  v60 = (void *)*((_QWORD *)hMem + 4);
  if ( v60 )
    CloseHandle(v60);
  v61 = (void *)*((_QWORD *)hMem + 5);
  if ( v61 )
    CloseHandle(v61);
  operator delete(hMem);
LABEL_73:
  if ( *(_QWORD *)pcbData )
  {
    if ( v115 && v40 == 1 )
      *v115 = *(void **)pcbData;
    else
      ObjectContextFree(v96, *(void **)pcbData);
  }
  SetLastError(v46);
  return v40;
}

```

## disassembly

```asm
0x180008f80  mov     [rsp-8+arg_8], rbx
0x180008f85  push    rbp
0x180008f86  push    rsi
0x180008f87  push    rdi
0x180008f88  push    r12
0x180008f8a  push    r13
0x180008f8c  push    r14
0x180008f8e  push    r15
0x180008f90  lea     rbp, [rsp-70h]
0x180008f95  sub     rsp, 170h
0x180008f9c  mov     rax, cs:__security_cookie
0x180008fa3  xor     rax, rsp
0x180008fa6  mov     [rbp+0A0h+var_40], rax
0x180008faa  mov     rsi, [rbp+0A0h+arg_38]
0x180008fb1  mov     rdi, rcx
0x180008fb4  mov     rax, [rbp+0A0h+arg_20]
0x180008fbb  mov     r15, r8
0x180008fbe  mov     r14, [rbp+0A0h+pCertContext]
0x180008fc5  xor     r8d, r8d
0x180008fc8  mov     rbx, [rbp+0A0h+hMem]
0x180008fcf  mov     [rbp+0A0h+lpCriticalSection], rcx
0x180008fd3  mov     rcx, [rbp+0A0h+arg_28]
0x180008fda  mov     [rbp+0A0h+var_90], rcx
0x180008fde  mov     rcx, [rbp+0A0h+arg_40]
0x180008fe5  mov     [rbp+0A0h+var_D0], rcx
0x180008fe9  mov     rcx, [rbp+0A0h+arg_58]
0x180008ff0  mov     [rbp+0A0h+var_68], rcx
0x180008ff4  mov     rcx, [rbp+0A0h+arg_68]
0x180008ffb  mov     [rbp+0A0h+var_F8], rcx
0x180008fff  mov     rcx, [rbp+0A0h+arg_70]
0x180009006  mov     r13d, r9d
0x180009009  mov     [rbp+0A0h+var_E0], rsi
0x18000900d  mov     esi, r8d
0x180009010  mov     [rbp+0A0h+var_E8], rcx
0x180009014  mov     [rbp+0A0h+var_94], r13d
0x180009018  mov     [rbp+0A0h+var_98], edx
0x18000901b  mov     [rbp+0A0h+var_110], rax
0x18000901f  mov     [rbp+0A0h+pCert], r14
0x180009023  mov     [rbp+0A0h+var_D8], r8
0x180009027  mov     [rbp+0A0h+lpString1], r8
0x18000902b  mov     qword ptr [rbp+0A0h+FileTime1.dwLowDateTime], r8
0x18000902f  cmp     rax, 2
0x180009033  jnz     loc_180009683
0x180009039  test    r14, r14
0x18000903c  jz      loc_180009683
0x180009042  lea     r9, [rbp+0A0h+pcbData]; pcbData
0x180009046  mov     [rbp+0A0h+pcbData], 20h ; ' '
0x18000904d  lea     r8, [rbp+0A0h+pvData]; pvData
0x180009051  mov     edx, 6Bh ; 'k'; dwPropId
0x180009056  mov     rcx, r14; pCertContext
0x180009059  call    cs:__imp_CertGetCertificateContextProperty
0x18000905f  test    eax, eax
0x180009061  jz      loc_18000973C
0x180009067  cmp     [rbp+0A0h+pcbData], 20h ; ' '
0x18000906b  jnz     loc_180009AED
0x180009071  mov     r9d, [rbp+0A0h+arg_48]
0x180009078  bt      r9d, 18h
0x18000907d  jb      short loc_180009092
0x18000907f  call    ?GetCrlPreFetchUrlList@@YAPEAGXZ; GetCrlPreFetchUrlList(void)
0x180009084  mov     r9d, [rbp+0A0h+arg_48]
0x18000908b  mov     rsi, rax
0x18000908e  mov     [rbp+0A0h+lpString1], rax
0x180009092  xor     r8d, r8d
0x180009095  xor     r12d, r12d
0x180009098  mov     [rsp+1A0h+var_128], r8d
0x18000909d  mov     [rbp+0A0h+var_100], r8
0x1800090a1  mov     [rbp+0A0h+var_C8], r8
0x1800090a5  mov     [rbp+0A0h+var_F0], r8d
0x1800090a9  mov     [rbp+0A0h+pcbData], r8d
0x1800090ad  mov     [rsp+1A0h+var_130], r8d
0x1800090b2  mov     [rsp+1A0h+var_12C], r8d
0x1800090b7  mov     [rbp+0A0h+var_C0], r12
0x1800090bb  test    r13d, r13d
0x1800090be  jnz     loc_180009AFD
0x1800090c4  bt      r9d, 0Bh
0x1800090c9  jb      loc_18000997E
0x1800090cf  mov     r12d, 1
0x1800090d5  test    rsi, rsi
0x1800090d8  jnz     loc_180009B20
0x1800090de  lea     rax, [r15+8]
0x1800090e2  xor     edi, edi
0x1800090e4  mov     [rbp+0A0h+var_B8], rax
0x1800090e8  mov     r13, rax
0x1800090eb  cmp     edi, [r15]
0x1800090ee  jnb     loc_1800096F3
0x1800090f4  test    r8d, r8d
0x1800090f7  jnz     loc_1800096E6
0x1800090fd  bt      r9d, 0Bh
0x180009102  jb      loc_180009A26
0x180009108  mov     rcx, [r15+8]
0x18000910c  lea     r13, [r15+8]
0x180009110  mov     rdx, [rbp+0A0h+var_110]; char *
0x180009114  lea     r12, ds:0[rdi*8]
0x18000911c  mov     r8, r14; void *
0x18000911f  mov     rsi, [r12+rcx]
0x180009123  mov     rcx, rsi; unsigned __int16 *
0x180009126  call    ?IsOcspUrl@@YAHPEBGPEBDPEAX@Z; IsOcspUrl(ushort const *,char const *,void *)
0x18000912b  mov     r9d, [rbp+0A0h+arg_48]
0x180009132  mov     r14d, eax
0x180009135  test    eax, eax
0x180009137  jz      loc_1800091EF
0x18000913d  mov     rax, [rbp+0A0h+var_E8]
0x180009141  cmp     dword ptr [rax+4], 0
0x180009145  jg      loc_1800091D9
0x18000914b  mov     [rbp+0A0h+pcbData], 1
0x180009152  add     rsi, 0Ah
0x180009156  mov     rcx, [rbp+0A0h+var_E8]
0x18000915a  lea     rax, [rbp+0A0h+pvData]
0x18000915e  mov     edx, [rbp+0A0h+pcbData]; int
0x180009161  test    r14d, r14d
0x180009164  mov     [rsp+1A0h+var_138], rcx; struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *
0x180009169  lea     rcx, [rbp+0A0h+var_D8]
0x18000916d  cmovz   rax, [rbp+0A0h+var_E0]
0x180009172  xor     r8d, r8d
0x180009175  cmp     edi, [rsp+1A0h+var_12C]
0x180009179  mov     [rsp+1A0h+var_140], rcx; void **
0x18000917e  mov     ecx, r14d; int
0x180009181  mov     [rsp+1A0h+var_148], rax; unsigned __int8 *
0x180009186  setb    r8b; int
0x18000918a  mov     qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000918e  mov     rax, [rbp+0A0h+pCert]
0x180009192  mov     [rsp+1A0h+var_150], rax; void *
0x180009197  mov     rax, [rbp+0A0h+var_90]
0x18000919b  mov     [rsp+1A0h+var_158], rax; struct _CERT_CONTEXT *
0x1800091a0  mov     eax, [rbp+0A0h+arg_50]
0x1800091a6  mov     [rsp+1A0h+var_168], eax; unsigned int
0x1800091aa  mov     rax, [rbp+0A0h+var_D0]
0x1800091ae  mov     dword ptr [rsp+1A0h+var_170], r9d; unsigned int
0x1800091b3  mov     r9, rsi; unsigned __int16 *
0x1800091b6  mov     qword ptr [rsp+1A0h+cchCount2], rax; struct _FILETIME *
0x1800091bb  mov     rax, [rbp+0A0h+var_110]
0x1800091bf  mov     [rsp+1A0h+lpString2], rax; char *
0x1800091c4  call    ?RetrieveTimeValidObjectByUrl@@YAHHHHPEAGPEBDPEAU_FILETIME@@KKPEAU_CRYPT_CREDENTIALS@@PEBU_CERT_CONTEXT@@PEAXQEAEPEAPEAXPEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@@Z; RetrieveTimeValidObjectByUrl(int,int,int,ushort *,char const *,_FILETIME *,ulong,ulong,_CRYPT_CREDENTIALS *,_CERT_CONTEXT const *,void *,uchar * const,void * *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)
0x1800091c9  mov     [rsp+1A0h+var_128], eax
0x1800091cd  cmp     eax, 1
0x1800091d0  jz      short loc_180009206
0x1800091d2  mov     r9d, [rbp+0A0h+arg_48]
0x1800091d9  mov     r14, [rbp+0A0h+pCert]
0x1800091dd  inc     edi
0x1800091df  mov     r8d, [rsp+1A0h+var_12C]
0x1800091e4  mov     r12d, 1
0x1800091ea  jmp     loc_1800090EB
0x1800091ef  bt      r9d, 18h
0x1800091f4  jb      loc_180009C74
0x1800091fa  mov     [rbp+0A0h+var_F0], 1
0x180009201  jmp     loc_180009156
0x180009206  mov     rcx, [rbp+0A0h+var_E8]
0x18000920a  xor     eax, eax
0x18000920c  xorps   xmm0, xmm0
0x18000920f  test    r14d, r14d
0x180009212  movups  [rbp+0A0h+var_A8], xmm0
0x180009216  setnz   al
0x180009219  mov     [rsp+1A0h+var_130], eax
0x18000921d  mov     rax, [rcx+18h]
0x180009221  mov     [rbp+0A0h+var_E0], rax
0x180009225  mov     rax, [rcx+10h]
0x180009229  mov     rcx, [rbp+0A0h+lpCriticalSection]
0x18000922d  mov     [rbp+0A0h+var_B8], rax
0x180009231  mov     rax, [rcx+28h]
0x180009235  mov     ecx, 98h; uBytes
0x18000923a  mov     [rbp+0A0h+var_E8], rax
0x18000923e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009243  mov     rsi, rax
0x180009246  mov     rax, [rbp+0A0h+var_D8]
0x18000924a  mov     qword ptr [rbp+0A0h+pcbData], rax
0x18000924e  test    rsi, rsi
0x180009251  jz      loc_1800097AB
0x180009257  xor     edx, edx; Val
0x180009259  mov     r8d, 98h; Size
0x18000925f  mov     rcx, rsi; void *
0x180009262  call    memset_0
0x180009267  mov     rax, [rbp+0A0h+var_110]
0x18000926b  mov     [rsi+20h], rax
0x18000926f  cmp     rax, 1
0x180009273  jz      loc_1800099BA
0x180009279  cmp     rax, 3
0x18000927d  jz      loc_180009C93
0x180009283  cmp     rax, 2
0x180009287  jnz     loc_180009CA2
0x18000928d  mov     rcx, qword ptr [rbp+0A0h+pcbData]; pCrlContext
0x180009291  call    cs:__imp_CertDuplicateCRLContext
0x180009297  mov     rcx, [rbp+0A0h+var_E8]
0x18000929b  lea     r9, [rsi+78h]
0x18000929f  mov     [rsi+28h], rax
0x1800092a3  lea     rdx, [rbp+0A0h+var_A8]
0x1800092a7  mov     rax, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800092ab  mov     r8, rsi
0x1800092ae  movups  xmm0, xmmword ptr [rax]
0x1800092b1  movups  xmmword ptr [rsi], xmm0
0x1800092b4  movups  xmm1, xmmword ptr [rax+10h]
0x1800092b8  mov     rax, [rbp+0A0h+var_B8]
0x1800092bc  movups  xmmword ptr [rsi+10h], xmm1
0x1800092c0  mov     rax, [rax]
0x1800092c3  mov     [rsi+64h], rax
0x1800092c7  mov     rax, [rbp+0A0h+var_E0]
0x1800092cb  mov     rax, [rax]
0x1800092ce  mov     [rsi+6Ch], rax
0x1800092d2  mov     dword ptr [rbp+0A0h+var_A8], 20h ; ' '
0x1800092d9  mov     qword ptr [rbp+0A0h+var_A8+8], rsi
0x1800092dd  call    cs:__imp_I_CryptCreateLruEntry
0x1800092e3  mov     [rsp+1A0h+var_128], eax
0x1800092e7  cmp     eax, 1
0x1800092ea  jnz     loc_180009CE0
0x1800092f0  mov     r9, [r13+0]
0x1800092f4  lea     rax, [rsi+50h]
0x1800092f8  mov     r8, [rbp+0A0h+var_90]; struct _CERT_CONTEXT *
0x1800092fc  lea     rcx, [rsi+44h]
0x180009300  mov     [rsp+1A0h+var_170], rax; unsigned int *
0x180009305  lea     rdx, [rsi+48h]
0x180009309  mov     qword ptr [rsp+1A0h+cchCount2], rcx; unsigned int *
0x18000930e  mov     r9, [r12+r9]; unsigned __int16 *
0x180009312  mov     r12, qword ptr [rbp+0A0h+pcbData]
0x180009316  mov     rcx, [rbp+0A0h+var_110]; char *
0x18000931a  mov     [rsp+1A0h+lpString2], rdx; struct _CRYPT_URL_ARRAY **
0x18000931f  mov     rdx, r12; void *
0x180009322  call    ?ObjectContextGetNextUpdateUrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@PEAGPEAPEAU_CRYPT_URL_ARRAY@@PEAK5@Z; ObjectContextGetNextUpdateUrl(char const *,void *,_CERT_CONTEXT const *,ushort *,_CRYPT_URL_ARRAY * *,ulong *,ulong *)
0x180009327  mov     rax, [rbp+0A0h+var_110]
0x18000932b  cmp     rax, 1
0x18000932f  jz      loc_180009A40
0x180009335  cmp     rax, 3
0x180009339  jz      loc_180009CB4
0x18000933f  cmp     rax, 2
0x180009343  jnz     loc_180009CCF
0x180009349  mov     rax, [r12+18h]
0x18000934e  mov     rcx, [rax+30h]
0x180009352  mov     [rsi+54h], rcx
0x180009356  mov     rax, [r12+18h]
0x18000935b  mov     rcx, [rax+38h]
0x18000935f  mov     eax, [rbp+0A0h+var_98]
0x180009362  mov     [rsi+5Ch], rcx
0x180009366  mov     [rsi+30h], eax
0x180009369  mov     [rsi+38h], r15
0x18000936d  mov     [rsi+40h], edi
0x180009370  mov     [rsp+1A0h+var_128], 1
0x180009378  mov     [rbp+0A0h+var_100], rsi
0x18000937c  mov     r12d, [rsp+1A0h+var_128]
0x180009381  mov     rcx, [rbp+0A0h+var_F8]
0x180009385  mov     r15, [rbp+0A0h+pCert]
0x180009389  mov     [rcx], r12d
0x18000938c  cmp     edi, [rsp+1A0h+var_12C]
0x180009390  jb      loc_180009CED
0x180009396  mov     ecx, [rsp+1A0h+var_130]
0x18000939a  mov     rsi, qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime]
0x18000939e  mov     [rsp+1A0h+var_130], ecx
0x1800093a2  mov     rcx, [rbp+0A0h+var_F8]
0x1800093a6  mov     eax, [rbp+0A0h+var_94]
0x1800093a9  test    eax, eax
0x1800093ab  jnz     loc_1800099C9
0x1800093b1  call    cs:__imp_GetLastError
0x1800093b7  mov     r13, [rbp+0A0h+lpCriticalSection]
0x1800093bb  mov     r14d, eax
0x1800093be  mov     rcx, r13; lpCriticalSection
0x1800093c1  call    cs:__imp_EnterCriticalSection
0x1800093c7  mov     rcx, [r13+28h]
0x1800093cb  lea     rdx, [rbp+0A0h+var_B8]
0x1800093cf  mov     [rbp+0A0h+var_B8], 20h ; ' '
0x1800093d7  mov     [rbp+0A0h+var_B0], rsi
0x1800093db  call    cs:__imp_I_CryptFindLruEntry
0x1800093e1  xor     esi, esi
0x1800093e3  mov     rdi, rax
0x1800093e6  test    rax, rax
0x1800093e9  jnz     loc_1800095CA
0x1800093ef  cmp     [rbp+0A0h+var_110], 2
0x1800093f4  jnz     short loc_180009434
0x1800093f6  test    r15, r15
0x1800093f9  jz      short loc_180009434
0x1800093fb  cmp     [rsp+1A0h+var_130], 0
0x180009400  jnz     short loc_180009434
0x180009402  mov     rcx, [r13+28h]
0x180009406  lea     rax, [rbp+0A0h+pvData]
0x18000940a  lea     rdx, [rbp+0A0h+lpCriticalSection]
0x18000940e  mov     [rbp+0A0h+var_78], rax
0x180009412  mov     [rbp+0A0h+lpCriticalSection], 20h ; ' '
0x18000941a  call    cs:__imp_I_CryptFindLruEntry
0x180009420  mov     [rbp+0A0h+var_C8], 0
0x180009428  mov     rdi, rax
0x18000942b  test    rax, rax
0x18000942e  jnz     loc_18000969A
0x180009434  test    r12d, r12d
0x180009437  jnz     loc_180009618
0x18000943d  mov     r15d, [rbp+0A0h+arg_48]
0x180009444  test    r15b, 2
0x180009448  jz      loc_180009950
0x18000944e  mov     rax, [rbp+0A0h+var_100]
0x180009452  test    rax, rax
0x180009455  jnz     loc_180009DAC
0x18000945b  mov     rcx, r13; lpCriticalSection
0x18000945e  call    cs:__imp_LeaveCriticalSection
0x180009464  test    r12d, r12d
0x180009467  jnz     loc_18000967B
0x18000946d  test    r14d, r14d
0x180009470  jz      loc_18000983D
0x180009476  mov     rax, [rbp+0A0h+var_C0]
0x18000947a  test    rax, rax
0x18000947d  jnz     loc_180009DB9
0x180009483  mov     rax, [rbp+0A0h+lpString1]
0x180009487  test    rax, rax
0x18000948a  jnz     loc_180009DC6
0x180009490  test    r14d, r14d
0x180009493  jz      short loc_18000949F
  ... truncated ...
```
