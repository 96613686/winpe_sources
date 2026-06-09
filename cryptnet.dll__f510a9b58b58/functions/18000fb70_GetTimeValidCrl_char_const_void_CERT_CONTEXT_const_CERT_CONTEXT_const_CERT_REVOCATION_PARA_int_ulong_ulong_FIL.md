# GetTimeValidCrl(char const *,void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *)

- ea: `0x18000fb70`
- end: `0x1800101d7`
- name: `?GetTimeValidCrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@2PEAU_CERT_REVOCATION_PARA@@HKKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH@Z`
- size: `1639`
- prototype: `__int64 __fastcall(const char *, void *, const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *, struct _CERT_REVOCATION_PARA *ppvFuncAddr, int, unsigned int, char, struct _FILETIME *lpFileTime1, LPVOID *, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f140`
- `0x18000f980`
- `0x1800105e0`

## callees

- `0x18000fb70`
- `0x1800101e0`
- `0x180010ba0`
- `0x180010cf4`
- `0x180010e80`
- `0x1800189b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fd39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fd39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001009a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001009a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001000d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001000d`
- `CRYPT32!I_CertDiagControl` at `0x180010042`
- `CRYPT32!I_CertDiagControl` at `0x180010042`
- `CRYPT32!CertFreeCRLContext` at `0x180010164`
- `CRYPT32!CertFreeCRLContext` at `0x180010164`
- `CRYPT32!CertDuplicateCRLContext` at `0x18001016f`
- `CRYPT32!CertDuplicateCRLContext` at `0x18001016f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000fee9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000fee9`
- `CRYPT32!CertFindCRLInStore` at `0x18000fdb9`
- `CRYPT32!CertFindCRLInStore` at `0x18001019a`
- `CRYPT32!CertFindCRLInStore` at `0x18000fdb9`
- `CRYPT32!CertFindCRLInStore` at `0x18001019a`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x180010090`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x180010090`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x18000fccf`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x18000ff29`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x18000fccf`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x18000ff29`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000fd31`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000ff75`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000fd31`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000ff75`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800100e3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010120`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010156`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800100e3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010120`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180010156`

## pseudocode

```c
__int64 __fastcall GetTimeValidCrl(
        const char *a1,
        void *a2,
        const struct _CERT_CONTEXT *a3,
        const struct _CERT_CONTEXT *a4,
        struct _CERT_REVOCATION_PARA *ppvFuncAddr,
        int a6,
        unsigned int a7,
        char a8,
        struct _FILETIME *lpFileTime1,
        LPVOID *a10,
        int *a11)
{
  struct _CERT_REVOCATION_PARA *v11; // rdi
  HCERTSTORE hCrlStore; // r10
  struct _CERT_REVOCATION_CHAIN_PARA *pftTimeToUse; // rdx
  int v16; // r8d
  FILETIME *v17; // r15
  int v18; // ecx
  LPVOID *ppvObject; // r13
  int v20; // eax
  struct _FILETIME *v21; // r9
  int v22; // r14d
  unsigned int v23; // ebx
  unsigned int TimeValidObject; // esi
  int v26; // r12d
  unsigned int v27; // r14d
  struct _FILETIME *p_SystemTimeAsFileTime; // r9
  DWORD LastError; // ebx
  HCERTSTORE v30; // rbx
  DWORD v31; // eax
  DWORD v32; // r13d
  PCCRL_CONTEXT CRLInStore; // rax
  DWORD v34; // ecx
  DWORD v35; // eax
  int v36; // edi
  DWORD v37; // ebx
  __int64 v38; // rax
  struct _FILETIME v39; // rax
  const struct _CRL_CONTEXT **v40; // r12
  DWORD v41; // eax
  DWORD v42; // eax
  const FILETIME *v43; // rdx
  LONG v44; // eax
  const CRL_CONTEXT *v45; // rcx
  LONG v46; // eax
  struct _CRL_CONTEXT *v47; // rax
  DWORD pcbData[2]; // [rsp+50h] [rbp-81h] BYREF
  DWORD v49; // [rsp+58h] [rbp-79h]
  PCRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO pExtraInfo; // [rsp+60h] [rbp-71h] BYREF
  int v51; // [rsp+68h] [rbp-69h]
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+70h] [rbp-61h] BYREF
  void *pvFindPara[2]; // [rsp+78h] [rbp-59h] BYREF
  __int64 v54; // [rsp+88h] [rbp-49h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-41h] BYREF
  const wchar_t *v56; // [rsp+98h] [rbp-39h]
  _OWORD v57[2]; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v58; // [rsp+C0h] [rbp-11h]

  v11 = ppvFuncAddr;
  v54 = 0;
  memset(v57, 0, sizeof(v57));
  hCrlStore = ppvFuncAddr[1].hCrlStore;
  v58 = 0;
  if ( __PAIR128__(ppvFuncAddr[1].pftTimeToUse, (unsigned __int64)hCrlStore) == 0 )
  {
    pExtraInfo = 0;
    pftTimeToUse = 0;
  }
  else
  {
    pftTimeToUse = (struct _CERT_REVOCATION_CHAIN_PARA *)ppvFuncAddr[1].pftTimeToUse;
    *(_QWORD *)&v58 = pftTimeToUse;
    pExtraInfo = (PCRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO)v57;
    LODWORD(v57[0]) = 48;
    *((_QWORD *)&v57[0] + 1) = hCrlStore;
  }
  v16 = *(&ppvFuncAddr[1].cbSize + 1);
  v17 = *(FILETIME **)&ppvFuncAddr[1].cCertStore;
  if ( v16 )
  {
    v39 = *v17;
    v17 = (FILETIME *)&v54;
    v18 = 1024;
    v54 = *(_QWORD *)&v39 - 10000000LL * LODWORD(ppvFuncAddr[1].pIssuerCert);
  }
  else
  {
    v18 = 0;
  }
  ppvObject = a10;
  v20 = v18 | 0x200;
  v51 = a8 & 1;
  v21 = v17;
  if ( (a8 & 1) == 0 )
    v20 = v18;
  v22 = v20 | 0x1000000;
  v23 = a7 & 8;
  v49 = v23;
  if ( (a7 & 8) == 0 )
    v22 = v20;
  if ( (a7 & 0x10) != 0 )
    v22 |= 0x2000000u;
  if ( (a7 & 8) != 0 )
    v21 = 0;
  LODWORD(ppvFuncAddr) = GetTimeValidCrlFromOcspResponseProperty(
                           a3,
                           a4,
                           v16,
                           v21,
                           pftTimeToUse,
                           (const struct _CRL_CONTEXT **)a10);
  TimeValidObject = (unsigned int)ppvFuncAddr;
  if ( (_DWORD)ppvFuncAddr || !v23 || (pcbData[0] = 0, !CertGetCertificateContextProperty(a3, 0x46u, 0, pcbData)) )
  {
    if ( TimeValidObject )
      return TimeValidObject;
    v26 = a6;
    v27 = v22 | 0x80000000;
    if ( a6 && (a7 & 0x20) == 0 )
    {
      TimeValidObject = 0;
      hFuncAddr = 0;
      pvFindPara[0] = 0;
      SystemTimeAsFileTime = 0;
      if ( CryptGetOIDFunctionAddress(hGetTimeValidObjectFuncSet, 1u, a1, 0, pvFindPara, &hFuncAddr) )
      {
        if ( v17 )
        {
          p_SystemTimeAsFileTime = v17;
        }
        else
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
        }
        TimeValidObject = ((__int64 (__fastcall *)(const char *, void *, const struct _CERT_CONTEXT *, struct _FILETIME *, unsigned int, _DWORD, LPVOID *, _QWORD, PCRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO))pvFindPara[0])(
                            a1,
                            a2,
                            a4,
                            p_SystemTimeAsFileTime,
                            v27 | 2,
                            0,
                            ppvObject,
                            0,
                            pExtraInfo);
        LODWORD(ppvFuncAddr) = TimeValidObject;
        LastError = GetLastError();
        CryptFreeOIDFunctionAddress(hFuncAddr, 0);
        SetLastError(LastError);
        if ( TimeValidObject )
          return TimeValidObject;
      }
      else
      {
        LODWORD(ppvFuncAddr) = 0;
      }
    }
    v30 = v11->hCrlStore;
    v31 = 0;
    *ppvObject = 0;
    if ( !v30 || v49 )
    {
LABEL_32:
      if ( !v26 )
      {
        SetLastError(0x80092012);
        return 0;
      }
      if ( (a7 & 2) != 0 || v51 )
      {
        if ( v30 )
          SetLastError(v31);
      }
      else
      {
        if ( (a7 & 4) != 0 )
        {
          v35 = I_CryptRemainingMilliseconds(lpFileTime1);
          v11[1].cbSize = v35;
          if ( !v35 )
            v11[1].cbSize = 1;
          v27 |= 0x800u;
        }
        TimeValidObject = CryptGetTimeValidObject(a1, a2, a4, v17, v27 | 4, v11[1].cbSize, ppvObject, 0, pExtraInfo);
        *a11 = 1;
        if ( TimeValidObject )
          return TimeValidObject;
      }
      if ( GetLastError() == -2146885628 )
        v34 = -2146885614;
      else
        v34 = -2146885613;
      SetLastError(v34);
      return TimeValidObject;
    }
    *(_OWORD *)pvFindPara = 0;
    v49 = GetLastError();
    v32 = 23;
    if ( (a8 & 2) == 0 )
      v32 = 27;
    pvFindPara[0] = (void *)a3;
    pvFindPara[1] = (void *)a4;
    CRLInStore = CertFindCRLInStore(v30, a4->dwCertEncodingType, v32, 3u, pvFindPara, 0);
    *(_QWORD *)pcbData = CRLInStore;
    if ( !CRLInStore )
    {
LABEL_28:
      ppvObject = a10;
      if ( *a10 )
        return 1;
      v31 = v49;
      goto LABEL_32;
    }
    v40 = (const struct _CRL_CONTEXT **)a10;
    while ( 1 )
    {
      v56 = L"Store";
      SystemTimeAsFileTime = (struct _FILETIME)CRLInStore;
      I_CertDiagControl(2, &SystemTimeAsFileTime, 0);
      if ( !(unsigned int)IsValidCrlIssuerKeyUsage(a4) )
      {
        v41 = GetLastError();
        CertDiagRejectCrl(pcbData[0], (unsigned int)L"IsCrlSignKeyUsagePresent", v41, 0, 0, 0);
        goto LABEL_74;
      }
      if ( !CertIsValidCRLForCertificate(a3, *(PCCRL_CONTEXT *)pcbData, 0, 0) )
      {
        v42 = GetLastError();
        CertDiagRejectCrl(pcbData[0], (unsigned int)L"Call_CertIsValidCRLForCertificate", v42, 0, 0, 0);
        goto LABEL_74;
      }
      if ( v51 )
      {
        v45 = *(const CRL_CONTEXT **)pcbData;
      }
      else
      {
        v43 = *(const FILETIME **)(*(_QWORD *)pcbData + 24LL);
        if ( *(&v11[1].cbSize + 1) )
        {
          v44 = CompareFileTime(v17, v43 + 6);
          v45 = *(const CRL_CONTEXT **)pcbData;
          if ( v44 > 0 )
          {
            CertDiagRejectCrl(pcbData[0], (unsigned int)L"CheckFreshnessTime", 1931, 0, 0, v27 | 2);
            goto LABEL_74;
          }
        }
        else
        {
          v46 = CompareFileTime(v17, v43 + 7);
          v45 = *(const CRL_CONTEXT **)pcbData;
          if ( v46 > 0 )
          {
            v38 = *(_QWORD *)(*(_QWORD *)pcbData + 24LL);
            if ( *(_DWORD *)(v38 + 56) || *(_DWORD *)(v38 + 60) )
            {
              CertDiagRejectCrl(pcbData[0], (unsigned int)L"CheckTimeValidity", 1931, 0, 0, v27 | 2);
              goto LABEL_74;
            }
          }
        }
      }
      v47 = (struct _CRL_CONTEXT *)*v40;
      hFuncAddr = v47;
      if ( !v47 )
        goto LABEL_73;
      if ( CompareFileTime(&v45->pCrlInfo->ThisUpdate, &v47->pCrlInfo->ThisUpdate) > 0 )
      {
        CertFreeCRLContext((PCCRL_CONTEXT)hFuncAddr);
        v45 = *(const CRL_CONTEXT **)pcbData;
LABEL_73:
        *v40 = CertDuplicateCRLContext(v45);
      }
LABEL_74:
      CRLInStore = CertFindCRLInStore(v30, a4->dwCertEncodingType, v32, 3u, pvFindPara, *(PCCRL_CONTEXT *)pcbData);
      *(_QWORD *)pcbData = CRLInStore;
      if ( !CRLInStore )
      {
        TimeValidObject = (unsigned int)ppvFuncAddr;
        v26 = a6;
        goto LABEL_28;
      }
    }
  }
  a7 = 0;
  pExtraInfo = 0;
  ppvFuncAddr = 0;
  if ( CryptGetOIDFunctionAddress(
         hGetObjectUrlFuncSet,
         1u,
         (LPCSTR)9,
         0,
         (void **)&ppvFuncAddr,
         (HCRYPTOIDFUNCADDR *)&pExtraInfo) )
  {
    v36 = ((__int64 (__fastcall *)(__int64, const struct _CERT_CONTEXT *, __int64, _QWORD, unsigned int *, _QWORD, _QWORD, _QWORD))ppvFuncAddr)(
            9,
            a3,
            15,
            0,
            &a7,
            0,
            0,
            0);
    v37 = GetLastError();
    CryptFreeOIDFunctionAddress(pExtraInfo, 0);
    SetLastError(v37);
  }
  else
  {
    v36 = 0;
  }
  SetLastError(-(v36 != 0) - 2146885612);
  return 0;
}

```

## disassembly

```asm
0x18000fb70  mov     [rsp-8+pIssuer], r9
0x18000fb75  mov     [rsp-8+pCert], r8
0x18000fb7a  mov     [rsp-8+pvPara], rdx
0x18000fb7f  mov     [rsp-8+pszOID], rcx
0x18000fb84  push    rbp
0x18000fb85  push    rbx
0x18000fb86  push    rsi
0x18000fb87  push    rdi
0x18000fb88  push    r12
0x18000fb8a  push    r13
0x18000fb8c  push    r14
0x18000fb8e  push    r15
0x18000fb90  lea     rbp, [rsp-7]
0x18000fb95  sub     rsp, 0D8h
0x18000fb9c  mov     rdi, [rbp+3Fh+arg_20]
0x18000fba0  xorps   xmm0, xmm0
0x18000fba3  xor     esi, esi
0x18000fba5  mov     r11, r9
0x18000fba8  mov     r12, r8
0x18000fbab  mov     [rbp+3Fh+var_88], rsi
0x18000fbaf  movups  [rbp+3Fh+var_70], xmm0
0x18000fbb3  mov     r10, [rdi+50h]
0x18000fbb7  movups  [rbp+3Fh+var_60], xmm0
0x18000fbbb  movups  [rbp+3Fh+var_50], xmm0
0x18000fbbf  test    r10, r10
0x18000fbc2  jnz     loc_18000FDE5
0x18000fbc8  cmp     [rdi+58h], rsi
0x18000fbcc  jnz     loc_18000FDE5
0x18000fbd2  mov     [rbp+3Fh+var_B0], rsi
0x18000fbd6  mov     edx, esi
0x18000fbd8  mov     r8d, [rdi+34h]; int
0x18000fbdc  mov     r15, [rdi+40h]
0x18000fbe0  test    r8d, r8d
0x18000fbe3  jnz     loc_18000FFDF
0x18000fbe9  mov     ecx, esi
0x18000fbeb  mov     r9d, dword ptr [rbp+3Fh+arg_38]
0x18000fbf2  mov     eax, ecx
0x18000fbf4  mov     r13, [rbp+3Fh+arg_48]
0x18000fbfb  and     r9d, 1
0x18000fbff  bts     eax, 9
0x18000fc03  mov     [rbp+3Fh+var_A8], r9d
0x18000fc07  test    r9d, r9d
0x18000fc0a  mov     [rsp+110h+phFuncAddr], r13; struct _CRL_CONTEXT **
0x18000fc0f  mov     [rsp+110h+ppvFuncAddr], rdx; struct _CERT_REVOCATION_CHAIN_PARA *
0x18000fc14  mov     r9, r15
0x18000fc17  cmovz   eax, ecx
0x18000fc1a  mov     rdx, r11; struct _CERT_CONTEXT *
0x18000fc1d  mov     ecx, [rbp+3Fh+arg_30]
0x18000fc20  mov     r14d, eax
0x18000fc23  bts     r14d, 18h
0x18000fc28  mov     ebx, ecx
0x18000fc2a  and     ebx, 8
0x18000fc2d  test    ebx, ebx
0x18000fc2f  mov     [rbp+3Fh+var_B8], ebx
0x18000fc32  cmovz   r14d, eax
0x18000fc36  mov     eax, r14d
0x18000fc39  bts     eax, 19h
0x18000fc3d  test    cl, 10h
0x18000fc40  mov     rcx, r12; struct _CERT_CONTEXT *
0x18000fc43  cmovnz  r14d, eax
0x18000fc47  test    ebx, ebx
0x18000fc49  cmovnz  r9, rsi; struct _FILETIME *
0x18000fc4d  call    ?GetTimeValidCrlFromOcspResponseProperty@@YAHPEBU_CERT_CONTEXT@@0HPEAU_FILETIME@@PEAU_CERT_REVOCATION_CHAIN_PARA@@PEAPEBU_CRL_CONTEXT@@@Z; GetTimeValidCrlFromOcspResponseProperty(_CERT_CONTEXT const *,_CERT_CONTEXT const *,int,_FILETIME *,_CERT_REVOCATION_CHAIN_PARA *,_CRL_CONTEXT const * *)
0x18000fc52  mov     dword ptr [rbp+3Fh+arg_20], eax
0x18000fc55  mov     esi, eax
0x18000fc57  test    eax, eax
0x18000fc59  jnz     short loc_18000FC63
0x18000fc5b  test    ebx, ebx
0x18000fc5d  jnz     loc_18000FED3
0x18000fc63  test    esi, esi
0x18000fc65  jz      short loc_18000FC7D
0x18000fc67  mov     eax, esi
0x18000fc69  add     rsp, 0D8h
0x18000fc70  pop     r15
0x18000fc72  pop     r14
0x18000fc74  pop     r13
0x18000fc76  pop     r12
0x18000fc78  pop     rdi
0x18000fc79  pop     rsi
0x18000fc7a  pop     rbx
0x18000fc7b  pop     rbp
0x18000fc7c  retn
0x18000fc7d  mov     r12d, [rbp+3Fh+arg_28]
0x18000fc81  bts     r14d, 1Fh
0x18000fc86  test    r12d, r12d
0x18000fc89  jz      loc_18000FD47
0x18000fc8f  test    byte ptr [rbp+3Fh+arg_30], 20h
0x18000fc93  jnz     loc_18000FD47
0x18000fc99  mov     rbx, [rbp+3Fh+pszOID]
0x18000fc9d  lea     rax, [rbp+3Fh+hFuncAddr]
0x18000fca1  mov     rcx, cs:?hGetTimeValidObjectFuncSet@@3PEAXEA; hFuncSet
0x18000fca8  xor     esi, esi
0x18000fcaa  mov     [rsp+110h+phFuncAddr], rax; phFuncAddr
0x18000fcaf  xor     r9d, r9d; dwFlags
0x18000fcb2  lea     rax, [rbp+3Fh+pvFindPara]
0x18000fcb6  mov     [rbp+3Fh+hFuncAddr], rsi
0x18000fcba  mov     r8, rbx; pszOID
0x18000fcbd  mov     [rsp+110h+ppvFuncAddr], rax; ppvFuncAddr
0x18000fcc2  mov     edx, 1; dwEncodingType
0x18000fcc7  mov     [rbp+3Fh+pvFindPara], rsi
0x18000fccb  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18000fccf  call    cs:__imp_CryptGetOIDFunctionAddress
0x18000fcd5  test    eax, eax
0x18000fcd7  jz      loc_180010001
0x18000fcdd  test    r15, r15
0x18000fce0  jz      loc_180010009
0x18000fce6  mov     r9, r15
0x18000fce9  mov     rax, [rbp+3Fh+var_B0]
0x18000fced  mov     ecx, r14d
0x18000fcf0  mov     r8, [rbp+3Fh+pIssuer]
0x18000fcf4  or      ecx, 2
0x18000fcf7  mov     rdx, [rbp+3Fh+pvPara]
0x18000fcfb  mov     [rsp+110h+pExtraInfo], rax
0x18000fd00  mov     rax, [rbp+3Fh+pvFindPara]
0x18000fd04  mov     [rsp+110h+pCredentials], rsi
0x18000fd09  mov     [rsp+110h+ppvObject], r13
0x18000fd0e  mov     dword ptr [rsp+110h+phFuncAddr], esi
0x18000fd12  mov     dword ptr [rsp+110h+ppvFuncAddr], ecx
0x18000fd16  mov     rcx, rbx
0x18000fd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd1e  mov     esi, eax
0x18000fd20  mov     dword ptr [rbp+3Fh+arg_20], eax
0x18000fd23  call    cs:__imp_GetLastError
0x18000fd29  mov     rcx, [rbp+3Fh+hFuncAddr]; hFuncAddr
0x18000fd2d  xor     edx, edx; dwFlags
0x18000fd2f  mov     ebx, eax
0x18000fd31  call    cs:__imp_CryptFreeOIDFunctionAddress
0x18000fd37  mov     ecx, ebx; dwErrCode
0x18000fd39  call    cs:__imp_SetLastError
0x18000fd3f  test    esi, esi
0x18000fd41  jnz     loc_18000FC67
0x18000fd47  mov     rbx, [rdi+20h]
0x18000fd4b  xor     eax, eax
0x18000fd4d  mov     [r13+0], rax
0x18000fd51  test    rbx, rbx
0x18000fd54  jz      loc_18000FE08
0x18000fd5a  cmp     [rbp+3Fh+var_B8], eax
0x18000fd5d  jnz     loc_18000FE08
0x18000fd63  xorps   xmm0, xmm0
0x18000fd66  movups  xmmword ptr [rbp+3Fh+pvFindPara], xmm0
0x18000fd6a  call    cs:__imp_GetLastError
0x18000fd70  test    [rbp+3Fh+arg_38], 2
0x18000fd77  lea     rcx, [rbp+3Fh+pvFindPara]
0x18000fd7b  mov     [rbp+3Fh+var_B8], eax
0x18000fd7e  mov     r13d, 17h
0x18000fd84  mov     eax, 1Bh
0x18000fd89  mov     [rsp+110h+phFuncAddr], 0; pPrevCrlContext
0x18000fd92  cmovz   r13d, eax
0x18000fd96  mov     [rsp+110h+ppvFuncAddr], rcx; pvFindPara
0x18000fd9b  mov     rax, [rbp+3Fh+pCert]
0x18000fd9f  mov     r9d, 3; dwFindType
0x18000fda5  mov     [rbp+3Fh+pvFindPara], rax
0x18000fda9  mov     r8d, r13d; dwFindFlags
0x18000fdac  mov     rax, [rbp+3Fh+pIssuer]
0x18000fdb0  mov     rcx, rbx; hCertStore
0x18000fdb3  mov     [rbp+3Fh+pvFindPara+8], rax
0x18000fdb7  mov     edx, [rax]; dwCertEncodingType
0x18000fdb9  call    cs:__imp_CertFindCRLInStore
0x18000fdbf  mov     qword ptr [rsp+110h+pcbData], rax
0x18000fdc4  test    rax, rax
0x18000fdc7  jnz     loc_18001001C
0x18000fdcd  mov     r13, [rbp+3Fh+arg_48]
0x18000fdd4  cmp     qword ptr [r13+0], 0
0x18000fdd9  jz      short loc_18000FE05
0x18000fddb  mov     eax, 1
0x18000fde0  jmp     loc_18000FC69
0x18000fde5  mov     rdx, [rdi+58h]
0x18000fde9  lea     rax, [rbp+3Fh+var_70]
0x18000fded  mov     qword ptr [rbp+3Fh+var_50], rdx
0x18000fdf1  mov     [rbp+3Fh+var_B0], rax
0x18000fdf5  mov     dword ptr [rbp+3Fh+var_70], 30h ; '0'
0x18000fdfc  mov     qword ptr [rbp+3Fh+var_70+8], r10
0x18000fe00  jmp     loc_18000FBD8
0x18000fe05  mov     eax, [rbp+3Fh+var_B8]
0x18000fe08  test    r12d, r12d
0x18000fe0b  jz      short loc_18000FE43
0x18000fe0d  mov     ecx, [rbp+3Fh+arg_30]
0x18000fe10  test    cl, 2
0x18000fe13  jz      short loc_18000FE55
0x18000fe15  test    rbx, rbx
0x18000fe18  jz      short loc_18000FE22
0x18000fe1a  mov     ecx, eax; dwErrCode
0x18000fe1c  call    cs:__imp_SetLastError
0x18000fe22  call    cs:__imp_GetLastError
0x18000fe28  cmp     eax, 80092004h
0x18000fe2d  jz      loc_1800101CD
0x18000fe33  mov     ecx, 80092013h; dwErrCode
0x18000fe38  call    cs:__imp_SetLastError
0x18000fe3e  jmp     loc_18000FC67
0x18000fe43  mov     ecx, 80092012h; dwErrCode
0x18000fe48  call    cs:__imp_SetLastError
0x18000fe4e  xor     eax, eax
0x18000fe50  jmp     loc_18000FC69
0x18000fe55  cmp     [rbp+3Fh+var_A8], 0
0x18000fe59  jnz     short loc_18000FE15
0x18000fe5b  test    cl, 4
0x18000fe5e  jz      short loc_18000FE7C
0x18000fe60  mov     rcx, [rbp+3Fh+lpFileTime1]; lpFileTime1
0x18000fe67  call    I_CryptRemainingMilliseconds
0x18000fe6c  mov     [rdi+30h], eax
0x18000fe6f  test    eax, eax
0x18000fe71  jz      loc_1800101C1
0x18000fe77  bts     r14d, 0Bh
0x18000fe7c  mov     rax, [rbp+3Fh+var_B0]
0x18000fe80  or      r14d, 4
0x18000fe84  mov     r8, [rbp+3Fh+pIssuer]; pIssuer
0x18000fe88  mov     r9, r15; pftValidFor
0x18000fe8b  mov     rdx, [rbp+3Fh+pvPara]; pvPara
0x18000fe8f  mov     rcx, [rbp+3Fh+pszOID]; pszTimeValidOid
0x18000fe93  mov     [rsp+110h+pExtraInfo], rax; pExtraInfo
0x18000fe98  mov     eax, [rdi+30h]
0x18000fe9b  mov     [rsp+110h+pCredentials], 0; pCredentials
0x18000fea4  mov     [rsp+110h+ppvObject], r13; ppvObject
0x18000fea9  mov     dword ptr [rsp+110h+phFuncAddr], eax; dwTimeout
0x18000fead  mov     dword ptr [rsp+110h+ppvFuncAddr], r14d; dwFlags
0x18000feb2  call    CryptGetTimeValidObject
0x18000feb7  mov     esi, eax
0x18000feb9  mov     rax, [rbp+3Fh+arg_50]
0x18000fec0  mov     dword ptr [rax], 1
0x18000fec6  test    esi, esi
0x18000fec8  jnz     loc_18000FC67
0x18000fece  jmp     loc_18000FE22
0x18000fed3  xor     ebx, ebx
0x18000fed5  lea     r9, [rsp+110h+pcbData]; pcbData
0x18000feda  xor     r8d, r8d; pvData
0x18000fedd  mov     [rsp+110h+pcbData], ebx
0x18000fee1  mov     edx, 46h ; 'F'; dwPropId
0x18000fee6  mov     rcx, r12; pCertContext
0x18000fee9  call    cs:__imp_CertGetCertificateContextProperty
0x18000feef  test    eax, eax
0x18000fef1  jz      loc_18000FC63
0x18000fef7  mov     rcx, cs:hGetObjectUrlFuncSet; hFuncSet
0x18000fefe  lea     rax, [rbp+3Fh+var_B0]
0x18000ff02  mov     [rsp+110h+phFuncAddr], rax; phFuncAddr
0x18000ff07  xor     r9d, r9d; dwFlags
0x18000ff0a  lea     rax, [rbp+3Fh+arg_20]
0x18000ff0e  mov     [rbp+3Fh+arg_30], ebx
0x18000ff11  mov     edx, 1; dwEncodingType
0x18000ff16  mov     [rsp+110h+ppvFuncAddr], rax; ppvFuncAddr
0x18000ff1b  mov     r8d, 9; pszOID
0x18000ff21  mov     [rbp+3Fh+var_B0], rbx
0x18000ff25  mov     [rbp+3Fh+arg_20], rbx
0x18000ff29  call    cs:__imp_CryptGetOIDFunctionAddress
0x18000ff2f  test    eax, eax
0x18000ff31  jz      short loc_18000FF9A
0x18000ff33  mov     [rsp+110h+pCredentials], rbx
0x18000ff38  lea     rax, [rbp+3Fh+arg_30]
0x18000ff3c  mov     [rsp+110h+ppvObject], rbx
0x18000ff41  xor     r9d, r9d
0x18000ff44  mov     [rsp+110h+phFuncAddr], rbx
0x18000ff49  mov     r8d, 0Fh
0x18000ff4f  mov     [rsp+110h+ppvFuncAddr], rax
0x18000ff54  mov     rdx, r12
0x18000ff57  mov     rax, [rbp+3Fh+arg_20]
0x18000ff5b  mov     ecx, 9
0x18000ff60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff65  mov     edi, eax
0x18000ff67  call    cs:__imp_GetLastError
0x18000ff6d  mov     rcx, [rbp+3Fh+var_B0]; hFuncAddr
0x18000ff71  xor     edx, edx; dwFlags
0x18000ff73  mov     ebx, eax
0x18000ff75  call    cs:__imp_CryptFreeOIDFunctionAddress
0x18000ff7b  mov     ecx, ebx; dwErrCode
0x18000ff7d  call    cs:__imp_SetLastError
0x18000ff83  neg     edi
0x18000ff85  sbb     ecx, ecx
0x18000ff87  add     ecx, 80092014h; dwErrCode
0x18000ff8d  call    cs:__imp_SetLastError
0x18000ff93  xor     eax, eax
0x18000ff95  jmp     loc_18000FC69
0x18000ff9a  mov     edi, ebx
0x18000ff9c  jmp     short loc_18000FF83
0x18000ff9e  mov     rax, [rcx+18h]
0x18000ffa2  cmp     dword ptr [rax+38h], 0
0x18000ffa6  jnz     short loc_18000FFB2
0x18000ffa8  cmp     dword ptr [rax+3Ch], 0
0x18000ffac  jz      loc_180010139
0x18000ffb2  mov     eax, r14d
0x18000ffb5  lea     rdx, aChecktimevalid; "CheckTimeValidity"
0x18000ffbc  or      eax, 2
0x18000ffbf  xor     r9d, r9d
0x18000ffc2  mov     dword ptr [rsp+110h+phFuncAddr], eax
0x18000ffc6  mov     r8d, 78Bh
0x18000ffcc  mov     [rsp+110h+ppvFuncAddr], 0
0x18000ffd5  call    CertDiagRejectCrl
0x18000ffda  jmp     loc_180010179
0x18000ffdf  mov     eax, [rdi+38h]
0x18000ffe2  imul    rcx, rax, 989680h
0x18000ffe9  mov     rax, [r15]
0x18000ffec  lea     r15, [rbp+3Fh+var_88]
0x18000fff0  sub     rax, rcx
0x18000fff3  mov     ecx, 400h
0x18000fff8  mov     [rbp+3Fh+var_88], rax
0x18000fffc  jmp     loc_18000FBEB
0x180010001  mov     dword ptr [rbp+3Fh+arg_20], esi
0x180010004  jmp     loc_18000FD47
0x180010009  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001000d  call    cs:__imp_GetSystemTimeAsFileTime
0x180010013  lea     r9, [rbp+3Fh+SystemTimeAsFileTime]
0x180010017  jmp     loc_18000FCE9
  ... truncated ...
```
