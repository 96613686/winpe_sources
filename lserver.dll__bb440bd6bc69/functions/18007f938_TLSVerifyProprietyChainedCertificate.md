# TLSVerifyProprietyChainedCertificate

- ea: `0x18007f938`
- end: `0x18007fb0b`
- name: `TLSVerifyProprietyChainedCertificate`
- size: `467`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d998`

## callees

- `0x18007f938`

## import_xrefs

- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18007fa5b`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x18007fa5b`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007fa28`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007fa28`
- `CRYPT32!CertCreateCertificateContext` at `0x18007fa07`
- `CRYPT32!CertCreateCertificateContext` at `0x18007fa9d`
- `CRYPT32!CertCreateCertificateContext` at `0x18007fa07`
- `CRYPT32!CertCreateCertificateContext` at `0x18007fa9d`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fa74`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fac8`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fadc`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fa74`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fac8`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fadc`

## pseudocode

```c
__int64 __fastcall TLSVerifyProprietyChainedCertificate(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v5; // rdx
  unsigned int v6; // r9d
  unsigned int *v7; // r15
  _DWORD *v8; // r11
  unsigned int v9; // ecx
  unsigned int i; // r10d
  unsigned int v11; // ecx
  unsigned int v12; // eax
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v14; // rdi
  unsigned int v15; // ebx
  const CERT_CONTEXT *v16; // rax
  unsigned int j; // ebp
  const CERT_CONTEXT *v18; // rsi
  DWORD pdwFlags; // [rsp+58h] [rbp+20h] BYREF
  int v21; // [rsp+5Ch] [rbp+24h]

  v21 = HIDWORD(a4);
  pdwFlags = 3;
  if ( !a2 )
    return 3;
  if ( a3 < 0x40 )
    return 3;
  if ( (*(_DWORD *)a2 & 0xFFFFFFFu) > 2 )
    return 3;
  v5 = *(unsigned int *)(a2 + 4);
  if ( (unsigned int)(v5 - 2) > 0xC6 || a3 < (unsigned __int64)(8 * v5 + 8) )
    return 3;
  v6 = 8;
  v7 = (unsigned int *)(a2 + 8);
  v8 = (_DWORD *)(a2 + 8);
  v9 = 8;
  for ( i = 0; i < (unsigned int)v5; ++i )
  {
    v11 = v9 + 4;
    if ( v11 < v6 )
      return 3;
    if ( v11 > a3 )
      return 3;
    v12 = v11;
    v9 = *v8 + v11;
    if ( v9 < v12 || v9 > a3 )
      return 3;
    v6 = v9;
    v8 = (_DWORD *)((char *)v8 + (unsigned int)*v8 + 4);
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, (const BYTE *)(a2 + 12), *v7);
  v14 = CertificateContext;
  if ( CertificateContext )
  {
    v15 = 0;
    v16 = CertDuplicateCertificateContext(CertificateContext);
    for ( j = 0; ; ++j )
    {
      v18 = v16;
      if ( j >= *(_DWORD *)(a2 + 4) )
        break;
      if ( !v16 )
      {
        v15 = 16;
LABEL_25:
        if ( !v14 )
          goto LABEL_27;
        break;
      }
      pdwFlags = 1;
      if ( !CertVerifySubjectCertificateContext(v16, v14, &pdwFlags) )
        goto LABEL_23;
      if ( pdwFlags )
      {
        v15 = 3;
        goto LABEL_25;
      }
      if ( !CertFreeCertificateContext(v14) )
      {
LABEL_23:
        v15 = 7;
        goto LABEL_25;
      }
      v14 = v18;
      v7 = (unsigned int *)((char *)v7 + *v7 + 4);
      v16 = CertCreateCertificateContext(0x10001u, (const BYTE *)v7 + 4, *v7);
    }
    CertFreeCertificateContext(v14);
LABEL_27:
    if ( v18 )
      CertFreeCertificateContext(v18);
  }
  else
  {
    return 16;
  }
  return v15;
}

```

## disassembly

```asm
0x18007f938  mov     rax, rsp
0x18007f93b  mov     [rax+8], rbx
0x18007f93f  mov     [rax+10h], rbp
0x18007f943  mov     [rax+18h], rsi
0x18007f947  mov     [rax+20h], r9
0x18007f94b  push    rdi
0x18007f94c  push    r14
0x18007f94e  push    r15
0x18007f950  sub     rsp, 20h
0x18007f954  mov     dword ptr [rax+20h], 3
0x18007f95b  mov     r14, rdx
0x18007f95e  test    rdx, rdx
0x18007f961  jz      loc_18007FAEC
0x18007f967  cmp     r8d, 40h ; '@'
0x18007f96b  jb      loc_18007FAEC
0x18007f971  mov     eax, [rdx]
0x18007f973  and     eax, 0FFFFFFFh
0x18007f978  cmp     eax, 2
0x18007f97b  ja      loc_18007FAEC
0x18007f981  mov     edx, [rdx+4]
0x18007f984  lea     eax, [rdx-2]
0x18007f987  cmp     eax, 0C6h
0x18007f98c  ja      loc_18007FAEC
0x18007f992  lea     rcx, ds:8[rdx*8]
0x18007f99a  mov     eax, r8d
0x18007f99d  cmp     rax, rcx
0x18007f9a0  jb      loc_18007FAEC
0x18007f9a6  mov     r9d, 8
0x18007f9ac  lea     r15, [r14+8]
0x18007f9b0  mov     r11, r15
0x18007f9b3  mov     ecx, r9d
0x18007f9b6  xor     r10d, r10d
0x18007f9b9  cmp     r10d, edx
0x18007f9bc  jnb     short loc_18007F9FB
0x18007f9be  add     ecx, 4
0x18007f9c1  cmp     ecx, r9d
0x18007f9c4  jb      loc_18007FAEC
0x18007f9ca  cmp     ecx, r8d
0x18007f9cd  ja      loc_18007FAEC
0x18007f9d3  mov     eax, ecx
0x18007f9d5  add     ecx, [r11]
0x18007f9d8  cmp     ecx, eax
0x18007f9da  jb      loc_18007FAEC
0x18007f9e0  cmp     ecx, r8d
0x18007f9e3  ja      loc_18007FAEC
0x18007f9e9  mov     eax, [r11]
0x18007f9ec  mov     r9d, ecx
0x18007f9ef  add     r11, 4
0x18007f9f3  add     r11, rax
0x18007f9f6  inc     r10d
0x18007f9f9  jmp     short loc_18007F9B9
0x18007f9fb  mov     r8d, [r15]; cbCertEncoded
0x18007f9fe  lea     rdx, [r15+4]; pbCertEncoded
0x18007fa02  mov     ecx, 10001h; dwCertEncodingType
0x18007fa07  call    cs:__imp_CertCreateCertificateContext
0x18007fa0e  nop     dword ptr [rax+rax+00h]
0x18007fa13  mov     rdi, rax
0x18007fa16  test    rax, rax
0x18007fa19  jnz     short loc_18007FA23
0x18007fa1b  lea     ebx, [rax+10h]
0x18007fa1e  jmp     loc_18007FAE8
0x18007fa23  mov     rcx, rax; pCertContext
0x18007fa26  xor     ebx, ebx
0x18007fa28  call    cs:__imp_CertDuplicateCertificateContext
0x18007fa2f  nop     dword ptr [rax+rax+00h]
0x18007fa34  xor     ebp, ebp
0x18007fa36  mov     rsi, rax
0x18007fa39  cmp     ebp, [r14+4]
0x18007fa3d  jnb     loc_18007FAC5
0x18007fa43  test    rax, rax
0x18007fa46  jz      short loc_18007FABB
0x18007fa48  lea     r8, [rsp+38h+pdwFlags]; pdwFlags
0x18007fa4d  mov     [rsp+38h+pdwFlags], 1
0x18007fa55  mov     rdx, rdi; pIssuer
0x18007fa58  mov     rcx, rax; pSubject
0x18007fa5b  call    cs:__imp_CertVerifySubjectCertificateContext
0x18007fa62  nop     dword ptr [rax+rax+00h]
0x18007fa67  test    eax, eax
0x18007fa69  jz      short loc_18007FAB4
0x18007fa6b  cmp     [rsp+38h+pdwFlags], ebx
0x18007fa6f  jnz     short loc_18007FAAD
0x18007fa71  mov     rcx, rdi; pCertContext
0x18007fa74  call    cs:__imp_CertFreeCertificateContext
0x18007fa7b  nop     dword ptr [rax+rax+00h]
0x18007fa80  test    eax, eax
0x18007fa82  jz      short loc_18007FAB4
0x18007fa84  mov     eax, [r15]
0x18007fa87  mov     ecx, 10001h; dwCertEncodingType
0x18007fa8c  add     rax, 4
0x18007fa90  mov     rdi, rsi
0x18007fa93  add     r15, rax
0x18007fa96  mov     r8d, [r15]; cbCertEncoded
0x18007fa99  lea     rdx, [r15+4]; pbCertEncoded
0x18007fa9d  call    cs:__imp_CertCreateCertificateContext
0x18007faa4  nop     dword ptr [rax+rax+00h]
0x18007faa9  inc     ebp
0x18007faab  jmp     short loc_18007FA36
0x18007faad  mov     ebx, 3
0x18007fab2  jmp     short loc_18007FAC0
0x18007fab4  mov     ebx, 7
0x18007fab9  jmp     short loc_18007FAC0
0x18007fabb  mov     ebx, 10h
0x18007fac0  test    rdi, rdi
0x18007fac3  jz      short loc_18007FAD4
0x18007fac5  mov     rcx, rdi; pCertContext
0x18007fac8  call    cs:__imp_CertFreeCertificateContext
0x18007facf  nop     dword ptr [rax+rax+00h]
0x18007fad4  test    rsi, rsi
0x18007fad7  jz      short loc_18007FAE8
0x18007fad9  mov     rcx, rsi; pCertContext
0x18007fadc  call    cs:__imp_CertFreeCertificateContext
0x18007fae3  nop     dword ptr [rax+rax+00h]
0x18007fae8  mov     eax, ebx
0x18007faea  jmp     short loc_18007FAF1
0x18007faec  mov     eax, 3
0x18007faf1  mov     rbx, [rsp+38h+arg_0]
0x18007faf6  mov     rbp, [rsp+38h+arg_8]
0x18007fafb  mov     rsi, [rsp+38h+arg_10]
0x18007fb00  add     rsp, 20h
0x18007fb04  pop     r15
0x18007fb06  pop     r14
0x18007fb08  pop     rdi
0x18007fb09  retn
```
