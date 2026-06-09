# MicrosoftCertDllVerifyRevocation(ulong,ulong,ulong,void * * const,ulong,_CERT_REVOCATION_PARA *,_CERT_REVOCATION_STATUS *)

- ea: `0x18000f140`
- end: `0x18000f96b`
- name: `?MicrosoftCertDllVerifyRevocation@@YAHKKKQEAPEAXKPEAU_CERT_REVOCATION_PARA@@PEAU_CERT_REVOCATION_STATUS@@@Z`
- size: `2091`
- prototype: `__int64 __fastcall(__int16, int, unsigned int, void **const, unsigned int, struct _FILETIME SystemTimeAsFileTime, struct _CERT_REVOCATION_STATUS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f130`

## callees

- `0x18000f140`
- `0x18000f980`
- `0x18000fb70`
- `0x180010510`
- `0x1800105e0`
- `0x180010d50`
- `0x180010de0`
- `0x180017d34`
- `0x18001a174`
- `0x180026552`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f4df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f543`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f69e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f6ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f72a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f76b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f780`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f7c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f4df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f543`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f69e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f6ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f72a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f76b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f780`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f688`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f1f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f6ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f1f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f6ce`
- `CRYPT32!I_CertDiagControl` at `0x18000f2c1`
- `CRYPT32!I_CertDiagControl` at `0x18000f2c1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000f29d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000f29d`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f510`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f510`
- `CRYPT32!CertFindExtension` at `0x18000f24b`
- `CRYPT32!CertFindExtension` at `0x18000f24b`
- `CRYPT32!CertFreeCRLContext` at `0x18000f51e`
- `CRYPT32!CertFreeCRLContext` at `0x18000f832`
- `CRYPT32!CertFreeCRLContext` at `0x18000f915`
- `CRYPT32!CertFreeCRLContext` at `0x18000f920`
- `CRYPT32!CertFreeCRLContext` at `0x18000f948`
- `CRYPT32!CertFreeCRLContext` at `0x18000f960`
- `CRYPT32!CertFreeCRLContext` at `0x18000f51e`
- `CRYPT32!CertFreeCRLContext` at `0x18000f832`
- `CRYPT32!CertFreeCRLContext` at `0x18000f915`
- `CRYPT32!CertFreeCRLContext` at `0x18000f920`
- `CRYPT32!CertFreeCRLContext` at `0x18000f948`
- `CRYPT32!CertFreeCRLContext` at `0x18000f960`
- `CRYPT32!CertFindCertificateInCRL` at `0x18000f43c`
- `CRYPT32!CertFindCertificateInCRL` at `0x18000f59c`
- `CRYPT32!CertFindCertificateInCRL` at `0x18000f893`
- `CRYPT32!CertFindCertificateInCRL` at `0x18000f43c`
- `CRYPT32!CertFindCertificateInCRL` at `0x18000f59c`
- `CRYPT32!CertFindCertificateInCRL` at `0x18000f893`
- `CRYPT32!CertDuplicateCRLContext` at `0x18000f498`
- `CRYPT32!CertDuplicateCRLContext` at `0x18000f936`
- `CRYPT32!CertDuplicateCRLContext` at `0x18000f498`
- `CRYPT32!CertDuplicateCRLContext` at `0x18000f936`
- `CRYPT32!CertCompareCertificateName` at `0x18000f7a8`
- `CRYPT32!CertCompareCertificateName` at `0x18000f7a8`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x18000f64a`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x18000f64a`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000f696`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18000f696`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f3c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f8fd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f3c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f8fd`

## pseudocode

```c
__int64 __fastcall MicrosoftCertDllVerifyRevocation(
        __int16 a1,
        int a2,
        unsigned int a3,
        void **const a4,
        unsigned int a5,
        struct _FILETIME SystemTimeAsFileTime,
        struct _CERT_REVOCATION_STATUS *a7)
{
  void **v8; // rsi
  const struct _CERT_CONTEXT *IssuerCertInStores; // rbx
  DWORD cbSize; // edi
  unsigned int v12; // r12d
  struct _CERT_REVOCATION_STATUS *v13; // r14
  CERT_CONTEXT *v14; // r13
  PCERT_EXTENSION Extension; // rcx
  unsigned int v16; // r15d
  const CERT_CONTEXT *v17; // rdi
  const CERT_CONTEXT *pIssuerCert; // rcx
  PCCERT_CONTEXT IssuerCertInDefaultStores; // rax
  DWORD v20; // esi
  int v21; // edi
  const CRL_CONTEXT *v22; // rsi
  const CRL_CONTEXT *v23; // rdi
  unsigned __int64 v24; // rax
  const CRL_CONTEXT *v25; // r12
  DWORD v26; // edi
  HCERTSTORE *rgCertStore; // r13
  const CRL_CONTEXT *v28; // rcx
  PCCRL_CONTEXT v29; // rax
  const CRL_CONTEXT *v30; // rcx
  int v31; // esi
  int v33; // esi
  DWORD LastError; // edi
  bool v35; // zf
  PCRL_ENTRY v36; // rdx
  PCCRL_CONTEXT pCrlContext; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int CrlReason; // [rsp+68h] [rbp-98h]
  PCRL_ENTRY ppCrlEntry; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v40[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME v41; // [rsp+80h] [rbp-80h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr[2]; // [rsp+88h] [rbp-78h] BYREF
  PCCRL_CONTEXT v43; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME v44; // [rsp+A0h] [rbp-60h] BYREF
  void *ppvFuncAddr; // [rsp+A8h] [rbp-58h] BYREF
  struct _CERT_REVOCATION_PARA v46[3]; // [rsp+B0h] [rbp-50h] BYREF

  CrlReason = 0;
  v8 = a4;
  pCrlContext = 0;
  v43 = 0;
  IssuerCertInStores = 0;
  ppCrlEntry = 0;
  v40[0] = 0;
  v44 = 0;
  v41 = 0;
  memset(&v46[0].cbSize + 1, 0, sizeof(struct _CERT_REVOCATION_PARA));
  memset(&v46[1].cbSize + 1, 0, 44);
  if ( SystemTimeAsFileTime )
  {
    if ( *(_DWORD *)SystemTimeAsFileTime.dwLowDateTime < 0x60u )
      memcpy_0(v46, *(const void **)&SystemTimeAsFileTime, *(unsigned int *)SystemTimeAsFileTime.dwLowDateTime);
    else
      memcpy_0(v46, *(const void **)&SystemTimeAsFileTime, 0x60u);
  }
  cbSize = v46[1].cbSize;
  v46[0].cbSize = 96;
  if ( !v46[1].cbSize )
    cbSize = 15000;
  v46[1].cbSize = cbSize;
  if ( !*(_QWORD *)&v46[1].cCertStore )
  {
    GetSystemTimeAsFileTime(&v44);
    *(_QWORD *)&v46[1].cCertStore = &v44;
  }
  v12 = a5;
  if ( (a5 & 4) != 0 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v41 = (struct _FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 10000LL * cbSize);
  }
  v13 = a7;
  if ( !a3 )
  {
    SetLastError(0x80070057);
    goto LABEL_74;
  }
  if ( a1 != 1 || a2 != 1 )
  {
    SetLastError(0x80092012);
    v25 = pCrlContext;
    goto LABEL_48;
  }
  v14 = (CERT_CONTEXT *)*v8;
  Extension = CertFindExtension(
                "2.5.29.31",
                *(_DWORD *)(*((_QWORD *)*v8 + 3) + 192LL),
                *(CERT_EXTENSION **)(*((_QWORD *)*v8 + 3) + 200LL));
  v16 = 1;
  a5 = v12 & 8;
  if ( Extension )
  {
    LODWORD(a7) = 1;
    if ( (v12 & 8) == 0 )
      goto LABEL_13;
    a5 = v12 & 8;
  }
  else
  {
    LODWORD(a7) = 0;
  }
  SystemTimeAsFileTime.dwLowDateTime = 0;
  hFuncAddr[0] = 0;
  ppvFuncAddr = 0;
  if ( CryptGetOIDFunctionAddress(hGetObjectUrlFuncSet, 1u, (LPCSTR)9, 0, &ppvFuncAddr, hFuncAddr)
    && (v33 = ((__int64 (__fastcall *)(__int64, CERT_CONTEXT *, __int64, _QWORD, struct _FILETIME *, _QWORD, _QWORD, _QWORD))ppvFuncAddr)(
                9,
                v14,
                15,
                0,
                &SystemTimeAsFileTime,
                0,
                0,
                0),
        LastError = GetLastError(),
        CryptFreeOIDFunctionAddress(hFuncAddr[0], 0),
        SetLastError(LastError),
        v35 = v33 == 0,
        v8 = a4,
        !v35) )
  {
    LODWORD(a7) = 1;
  }
  else if ( a5 )
  {
    SetLastError(0x80092014);
    v25 = pCrlContext;
    goto LABEL_48;
  }
LABEL_13:
  v17 = (const CERT_CONTEXT *)*v8;
  if ( a3 != 1 )
  {
    if ( (v12 & 1) == 0 )
      goto LABEL_70;
    pIssuerCert = (const CERT_CONTEXT *)v8[1];
    goto LABEL_77;
  }
  pIssuerCert = v46[0].pIssuerCert;
  if ( v46[0].pIssuerCert )
  {
LABEL_15:
    IssuerCertInDefaultStores = CertDuplicateCertificateContext(pIssuerCert);
    goto LABEL_16;
  }
  if ( CertCompareCertificateName(v17->dwCertEncodingType, &v17->pCertInfo->Subject, &v17->pCertInfo->Issuer) )
  {
    pIssuerCert = v17;
LABEL_77:
    if ( pIssuerCert )
      goto LABEL_15;
  }
LABEL_70:
  IssuerCertInStores = FindIssuerCertInStores(v17, v46[0].cCertStore, v46[0].rgCertStore);
  if ( IssuerCertInStores )
    goto LABEL_17;
  IssuerCertInDefaultStores = (PCCERT_CONTEXT)FindIssuerCertInDefaultStores(v17);
LABEL_16:
  IssuerCertInStores = IssuerCertInDefaultStores;
  if ( !IssuerCertInDefaultStores )
  {
    SetLastError(0x80092013);
    v25 = pCrlContext;
    goto LABEL_48;
  }
LABEL_17:
  hFuncAddr[0] = v14;
  hFuncAddr[1] = (HCRYPTOIDFUNCADDR)IssuerCertInStores;
  I_CertDiagControl(1, hFuncAddr, 0);
  v20 = *(&v46[1].cbSize + 1);
  v21 = (int)a7;
  *(&v46[1].cbSize + 1) = 0;
  pCrlContext = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  if ( (unsigned int)GetTimeValidCrl(
                       (const char *)3,
                       v14,
                       v14,
                       IssuerCertInStores,
                       v46,
                       (int)a7,
                       v12,
                       0,
                       &v41,
                       (LPVOID *)&pCrlContext,
                       (int *)&SystemTimeAsFileTime) )
  {
    a5 = 1;
  }
  else
  {
    a5 = 0;
    if ( !(unsigned int)GetTimeValidCrl(
                          (const char *)3,
                          v14,
                          v14,
                          IssuerCertInStores,
                          v46,
                          v21,
                          v12,
                          1,
                          &v41,
                          (LPVOID *)&pCrlContext,
                          (int *)&SystemTimeAsFileTime) )
    {
LABEL_46:
      v25 = pCrlContext;
      if ( pCrlContext )
      {
        CertFreeCRLContext(pCrlContext);
        v25 = 0;
      }
      goto LABEL_48;
    }
  }
  if ( (unsigned int)HasUnsupportedCrlCriticalExtension(pCrlContext) )
  {
    SetLastError(0x80092012);
    goto LABEL_46;
  }
  *(&v46[1].cbSize + 1) = v20;
  if ( !(unsigned int)GetDeltaCrl(
                        v14,
                        IssuerCertInStores,
                        v46,
                        v12,
                        SystemTimeAsFileTime.dwLowDateTime,
                        &v41,
                        (DWORD)&pCrlContext,
                        (int *)&a5,
                        &v43,
                        v40) )
    goto LABEL_74;
  v22 = v43;
  if ( v43 )
  {
    if ( CertFindCertificateInCRL(v14, v43, 0, 0, &ppCrlEntry) )
    {
      *(_QWORD *)v40 = v40[0];
LABEL_25:
      v25 = pCrlContext;
      goto LABEL_26;
    }
LABEL_74:
    v25 = pCrlContext;
    goto LABEL_48;
  }
  v23 = pCrlContext;
  hFuncAddr[0] = &pCrlContext->pCrlInfo->ThisUpdate;
  if ( CompareFileTime(*(const FILETIME **)&v46[1].cCertStore, (const FILETIME *)hFuncAddr[0]) <= 0 )
    v24 = 0;
  else
    v24 = (**(_QWORD **)&v46[1].cCertStore - *(_QWORD *)hFuncAddr[0]) / 0x989680uLL;
  *(_QWORD *)v40 = v24;
  if ( !*(&v46[1].cbSize + 1) )
    goto LABEL_25;
  if ( LODWORD(v46[1].pIssuerCert) >= (unsigned int)v24 )
  {
    a5 = 1;
    goto LABEL_25;
  }
  hFuncAddr[0] = 0;
  if ( !(unsigned int)GetBaseCrl(
                        v14,
                        IssuerCertInStores,
                        v46,
                        (int)a7,
                        v12,
                        &v41,
                        (const struct _CRL_CONTEXT **)hFuncAddr,
                        (int *)&a5,
                        (int *)&SystemTimeAsFileTime) )
  {
    a5 = 0;
    goto LABEL_25;
  }
  CertFreeCRLContext(v23);
  v25 = (const CRL_CONTEXT *)hFuncAddr[0];
  v40[0] = I_CryptSubtractFileTimes(*(_QWORD *)&v46[1].cCertStore, *((_QWORD *)hFuncAddr[0] + 3) + 48LL);
LABEL_26:
  SystemTimeAsFileTime.dwLowDateTime = 0;
  if ( !ppCrlEntry )
  {
    if ( CertFindCertificateInCRL(v14, v25, 0, 0, &ppCrlEntry) )
    {
      if ( !ppCrlEntry )
        goto LABEL_29;
      CrlReason = GetCrlReason(ppCrlEntry);
      goto LABEL_100;
    }
    goto LABEL_48;
  }
  CrlReason = GetCrlReason(ppCrlEntry);
  if ( CrlReason != 8 )
  {
    SystemTimeAsFileTime.dwLowDateTime = 1;
LABEL_100:
    v36 = ppCrlEntry;
LABEL_101:
    if ( !v36 )
      goto LABEL_29;
    goto LABEL_102;
  }
  if ( !CertFindCertificateInCRL(v14, v25, 0, 0, &ppCrlEntry) )
  {
LABEL_48:
    v26 = GetLastError();
    if ( !v26 )
      v26 = -2147418113;
LABEL_50:
    v16 = 0;
    v31 = 0;
    if ( !IssuerCertInStores )
      goto LABEL_52;
    goto LABEL_51;
  }
  v36 = ppCrlEntry;
  if ( !ppCrlEntry )
  {
LABEL_98:
    CrlReason = 0;
    goto LABEL_101;
  }
  CrlReason = GetCrlReason(ppCrlEntry);
  if ( CrlReason == 6 )
  {
    v36 = 0;
    ppCrlEntry = 0;
    goto LABEL_98;
  }
  v36 = ppCrlEntry;
  if ( !ppCrlEntry )
    goto LABEL_98;
LABEL_102:
  if ( !v46[0].pftTimeToUse || CompareFileTime(v46[0].pftTimeToUse, &v36->RevocationDate) >= 0 )
  {
    v26 = -2146885616;
    goto LABEL_31;
  }
LABEL_29:
  v26 = 0;
  if ( !a5 )
    v26 = -2146885613;
LABEL_31:
  if ( v13->cbSize >= 0x18 )
  {
    v13->dwFreshnessTime = v40[0];
    v13->fHasFreshnessTime = 1;
  }
  rgCertStore = v46[1].rgCertStore;
  if ( v46[1].rgCertStore && *(_DWORD *)v46[1].rgCertStore >= 0x28u )
  {
    v28 = (const CRL_CONTEXT *)*((_QWORD *)v46[1].rgCertStore + 1);
    if ( v28 )
      CertFreeCRLContext(v28);
    v29 = CertDuplicateCRLContext(v25);
    v30 = (const CRL_CONTEXT *)rgCertStore[2];
    rgCertStore[1] = (HCERTSTORE)v29;
    if ( v30 )
    {
      CertFreeCRLContext(v30);
      rgCertStore[2] = 0;
    }
    if ( v22 )
      rgCertStore[2] = (HCERTSTORE)CertDuplicateCRLContext(v22);
    *((_DWORD *)rgCertStore + 8) = SystemTimeAsFileTime.dwLowDateTime;
    rgCertStore[3] = ppCrlEntry;
  }
  if ( v26 )
    goto LABEL_50;
  if ( a3 > 1 )
  {
    v31 = 1;
    v26 = -2146885614;
    v16 = 0;
  }
  else
  {
    v31 = 0;
  }
LABEL_51:
  CertFreeCertificateContext(IssuerCertInStores);
LABEL_52:
  if ( v25 )
    CertFreeCRLContext(v25);
  if ( v43 )
    CertFreeCRLContext(v43);
  v13->dwReason = CrlReason;
  v13->dwIndex = v31;
  v13->dwError = v26;
  SetLastError(v26);
  return v16;
}

```

## disassembly

```asm
0x18000f140  mov     [rsp-8+arg_8], rbx
0x18000f145  mov     [rsp-8+arg_18], r9
0x18000f14a  mov     [rsp-8+arg_10], r8d
0x18000f14f  mov     [rsp-8+arg_0], ecx
0x18000f153  push    rbp
0x18000f154  push    rsi
0x18000f155  push    rdi
0x18000f156  push    r12
0x18000f158  push    r13
0x18000f15a  push    r14
0x18000f15c  push    r15
0x18000f15e  lea     rbp, [rsp-10h]
0x18000f163  sub     rsp, 110h
0x18000f16a  xor     r14d, r14d
0x18000f16d  xorps   xmm0, xmm0
0x18000f170  mov     r13d, edx
0x18000f173  mov     [rsp+140h+var_D8], r14d
0x18000f178  mov     rdx, qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime]; Src
0x18000f17c  mov     rsi, r9
0x18000f17f  mov     [rsp+140h+pCrlContext], r14
0x18000f184  mov     r15d, r8d
0x18000f187  mov     [rbp+40h+var_A8], r14
0x18000f18b  mov     ebx, r14d
0x18000f18e  mov     [rsp+140h+var_D0], r14
0x18000f193  mov     [rsp+140h+var_C8], r14d
0x18000f198  mov     qword ptr [rbp+40h+var_A0.dwLowDateTime], r14
0x18000f19c  mov     qword ptr [rbp+40h+var_C0.dwLowDateTime], r14
0x18000f1a0  movups  [rbp+40h+var_4C], xmm0
0x18000f1a4  movups  xmmword ptr [rbp+40h+var_90+4], xmm0
0x18000f1a8  movups  xmmword ptr [rbp+40h+var_90+14h], xmm0
0x18000f1ac  movups  xmmword ptr [rbp+40h+var_90+24h], xmm0
0x18000f1b0  movups  xmmword ptr [rbp+40h+lpFileTime1], xmm0
0x18000f1b4  movups  [rbp+40h+var_4C+0Ch], xmm0
0x18000f1b8  test    rdx, rdx
0x18000f1bb  jnz     loc_18000F567
0x18000f1c1  mov     edi, dword ptr [rbp+40h+var_90+30h]
0x18000f1c4  mov     eax, 3A98h
0x18000f1c9  test    edi, edi
0x18000f1cb  mov     dword ptr [rbp+40h+var_90], 60h ; '`'
0x18000f1d2  cmovz   edi, eax
0x18000f1d5  mov     dword ptr [rbp+40h+var_90+30h], edi
0x18000f1d8  cmp     [rbp+40h+lpFileTime1+0Ch], rbx
0x18000f1dc  jz      loc_18000F6CA
0x18000f1e2  mov     r12d, [rbp+40h+arg_20]
0x18000f1e6  test    r12b, 4
0x18000f1ea  jz      short loc_18000F20B
0x18000f1ec  lea     rcx, [rbp+40h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000f1f0  mov     qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18000f1f4  call    cs:__imp_GetSystemTimeAsFileTime
0x18000f1fa  mov     eax, edi
0x18000f1fc  imul    rcx, rax, 2710h
0x18000f203  add     rcx, qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime]
0x18000f207  mov     qword ptr [rbp+40h+var_C0.dwLowDateTime], rcx
0x18000f20b  mov     r14, [rbp+40h+arg_30]
0x18000f212  test    r15d, r15d
0x18000f215  jz      loc_18000F725
0x18000f21b  cmp     word ptr [rbp+40h+arg_0], 1
0x18000f220  jnz     loc_18000F766
0x18000f226  cmp     r13d, 1
0x18000f22a  jnz     loc_18000F77B
0x18000f230  mov     r13, [rsi]
0x18000f233  lea     rcx, pszObjId; "2.5.29.31"
0x18000f23a  mov     rdx, [r13+18h]
0x18000f23e  mov     r8, [rdx+0C8h]; rgExtensions
0x18000f245  mov     edx, [rdx+0C0h]; cExtensions
0x18000f24b  call    cs:__imp_CertFindExtension
0x18000f251  mov     rcx, rax
0x18000f254  mov     r15d, 1
0x18000f25a  mov     eax, r12d
0x18000f25d  and     eax, 8
0x18000f260  mov     [rbp+40h+arg_20], eax
0x18000f263  test    rcx, rcx
0x18000f266  jz      loc_18000F612
0x18000f26c  xor     edi, edi
0x18000f26e  test    rcx, rcx
0x18000f271  setnz   dil
0x18000f275  mov     dword ptr [rbp+40h+arg_30], edi
0x18000f27b  test    eax, eax
0x18000f27d  jnz     loc_18000F790
0x18000f283  mov     rdi, [rsi]
0x18000f286  cmp     [rbp+40h+arg_10], r15d
0x18000f28a  jnz     loc_18000F6ED
0x18000f290  mov     rcx, qword ptr [rbp+40h+var_90+8]; pCertContext
0x18000f294  test    rcx, rcx
0x18000f297  jz      loc_18000F79A
0x18000f29d  call    cs:__imp_CertDuplicateCertificateContext
0x18000f2a3  mov     rbx, rax
0x18000f2a6  test    rax, rax
0x18000f2a9  jz      loc_18000F7C1
0x18000f2af  xor     r8d, r8d
0x18000f2b2  mov     [rbp+40h+hFuncAddr], r13
0x18000f2b6  lea     rdx, [rbp+40h+hFuncAddr]
0x18000f2ba  mov     [rbp+40h+var_B0], rbx
0x18000f2be  mov     ecx, r15d
0x18000f2c1  call    cs:__imp_I_CertDiagControl
0x18000f2c7  mov     esi, dword ptr [rbp+40h+lpFileTime1]
0x18000f2ca  lea     rax, [rbp+40h+SystemTimeAsFileTime]
0x18000f2ce  mov     edi, dword ptr [rbp+40h+arg_30]
0x18000f2d4  xor     ecx, ecx
0x18000f2d6  mov     [rsp+140h+var_F0], rax; int *
0x18000f2db  mov     r9, rbx; struct _CERT_CONTEXT *
0x18000f2de  lea     rax, [rsp+140h+pCrlContext]
0x18000f2e3  mov     dword ptr [rbp+40h+lpFileTime1], ecx
0x18000f2e6  mov     [rsp+140h+var_F8], rax; struct _CRL_CONTEXT **
0x18000f2eb  mov     r8, r13; struct _CERT_CONTEXT *
0x18000f2ee  lea     rax, [rbp+40h+var_C0]
0x18000f2f2  mov     [rsp+140h+pCrlContext], rcx
0x18000f2f7  mov     [rsp+140h+var_100], rax; struct _FILETIME *
0x18000f2fc  mov     rdx, r13; void *
0x18000f2ff  mov     dword ptr [rsp+140h+var_108], ecx; unsigned int
0x18000f303  lea     rax, [rbp+40h+var_90]
0x18000f307  mov     [rsp+140h+var_110], r12d; unsigned int
0x18000f30c  mov     [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x18000f30f  mov     ecx, 3; char *
0x18000f314  mov     dword ptr [rsp+140h+phFuncAddr], edi; int
0x18000f318  mov     [rsp+140h+ppCrlEntry], rax; struct _CERT_REVOCATION_PARA *
0x18000f31d  call    ?GetTimeValidCrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@2PEAU_CERT_REVOCATION_PARA@@HKKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH@Z; GetTimeValidCrl(char const *,void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *)
0x18000f322  test    eax, eax
0x18000f324  jz      loc_18000F5B8
0x18000f32a  mov     [rbp+40h+arg_20], r15d
0x18000f32e  mov     rcx, [rsp+140h+pCrlContext]; struct _CRL_CONTEXT *
0x18000f333  call    ?HasUnsupportedCrlCriticalExtension@@YAHPEBU_CRL_CONTEXT@@@Z; HasUnsupportedCrlCriticalExtension(_CRL_CONTEXT const *)
0x18000f338  test    eax, eax
0x18000f33a  jnz     loc_18000F4DA
0x18000f340  mov     rax, [rsp+140h+pCrlContext]
0x18000f345  mov     [rsp+140h+pCrlContext], rax
0x18000f34a  lea     rax, [rsp+140h+var_C8]
0x18000f34f  mov     dword ptr [rbp+40h+lpFileTime1], esi
0x18000f352  mov     [rsp+140h+var_F8], rax; unsigned int *
0x18000f357  lea     r8, [rbp+40h+var_90]; struct _CERT_REVOCATION_PARA *
0x18000f35b  lea     rax, [rbp+40h+var_A8]
0x18000f35f  mov     r9d, r12d; unsigned int
0x18000f362  mov     [rsp+140h+var_100], rax; struct _CRL_CONTEXT **
0x18000f367  mov     rdx, rbx; struct _CERT_CONTEXT *
0x18000f36a  lea     rax, [rbp+40h+arg_20]
0x18000f36e  mov     rcx, r13; struct _CERT_CONTEXT *
0x18000f371  mov     [rsp+140h+var_108], rax; int *
0x18000f376  lea     rax, [rsp+140h+pCrlContext]
0x18000f37b  mov     qword ptr [rsp+140h+var_110], rax; DWORD
0x18000f380  lea     rax, [rbp+40h+var_C0]
0x18000f384  mov     [rsp+140h+phFuncAddr], rax; struct _FILETIME *
0x18000f389  mov     eax, [rbp+40h+SystemTimeAsFileTime.dwLowDateTime]
0x18000f38c  mov     dword ptr [rsp+140h+ppCrlEntry], eax; int
0x18000f390  call    ?GetDeltaCrl@@YAHPEBU_CERT_CONTEXT@@0PEAU_CERT_REVOCATION_PARA@@KHPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH3PEAK@Z; GetDeltaCrl(_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,ulong,int,_FILETIME *,_CRL_CONTEXT const * *,int *,_CRL_CONTEXT const * *,ulong *)
0x18000f395  test    eax, eax
0x18000f397  jz      loc_18000F730
0x18000f39d  mov     rsi, [rbp+40h+var_A8]
0x18000f3a1  test    rsi, rsi
0x18000f3a4  jnz     loc_18000F586
0x18000f3aa  mov     rdi, [rsp+140h+pCrlContext]
0x18000f3af  mov     rcx, [rbp+40h+lpFileTime1+0Ch]; lpFileTime1
0x18000f3b3  mov     [rsp+140h+pCrlContext], rdi
0x18000f3b8  mov     rax, [rdi+18h]
0x18000f3bc  add     rax, 30h ; '0'
0x18000f3c0  mov     rdx, rax; lpFileTime2
0x18000f3c3  mov     [rbp+40h+hFuncAddr], rax
0x18000f3c7  call    cs:__imp_CompareFileTime
0x18000f3cd  test    eax, eax
0x18000f3cf  jle     loc_18000F71E
0x18000f3d5  mov     rax, [rbp+40h+lpFileTime1+0Ch]
0x18000f3d9  mov     rcx, [rax]
0x18000f3dc  mov     rax, [rbp+40h+hFuncAddr]
0x18000f3e0  sub     rcx, [rax]
0x18000f3e3  mov     rax, 0D6BF94D5E57A42BDh
0x18000f3ed  mul     rcx
0x18000f3f0  mov     rax, rdx
0x18000f3f3  shr     rax, 17h
0x18000f3f7  cmp     dword ptr [rbp+40h+lpFileTime1], 0
0x18000f3fb  mov     qword ptr [rsp+140h+var_C8], rax
0x18000f400  jnz     loc_18000F7D6
0x18000f406  mov     edx, [rbp+40h+arg_20]
0x18000f409  mov     [rbp+40h+arg_20], edx
0x18000f40c  mov     r12, [rsp+140h+pCrlContext]
0x18000f411  mov     rcx, [rsp+140h+var_D0]; struct _CRL_ENTRY *
0x18000f416  mov     [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000f41d  test    rcx, rcx
0x18000f420  jnz     loc_18000F869
0x18000f426  lea     rax, [rsp+140h+var_D0]
0x18000f42b  xor     r9d, r9d; pvReserved
0x18000f42e  xor     r8d, r8d; dwFlags
0x18000f431  mov     [rsp+140h+ppCrlEntry], rax; ppCrlEntry
0x18000f436  mov     rdx, r12; pCrlContext
0x18000f439  mov     rcx, r13; pCert
0x18000f43c  call    cs:__imp_CertFindCertificateInCRL
0x18000f442  test    eax, eax
0x18000f444  jz      loc_18000F4F3
0x18000f44a  mov     rcx, [rsp+140h+var_D0]; struct _CRL_ENTRY *
0x18000f44f  test    rcx, rcx
0x18000f452  jnz     loc_18000F8D9
0x18000f458  xor     edi, edi
0x18000f45a  mov     eax, 80092013h
0x18000f45f  cmp     [rbp+40h+arg_20], edi
0x18000f462  cmovz   edi, eax
0x18000f465  cmp     dword ptr [r14], 18h
0x18000f469  jb      short loc_18000F478
0x18000f46b  mov     rax, qword ptr [rsp+140h+var_C8]
0x18000f470  mov     [r14+14h], eax
0x18000f474  mov     [r14+10h], r15d
0x18000f478  mov     r13, qword ptr [rbp+40h+var_4C+4]
0x18000f47c  test    r13, r13
0x18000f47f  jz      short loc_18000F4C8
0x18000f481  cmp     dword ptr [r13+0], 28h ; '('
0x18000f486  jb      short loc_18000F4C8
0x18000f488  mov     rcx, [r13+8]; pCrlContext
0x18000f48c  test    rcx, rcx
0x18000f48f  jnz     loc_18000F915
0x18000f495  mov     rcx, r12; pCrlContext
0x18000f498  call    cs:__imp_CertDuplicateCRLContext
0x18000f49e  mov     rcx, [r13+10h]; pCrlContext
0x18000f4a2  mov     [r13+8], rax
0x18000f4a6  test    rcx, rcx
0x18000f4a9  jnz     loc_18000F920
0x18000f4af  test    rsi, rsi
0x18000f4b2  jnz     loc_18000F933
0x18000f4b8  mov     eax, [rbp+40h+SystemTimeAsFileTime.dwLowDateTime]
0x18000f4bb  mov     [r13+20h], eax
0x18000f4bf  mov     rax, [rsp+140h+var_D0]
0x18000f4c4  mov     [r13+18h], rax
0x18000f4c8  test    edi, edi
0x18000f4ca  jnz     short loc_18000F503
0x18000f4cc  cmp     [rbp+40h+arg_10], r15d
0x18000f4d0  ja      loc_18000F74B
0x18000f4d6  xor     esi, esi
0x18000f4d8  jmp     short loc_18000F50D
0x18000f4da  mov     ecx, 80092012h; dwErrCode
0x18000f4df  call    cs:__imp_SetLastError
0x18000f4e5  mov     r12, [rsp+140h+pCrlContext]
0x18000f4ea  test    r12, r12
0x18000f4ed  jnz     loc_18000F945
0x18000f4f3  call    cs:__imp_GetLastError
0x18000f4f9  mov     edi, eax
0x18000f4fb  test    eax, eax
0x18000f4fd  jz      loc_18000F956
0x18000f503  xor     r15d, r15d
0x18000f506  xor     esi, esi
0x18000f508  test    rbx, rbx
0x18000f50b  jz      short loc_18000F516
0x18000f50d  mov     rcx, rbx; pCertContext
0x18000f510  call    cs:__imp_CertFreeCertificateContext
0x18000f516  test    r12, r12
0x18000f519  jz      short loc_18000F524
0x18000f51b  mov     rcx, r12; pCrlContext
0x18000f51e  call    cs:__imp_CertFreeCRLContext
0x18000f524  mov     rcx, [rbp+40h+var_A8]; pCrlContext
0x18000f528  test    rcx, rcx
0x18000f52b  jnz     loc_18000F960
0x18000f531  mov     eax, [rsp+140h+var_D8]
0x18000f535  mov     ecx, edi; dwErrCode
0x18000f537  mov     [r14+0Ch], eax
0x18000f53b  mov     [r14+4], esi
0x18000f53f  mov     [r14+8], edi
0x18000f543  call    cs:__imp_SetLastError
0x18000f549  mov     rbx, [rsp+140h+arg_8]
0x18000f551  mov     eax, r15d
0x18000f554  add     rsp, 110h
0x18000f55b  pop     r15
0x18000f55d  pop     r14
0x18000f55f  pop     r13
0x18000f561  pop     r12
0x18000f563  pop     rdi
0x18000f564  pop     rsi
0x18000f565  pop     rbp
0x18000f566  retn
0x18000f567  mov     eax, [rdx]
0x18000f569  cmp     eax, 60h ; '`'
0x18000f56c  jb      loc_18000F73A
0x18000f572  mov     r8d, 60h ; '`'; Size
0x18000f578  lea     rcx, [rbp+40h+var_90]; void *
0x18000f57c  call    memcpy_0
0x18000f581  jmp     loc_18000F1C1
0x18000f586  lea     rax, [rsp+140h+var_D0]
0x18000f58b  xor     r9d, r9d; pvReserved
0x18000f58e  xor     r8d, r8d; dwFlags
0x18000f591  mov     [rsp+140h+ppCrlEntry], rax; ppCrlEntry
0x18000f596  mov     rdx, rsi; pCrlContext
0x18000f599  mov     rcx, r13; pCert
0x18000f59c  call    cs:__imp_CertFindCertificateInCRL
0x18000f5a2  test    eax, eax
0x18000f5a4  jz      loc_18000F730
0x18000f5aa  mov     eax, [rsp+140h+var_C8]
0x18000f5ae  mov     qword ptr [rsp+140h+var_C8], rax
0x18000f5b3  jmp     loc_18000F406
0x18000f5b8  lea     rax, [rbp+40h+SystemTimeAsFileTime]
0x18000f5bc  mov     [rbp+40h+arg_20], 0
0x18000f5c3  mov     [rsp+140h+var_F0], rax; int *
0x18000f5c8  mov     r9, rbx; struct _CERT_CONTEXT *
0x18000f5cb  lea     rax, [rsp+140h+pCrlContext]
0x18000f5d0  mov     r8, r13; struct _CERT_CONTEXT *
0x18000f5d3  mov     [rsp+140h+var_F8], rax; struct _CRL_CONTEXT **
0x18000f5d8  mov     rdx, r13; void *
0x18000f5db  lea     rax, [rbp+40h+var_C0]
0x18000f5df  mov     ecx, 3; char *
0x18000f5e4  mov     [rsp+140h+var_100], rax; struct _FILETIME *
0x18000f5e9  lea     rax, [rbp+40h+var_90]
0x18000f5ed  mov     dword ptr [rsp+140h+var_108], r15d; unsigned int
0x18000f5f2  mov     [rsp+140h+var_110], r12d; unsigned int
0x18000f5f7  mov     dword ptr [rsp+140h+phFuncAddr], edi; int
0x18000f5fb  mov     [rsp+140h+ppCrlEntry], rax; struct _CERT_REVOCATION_PARA *
0x18000f600  call    ?GetTimeValidCrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@2PEAU_CERT_REVOCATION_PARA@@HKKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH@Z; GetTimeValidCrl(char const *,void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *)
0x18000f605  test    eax, eax
  ... truncated ...
```
