# GetSSOCertHash

- ea: `0x1800598b4`
- end: `0x18005a74d`
- name: `GetSSOCertHash`
- size: `3737`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hToken, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005b06c`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x18004bcd4`
- `0x180058574`
- `0x180058a84`
- `0x180058dfc`
- `0x1800598b4`
- `0x18005a754`
- `0x18005c100`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!malloc` at `0x180059aa9`
- `msvcrt!malloc` at `0x180059b6b`
- `msvcrt!malloc` at `0x180059ce0`
- `msvcrt!malloc` at `0x18005a42f`
- `msvcrt!malloc` at `0x180059aa9`
- `msvcrt!malloc` at `0x180059b6b`
- `msvcrt!malloc` at `0x180059ce0`
- `msvcrt!malloc` at `0x18005a42f`
- `msvcrt!free` at `0x18005a530`
- `msvcrt!free` at `0x18005a636`
- `msvcrt!free` at `0x18005a654`
- `msvcrt!free` at `0x18005a680`
- `msvcrt!free` at `0x18005a69f`
- `msvcrt!free` at `0x18005a530`
- `msvcrt!free` at `0x18005a636`
- `msvcrt!free` at `0x18005a654`
- `msvcrt!free` at `0x18005a680`
- `msvcrt!free` at `0x18005a69f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a60e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180059983`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180059983`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a5fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a5fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180059f74`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180059f74`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059b51`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059bbb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059b51`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180059bbb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180059f88`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180059f88`
- `CRYPT32!CertFindChainInStore` at `0x180059ea4`
- `CRYPT32!CertFindChainInStore` at `0x180059ea4`
- `CRYPT32!CertVerifyTimeValidity` at `0x180059feb`
- `CRYPT32!CertVerifyTimeValidity` at `0x180059feb`
- `CRYPT32!CertCloseStore` at `0x18005a5ee`
- `CRYPT32!CertCloseStore` at `0x18005a5ee`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a5cf`
- `CRYPT32!CertFreeCertificateChain` at `0x18005a5cf`
- `CRYPT32!CertOpenStore` at `0x180059a22`
- `CRYPT32!CertOpenStore` at `0x180059a22`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005a3c9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005a49d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005a3c9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18005a49d`

## pseudocode

```c
__int64 __fastcall GetSSOCertHash(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        HANDLE hToken,
        _QWORD *a6,
        DWORD *a7,
        _DWORD *a8)
{
  __int64 v10; // rsi
  DWORD LastError; // eax
  DWORD v12; // ebx
  struct _LIST_ENTRY *v13; // rcx
  _QWORD *v14; // r15
  _QWORD *v15; // r14
  _QWORD *v16; // rax
  __int64 v17; // rdi
  int v18; // eax
  size_t cbMultiByte; // r14
  CHAR *v20; // rax
  CHAR *v21; // rbx
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned int v25; // ebx
  _QWORD *v26; // rax
  _QWORD *v27; // r12
  __int64 v28; // r9
  struct _LIST_ENTRY *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  DWORD v32; // eax
  __int64 v33; // rsi
  struct _LIST_ENTRY *v34; // rcx
  const CERT_CHAIN_CONTEXT *v35; // r14
  unsigned int v36; // r15d
  PCCERT_CHAIN_CONTEXT ChainInStore; // rax
  const CERT_CONTEXT *pCertContext; // rsi
  DWORD v39; // eax
  struct _LIST_ENTRY *Flink; // rcx
  __int64 v41; // rdx
  __int64 v42; // rdx
  struct _LIST_ENTRY *v43; // rbx
  unsigned int v44; // eax
  struct _LIST_ENTRY *v45; // rcx
  int v46; // eax
  int v47; // eax
  DWORD v48; // eax
  struct _LIST_ENTRY *v49; // rcx
  DWORD v50; // eax
  struct _LIST_ENTRY *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r9
  void *v54; // rax
  void *v55; // rdi
  DWORD *v56; // rdx
  HCERTSTORE v57; // rcx
  unsigned int v58; // r12d
  __int64 i; // rdi
  void *v60; // rcx
  unsigned int v61; // r15d
  unsigned int j; // edi
  void *v63; // rcx
  int pvPara; // [rsp+20h] [rbp-D1h]
  _QWORD *v66; // [rsp+40h] [rbp-B1h]
  _QWORD *v67; // [rsp+48h] [rbp-A9h]
  DWORD v68; // [rsp+50h] [rbp-A1h] BYREF
  unsigned int v69; // [rsp+54h] [rbp-9Dh]
  int v70; // [rsp+58h] [rbp-99h]
  DWORD pcbData; // [rsp+5Ch] [rbp-95h] BYREF
  unsigned int v72; // [rsp+60h] [rbp-91h]
  __int64 v73; // [rsp+68h] [rbp-89h] BYREF
  int v74; // [rsp+70h] [rbp-81h] BYREF
  HCERTSTORE hCertStore; // [rsp+78h] [rbp-79h]
  struct _FILETIME FileTime; // [rsp+80h] [rbp-71h] BYREF
  _DWORD *v77; // [rsp+88h] [rbp-69h]
  DWORD *v78; // [rsp+90h] [rbp-61h]
  _QWORD *v79; // [rsp+98h] [rbp-59h]
  __int128 pvFindPara; // [rsp+A0h] [rbp-51h] BYREF
  __int128 v81; // [rsp+B0h] [rbp-41h]
  __int128 v82; // [rsp+C0h] [rbp-31h]
  __int64 v83; // [rsp+D0h] [rbp-21h]
  _SYSTEMTIME SystemTime; // [rsp+D8h] [rbp-19h] BYREF

  v10 = a1;
  v72 = a3;
  v69 = a1;
  v79 = a6;
  v78 = a7;
  v77 = a8;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_ddq(WPP_GLOBAL_Control[1].Flink, &WPP_GLOBAL_Control, a3, a1, a3, hToken);
  }
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  pcbData = 0;
  v70 = 0;
  v74 = 0;
  v68 = 0;
  v73 = 0;
  FileTime = 0;
  pvFindPara = 0;
  LODWORD(v83) = 0;
  v81 = 0;
  v82 = 0;
  SystemTime = 0;
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( !LastError )
      goto LABEL_212;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 55, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, LastError);
        goto LABEL_212;
      }
      goto LABEL_213;
    }
    return v12;
  }
  v14 = 0;
  v15 = 0;
  v67 = 0;
  v66 = 0;
  hCertStore = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x18000u, L"MY");
  if ( !hCertStore )
  {
    v12 = GetLastError();
    if ( v12
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 56, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v12);
    }
    goto LABEL_197;
  }
  if ( (_DWORD)v10 )
  {
    v16 = malloc(8 * v10);
    v67 = v16;
    v14 = v16;
    if ( !v16 )
    {
      v12 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 57, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, 14);
      }
      goto LABEL_196;
    }
    memset_0(v16, 0, 8 * v10);
    v17 = 0;
    while ( 1 )
    {
      v18 = WideCharToMultiByte(0, 0x400u, *(LPCWCH *)(a2 + 8 * v17), -1, 0, 0, 0, 0);
      cbMultiByte = v18;
      if ( !v18 )
      {
        v12 = GetLastError();
        if ( v12
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 58, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v12);
        }
        goto LABEL_195;
      }
      v20 = (CHAR *)malloc(v18);
      v21 = v20;
      if ( !v20 )
        break;
      memset_0(v20, 0, cbMultiByte);
      if ( !WideCharToMultiByte(0, 0x400u, *(LPCWCH *)(a2 + 8 * v17), -1, v21, cbMultiByte, 0, 0) )
      {
        v12 = GetLastError();
        if ( !v12 )
          goto LABEL_35;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_35;
        }
        v23 = 60;
        v24 = v12;
        goto LABEL_34;
      }
      v14 = v67;
      v67[v17] = v21;
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= (unsigned int)v10 )
        goto LABEL_46;
    }
    v24 = 14;
    v12 = 14;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_35;
    }
    v23 = 59;
LABEL_34:
    WPP_SF_d(v22[1].Flink, v23, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v24);
    goto LABEL_35;
  }
  LODWORD(v17) = 0;
LABEL_46:
  v25 = v72;
  if ( v72 )
  {
    v26 = malloc(16LL * v72);
    v66 = v26;
    v27 = v26;
    if ( v26 )
    {
      memset_0(v26, 0, 16LL * v72);
      v17 = 0;
      while ( 1 )
      {
        v12 = ConvertHexStringToBlob(*(_QWORD *)(a4 + 8 * v17), &v68, &v73);
        if ( v12 )
          break;
        v31 = v73;
        if ( !v73 )
        {
          v12 = 87;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v30 = 63;
            goto LABEL_63;
          }
LABEL_53:
          v15 = v27;
          goto LABEL_196;
        }
        v32 = v68;
        v33 = 2LL * (unsigned int)v17;
        v68 = v12;
        v17 = (unsigned int)(v17 + 1);
        v25 = v72;
        v73 = 0;
        LODWORD(v27[v33]) = v32;
        v27[v33 + 1] = v31;
        if ( (unsigned int)v17 >= v25 )
          goto LABEL_69;
      }
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_53;
      }
      v30 = 62;
LABEL_63:
      v28 = v12;
    }
    else
    {
      v28 = 14;
      v12 = 14;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_53;
      }
      v30 = 61;
    }
    WPP_SF_d(v29[1].Flink, v30, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v28);
    goto LABEL_53;
  }
  v27 = 0;
LABEL_69:
  v34 = WPP_GLOBAL_Control;
  v35 = 0;
  pvFindPara = 0x38u;
  v36 = 0;
  v83 = 0;
  v81 = 0;
  v82 = 0;
LABEL_70:
  if ( v34 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v34[1].Blink) & 0x2000) != 0
    && BYTE1(v34[1].Blink) >= 5u )
  {
    WPP_SF_d(v34[1].Flink, 64, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v36);
  }
  v68 = 0;
  LODWORD(v73) = 0;
  ChainInStore = CertFindChainInStore(hCertStore, 1u, 0, 1u, &pvFindPara, v35);
  v35 = ChainInStore;
  if ( !ChainInStore )
  {
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 65, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids);
      v49 = WPP_GLOBAL_Control;
    }
    goto LABEL_188;
  }
  pCertContext = (*(*ChainInStore->rgpChain)->rgpElement)->pCertContext;
  v39 = CheckCertForUsage(pCertContext);
  if ( v39 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 3u )
    {
      goto LABEL_156;
    }
    Flink = WPP_GLOBAL_Control[1].Flink;
    v41 = 66;
LABEL_80:
    WPP_SF_d(Flink, v41, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v39);
    goto LABEL_155;
  }
  if ( !v70 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 3u )
    {
      goto LABEL_156;
    }
    v42 = 67;
    goto LABEL_154;
  }
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 3u )
    {
      goto LABEL_156;
    }
    v43 = WPP_GLOBAL_Control[1].Flink;
    v39 = GetLastError();
    v41 = 68;
    Flink = v43;
    goto LABEL_80;
  }
  v44 = CertVerifyTimeValidity(&FileTime, pCertContext->pCertInfo);
  if ( v44 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 3u )
    {
      goto LABEL_156;
    }
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 69, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v44);
    goto LABEL_155;
  }
  v45 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 70, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids);
      v45 = WPP_GLOBAL_Control;
    }
    if ( v45 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v45[1].Blink) & 0x2000) != 0
      && BYTE1(v45[1].Blink) >= 5u )
    {
      WPP_SF_d(v45[1].Flink, 71, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v69);
      v45 = WPP_GLOBAL_Control;
    }
  }
  if ( !v69 )
  {
LABEL_122:
    if ( v45 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v45[1].Blink) & 0x2000) != 0
      && BYTE1(v45[1].Blink) >= 5u )
    {
      WPP_SF_d(v45[1].Flink, 75, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v25);
    }
    goto LABEL_126;
  }
  LODWORD(v17) = 0;
  while ( 1 )
  {
    v46 = CheckCertForUsage(pCertContext);
    if ( !v46 )
      break;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_113;
    }
    WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 72, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, (unsigned int)v17, v46);
LABEL_112:
    v34 = WPP_GLOBAL_Control;
LABEL_113:
    LODWORD(v17) = v17 + 1;
    if ( (unsigned int)v17 >= v69 )
    {
      if ( v34 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v34[1].Blink) & 0x2000) == 0
        || BYTE1(v34[1].Blink) < 5u )
      {
        goto LABEL_156;
      }
      v42 = 74;
      goto LABEL_154;
    }
  }
  if ( !v70 )
    goto LABEL_112;
  v45 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 73, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids);
      v45 = WPP_GLOBAL_Control;
    }
    goto LABEL_122;
  }
LABEL_126:
  if ( v25 )
  {
    LODWORD(v17) = 0;
    while ( 1 )
    {
      v47 = CheckCertForIssuerHash(v35, LODWORD(v27[2 * (unsigned int)v17]), v27[2 * (unsigned int)v17 + 1], &v74);
      if ( v47 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_135;
        }
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          76,
          WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids,
          (unsigned int)v17,
          v47);
      }
      else if ( v74 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 77, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids);
        }
        break;
      }
      v34 = WPP_GLOBAL_Control;
LABEL_135:
      LODWORD(v17) = v17 + 1;
      if ( (unsigned int)v17 >= v25 )
      {
        if ( v34 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v34[1].Blink) & 0x2000) != 0
          && BYTE1(v34[1].Blink) >= 5u )
        {
          v42 = 78;
          goto LABEL_154;
        }
LABEL_156:
        v25 = v72;
        ++v36;
        goto LABEL_70;
      }
    }
  }
  v48 = IsCertAcceptable(pCertContext);
  v12 = v48;
  if ( v48 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_156;
    }
    WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 79, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, (unsigned int)v17, v48);
    goto LABEL_155;
  }
  if ( !v68 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 5u )
    {
      goto LABEL_156;
    }
    v42 = 80;
LABEL_154:
    WPP_SF_(v34[1].Flink, v42, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids);
LABEL_155:
    v34 = WPP_GLOBAL_Control;
    goto LABEL_156;
  }
  v49 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 81, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids);
    v49 = WPP_GLOBAL_Control;
  }
  if ( !pCertContext )
  {
LABEL_188:
    v12 = 874;
    if ( v49 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v49[1].Blink) & 0x2000) != 0
      && BYTE1(v49[1].Blink) >= 2u )
    {
      WPP_SF_d(v49[1].Flink, 85, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, 874);
    }
    if ( v35 )
      goto LABEL_193;
    v14 = v67;
    goto LABEL_195;
  }
  if ( CertGetCertificateContextProperty(pCertContext, 3u, 0, &pcbData) || (v50 = GetLastError(), v12 = v50, v50 == 234) )
  {
    v54 = malloc(pcbData);
    v55 = v54;
    if ( v54 )
    {
      if ( CertGetCertificateContextProperty(pCertContext, 3u, v54, &pcbData) )
      {
        v56 = v78;
        v57 = hCertStore;
        *v79 = v55;
        *v56 = pcbData;
        v66 = v27;
        *v77 = v73;
        if ( !v12 )
        {
          hCertStore = v57;
          v66 = v27;
          goto LABEL_193;
        }
      }
      else
      {
        v12 = GetLastError();
        if ( !v12 )
          goto LABEL_193;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 84, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v12);
        }
      }
      free(v55);
      goto LABEL_193;
    }
    v53 = 14;
    v12 = 14;
    v51 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v52 = 83;
LABEL_174:
      WPP_SF_d(v51[1].Flink, v52, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v53);
    }
  }
  else if ( v50 )
  {
    v51 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v52 = 82;
      v53 = v50;
      goto LABEL_174;
    }
  }
LABEL_193:
  CertFreeCertificateChain(v35);
LABEL_35:
  v14 = v67;
LABEL_195:
  v15 = v66;
LABEL_196:
  CertCloseStore(hCertStore, 0);
LABEL_197:
  if ( !RevertToSelf() && !v12 )
    v12 = GetLastError();
  if ( v14 )
  {
    v58 = v69;
    for ( i = 0; (unsigned int)i < v58; i = (unsigned int)(i + 1) )
    {
      v60 = (void *)v14[i];
      if ( v60 )
      {
        free(v60);
        v14[i] = 0;
      }
    }
    free(v14);
  }
  if ( v15 )
  {
    v61 = v72;
    for ( j = 0; j < v61; ++j )
    {
      v63 = (void *)v15[2 * j + 1];
      if ( v63 )
      {
        free(v63);
        v15[2 * j + 1] = 0;
      }
    }
    free(v15);
  }
LABEL_212:
  v13 = WPP_GLOBAL_Control;
LABEL_213:
  if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(v13[1].Blink) & 0x2000) != 0 && BYTE1(v13[1].Blink) >= 5u )
    {
      LOBYTE(pvPara) = *v77 != 0;
      WPP_SF_dc(v13[1].Flink, 86, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, *v78, pvPara);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v13[1].Blink) & 0x2000) != 0
      && BYTE1(v13[1].Blink) >= 6u )
    {
      WPP_SF_d(v13[1].Flink, 87, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v12);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800598b4  push    rbp
0x1800598b6  push    rbx
0x1800598b7  push    rsi
0x1800598b8  push    rdi
0x1800598b9  push    r12
0x1800598bb  push    r13
0x1800598bd  push    r14
0x1800598bf  push    r15
0x1800598c1  lea     rbp, [rsp-7]
0x1800598c6  sub     rsp, 0F8h
0x1800598cd  mov     rax, cs:__security_cookie
0x1800598d4  xor     rax, rsp
0x1800598d7  mov     [rbp+3Fh+var_48], rax
0x1800598db  mov     rdi, [rbp+3Fh+arg_28]
0x1800598df  mov     eax, r8d
0x1800598e2  mov     r14, [rbp+3Fh+arg_30]
0x1800598e6  mov     r13, r9
0x1800598e9  mov     r15, [rbp+3Fh+arg_38]
0x1800598f0  mov     r12, rdx
0x1800598f3  mov     rbx, [rbp+3Fh+hToken]
0x1800598f7  mov     esi, ecx
0x1800598f9  mov     [rsp+130h+var_D0], eax
0x1800598fd  mov     [rsp+130h+var_DC], esi
0x180059901  mov     [rbp+3Fh+var_98], rdi
0x180059905  mov     [rbp+3Fh+var_A0], r14
0x180059909  mov     [rbp+3Fh+var_A8], r15
0x18005990d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059914  lea     rdx, WPP_GLOBAL_Control
0x18005991b  cmp     rcx, rdx
0x18005991e  jz      short loc_180059944
0x180059920  test    dword ptr [rcx+1Ch], 2000h
0x180059927  jz      short loc_180059944
0x180059929  cmp     byte ptr [rcx+19h], 6
0x18005992d  jb      short loc_180059944
0x18005992f  mov     rcx, [rcx+10h]
0x180059933  mov     r9d, esi
0x180059936  mov     qword ptr [rsp+130h+cbMultiByte], rbx
0x18005993b  mov     dword ptr [rsp+130h+pvPara], eax
0x18005993f  call    WPP_SF_ddq
0x180059944  xor     ecx, ecx
0x180059946  xorps   xmm0, xmm0
0x180059949  mov     [rdi], rcx
0x18005994c  xor     eax, eax
0x18005994e  mov     [r14], ecx
0x180059951  mov     [r15], ecx
0x180059954  mov     [rsp+130h+pcbData], ecx
0x180059958  mov     [rsp+130h+var_D8], ecx
0x18005995c  mov     [rsp+130h+var_C0], ecx
0x180059960  mov     [rsp+130h+var_E0], ecx
0x180059964  mov     [rsp+130h+var_C8], rcx
0x180059969  mov     qword ptr [rbp+3Fh+FileTime.dwLowDateTime], rcx
0x18005996d  mov     rcx, rbx; hToken
0x180059970  movups  [rbp+3Fh+pvFindPara], xmm0
0x180059974  mov     dword ptr [rbp+3Fh+var_60], eax
0x180059977  movups  [rbp+3Fh+var_80], xmm0
0x18005997b  movups  [rbp+3Fh+var_70], xmm0
0x18005997f  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x180059983  call    cs:__imp_ImpersonateLoggedOnUser
0x18005998a  nop     dword ptr [rax+rax+00h]
0x18005998f  test    eax, eax
0x180059991  jnz     short loc_1800599F4
0x180059993  call    cs:__imp_GetLastError
0x18005999a  nop     dword ptr [rax+rax+00h]
0x18005999f  mov     ebx, eax
0x1800599a1  test    eax, eax
0x1800599a3  jz      loc_18005A6AB
0x1800599a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800599b0  lea     rdi, WPP_GLOBAL_Control
0x1800599b7  cmp     rcx, rdi
0x1800599ba  jz      loc_18005A72A
0x1800599c0  test    dword ptr [rcx+1Ch], 2000h
0x1800599c7  jz      loc_18005A6B9
0x1800599cd  cmp     byte ptr [rcx+19h], 2
0x1800599d1  jb      loc_18005A6B9
0x1800599d7  mov     rcx, [rcx+10h]
0x1800599db  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x1800599e2  mov     edx, 37h ; '7'
0x1800599e7  mov     r9d, eax
0x1800599ea  call    WPP_SF_d
0x1800599ef  jmp     loc_18005A6B2
0x1800599f4  xor     r15d, r15d
0x1800599f7  lea     rax, aMy_0; "MY"
0x1800599fe  xor     r14d, r14d
0x180059a01  mov     [rsp+130h+var_E8], r15
0x180059a06  mov     r9d, 18000h; dwFlags
0x180059a0c  mov     [rsp+130h+var_F0], r14
0x180059a11  xor     r8d, r8d; hCryptProv
0x180059a14  mov     [rsp+130h+pvPara], rax; pvPara
0x180059a19  lea     ecx, [r15+0Ah]; lpszStoreProvider
0x180059a1d  mov     edx, 10001h; dwEncodingType
0x180059a22  call    cs:__imp_CertOpenStore
0x180059a29  nop     dword ptr [rax+rax+00h]
0x180059a2e  mov     [rbp+3Fh+hCertStore], rax
0x180059a32  test    rax, rax
0x180059a35  jnz     short loc_180059A97
0x180059a37  call    cs:__imp_GetLastError
0x180059a3e  nop     dword ptr [rax+rax+00h]
0x180059a43  mov     ebx, eax
0x180059a45  test    eax, eax
0x180059a47  jz      loc_18005A5FA
0x180059a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a54  lea     rax, WPP_GLOBAL_Control
0x180059a5b  cmp     rcx, rax
0x180059a5e  jz      loc_18005A5FA
0x180059a64  test    dword ptr [rcx+1Ch], 2000h
0x180059a6b  jz      loc_18005A5FA
0x180059a71  cmp     byte ptr [rcx+19h], 2
0x180059a75  jb      loc_18005A5FA
0x180059a7b  mov     rcx, [rcx+10h]
0x180059a7f  lea     edx, [r15+38h]
0x180059a83  mov     r9d, ebx
0x180059a86  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180059a8d  call    WPP_SF_d
0x180059a92  jmp     loc_18005A5FA
0x180059a97  test    esi, esi
0x180059a99  jz      loc_180059CCB
0x180059a9f  mov     rbx, rsi
0x180059aa2  shl     rbx, 3
0x180059aa6  mov     rcx, rbx; Size
0x180059aa9  call    cs:__imp_malloc
0x180059ab0  nop     dword ptr [rax+rax+00h]
0x180059ab5  mov     [rsp+130h+var_E8], rax
0x180059aba  mov     r15, rax
0x180059abd  test    rax, rax
0x180059ac0  jnz     short loc_180059B10
0x180059ac2  lea     r9d, [rax+0Eh]
0x180059ac6  mov     ebx, r9d
0x180059ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180059ad0  lea     rax, WPP_GLOBAL_Control
0x180059ad7  cmp     rcx, rax
0x180059ada  jz      loc_18005A5E8
0x180059ae0  test    dword ptr [rcx+1Ch], 2000h
0x180059ae7  jz      loc_18005A5E8
0x180059aed  cmp     byte ptr [rcx+19h], 2
0x180059af1  jb      loc_18005A5E8
0x180059af7  mov     rcx, [rcx+10h]
0x180059afb  lea     edx, [r15+39h]
0x180059aff  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180059b06  call    WPP_SF_d
0x180059b0b  jmp     loc_18005A5E8
0x180059b10  mov     r8, rbx; Size
0x180059b13  xor     edx, edx; Val
0x180059b15  mov     rcx, rax; void *
0x180059b18  call    memset_0
0x180059b1d  xor     edi, edi
0x180059b1f  mov     r8, [r12+rdi*8]; lpWideCharStr
0x180059b23  or      r9d, 0FFFFFFFFh; cchWideChar
0x180059b27  mov     [rsp+130h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180059b30  mov     edx, 400h; dwFlags
0x180059b35  mov     [rsp+130h+lpDefaultChar], 0; lpDefaultChar
0x180059b3e  xor     ecx, ecx; CodePage
0x180059b40  mov     [rsp+130h+cbMultiByte], 0; cbMultiByte
0x180059b48  mov     [rsp+130h+pvPara], 0; lpMultiByteStr
0x180059b51  call    cs:__imp_WideCharToMultiByte
0x180059b58  nop     dword ptr [rax+rax+00h]
0x180059b5d  movsxd  r14, eax
0x180059b60  test    eax, eax
0x180059b62  jz      loc_180059C6A
0x180059b68  mov     rcx, r14; Size
0x180059b6b  call    cs:__imp_malloc
0x180059b72  nop     dword ptr [rax+rax+00h]
0x180059b77  mov     rbx, rax
0x180059b7a  test    rax, rax
0x180059b7d  jz      loc_180059C39
0x180059b83  mov     r8, r14; Size
0x180059b86  xor     edx, edx; Val
0x180059b88  mov     rcx, rax; void *
0x180059b8b  call    memset_0
0x180059b90  mov     r8, [r12+rdi*8]; lpWideCharStr
0x180059b94  or      r9d, 0FFFFFFFFh; cchWideChar
0x180059b98  mov     [rsp+130h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180059ba1  mov     edx, 400h; dwFlags
0x180059ba6  mov     [rsp+130h+lpDefaultChar], 0; lpDefaultChar
0x180059baf  xor     ecx, ecx; CodePage
0x180059bb1  mov     [rsp+130h+cbMultiByte], r14d; cbMultiByte
0x180059bb6  mov     [rsp+130h+pvPara], rbx; lpMultiByteStr
0x180059bbb  call    cs:__imp_WideCharToMultiByte
0x180059bc2  nop     dword ptr [rax+rax+00h]
0x180059bc7  test    eax, eax
0x180059bc9  jz      short loc_180059BE3
0x180059bcb  mov     r15, [rsp+130h+var_E8]
0x180059bd0  mov     [r15+rdi*8], rbx
0x180059bd4  inc     edi
0x180059bd6  cmp     edi, esi
0x180059bd8  jb      loc_180059B1F
0x180059bde  jmp     loc_180059CCD
0x180059be3  call    cs:__imp_GetLastError
0x180059bea  nop     dword ptr [rax+rax+00h]
0x180059bef  mov     ebx, eax
0x180059bf1  test    eax, eax
0x180059bf3  jz      short loc_180059C2F
0x180059bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180059bfc  lea     rax, WPP_GLOBAL_Control
0x180059c03  cmp     rcx, rax
0x180059c06  jz      short loc_180059C2F
0x180059c08  test    dword ptr [rcx+1Ch], 2000h
0x180059c0f  jz      short loc_180059C2F
0x180059c11  cmp     byte ptr [rcx+19h], 2
0x180059c15  jb      short loc_180059C2F
0x180059c17  mov     edx, 3Ch ; '<'
0x180059c1c  mov     r9d, ebx
0x180059c1f  mov     rcx, [rcx+10h]
0x180059c23  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180059c2a  call    WPP_SF_d
0x180059c2f  mov     r15, [rsp+130h+var_E8]
0x180059c34  jmp     loc_18005A5E3
0x180059c39  mov     r9d, 0Eh
0x180059c3f  mov     ebx, r9d
0x180059c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c49  lea     rax, WPP_GLOBAL_Control
0x180059c50  cmp     rcx, rax
0x180059c53  jz      short loc_180059C2F
0x180059c55  test    dword ptr [rcx+1Ch], 2000h
0x180059c5c  jz      short loc_180059C2F
0x180059c5e  cmp     byte ptr [rcx+19h], 2
0x180059c62  jb      short loc_180059C2F
0x180059c64  lea     edx, [r9+2Dh]
0x180059c68  jmp     short loc_180059C1F
0x180059c6a  call    cs:__imp_GetLastError
0x180059c71  nop     dword ptr [rax+rax+00h]
0x180059c76  mov     ebx, eax
0x180059c78  test    eax, eax
0x180059c7a  jz      loc_18005A5E3
0x180059c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c87  lea     rax, WPP_GLOBAL_Control
0x180059c8e  cmp     rcx, rax
0x180059c91  jz      loc_18005A5E3
0x180059c97  test    dword ptr [rcx+1Ch], 2000h
0x180059c9e  jz      loc_18005A5E3
0x180059ca4  cmp     byte ptr [rcx+19h], 2
0x180059ca8  jb      loc_18005A5E3
0x180059cae  mov     rcx, [rcx+10h]
0x180059cb2  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180059cb9  mov     edx, 3Ah ; ':'
0x180059cbe  mov     r9d, ebx
0x180059cc1  call    WPP_SF_d
0x180059cc6  jmp     loc_18005A5E3
0x180059ccb  xor     edi, edi
0x180059ccd  mov     ebx, [rsp+130h+var_D0]
0x180059cd1  test    ebx, ebx
0x180059cd3  jz      loc_180059E0C
0x180059cd9  shl     rbx, 4
0x180059cdd  mov     rcx, rbx; Size
0x180059ce0  call    cs:__imp_malloc
0x180059ce7  nop     dword ptr [rax+rax+00h]
0x180059cec  mov     [rsp+130h+var_F0], rax
0x180059cf1  mov     r12, rax
0x180059cf4  test    rax, rax
0x180059cf7  jnz     short loc_180059D3F
0x180059cf9  lea     r9d, [rax+0Eh]
0x180059cfd  mov     ebx, r9d
0x180059d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d07  lea     rax, WPP_GLOBAL_Control
0x180059d0e  cmp     rcx, rax
0x180059d11  jz      short loc_180059D37
0x180059d13  test    dword ptr [rcx+1Ch], 2000h
0x180059d1a  jz      short loc_180059D37
0x180059d1c  cmp     byte ptr [rcx+19h], 2
0x180059d20  jb      short loc_180059D37
0x180059d22  lea     edx, [r12+3Dh]
0x180059d27  mov     rcx, [rcx+10h]
0x180059d2b  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180059d32  call    WPP_SF_d
0x180059d37  mov     r14, r12
0x180059d3a  jmp     loc_18005A5E8
0x180059d3f  mov     r8, rbx; Size
0x180059d42  xor     edx, edx; Val
0x180059d44  mov     rcx, r12; void *
0x180059d47  call    memset_0
0x180059d4c  xor     edi, edi
0x180059d4e  mov     rcx, [r13+rdi*8+0]
0x180059d53  lea     r8, [rsp+130h+var_C8]
0x180059d58  lea     rdx, [rsp+130h+var_E0]
0x180059d5d  mov     esi, edi
0x180059d5f  call    ConvertHexStringToBlob
0x180059d64  mov     ebx, eax
0x180059d66  test    eax, eax
0x180059d68  jnz     short loc_180059DD7
0x180059d6a  mov     rcx, [rsp+130h+var_C8]
0x180059d6f  test    rcx, rcx
0x180059d72  jz      short loc_180059D9D
0x180059d74  mov     eax, [rsp+130h+var_E0]
0x180059d78  add     rsi, rsi
0x180059d7b  mov     [rsp+130h+var_E0], ebx
0x180059d7f  inc     edi
0x180059d81  mov     ebx, [rsp+130h+var_D0]
0x180059d85  mov     [rsp+130h+var_C8], 0
0x180059d8e  mov     [r12+rsi*8], eax
0x180059d92  mov     [r12+rsi*8+8], rcx
0x180059d97  cmp     edi, ebx
0x180059d99  jb      short loc_180059D4E
0x180059d9b  jmp     short loc_180059E11
0x180059d9d  mov     ebx, 57h ; 'W'
0x180059da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180059da9  lea     rax, WPP_GLOBAL_Control
0x180059db0  cmp     rcx, rax
0x180059db3  jz      short loc_180059D37
0x180059db5  test    dword ptr [rcx+1Ch], 2000h
0x180059dbc  jz      loc_180059D37
0x180059dc2  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
