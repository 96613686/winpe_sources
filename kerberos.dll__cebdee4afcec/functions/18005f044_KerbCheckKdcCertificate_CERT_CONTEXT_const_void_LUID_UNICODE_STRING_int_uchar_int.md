# KerbCheckKdcCertificate(_CERT_CONTEXT const *,void *,_LUID *,_UNICODE_STRING *,int,uchar,int)

- ea: `0x18005f044`
- end: `0x18005f50a`
- name: `?KerbCheckKdcCertificate@@YAJPEBU_CERT_CONTEXT@@PEAXPEAU_LUID@@PEAU_UNICODE_STRING@@HEH@Z`
- size: `1222`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, HCERTSTORE hAdditionalStore, struct _LUID *, struct _UNICODE_STRING *, DWORD pcbStructInfo, unsigned __int8, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800baae4`

## callees

- `0x18001018c`
- `0x1800107f8`
- `0x180010e90`
- `0x180050934`
- `0x18005f044`
- `0x18005f510`
- `0x180065c48`
- `0x18006e840`
- `0x18007108c`
- `0x18008a114`
- `0x18008b2f4`
- `0x18008b70c`
- `0x180093520`
- `0x1800f1ef4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f4ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f4ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f426`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f426`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005f13d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005f30a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005f13d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005f30a`
- `ntdll!RtlEqualDomainName` at `0x18005f40c`
- `ntdll!RtlEqualDomainName` at `0x18005f40c`
- `ntdll!RtlInitUnicodeString` at `0x18005f3fd`
- `ntdll!RtlInitUnicodeString` at `0x18005f3fd`
- `ntdll!NtOpenThreadToken` at `0x18005f11f`
- `ntdll!NtOpenThreadToken` at `0x18005f11f`
- `CRYPT32!CertGetCertificateChain` at `0x18005f1fa`
- `CRYPT32!CertGetCertificateChain` at `0x18005f1fa`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005f2a9`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005f2a9`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005f3b7`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005f3b7`
- `CRYPT32!CertFreeCertificateChain` at `0x18005f4d4`
- `CRYPT32!CertFreeCertificateChain` at `0x18005f4d4`

## string_xrefs

- `0x18005f0e4`: `unable to impersonate the client: %#x\n`

## pseudocode

```c
__int64 __fastcall KerbCheckKdcCertificate(
        const struct _CERT_CONTEXT *a1,
        HCERTSTORE hAdditionalStore,
        struct _LUID *a3,
        struct _UNICODE_STRING *a4,
        DWORD pcbStructInfo,
        unsigned __int8 a6,
        int a7)
{
  unsigned int v9; // esi
  char v11; // r13
  DWORD v12; // r14d
  int v13; // eax
  int v14; // ebx
  NTSTATUS v15; // eax
  unsigned __int8 v16; // di
  int v17; // eax
  void *v18; // rcx
  const char **v19; // rax
  DWORD v20; // eax
  DWORD v21; // eax
  __int64 v22; // rcx
  DWORD LastError; // eax
  PCERT_INFO pCertInfo; // rax
  int v25; // r15d
  DWORD v26; // esi
  PCERT_EXTENSION rgExtension; // r14
  __int64 v28; // rdi
  BOOL v29; // eax
  _QWORD *v30; // rcx
  unsigned int v31; // edi
  __int64 v32; // rax
  const WCHAR *v33; // rdx
  BOOLEAN v34; // al
  __int64 *CorrelationId; // rax
  int v36; // ecx
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+60h] [rbp-A0h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+68h] [rbp-98h] BYREF
  const char *v43; // [rsp+88h] [rbp-78h] BYREF
  const char *v44; // [rsp+90h] [rbp-70h] BYREF
  const char *v45; // [rsp+98h] [rbp-68h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+A0h] [rbp-60h] BYREF
  int v47; // [rsp+D8h] [rbp-28h]

  a7 = 0;
  v9 = KerbGlobalUseCachedCRLOnlyAndIgnoreRevocationUnknownErrors;
  v11 = 0;
  memset_0(&pChainPara, 0, 0x60u);
  pChainContext = 0;
  v45 = "1.3.6.1.5.5.7.3.1";
  v43 = "1.3.6.1.5.2.3.5";
  TokenHandle = 0;
  a7 = 0;
  v39 = 0;
  pPolicyPara.cbSize = 0;
  v12 = pcbStructInfo;
  v44 = "1.3.6.1.4.1.311.20.2.2";
  if ( pcbStructInfo )
  {
    v13 = KerbImpersonateClient(a3, &TokenHandle);
    v14 = v13;
    if ( v13 < 0 )
    {
      KerbTracerT::Log(1, "KerbCheckKdcCertificate", 1609, "unable to impersonate the client: %#x\n", v13);
      goto LABEL_49;
    }
  }
  else
  {
    v15 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    v14 = v15;
    if ( v15 >= 0 )
    {
      RevertToSelf();
    }
    else
    {
      TokenHandle = 0;
      if ( v15 != -1073741700 )
        goto LABEL_49;
    }
  }
  v16 = a6;
  v17 = KerbCheckKdcCertificateKeyUsage(a1, a6, &a7, &v39, (int *)&pPolicyPara);
  v18 = 0;
  v14 = v17;
  if ( v17 >= 0 )
  {
    pChainPara.cbSize = 96;
    if ( a7 )
    {
      v19 = &v43;
    }
    else if ( v39 )
    {
      v19 = &v44;
    }
    else
    {
      if ( !pPolicyPara.cbSize )
        goto LABEL_16;
      v19 = &v45;
    }
    pChainPara.RequestedUsage.dwType = 0;
    pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
    pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)v19;
LABEL_16:
    v47 = 1000 * KerbGlobalCRLRetrievalTimeout;
    LOBYTE(v18) = v12 == 0;
    if ( CertGetCertificateChain(
           v18,
           a1,
           0,
           hAdditionalStore,
           &pChainPara,
           v9 != 0 ? -1073741824 : 0x40000000,
           0,
           &pChainContext) )
    {
      *(_QWORD *)&pPolicyStatus.cbSize = 24;
      pPolicyStatus.pvExtraPolicyStatus = 0;
      pPolicyPara = 0;
      v21 = 0;
      if ( v9 )
        v21 = 3840;
      pPolicyPara.cbSize = 16;
      pPolicyPara.dwFlags = v21;
      pPolicyStatus.lChainIndex = -1;
      pPolicyStatus.lElementIndex = -1;
      if ( !KerbGlobalKdcValidation && !v16 || !(_BYTE)KerbGlobalRoles || (v22 = 6, !fRebootedSinceJoin) )
        v22 = 1;
      if ( !CertVerifyCertificateChainPolicy((LPCSTR)v22, pChainContext, &pPolicyPara, &pPolicyStatus) )
      {
        LastError = GetLastError();
        KerbTracerT::Log(
          2,
          "KerbCheckKdcCertificate",
          1725,
          "CertVerifyCertificateChainPolicy failure: 0x%x\n",
          LastError);
        v14 = -1073741024;
      }
      if ( pPolicyStatus.dwError )
      {
        KerbTracerT::Log(
          1,
          "KerbCheckKdcCertificate",
          1730,
          "CertVerifyCertificateChainPolicy - Chain Status failure: 0x%x\n",
          pPolicyStatus.dwError);
        RevertToSelf();
        KerbReportPkinitError(0xC0000009, pPolicyStatus.dwError, a1);
        v14 = KerbMapCertChainError(pPolicyStatus.dwError, 0);
      }
      if ( v14 >= 0 && v16 )
      {
        pCertInfo = a1->pCertInfo;
        if ( !pCertInfo->cExtension )
          goto LABEL_45;
        v25 = 0;
        v26 = 0;
        do
        {
          rgExtension = pCertInfo->rgExtension;
          v28 = v26;
          if ( !strcmp_0(rgExtension[v28].pszObjId, "2.5.29.17") )
          {
            *(_QWORD *)&pPolicyPara.cbSize = 0;
            pcbStructInfo = 0;
            v29 = CryptDecodeObjectEx(
                    a1->dwCertEncodingType,
                    (LPCSTR)0xC,
                    rgExtension[v28].Value.pbData,
                    rgExtension[v28].Value.cbData,
                    0x2008000u,
                    0,
                    &pPolicyPara,
                    &pcbStructInfo);
            v30 = *(_QWORD **)&pPolicyPara.cbSize;
            if ( v29 )
            {
              v31 = 0;
              if ( **(_DWORD **)&pPolicyPara.cbSize )
              {
                do
                {
                  if ( v25 )
                    break;
                  v32 = v30[1];
                  if ( *(_DWORD *)(v32 + 24LL * v31) == 3 )
                  {
                    v33 = *(const WCHAR **)(v32 + 24LL * v31 + 8);
                    if ( v33 )
                    {
                      *(_OWORD *)&pPolicyStatus.cbSize = 0;
                      RtlInitUnicodeString((PUNICODE_STRING)&pPolicyStatus, v33);
                      v34 = RtlEqualDomainName((PUNICODE_STRING)&pPolicyStatus, a4);
                      v30 = *(_QWORD **)&pPolicyPara.cbSize;
                      v25 = v34;
                    }
                  }
                  ++v31;
                }
                while ( v31 < *(_DWORD *)v30 );
              }
            }
            if ( v30 )
              LocalFree(v30);
          }
          pCertInfo = a1->pCertInfo;
          ++v26;
        }
        while ( v26 < pCertInfo->cExtension );
        if ( !v25 )
        {
LABEL_45:
          KerbTracerT::Log(
            2,
            "KerbCheckKdcCertificate",
            1801,
            "KDC certificate is not intended for the KDC: %wZ expected\n",
            a4);
          v14 = KerbMapKerbError(63);
          KerbReportKdcCertValidationDomainNameMismatch(a4->Buffer, v14);
          if ( (Microsoft_Windows_Security_KerberosEnableBits & 2) != 0 )
          {
            CorrelationId = (__int64 *)KerbTracerT::GetCorrelationId(&pPolicyStatus);
            v11 = 1;
            McTemplateU0zqz_EtwEventWriteTransfer(
              v36,
              (unsigned int)KdcCertValidationDomainNameMismatch,
              a4->Buffer,
              v14,
              *CorrelationId);
          }
          if ( (v11 & 1) != 0 )
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&pPolicyStatus);
        }
      }
    }
    else
    {
      v20 = GetLastError();
      KerbTracerT::Log(1, "KerbCheckKdcCertificate", 1698, "Failed to verify certificate chain: 0x%x\n", v20);
      v14 = -1073741024;
    }
  }
LABEL_49:
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  KerbRevertImpersonation(TokenHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18005f044  mov     [rsp-8+DomainName2], r9
0x18005f049  push    rbp
0x18005f04a  push    rbx
0x18005f04b  push    rsi
0x18005f04c  push    rdi
0x18005f04d  push    r12
0x18005f04f  push    r13
0x18005f051  push    r14
0x18005f053  push    r15
0x18005f055  lea     rbp, [rsp-8]
0x18005f05a  sub     rsp, 108h
0x18005f061  xor     r14d, r14d
0x18005f064  mov     rbx, r8
0x18005f067  mov     r15, rdx
0x18005f06a  mov     [rbp+40h+arg_30], r14d
0x18005f071  mov     esi, cs:?KerbGlobalUseCachedCRLOnlyAndIgnoreRevocationUnknownErrors@@3KA; ulong KerbGlobalUseCachedCRLOnlyAndIgnoreRevocationUnknownErrors
0x18005f077  mov     r12, rcx
0x18005f07a  xor     edx, edx; Val
0x18005f07c  lea     rcx, [rbp+40h+var_A0]; void *
0x18005f080  lea     r8d, [r14+60h]; Size
0x18005f084  mov     r13d, r14d
0x18005f087  call    memset_0
0x18005f08c  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x18005f093  mov     [rsp+140h+pChainContext], r14
0x18005f098  mov     [rbp+40h+var_A8], rax
0x18005f09c  lea     rax, a13615235; "1.3.6.1.5.2.3.5"
0x18005f0a3  mov     [rbp+40h+var_B8], rax
0x18005f0a7  lea     rax, a1361413112022; "1.3.6.1.4.1.311.20.2.2"
0x18005f0ae  mov     [rsp+140h+TokenHandle], r14
0x18005f0b3  mov     [rbp+40h+arg_30], r14d
0x18005f0ba  mov     [rsp+140h+var_F0], r14d
0x18005f0bf  mov     [rsp+140h+pPolicyPara.cbSize], r14d
0x18005f0c4  mov     r14d, [rbp+40h+pcbStructInfo]
0x18005f0c8  mov     [rbp+40h+var_B0], rax
0x18005f0cc  test    r14d, r14d
0x18005f0cf  jz      short loc_18005F10B
0x18005f0d1  lea     rdx, [rsp+140h+TokenHandle]; void **
0x18005f0d6  mov     rcx, rbx; struct _LUID *
0x18005f0d9  call    ?KerbImpersonateClient@@YAJPEAU_LUID@@PEAPEAX@Z; KerbImpersonateClient(_LUID *,void * *)
0x18005f0de  mov     ebx, eax
0x18005f0e0  test    eax, eax
0x18005f0e2  jns     short loc_18005F143
0x18005f0e4  lea     r9, aUnableToImpers_0; "unable to impersonate the client: %#x\n"
0x18005f0eb  mov     dword ptr [rsp+140h+pChainPara], eax
0x18005f0ef  mov     r8d, 649h
0x18005f0f5  lea     rdx, aKerbcheckkdcce_0; "KerbCheckKdcCertificate"
0x18005f0fc  mov     ecx, 1
0x18005f101  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f106  jmp     loc_18005F4CA
0x18005f10b  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x18005f110  mov     r8b, 1; OpenAsSelf
0x18005f113  mov     edx, 0Ch; DesiredAccess
0x18005f118  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005f11f  call    cs:__imp_NtOpenThreadToken
0x18005f125  mov     ebx, eax
0x18005f127  test    eax, eax
0x18005f129  jns     short loc_18005F13D
0x18005f12b  mov     [rsp+140h+TokenHandle], r13
0x18005f130  cmp     eax, 0C000007Ch
0x18005f135  jnz     loc_18005F4CA
0x18005f13b  jmp     short loc_18005F143
0x18005f13d  call    cs:__imp_RevertToSelf
0x18005f143  mov     dil, [rbp+40h+arg_28]
0x18005f147  lea     rax, [rsp+140h+pPolicyPara]
0x18005f14c  mov     dl, dil; unsigned __int8
0x18005f14f  mov     [rsp+140h+pChainPara], rax; int *
0x18005f154  lea     r9, [rsp+140h+var_F0]; int *
0x18005f159  mov     rcx, r12; struct _CERT_CONTEXT *
0x18005f15c  lea     r8, [rbp+40h+arg_30]; int *
0x18005f163  call    ?KerbCheckKdcCertificateKeyUsage@@YAJPEBU_CERT_CONTEXT@@EPEAH11@Z; KerbCheckKdcCertificateKeyUsage(_CERT_CONTEXT const *,uchar,int *,int *,int *)
0x18005f168  xor     ecx, ecx
0x18005f16a  mov     ebx, eax
0x18005f16c  test    eax, eax
0x18005f16e  js      loc_18005F4CA
0x18005f174  mov     [rbp+40h+var_A0.cbSize], 60h ; '`'
0x18005f17b  cmp     [rbp+40h+arg_30], ecx
0x18005f181  jz      short loc_18005F189
0x18005f183  lea     rax, [rbp+40h+var_B8]
0x18005f187  jmp     short loc_18005F19F
0x18005f189  cmp     [rsp+140h+var_F0], ecx
0x18005f18d  jz      short loc_18005F195
0x18005f18f  lea     rax, [rbp+40h+var_B0]
0x18005f193  jmp     short loc_18005F19F
0x18005f195  cmp     [rsp+140h+pPolicyPara.cbSize], ecx
0x18005f199  jz      short loc_18005F1AD
0x18005f19b  lea     rax, [rbp+40h+var_A8]
0x18005f19f  mov     [rbp+40h+var_A0.RequestedUsage.dwType], ecx
0x18005f1a2  mov     [rbp+40h+var_A0.RequestedUsage.Usage.cUsageIdentifier], 1
0x18005f1a9  mov     [rbp+40h+var_A0.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x18005f1ad  imul    eax, cs:?KerbGlobalCRLRetrievalTimeout@@3JA, 3E8h; long KerbGlobalCRLRetrievalTimeout
0x18005f1b7  mov     r9, r15; hAdditionalStore
0x18005f1ba  mov     [rbp+40h+var_68], eax
0x18005f1bd  mov     eax, esi
0x18005f1bf  neg     eax
0x18005f1c1  lea     rax, [rsp+140h+pChainContext]
0x18005f1c6  sbb     edx, edx
0x18005f1c8  mov     [rsp+140h+ppChainContext], rax; ppChainContext
0x18005f1cd  and     edx, 80000000h
0x18005f1d3  lea     rax, [rbp+40h+var_A0]
0x18005f1d7  add     edx, 40000000h
0x18005f1dd  test    r14d, r14d
0x18005f1e0  setz    cl; hChainEngine
0x18005f1e3  xor     r14d, r14d
0x18005f1e6  mov     [rsp+140h+pvReserved], r14; pvReserved
0x18005f1eb  xor     r8d, r8d; pTime
0x18005f1ee  mov     [rsp+140h+dwFlags], edx; dwFlags
0x18005f1f2  mov     rdx, r12; pCertContext
0x18005f1f5  mov     [rsp+140h+pChainPara], rax; pChainPara
0x18005f1fa  call    cs:__imp_CertGetCertificateChain
0x18005f200  test    eax, eax
0x18005f202  jnz     short loc_18005F235
0x18005f204  call    cs:__imp_GetLastError
0x18005f20a  lea     r9, aFailedToVerify_7; "Failed to verify certificate chain: 0x%"...
0x18005f211  mov     r8d, 6A2h
0x18005f217  lea     rdx, aKerbcheckkdcce_0; "KerbCheckKdcCertificate"
0x18005f21e  mov     dword ptr [rsp+140h+pChainPara], eax
0x18005f222  lea     ecx, [r14+1]
0x18005f226  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f22b  mov     ebx, 0C0000320h
0x18005f230  jmp     loc_18005F4CA
0x18005f235  test    esi, esi
0x18005f237  mov     qword ptr [rsp+140h+pPolicyStatus.cbSize], 18h
0x18005f240  xorps   xmm0, xmm0
0x18005f243  mov     [rsp+140h+pPolicyStatus.pvExtraPolicyStatus], r14
0x18005f248  movups  xmmword ptr [rsp+140h+pPolicyPara.cbSize], xmm0
0x18005f24d  mov     eax, [rsp+140h+pPolicyPara.dwFlags]
0x18005f251  mov     ecx, 0F00h
0x18005f256  cmovnz  eax, ecx
0x18005f259  mov     [rsp+140h+pPolicyPara.cbSize], 10h
0x18005f261  mov     [rsp+140h+pPolicyPara.dwFlags], eax
0x18005f265  or      eax, 0FFFFFFFFh
0x18005f268  cmp     cs:?KerbGlobalKdcValidation@@3KA, 1; ulong KerbGlobalKdcValidation
0x18005f26f  mov     [rsp+140h+pPolicyStatus.lChainIndex], eax
0x18005f273  mov     [rsp+140h+pPolicyStatus.lElementIndex], eax
0x18005f277  jnb     short loc_18005F27E
0x18005f279  test    dil, dil
0x18005f27c  jz      short loc_18005F295
0x18005f27e  cmp     byte ptr cs:?KerbGlobalRoles@@3U_KerberosSystemRole@@A, r14b; _KerberosSystemRole KerbGlobalRoles
0x18005f285  jz      short loc_18005F295
0x18005f287  cmp     cs:?fRebootedSinceJoin@@3EA, r14b; uchar fRebootedSinceJoin
0x18005f28e  mov     ecx, 6
0x18005f293  jnz     short loc_18005F29A
0x18005f295  mov     ecx, 1; pszPolicyOID
0x18005f29a  mov     rdx, [rsp+140h+pChainContext]; pChainContext
0x18005f29f  lea     r9, [rsp+140h+pPolicyStatus]; pPolicyStatus
0x18005f2a4  lea     r8, [rsp+140h+pPolicyPara]; pPolicyPara
0x18005f2a9  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18005f2af  test    eax, eax
0x18005f2b1  jnz     short loc_18005F2E0
0x18005f2b3  call    cs:__imp_GetLastError
0x18005f2b9  lea     r9, aCertverifycert_0; "CertVerifyCertificateChainPolicy failur"...
0x18005f2c0  mov     r8d, 6BDh
0x18005f2c6  lea     rdx, aKerbcheckkdcce_0; "KerbCheckKdcCertificate"
0x18005f2cd  mov     dword ptr [rsp+140h+pChainPara], eax
0x18005f2d1  mov     ecx, 2
0x18005f2d6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f2db  mov     ebx, 0C0000320h
0x18005f2e0  mov     eax, [rsp+140h+pPolicyStatus.dwError]
0x18005f2e4  test    eax, eax
0x18005f2e6  jz      short loc_18005F32E
0x18005f2e8  lea     r9, aCertverifycert_1; "CertVerifyCertificateChainPolicy - Chai"...
0x18005f2ef  mov     dword ptr [rsp+140h+pChainPara], eax
0x18005f2f3  mov     r8d, 6C2h
0x18005f2f9  lea     rdx, aKerbcheckkdcce_0; "KerbCheckKdcCertificate"
0x18005f300  mov     ecx, 1
0x18005f305  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f30a  call    cs:__imp_RevertToSelf
0x18005f310  mov     edx, [rsp+140h+pPolicyStatus.dwError]; Value
0x18005f314  mov     r8, r12; struct _CERT_CONTEXT *
0x18005f317  mov     ecx, 0C0000009h; unsigned int
0x18005f31c  call    ?KerbReportPkinitError@@YAXKKPEBU_CERT_CONTEXT@@@Z; KerbReportPkinitError(ulong,ulong,_CERT_CONTEXT const *)
0x18005f321  mov     ecx, [rsp+140h+pPolicyStatus.dwError]; unsigned int
0x18005f325  xor     edx, edx; unsigned __int8
0x18005f327  call    ?KerbMapCertChainError@@YAJKE@Z; KerbMapCertChainError(ulong,uchar)
0x18005f32c  mov     ebx, eax
0x18005f32e  test    ebx, ebx
0x18005f330  js      loc_18005F4CA
0x18005f336  test    dil, dil
0x18005f339  jz      loc_18005F4CA
0x18005f33f  mov     rax, [r12+18h]
0x18005f344  cmp     [rax+0C0h], r14d
0x18005f34b  jbe     loc_18005F448
0x18005f351  mov     r15d, r14d
0x18005f354  mov     esi, r14d
0x18005f357  mov     r14, [rax+0C8h]
0x18005f35e  lea     rdx, Str2; "2.5.29.17"
0x18005f365  mov     edi, esi
0x18005f367  shl     rdi, 5
0x18005f36b  mov     rcx, [rdi+r14]; Str1
0x18005f36f  call    strcmp_0
0x18005f374  xor     ecx, ecx
0x18005f376  test    eax, eax
0x18005f378  jnz     loc_18005F42C
0x18005f37e  mov     qword ptr [rsp+140h+pPolicyPara.cbSize], rcx
0x18005f383  lea     rax, [rbp+40h+pcbStructInfo]
0x18005f387  mov     [rsp+140h+ppChainContext], rax; pcbStructInfo
0x18005f38c  lea     edx, [rcx+0Ch]; lpszStructType
0x18005f38f  mov     [rbp+40h+pcbStructInfo], ecx
0x18005f392  lea     rax, [rsp+140h+pPolicyPara]
0x18005f397  mov     r9d, [rdi+r14+10h]; cbEncoded
0x18005f39c  mov     r8, [rdi+r14+18h]; pbEncoded
0x18005f3a1  mov     [rsp+140h+pvReserved], rax; pvStructInfo
0x18005f3a6  mov     qword ptr [rsp+140h+dwFlags], rcx; pDecodePara
0x18005f3ab  mov     ecx, [r12]; dwCertEncodingType
0x18005f3af  mov     dword ptr [rsp+140h+pChainPara], 2008000h; dwFlags
0x18005f3b7  call    cs:__imp_CryptDecodeObjectEx
0x18005f3bd  mov     rcx, qword ptr [rsp+140h+pPolicyPara.cbSize]
0x18005f3c2  xor     r14d, r14d
0x18005f3c5  test    eax, eax
0x18005f3c7  jz      short loc_18005F421
0x18005f3c9  mov     edi, r14d
0x18005f3cc  cmp     [rcx], r14d
0x18005f3cf  jbe     short loc_18005F421
0x18005f3d1  test    r15d, r15d
0x18005f3d4  jnz     short loc_18005F421
0x18005f3d6  mov     eax, edi
0x18005f3d8  lea     rdx, [rax+rax*2]
0x18005f3dc  mov     rax, [rcx+8]
0x18005f3e0  cmp     dword ptr [rax+rdx*8], 3
0x18005f3e4  jnz     short loc_18005F41B
0x18005f3e6  mov     rdx, [rax+rdx*8+8]; SourceString
0x18005f3eb  test    rdx, rdx
0x18005f3ee  jz      short loc_18005F41B
0x18005f3f0  xorps   xmm0, xmm0
0x18005f3f3  lea     rcx, [rsp+140h+pPolicyStatus]; DestinationString
0x18005f3f8  movups  xmmword ptr [rsp+140h+pPolicyStatus.cbSize], xmm0
0x18005f3fd  call    cs:__imp_RtlInitUnicodeString
0x18005f403  mov     rdx, [rbp+40h+DomainName2]; DomainName2
0x18005f407  lea     rcx, [rsp+140h+pPolicyStatus]; DomainName1
0x18005f40c  call    cs:__imp_RtlEqualDomainName
0x18005f412  mov     rcx, qword ptr [rsp+140h+pPolicyPara.cbSize]; hMem
0x18005f417  movzx   r15d, al
0x18005f41b  inc     edi
0x18005f41d  cmp     edi, [rcx]
0x18005f41f  jb      short loc_18005F3D1
0x18005f421  test    rcx, rcx
0x18005f424  jz      short loc_18005F42C
0x18005f426  call    cs:__imp_LocalFree
0x18005f42c  mov     rax, [r12+18h]
0x18005f431  inc     esi
0x18005f433  cmp     esi, [rax+0C0h]
0x18005f439  jb      loc_18005F357
0x18005f43f  test    r15d, r15d
0x18005f442  jnz     loc_18005F4CA
0x18005f448  mov     rdi, [rbp+40h+DomainName2]
0x18005f44c  lea     r9, aKdcCertificate_0; "KDC certificate is not intended for the"...
0x18005f453  mov     r8d, 709h
0x18005f459  mov     [rsp+140h+pChainPara], rdi
0x18005f45e  lea     rdx, aKerbcheckkdcce_0; "KerbCheckKdcCertificate"
0x18005f465  mov     ecx, 2
0x18005f46a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005f46f  mov     ecx, 3Fh ; '?'; int
0x18005f474  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18005f479  mov     rcx, [rdi+8]; unsigned __int16 *
0x18005f47d  mov     edx, eax; int
0x18005f47f  mov     ebx, eax
0x18005f481  call    ?KerbReportKdcCertValidationDomainNameMismatch@@YAXPEAGJ@Z; KerbReportKdcCertValidationDomainNameMismatch(ushort *,long)
0x18005f486  test    cs:Microsoft_Windows_Security_KerberosEnableBits, 2
0x18005f48d  jz      short loc_18005F4BA
0x18005f48f  lea     rcx, [rsp+140h+pPolicyStatus]
0x18005f494  call    ?GetCorrelationId@KerbTracerT@@SA?BV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; KerbTracerT::GetCorrelationId(void)
0x18005f499  mov     r8, [rdi+8]
0x18005f49d  lea     rdx, KdcCertValidationDomainNameMismatch
0x18005f4a4  mov     r9d, ebx
0x18005f4a7  mov     r13d, 1
0x18005f4ad  mov     rax, [rax]
0x18005f4b0  mov     [rsp+140h+pChainPara], rax
0x18005f4b5  call    McTemplateU0zqz_EtwEventWriteTransfer
0x18005f4ba  test    r13b, 1
0x18005f4be  jz      short loc_18005F4CA
0x18005f4c0  lea     rcx, [rsp+140h+pPolicyStatus]
0x18005f4c5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005f4ca  mov     rcx, [rsp+140h+pChainContext]; pChainContext
0x18005f4cf  test    rcx, rcx
0x18005f4d2  jz      short loc_18005F4DA
0x18005f4d4  call    cs:__imp_CertFreeCertificateChain
0x18005f4da  mov     rcx, [rsp+140h+TokenHandle]; Token
0x18005f4df  call    ?KerbRevertImpersonation@@YAXPEAX@Z; KerbRevertImpersonation(void *)
0x18005f4e4  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x18005f4e9  test    rcx, rcx
0x18005f4ec  jz      short loc_18005F4F4
0x18005f4ee  call    cs:__imp_CloseHandle
0x18005f4f4  mov     eax, ebx
0x18005f4f6  add     rsp, 108h
0x18005f4fd  pop     r15
0x18005f4ff  pop     r14
0x18005f501  pop     r13
0x18005f503  pop     r12
0x18005f505  pop     rdi
0x18005f506  pop     rsi
0x18005f507  pop     rbx
0x18005f508  pop     rbp
0x18005f509  retn
```
