# SSCatDBQueryCertChainByCerts2

- ea: `0x180010b3c`
- end: `0x180010cf0`
- name: `SSCatDBQueryCertChainByCerts2`
- size: `436`
- prototype: `__int64 __fastcall(unsigned int, __int64, struct _FILETIME *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012700`

## callees

- `0x180008ccc`
- `0x18000be40`
- `0x180010b3c`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180010be0`
- `CRYPT32!CertCreateCertificateContext` at `0x180010be0`
- `CRYPT32!CertGetCertificateChain` at `0x180010c72`
- `CRYPT32!CertGetCertificateChain` at `0x180010c72`
- `CRYPT32!CertFreeCertificateContext` at `0x180010c11`
- `CRYPT32!CertFreeCertificateContext` at `0x180010cb1`
- `CRYPT32!CertFreeCertificateContext` at `0x180010c11`
- `CRYPT32!CertFreeCertificateContext` at `0x180010cb1`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180010bfb`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180010bfb`
- `CRYPT32!CertCloseStore` at `0x180010cc1`
- `CRYPT32!CertCloseStore` at `0x180010cc1`
- `CRYPT32!CertFreeCertificateChain` at `0x180010ca3`
- `CRYPT32!CertFreeCertificateChain` at `0x180010ca3`
- `CRYPT32!CertOpenStore` at `0x180010ba7`
- `CRYPT32!CertOpenStore` at `0x180010ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bb5`

## pseudocode

```c
__int64 __fastcall SSCatDBQueryCertChainByCerts2(
        unsigned int a1,
        __int64 a2,
        struct _FILETIME *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  const CERT_CONTEXT *v6; // rdi
  HCERTSTORE v9; // rsi
  DWORD LastError; // eax
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v14; // r14
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+58h] [rbp-21h] BYREF
  _CERT_CHAIN_PARA pChainPara; // [rsp+60h] [rbp-19h] BYREF
  __int64 v20; // [rsp+80h] [rbp+7h] BYREF

  v6 = 0;
  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  v9 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0x80u, 0);
  if ( !v9 )
    goto LABEL_2;
  v12 = 0;
  if ( a1 )
  {
    do
    {
      CertificateContext = CertCreateCertificateContext(
                             0x10001u,
                             *(const BYTE **)(a2 + 16LL * v12 + 8),
                             *(_DWORD *)(a2 + 16LL * v12));
      v14 = CertificateContext;
      if ( CertificateContext )
      {
        if ( !CertAddCertificateContextToStore(v9, CertificateContext, 4u, 0) )
          goto LABEL_2;
        if ( v12 )
          CertFreeCertificateContext(v14);
        else
          v6 = v14;
      }
      ++v12;
    }
    while ( v12 < a1 );
    if ( v6 )
    {
      v20 = a4;
      pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)&v20;
      pChainPara.cbSize = 32;
      pChainPara.RequestedUsage.dwType = 1;
      pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
      if ( CertGetCertificateChain((HCERTCHAINENGINE)1, v6, a3, v9, &pChainPara, 0, 0, &pChainContext) )
      {
        LastError = SerializeCertChainsAsP7B(pChainContext, a5, a6);
        goto LABEL_3;
      }
LABEL_2:
      LastError = GetLastError();
LABEL_3:
      v11 = LastError;
      goto LABEL_15;
    }
  }
  v11 = 232;
LABEL_15:
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( v9 )
    CertCloseStore(v9, 0);
  return v11;
}

```

## disassembly

```asm
0x180010b3c  mov     [rsp-8+arg_0], rbx
0x180010b41  push    rbp
0x180010b42  push    rsi
0x180010b43  push    rdi
0x180010b44  push    r12
0x180010b46  push    r13
0x180010b48  push    r14
0x180010b4a  push    r15
0x180010b4c  lea     rbp, [rsp-17h]
0x180010b51  sub     rsp, 90h
0x180010b58  mov     rax, cs:__security_cookie
0x180010b5f  xor     rax, rsp
0x180010b62  mov     [rbp+47h+var_38], rax
0x180010b66  mov     rax, [rbp+47h+arg_28]
0x180010b6a  xor     edi, edi
0x180010b6c  mov     r13, [rbp+47h+arg_20]
0x180010b70  xorps   xmm0, xmm0
0x180010b73  mov     [rbp+47h+var_80], r9
0x180010b77  mov     r12, rdx
0x180010b7a  mov     [rbp+47h+pTime], r8
0x180010b7e  mov     r15d, ecx
0x180010b81  lea     ecx, [rdi+2]; lpszStoreProvider
0x180010b84  mov     [rbp+47h+var_70], rax
0x180010b88  mov     r9d, 80h; dwFlags
0x180010b8e  mov     [rbp+47h+pChainContext], rdi
0x180010b92  xor     r8d, r8d; hCryptProv
0x180010b95  mov     [rsp+0C0h+pvPara], rdi; pvPara
0x180010b9a  mov     edx, 10001h; dwEncodingType
0x180010b9f  movups  xmmword ptr [rbp+47h+pChainPara.cbSize], xmm0
0x180010ba3  movups  xmmword ptr [rbp+47h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180010ba7  call    cs:__imp_CertOpenStore
0x180010bad  mov     rsi, rax
0x180010bb0  test    rax, rax
0x180010bb3  jnz     short loc_180010BC2
0x180010bb5  call    cs:__imp_GetLastError
0x180010bbb  mov     ebx, eax
0x180010bbd  jmp     loc_180010C9A
0x180010bc2  xor     ebx, ebx
0x180010bc4  test    r15d, r15d
0x180010bc7  jz      loc_180010C95
0x180010bcd  mov     edx, ebx
0x180010bcf  mov     ecx, 10001h; dwCertEncodingType
0x180010bd4  add     rdx, rdx
0x180010bd7  mov     r8d, [r12+rdx*8]; cbCertEncoded
0x180010bdb  mov     rdx, [r12+rdx*8+8]; pbCertEncoded
0x180010be0  call    cs:__imp_CertCreateCertificateContext
0x180010be6  mov     r14, rax
0x180010be9  test    rax, rax
0x180010bec  jz      short loc_180010C17
0x180010bee  xor     r9d, r9d; ppStoreContext
0x180010bf1  mov     rdx, rax; pCertContext
0x180010bf4  mov     rcx, rsi; hCertStore
0x180010bf7  lea     r8d, [r9+4]; dwAddDisposition
0x180010bfb  call    cs:__imp_CertAddCertificateContextToStore
0x180010c01  test    eax, eax
0x180010c03  jz      short loc_180010BB5
0x180010c05  test    ebx, ebx
0x180010c07  jnz     short loc_180010C0E
0x180010c09  mov     rdi, r14
0x180010c0c  jmp     short loc_180010C17
0x180010c0e  mov     rcx, r14; pCertContext
0x180010c11  call    cs:__imp_CertFreeCertificateContext
0x180010c17  mov     ecx, 1; hChainEngine
0x180010c1c  add     ebx, ecx
0x180010c1e  cmp     ebx, r15d
0x180010c21  jb      short loc_180010BCD
0x180010c23  test    rdi, rdi
0x180010c26  jz      short loc_180010C95
0x180010c28  mov     rax, [rbp+47h+var_80]
0x180010c2c  mov     r9, rsi; hAdditionalStore
0x180010c2f  mov     r8, [rbp+47h+pTime]; pTime
0x180010c33  mov     rdx, rdi; pCertContext
0x180010c36  mov     [rbp+47h+var_40], rax
0x180010c3a  lea     rax, [rbp+47h+var_40]
0x180010c3e  mov     [rbp+47h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x180010c42  lea     rax, [rbp+47h+pChainContext]
0x180010c46  mov     [rsp+0C0h+ppChainContext], rax; ppChainContext
0x180010c4b  lea     rax, [rbp+47h+pChainPara]
0x180010c4f  mov     [rsp+0C0h+pvReserved], 0; pvReserved
0x180010c58  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x180010c60  mov     [rsp+0C0h+pvPara], rax; pChainPara
0x180010c65  mov     [rbp+47h+pChainPara.cbSize], 20h ; ' '
0x180010c6c  mov     [rbp+47h+pChainPara.RequestedUsage.dwType], ecx
0x180010c6f  mov     [rbp+47h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], ecx
0x180010c72  call    cs:__imp_CertGetCertificateChain
0x180010c78  test    eax, eax
0x180010c7a  jz      loc_180010BB5
0x180010c80  mov     r8, [rbp+47h+var_70]
0x180010c84  mov     rdx, r13
0x180010c87  mov     rcx, [rbp+47h+pChainContext]
0x180010c8b  call    SerializeCertChainsAsP7B
0x180010c90  jmp     loc_180010BBB
0x180010c95  mov     ebx, 0E8h
0x180010c9a  mov     rcx, [rbp+47h+pChainContext]; pChainContext
0x180010c9e  test    rcx, rcx
0x180010ca1  jz      short loc_180010CA9
0x180010ca3  call    cs:__imp_CertFreeCertificateChain
0x180010ca9  test    rdi, rdi
0x180010cac  jz      short loc_180010CB7
0x180010cae  mov     rcx, rdi; pCertContext
0x180010cb1  call    cs:__imp_CertFreeCertificateContext
0x180010cb7  test    rsi, rsi
0x180010cba  jz      short loc_180010CC7
0x180010cbc  xor     edx, edx; dwFlags
0x180010cbe  mov     rcx, rsi; hCertStore
0x180010cc1  call    cs:__imp_CertCloseStore
0x180010cc7  mov     eax, ebx
0x180010cc9  mov     rcx, [rbp+47h+var_38]
0x180010ccd  xor     rcx, rsp; StackCookie
0x180010cd0  call    __security_check_cookie
0x180010cd5  mov     rbx, [rsp+0C0h+arg_0]
0x180010cdd  add     rsp, 90h
0x180010ce4  pop     r15
0x180010ce6  pop     r14
0x180010ce8  pop     r13
0x180010cea  pop     r12
0x180010cec  pop     rdi
0x180010ced  pop     rsi
0x180010cee  pop     rbp
0x180010cef  retn
```
