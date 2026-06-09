# CreateHGSSessionInternal

- ea: `0x100474030`
- end: `0x100474503`
- name: `CreateHGSSessionInternal`
- size: `1235`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x100474030`
- `0x1004750f0`
- `0x100475970`
- `0x100478100`
- `0x10047894c`
- `0x100478f30`
- `0x100546cf5`
- `0x100546d0d`
- `0x10054811c`
- `0x100548140`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100474461`
- `KERNEL32!GetLastError` at `0x1004744e0`
- `KERNEL32!GetLastError` at `0x100474461`
- `KERNEL32!GetLastError` at `0x1004744e0`
- `CRYPT32!CertCloseStore` at `0x100474400`
- `CRYPT32!CertCloseStore` at `0x100474400`
- `CRYPT32!CertFreeCertificateContext` at `0x1004743f5`
- `CRYPT32!CertFreeCertificateContext` at `0x1004743f5`
- `CRYPT32!CertGetCertificateChain` at `0x10047428e`
- `CRYPT32!CertGetCertificateChain` at `0x10047428e`
- `CRYPT32!CertFreeCertificateChain` at `0x1004743d1`
- `CRYPT32!CertFreeCertificateChain` at `0x1004743d1`
- `CRYPT32!CertCreateCertificateContext` at `0x1004741f2`
- `CRYPT32!CertCreateCertificateContext` at `0x1004741f2`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x10047423c`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x10047423c`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1004743ec`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1004743ec`

## pseudocode

```c
_BOOL8 __fastcall CreateHGSSessionInternal(
        void (__fastcall **a1)(_QWORD, __int64, _QWORD),
        UCHAR *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        __int64 a9)
{
  BOOL v10; // edi
  unsigned int inited; // eax
  void *AttestCert; // r14
  __int64 cbInput; // rdi
  __int64 v15; // r13
  __int64 v16; // r12
  PUCHAR v17; // rsi
  NTSTATUS v18; // eax
  PUCHAR v19; // rdi
  const CERT_CONTEXT *CertificateContext; // rsi
  PUCHAR v21; // rdi
  unsigned int v22; // r8d
  __int64 v23; // rcx
  PUCHAR pbCertEncoded; // [rsp+50h] [rbp-128h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-120h]
  ulong pExceptionObject; // [rsp+60h] [rbp-118h] BYREF
  NTSTATUS v27; // [rsp+64h] [rbp-114h] BYREF
  ulong v28; // [rsp+68h] [rbp-110h] BYREF
  ulong LastError; // [rsp+6Ch] [rbp-10Ch] BYREF
  ulong v30; // [rsp+70h] [rbp-108h] BYREF
  ulong v31; // [rsp+74h] [rbp-104h] BYREF
  ulong v32; // [rsp+78h] [rbp-100h] BYREF
  ulong v33; // [rsp+7Ch] [rbp-FCh] BYREF
  ulong v34; // [rsp+80h] [rbp-F8h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+88h] [rbp-F0h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp-E8h] BYREF
  HCERTCHAINENGINE phChainEngine; // [rsp+98h] [rbp-E0h] BYREF
  const CERT_CONTEXT *v38; // [rsp+A0h] [rbp-D8h]
  ulong v39; // [rsp+A8h] [rbp-D0h] BYREF
  void *v40; // [rsp+B0h] [rbp-C8h]
  __int64 v41; // [rsp+B8h] [rbp-C0h]
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+C0h] [rbp-B8h] BYREF
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+E0h] [rbp-98h] BYREF
  BOOL v45; // [rsp+188h] [rbp+10h]

  v41 = -2;
  pbCertEncoded = a2;
  v25 = a3;
  v10 = 0;
  inited = InitBCrypt();
  if ( inited )
  {
    (*a1)(a1, 0, inited);
    return 0;
  }
  else
  {
    AttestCert = (void *)GetAttestCert(a1, a7);
    v40 = AttestCert;
    if ( AttestCert )
    {
      phKey = 0;
      phChainEngine = 0;
      pChainContext = 0;
      v38 = 0;
      pConfig.cbSize = 88;
      memset_0(&pConfig.hRestrictedRoot, 0, sizeof(_CERT_CHAIN_ENGINE_CONFIG));
      pChainPara.cbSize = 32;
      memset(&pChainPara.RequestedUsage, 0, sizeof(pChainPara.RequestedUsage));
      try
      {
        read4(&pbCertEncoded);
        cbInput = (unsigned int)read4(&pbCertEncoded);
        v15 = (unsigned int)read4(&pbCertEncoded);
        v16 = (unsigned int)read4(&pbCertEncoded);
        if ( (unsigned int)cbInput > v25 )
        {
          pExceptionObject = -2146893023;
          throw &pExceptionObject;
        }
        _mm_lfence();
        v17 = pbCertEncoded;
        v18 = BCryptImportKeyPair_0(phAlgorithm, 0, L"RSAPUBLICBLOB", &phKey, pbCertEncoded, cbInput, 0);
        if ( v18 )
        {
          v27 = v18;
          throw (ulong *)&v27;
        }
        pbCertEncoded = &v17[cbInput];
        v25 -= cbInput;
        if ( (unsigned int)v15 > v25 )
        {
          v28 = -2146893023;
          throw &v28;
        }
        _mm_lfence();
        v19 = pbCertEncoded;
        CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, v15);
        v38 = CertificateContext;
        if ( !CertificateContext )
        {
          LastError = GetLastError();
          throw &LastError;
        }
        pbCertEncoded = &v19[v15];
        v25 -= v15;
        pConfig.hExclusiveRoot = AttestCert;
        if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine)
          || (_mm_lfence(),
              !CertGetCertificateChain(phChainEngine, CertificateContext, 0, 0, &pChainPara, 0, 0, &pChainContext))
          || pChainContext->TrustStatus.dwErrorStatus )
        {
          v34 = GetLastError();
          throw &v34;
        }
        if ( (unsigned int)v16 > v25 )
        {
          v30 = -2146893023;
          throw &v30;
        }
        _mm_lfence();
        v21 = pbCertEncoded;
        if ( !(unsigned int)parseEnclaveReport(a1, pbCertEncoded, (unsigned int)v16, CertificateContext) )
        {
          v31 = -2147418113;
          throw &v31;
        }
        pbCertEncoded = &v21[v16];
        v25 -= v16;
        if ( !v25 )
        {
          v32 = -1072877837;
          throw &v32;
        }
        v22 = read4(&pbCertEncoded);
        if ( v22 > v25 )
        {
          v33 = -2146893023;
          throw &v33;
        }
        _mm_lfence();
        v23 = parseAndCacheSessionInfo((_DWORD)a1, (_DWORD)pbCertEncoded, v22, (_DWORD)phKey, a4 + 24, a5, a6, a7, a9);
        *a8 = v23;
        v10 = v23 != 0;
        v45 = v10;
      }
      catch ( ulong v39 )
      {
        (*a1)(a1, 13, v39);
        v10 = v45;
        AttestCert = v40;
        CertificateContext = v38;
      }
      if ( pChainContext )
        CertFreeCertificateChain(pChainContext);
      BCryptDestroyKey_0(phKey);
      CertFreeCertificateChainEngine(phChainEngine);
      CertFreeCertificateContext(CertificateContext);
      CertCloseStore(AttestCert, 0);
    }
    return v10;
  }
}

```

## disassembly

```asm
0x100474030  mov     [rsp+arg_18], r9
0x100474035  mov     [rsp+arg_0], rcx
0x10047403a  push    rsi
0x10047403b  push    rdi
0x10047403c  push    r12
0x10047403e  push    r13
0x100474040  push    r14
0x100474042  push    r15
0x100474044  sub     rsp, 148h
0x10047404b  mov     [rsp+178h+var_C0], 0FFFFFFFFFFFFFFFEh
0x100474057  mov     r15, rcx
0x10047405a  mov     [rsp+178h+pbCertEncoded], rdx
0x10047405f  mov     [rsp+178h+var_120], r8d
0x100474064  xor     edi, edi
0x100474066  mov     [rsp+178h+arg_8], edi
0x10047406d  call    InitBCrypt
0x100474072  mov     rcx, r15
0x100474075  test    eax, eax
0x100474077  jz      short loc_10047408E
0x100474079  mov     r8d, eax
0x10047407c  xor     edx, edx
0x10047407e  mov     rax, [r15]
0x100474081  call    cs:__guard_dispatch_icall_fptr
0x100474087  xor     eax, eax
0x100474089  jmp     loc_100474408
0x10047408e  mov     rdx, [rsp+178h+arg_30]
0x100474096  call    GetAttestCert
0x10047409b  mov     r14, rax
0x10047409e  mov     [rsp+178h+var_C8], rax
0x1004740a6  test    rax, rax
0x1004740a9  jz      loc_100474406
0x1004740af  and     [rsp+178h+phKey], rdi
0x1004740b7  and     [rsp+178h+phChainEngine], rdi
0x1004740bf  and     [rsp+178h+pChainContext], rdi
0x1004740c7  and     [rsp+178h+var_D8], rdi
0x1004740cf  mov     [rsp+178h+pConfig.cbSize], 58h ; 'X'
0x1004740da  xor     edx, edx; Val
0x1004740dc  lea     r8d, [rdx+50h]; Size
0x1004740e0  lea     rcx, [rsp+178h+pConfig.hRestrictedRoot]; void *
0x1004740e8  call    memset_0
0x1004740ed  mov     [rsp+178h+pChainPara.cbSize], 20h ; ' '
0x1004740f8  xorps   xmm0, xmm0
0x1004740fb  xor     eax, eax
0x1004740fd  movups  xmmword ptr [rsp+178h+pChainPara.RequestedUsage.dwType], xmm0
0x100474105  mov     [rsp+178h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x10047410d  mov     [rsp+178h+arg_10], 2
0x100474118  lea     rcx, [rsp+178h+pbCertEncoded]
0x10047411d  call    read4
0x100474122  mov     [rsp+178h+arg_10], 3
0x10047412d  lea     rcx, [rsp+178h+pbCertEncoded]
0x100474132  call    read4
0x100474137  mov     edi, eax
0x100474139  mov     [rsp+178h+arg_10], 4
0x100474144  lea     rcx, [rsp+178h+pbCertEncoded]
0x100474149  call    read4
0x10047414e  mov     r13d, eax
0x100474151  mov     [rsp+178h+arg_10], 5
0x10047415c  lea     rcx, [rsp+178h+pbCertEncoded]
0x100474161  call    read4
0x100474166  mov     r12d, eax
0x100474169  mov     [rsp+178h+arg_10], 6
0x100474174  cmp     edi, [rsp+178h+var_120]
0x100474178  ja      loc_10047441A
0x10047417e  lfence
0x100474181  and     dword ptr [rsp+178h+var_148], 0
0x100474186  mov     [rsp+178h+cbInput], edi; cbInput
0x10047418a  mov     rsi, [rsp+178h+pbCertEncoded]
0x10047418f  mov     [rsp+178h+pbInput], rsi; pbInput
0x100474194  lea     r9, [rsp+178h+phKey]; phKey
0x10047419c  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x1004741a3  xor     edx, edx; hImportKey
0x1004741a5  mov     rcx, cs:phAlgorithm; hAlgorithm
0x1004741ac  call    BCryptImportKeyPair_0
0x1004741b1  test    eax, eax
0x1004741b3  jnz     loc_100474433
0x1004741b9  add     rsi, rdi
0x1004741bc  mov     [rsp+178h+pbCertEncoded], rsi
0x1004741c1  mov     eax, [rsp+178h+var_120]
0x1004741c5  sub     eax, edi
0x1004741c7  mov     [rsp+178h+var_120], eax
0x1004741cb  mov     [rsp+178h+arg_10], 7
0x1004741d6  cmp     r13d, eax
0x1004741d9  ja      loc_100474448
0x1004741df  lfence
0x1004741e2  mov     r8d, r13d; cbCertEncoded
0x1004741e5  mov     rdi, [rsp+178h+pbCertEncoded]
0x1004741ea  mov     rdx, rdi; pbCertEncoded
0x1004741ed  mov     ecx, 1; dwCertEncodingType
0x1004741f2  call    cs:__imp_CertCreateCertificateContext
0x1004741f8  mov     rsi, rax
0x1004741fb  mov     [rsp+178h+var_D8], rax
0x100474203  test    rax, rax
0x100474206  jz      loc_100474461
0x10047420c  add     rdi, r13
0x10047420f  mov     [rsp+178h+pbCertEncoded], rdi
0x100474214  sub     [rsp+178h+var_120], r13d
0x100474219  mov     [rsp+178h+arg_10], 8
0x100474224  mov     [rsp+178h+pConfig.hExclusiveRoot], r14
0x10047422c  lea     rdx, [rsp+178h+phChainEngine]; phChainEngine
0x100474234  lea     rcx, [rsp+178h+pConfig]; pConfig
0x10047423c  call    cs:__imp_CertCreateCertificateChainEngine
0x100474242  test    eax, eax
0x100474244  jz      loc_1004744E0
0x10047424a  lfence
0x10047424d  mov     [rsp+178h+arg_10], 9
0x100474258  lea     rax, [rsp+178h+pChainContext]
0x100474260  mov     [rsp+178h+ppChainContext], rax; ppChainContext
0x100474265  and     [rsp+178h+var_148], 0
0x10047426b  and     [rsp+178h+cbInput], 0
0x100474270  lea     rax, [rsp+178h+pChainPara]
0x100474278  mov     [rsp+178h+pbInput], rax; pChainPara
0x10047427d  xor     r9d, r9d; hAdditionalStore
0x100474280  xor     r8d, r8d; pTime
0x100474283  mov     rdx, rsi; pCertContext
0x100474286  mov     rcx, [rsp+178h+phChainEngine]; hChainEngine
0x10047428e  call    cs:__imp_CertGetCertificateChain
0x100474294  test    eax, eax
0x100474296  jz      loc_1004744E0
0x10047429c  mov     [rsp+178h+arg_10], 0Ah
0x1004742a7  mov     rax, [rsp+178h+pChainContext]
0x1004742af  cmp     dword ptr [rax+4], 0
0x1004742b3  jnz     loc_1004744E0
0x1004742b9  mov     [rsp+178h+arg_10], 0Bh
0x1004742c4  cmp     r12d, [rsp+178h+var_120]
0x1004742c9  ja      loc_10047447C
0x1004742cf  lfence
0x1004742d2  mov     r9, rsi
0x1004742d5  mov     r8d, r12d
0x1004742d8  mov     rdi, [rsp+178h+pbCertEncoded]
0x1004742dd  mov     rdx, rdi
0x1004742e0  mov     rcx, r15
0x1004742e3  call    parseEnclaveReport
0x1004742e8  test    eax, eax
0x1004742ea  jz      loc_100474495
0x1004742f0  add     rdi, r12
0x1004742f3  mov     [rsp+178h+pbCertEncoded], rdi
0x1004742f8  sub     [rsp+178h+var_120], r12d
0x1004742fd  jz      loc_1004744AE
0x100474303  lea     rcx, [rsp+178h+pbCertEncoded]
0x100474308  call    read4
0x10047430d  mov     r8d, eax
0x100474310  mov     [rsp+178h+arg_10], 0Ch
0x10047431b  cmp     eax, [rsp+178h+var_120]
0x10047431f  ja      loc_1004744C7
0x100474325  lfence
0x100474328  mov     [rsp+178h+arg_10], 0Dh
0x100474333  mov     rcx, [rsp+178h+arg_18]
0x10047433b  add     rcx, 18h
0x10047433f  mov     rax, [rsp+178h+arg_40]
0x100474347  mov     [rsp+178h+var_138], rax
0x10047434c  mov     rax, [rsp+178h+arg_30]
0x100474354  mov     [rsp+178h+ppChainContext], rax
0x100474359  mov     rax, [rsp+178h+arg_28]
0x100474361  mov     [rsp+178h+var_148], rax
0x100474366  mov     rax, [rsp+178h+arg_20]
0x10047436e  mov     qword ptr [rsp+178h+cbInput], rax
0x100474373  mov     [rsp+178h+pbInput], rcx
0x100474378  mov     r9, [rsp+178h+phKey]
0x100474380  mov     rdx, [rsp+178h+pbCertEncoded]
0x100474385  mov     rcx, r15
0x100474388  call    parseAndCacheSessionInfo
0x10047438d  mov     rcx, rax
0x100474390  mov     rax, [rsp+178h+arg_38]
0x100474398  mov     [rax], rcx
0x10047439b  xor     edi, edi
0x10047439d  test    rcx, rcx
0x1004743a0  setnz   dil
0x1004743a4  mov     [rsp+178h+arg_8], edi
0x1004743ab  jmp     short loc_1004743C4
0x1004743ad  mov     edi, [rsp+178h+arg_8]
0x1004743b4  mov     r14, [rsp+178h+var_C8]
0x1004743bc  mov     rsi, [rsp+178h+var_D8]
0x1004743c4  mov     rcx, [rsp+178h+pChainContext]; pChainContext
0x1004743cc  test    rcx, rcx
0x1004743cf  jz      short loc_1004743D7
0x1004743d1  call    cs:__imp_CertFreeCertificateChain
0x1004743d7  mov     rcx, [rsp+178h+phKey]; hKey
0x1004743df  call    BCryptDestroyKey_0
0x1004743e4  mov     rcx, [rsp+178h+phChainEngine]; hChainEngine
0x1004743ec  call    cs:__imp_CertFreeCertificateChainEngine
0x1004743f2  mov     rcx, rsi; pCertContext
0x1004743f5  call    cs:__imp_CertFreeCertificateContext
0x1004743fb  xor     edx, edx; dwFlags
0x1004743fd  mov     rcx, r14; hCertStore
0x100474400  call    cs:__imp_CertCloseStore
0x100474406  mov     eax, edi
0x100474408  add     rsp, 148h
0x10047440f  pop     r15
0x100474411  pop     r14
0x100474413  pop     r13
0x100474415  pop     r12
0x100474417  pop     rdi
0x100474418  pop     rsi
0x100474419  retn
0x10047441a  mov     [rsp+178h+pExceptionObject], 80090321h
0x100474422  lea     rdx, _TI1K; pThrowInfo
0x100474429  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x10047442e  call    _CxxThrowException_0
0x100474433  mov     [rsp+178h+var_114], eax
0x100474437  lea     rdx, _TI1K; pThrowInfo
0x10047443e  lea     rcx, [rsp+178h+var_114]; pExceptionObject
0x100474443  call    _CxxThrowException_0
0x100474448  mov     [rsp+178h+var_110], 80090321h
0x100474450  lea     rdx, _TI1K; pThrowInfo
0x100474457  lea     rcx, [rsp+178h+var_110]; pExceptionObject
0x10047445c  call    _CxxThrowException_0
0x100474461  call    cs:__imp_GetLastError
0x100474467  mov     [rsp+178h+var_10C], eax
0x10047446b  lea     rdx, _TI1K; pThrowInfo
0x100474472  lea     rcx, [rsp+178h+var_10C]; pExceptionObject
0x100474477  call    _CxxThrowException_0
0x10047447c  mov     [rsp+178h+var_108], 80090321h
0x100474484  lea     rdx, _TI1K; pThrowInfo
0x10047448b  lea     rcx, [rsp+178h+var_108]; pExceptionObject
0x100474490  call    _CxxThrowException_0
0x100474495  mov     [rsp+178h+var_104], 8000FFFFh
0x10047449d  lea     rdx, _TI1K; pThrowInfo
0x1004744a4  lea     rcx, [rsp+178h+var_104]; pExceptionObject
0x1004744a9  call    _CxxThrowException_0
0x1004744ae  mov     [rsp+178h+var_100], 0C00D2EF3h
0x1004744b6  lea     rdx, _TI1K; pThrowInfo
0x1004744bd  lea     rcx, [rsp+178h+var_100]; pExceptionObject
0x1004744c2  call    _CxxThrowException_0
0x1004744c7  mov     [rsp+178h+var_FC], 80090321h
0x1004744cf  lea     rdx, _TI1K; pThrowInfo
0x1004744d6  lea     rcx, [rsp+178h+var_FC]; pExceptionObject
0x1004744db  call    _CxxThrowException_0
0x1004744e0  call    cs:__imp_GetLastError
0x1004744e6  mov     [rsp+178h+var_F8], eax
0x1004744ed  lea     rdx, _TI1K; pThrowInfo
0x1004744f4  lea     rcx, [rsp+178h+var_F8]; pExceptionObject
0x1004744fc  call    _CxxThrowException_0
```
