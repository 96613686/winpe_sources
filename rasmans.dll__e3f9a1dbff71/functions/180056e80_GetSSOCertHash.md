# GetSSOCertHash

- ea: `0x180056e80`
- end: `0x180057c64`
- name: `GetSSOCertHash`
- size: `3556`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hToken, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800584e0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x1800498f4`
- `0x180055c04`
- `0x1800560e8`
- `0x180056438`
- `0x180056e80`
- `0x180057c6c`
- `0x1800594e8`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!malloc` at `0x18005705d`
- `msvcrt!malloc` at `0x180057113`
- `msvcrt!malloc` at `0x180057270`
- `msvcrt!malloc` at `0x18005798f`
- `msvcrt!malloc` at `0x18005705d`
- `msvcrt!malloc` at `0x180057113`
- `msvcrt!malloc` at `0x180057270`
- `msvcrt!malloc` at `0x18005798f`
- `msvcrt!free` at `0x180057a7e`
- `msvcrt!free` at `0x180057b66`
- `msvcrt!free` at `0x180057b7e`
- `msvcrt!free` at `0x180057ba4`
- `msvcrt!free` at `0x180057bbd`
- `msvcrt!free` at `0x180057a7e`
- `msvcrt!free` at `0x180057b66`
- `msvcrt!free` at `0x180057b7e`
- `msvcrt!free` at `0x180057ba4`
- `msvcrt!free` at `0x180057bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005717f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005793f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005717f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005793f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b44`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180056f4f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180056f4f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180057b36`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180057b36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800574f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800574f8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800570ff`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005715d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800570ff`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005715d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180057506`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180057506`
- `CRYPT32!CertFindChainInStore` at `0x18005742e`
- `CRYPT32!CertFindChainInStore` at `0x18005742e`
- `CRYPT32!CertVerifyTimeValidity` at `0x18005755d`
- `CRYPT32!CertVerifyTimeValidity` at `0x18005755d`
- `CRYPT32!CertCloseStore` at `0x180057b30`
- `CRYPT32!CertCloseStore` at `0x180057b30`
- `CRYPT32!CertFreeCertificateChain` at `0x180057b17`
- `CRYPT32!CertFreeCertificateChain` at `0x180057b17`
- `CRYPT32!CertOpenStore` at `0x180056fe2`
- `CRYPT32!CertOpenStore` at `0x180056fe2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057935`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800579f7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057935`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800579f7`

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
  int v32; // eax
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
  int v68; // [rsp+50h] [rbp-A1h] BYREF
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
        v68 = 0;
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
0x180056e80  push    rbp
0x180056e82  push    rbx
0x180056e83  push    rsi
0x180056e84  push    rdi
0x180056e85  push    r12
0x180056e87  push    r13
0x180056e89  push    r14
0x180056e8b  push    r15
0x180056e8d  lea     rbp, [rsp-7]
0x180056e92  sub     rsp, 0F8h
0x180056e99  mov     rax, cs:__security_cookie
0x180056ea0  xor     rax, rsp
0x180056ea3  mov     [rbp+3Fh+var_48], rax
0x180056ea7  mov     rdi, [rbp+3Fh+arg_28]
0x180056eab  mov     eax, r8d
0x180056eae  mov     r14, [rbp+3Fh+arg_30]
0x180056eb2  mov     r13, r9
0x180056eb5  mov     r15, [rbp+3Fh+arg_38]
0x180056ebc  mov     r12, rdx
0x180056ebf  mov     rbx, [rbp+3Fh+hToken]
0x180056ec3  mov     esi, ecx
0x180056ec5  mov     [rsp+130h+var_D0], eax
0x180056ec9  mov     [rsp+130h+var_DC], esi
0x180056ecd  mov     [rbp+3Fh+var_98], rdi
0x180056ed1  mov     [rbp+3Fh+var_A0], r14
0x180056ed5  mov     [rbp+3Fh+var_A8], r15
0x180056ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ee0  lea     rdx, WPP_GLOBAL_Control
0x180056ee7  cmp     rcx, rdx
0x180056eea  jz      short loc_180056F10
0x180056eec  test    dword ptr [rcx+1Ch], 2000h
0x180056ef3  jz      short loc_180056F10
0x180056ef5  cmp     byte ptr [rcx+19h], 6
0x180056ef9  jb      short loc_180056F10
0x180056efb  mov     rcx, [rcx+10h]
0x180056eff  mov     r9d, esi
0x180056f02  mov     qword ptr [rsp+130h+cbMultiByte], rbx
0x180056f07  mov     dword ptr [rsp+130h+pvPara], eax
0x180056f0b  call    WPP_SF_ddq
0x180056f10  xor     ecx, ecx
0x180056f12  xorps   xmm0, xmm0
0x180056f15  mov     [rdi], rcx
0x180056f18  xor     eax, eax
0x180056f1a  mov     [r14], ecx
0x180056f1d  mov     [r15], ecx
0x180056f20  mov     [rsp+130h+pcbData], ecx
0x180056f24  mov     [rsp+130h+var_D8], ecx
0x180056f28  mov     [rsp+130h+var_C0], ecx
0x180056f2c  mov     [rsp+130h+var_E0], ecx
0x180056f30  mov     [rsp+130h+var_C8], rcx
0x180056f35  mov     qword ptr [rbp+3Fh+FileTime.dwLowDateTime], rcx
0x180056f39  mov     rcx, rbx; hToken
0x180056f3c  movups  [rbp+3Fh+pvFindPara], xmm0
0x180056f40  mov     dword ptr [rbp+3Fh+var_60], eax
0x180056f43  movups  [rbp+3Fh+var_80], xmm0
0x180056f47  movups  [rbp+3Fh+var_70], xmm0
0x180056f4b  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x180056f4f  call    cs:__imp_ImpersonateLoggedOnUser
0x180056f55  test    eax, eax
0x180056f57  jnz     short loc_180056FB4
0x180056f59  call    cs:__imp_GetLastError
0x180056f5f  mov     ebx, eax
0x180056f61  test    eax, eax
0x180056f63  jz      loc_180057BC3
0x180056f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f70  lea     rdi, WPP_GLOBAL_Control
0x180056f77  cmp     rcx, rdi
0x180056f7a  jz      loc_180057C42
0x180056f80  test    dword ptr [rcx+1Ch], 2000h
0x180056f87  jz      loc_180057BD1
0x180056f8d  cmp     byte ptr [rcx+19h], 2
0x180056f91  jb      loc_180057BD1
0x180056f97  mov     rcx, [rcx+10h]
0x180056f9b  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180056fa2  mov     edx, 37h ; '7'
0x180056fa7  mov     r9d, eax
0x180056faa  call    WPP_SF_d
0x180056faf  jmp     loc_180057BCA
0x180056fb4  xor     r15d, r15d
0x180056fb7  lea     rax, aMy_0; "MY"
0x180056fbe  xor     r14d, r14d
0x180056fc1  mov     [rsp+130h+var_E8], r15
0x180056fc6  mov     r9d, 18000h; dwFlags
0x180056fcc  mov     [rsp+130h+var_F0], r14
0x180056fd1  xor     r8d, r8d; hCryptProv
0x180056fd4  mov     [rsp+130h+pvPara], rax; pvPara
0x180056fd9  lea     ecx, [r15+0Ah]; lpszStoreProvider
0x180056fdd  mov     edx, 10001h; dwEncodingType
0x180056fe2  call    cs:__imp_CertOpenStore
0x180056fe8  mov     [rbp+3Fh+hCertStore], rax
0x180056fec  test    rax, rax
0x180056fef  jnz     short loc_18005704B
0x180056ff1  call    cs:__imp_GetLastError
0x180056ff7  mov     ebx, eax
0x180056ff9  test    eax, eax
0x180056ffb  jz      loc_180057B36
0x180057001  mov     rcx, cs:WPP_GLOBAL_Control
0x180057008  lea     rax, WPP_GLOBAL_Control
0x18005700f  cmp     rcx, rax
0x180057012  jz      loc_180057B36
0x180057018  test    dword ptr [rcx+1Ch], 2000h
0x18005701f  jz      loc_180057B36
0x180057025  cmp     byte ptr [rcx+19h], 2
0x180057029  jb      loc_180057B36
0x18005702f  mov     rcx, [rcx+10h]
0x180057033  lea     edx, [r15+38h]
0x180057037  mov     r9d, ebx
0x18005703a  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180057041  call    WPP_SF_d
0x180057046  jmp     loc_180057B36
0x18005704b  test    esi, esi
0x18005704d  jz      loc_18005725B
0x180057053  mov     rbx, rsi
0x180057056  shl     rbx, 3
0x18005705a  mov     rcx, rbx; Size
0x18005705d  call    cs:__imp_malloc
0x180057063  mov     [rsp+130h+var_E8], rax
0x180057068  mov     r15, rax
0x18005706b  test    rax, rax
0x18005706e  jnz     short loc_1800570BE
0x180057070  lea     r9d, [rax+0Eh]
0x180057074  mov     ebx, r9d
0x180057077  mov     rcx, cs:WPP_GLOBAL_Control
0x18005707e  lea     rax, WPP_GLOBAL_Control
0x180057085  cmp     rcx, rax
0x180057088  jz      loc_180057B2A
0x18005708e  test    dword ptr [rcx+1Ch], 2000h
0x180057095  jz      loc_180057B2A
0x18005709b  cmp     byte ptr [rcx+19h], 2
0x18005709f  jb      loc_180057B2A
0x1800570a5  mov     rcx, [rcx+10h]
0x1800570a9  lea     edx, [r15+39h]
0x1800570ad  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x1800570b4  call    WPP_SF_d
0x1800570b9  jmp     loc_180057B2A
0x1800570be  mov     r8, rbx; Size
0x1800570c1  xor     edx, edx; Val
0x1800570c3  mov     rcx, rax; void *
0x1800570c6  call    memset_0
0x1800570cb  xor     edi, edi
0x1800570cd  mov     r8, [r12+rdi*8]; lpWideCharStr
0x1800570d1  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800570d5  mov     [rsp+130h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800570de  mov     edx, 400h; dwFlags
0x1800570e3  mov     [rsp+130h+lpDefaultChar], 0; lpDefaultChar
0x1800570ec  xor     ecx, ecx; CodePage
0x1800570ee  mov     [rsp+130h+cbMultiByte], 0; cbMultiByte
0x1800570f6  mov     [rsp+130h+pvPara], 0; lpMultiByteStr
0x1800570ff  call    cs:__imp_WideCharToMultiByte
0x180057105  movsxd  r14, eax
0x180057108  test    eax, eax
0x18005710a  jz      loc_180057200
0x180057110  mov     rcx, r14; Size
0x180057113  call    cs:__imp_malloc
0x180057119  mov     rbx, rax
0x18005711c  test    rax, rax
0x18005711f  jz      loc_1800571CF
0x180057125  mov     r8, r14; Size
0x180057128  xor     edx, edx; Val
0x18005712a  mov     rcx, rax; void *
0x18005712d  call    memset_0
0x180057132  mov     r8, [r12+rdi*8]; lpWideCharStr
0x180057136  or      r9d, 0FFFFFFFFh; cchWideChar
0x18005713a  mov     [rsp+130h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180057143  mov     edx, 400h; dwFlags
0x180057148  mov     [rsp+130h+lpDefaultChar], 0; lpDefaultChar
0x180057151  xor     ecx, ecx; CodePage
0x180057153  mov     [rsp+130h+cbMultiByte], r14d; cbMultiByte
0x180057158  mov     [rsp+130h+pvPara], rbx; lpMultiByteStr
0x18005715d  call    cs:__imp_WideCharToMultiByte
0x180057163  test    eax, eax
0x180057165  jz      short loc_18005717F
0x180057167  mov     r15, [rsp+130h+var_E8]
0x18005716c  mov     [r15+rdi*8], rbx
0x180057170  inc     edi
0x180057172  cmp     edi, esi
0x180057174  jb      loc_1800570CD
0x18005717a  jmp     loc_18005725D
0x18005717f  call    cs:__imp_GetLastError
0x180057185  mov     ebx, eax
0x180057187  test    eax, eax
0x180057189  jz      short loc_1800571C5
0x18005718b  mov     rcx, cs:WPP_GLOBAL_Control
0x180057192  lea     rax, WPP_GLOBAL_Control
0x180057199  cmp     rcx, rax
0x18005719c  jz      short loc_1800571C5
0x18005719e  test    dword ptr [rcx+1Ch], 2000h
0x1800571a5  jz      short loc_1800571C5
0x1800571a7  cmp     byte ptr [rcx+19h], 2
0x1800571ab  jb      short loc_1800571C5
0x1800571ad  mov     edx, 3Ch ; '<'
0x1800571b2  mov     r9d, ebx
0x1800571b5  mov     rcx, [rcx+10h]
0x1800571b9  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x1800571c0  call    WPP_SF_d
0x1800571c5  mov     r15, [rsp+130h+var_E8]
0x1800571ca  jmp     loc_180057B25
0x1800571cf  mov     r9d, 0Eh
0x1800571d5  mov     ebx, r9d
0x1800571d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571df  lea     rax, WPP_GLOBAL_Control
0x1800571e6  cmp     rcx, rax
0x1800571e9  jz      short loc_1800571C5
0x1800571eb  test    dword ptr [rcx+1Ch], 2000h
0x1800571f2  jz      short loc_1800571C5
0x1800571f4  cmp     byte ptr [rcx+19h], 2
0x1800571f8  jb      short loc_1800571C5
0x1800571fa  lea     edx, [r9+2Dh]
0x1800571fe  jmp     short loc_1800571B5
0x180057200  call    cs:__imp_GetLastError
0x180057206  mov     ebx, eax
0x180057208  test    eax, eax
0x18005720a  jz      loc_180057B25
0x180057210  mov     rcx, cs:WPP_GLOBAL_Control
0x180057217  lea     rax, WPP_GLOBAL_Control
0x18005721e  cmp     rcx, rax
0x180057221  jz      loc_180057B25
0x180057227  test    dword ptr [rcx+1Ch], 2000h
0x18005722e  jz      loc_180057B25
0x180057234  cmp     byte ptr [rcx+19h], 2
0x180057238  jb      loc_180057B25
0x18005723e  mov     rcx, [rcx+10h]
0x180057242  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180057249  mov     edx, 3Ah ; ':'
0x18005724e  mov     r9d, ebx
0x180057251  call    WPP_SF_d
0x180057256  jmp     loc_180057B25
0x18005725b  xor     edi, edi
0x18005725d  mov     ebx, [rsp+130h+var_D0]
0x180057261  test    ebx, ebx
0x180057263  jz      loc_180057396
0x180057269  shl     rbx, 4
0x18005726d  mov     rcx, rbx; Size
0x180057270  call    cs:__imp_malloc
0x180057276  mov     [rsp+130h+var_F0], rax
0x18005727b  mov     r12, rax
0x18005727e  test    rax, rax
0x180057281  jnz     short loc_1800572C9
0x180057283  lea     r9d, [rax+0Eh]
0x180057287  mov     ebx, r9d
0x18005728a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057291  lea     rax, WPP_GLOBAL_Control
0x180057298  cmp     rcx, rax
0x18005729b  jz      short loc_1800572C1
0x18005729d  test    dword ptr [rcx+1Ch], 2000h
0x1800572a4  jz      short loc_1800572C1
0x1800572a6  cmp     byte ptr [rcx+19h], 2
0x1800572aa  jb      short loc_1800572C1
0x1800572ac  lea     edx, [r12+3Dh]
0x1800572b1  mov     rcx, [rcx+10h]
0x1800572b5  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x1800572bc  call    WPP_SF_d
0x1800572c1  mov     r14, r12
0x1800572c4  jmp     loc_180057B2A
0x1800572c9  mov     r8, rbx; Size
0x1800572cc  xor     edx, edx; Val
0x1800572ce  mov     rcx, r12; void *
0x1800572d1  call    memset_0
0x1800572d6  xor     edi, edi
0x1800572d8  mov     rcx, [r13+rdi*8+0]
0x1800572dd  lea     r8, [rsp+130h+var_C8]
0x1800572e2  lea     rdx, [rsp+130h+var_E0]
0x1800572e7  mov     esi, edi
0x1800572e9  call    ConvertHexStringToBlob
0x1800572ee  mov     ebx, eax
0x1800572f0  test    eax, eax
0x1800572f2  jnz     short loc_180057361
0x1800572f4  mov     rcx, [rsp+130h+var_C8]
0x1800572f9  test    rcx, rcx
0x1800572fc  jz      short loc_180057327
0x1800572fe  mov     eax, [rsp+130h+var_E0]
0x180057302  add     rsi, rsi
0x180057305  mov     [rsp+130h+var_E0], ebx
0x180057309  inc     edi
0x18005730b  mov     ebx, [rsp+130h+var_D0]
0x18005730f  mov     [rsp+130h+var_C8], 0
0x180057318  mov     [r12+rsi*8], eax
0x18005731c  mov     [r12+rsi*8+8], rcx
0x180057321  cmp     edi, ebx
0x180057323  jb      short loc_1800572D8
0x180057325  jmp     short loc_18005739B
0x180057327  mov     ebx, 57h ; 'W'
0x18005732c  mov     rcx, cs:WPP_GLOBAL_Control
0x180057333  lea     rax, WPP_GLOBAL_Control
0x18005733a  cmp     rcx, rax
0x18005733d  jz      short loc_1800572C1
0x18005733f  test    dword ptr [rcx+1Ch], 2000h
0x180057346  jz      loc_1800572C1
0x18005734c  cmp     byte ptr [rcx+19h], 2
0x180057350  jb      loc_1800572C1
0x180057356  lea     edx, [rbx-18h]
0x180057359  mov     r9d, ebx
0x18005735c  jmp     loc_1800572B1
0x180057361  mov     rcx, cs:WPP_GLOBAL_Control
0x180057368  lea     rax, WPP_GLOBAL_Control
0x18005736f  cmp     rcx, rax
0x180057372  jz      loc_1800572C1
0x180057378  test    dword ptr [rcx+1Ch], 2000h
0x18005737f  jz      loc_1800572C1
0x180057385  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
