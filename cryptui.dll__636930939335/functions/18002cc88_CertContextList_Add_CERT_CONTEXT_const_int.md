# CertContextList::Add(_CERT_CONTEXT const *,int *)

- ea: `0x18002cc88`
- end: `0x18002cd4c`
- name: `?Add@CertContextList@@QEAAJPEBU_CERT_CONTEXT@@PEAH@Z`
- size: `196`
- prototype: `int(CertContextList *__hidden this, const struct _CERT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d1a4`

## callees

- `0x180001354`
- `0x18002cc88`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x18002ccf4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002cd19`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002ccf4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002cd19`
- `CRYPT32!CertFreeCertificateContext` at `0x18002cceb`
- `CRYPT32!CertFreeCertificateContext` at `0x18002cceb`
- `CRYPT32!CertCompareCertificate` at `0x18002ccce`
- `CRYPT32!CertCompareCertificate` at `0x18002ccce`

## pseudocode

```c
__int64 __fastcall CertContextList::Add(const CERT_CONTEXT ***this, const struct _CERT_CONTEXT *a2, int *a3)
{
  const CERT_CONTEXT **v6; // rbx
  unsigned int v7; // ebp
  const CERT_CONTEXT **v8; // rsi
  const CERT_CONTEXT *v9; // rcx
  PCCERT_CONTEXT v10; // rax
  const CERT_CONTEXT **v11; // rax

  if ( !a2 || !a3 )
    return 2147942487LL;
  v6 = *this;
  v7 = 0;
  v8 = 0;
  while ( v6 )
  {
    if ( (*v6)->dwCertEncodingType == a2->dwCertEncodingType
      && CertCompareCertificate(a2->dwCertEncodingType, a2->pCertInfo, (*v6)->pCertInfo) )
    {
      v9 = *v6;
      *a3 = 1;
      CertFreeCertificateContext(v9);
      v10 = CertDuplicateCertificateContext(a2);
LABEL_13:
      *v6 = v10;
      return v7;
    }
    v8 = v6;
    v6 = (const CERT_CONTEXT **)v6[1];
  }
  v11 = (const CERT_CONTEXT **)operator new(0x10u);
  v6 = v11;
  if ( v8 )
  {
    v8[1] = (const CERT_CONTEXT *)v11;
    if ( v11 )
      goto LABEL_12;
  }
  else if ( v11 )
  {
    *this = v11;
LABEL_12:
    v10 = CertDuplicateCertificateContext(a2);
    v6[1] = 0;
    goto LABEL_13;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18002cc88  push    rbx
0x18002cc8a  push    rbp
0x18002cc8b  push    rsi
0x18002cc8c  push    rdi
0x18002cc8d  push    r14
0x18002cc8f  push    r15
0x18002cc91  sub     rsp, 28h
0x18002cc95  mov     r14, r8
0x18002cc98  mov     rdi, rdx
0x18002cc9b  mov     r15, rcx
0x18002cc9e  test    rdx, rdx
0x18002cca1  jz      loc_18002CD3A
0x18002cca7  test    r8, r8
0x18002ccaa  jz      loc_18002CD3A
0x18002ccb0  mov     rbx, [rcx]
0x18002ccb3  xor     ebp, ebp
0x18002ccb5  xor     esi, esi
0x18002ccb7  test    rbx, rbx
0x18002ccba  jz      short loc_18002CCFC
0x18002ccbc  mov     r8, [rbx]
0x18002ccbf  mov     ecx, [rdi]; dwCertEncodingType
0x18002ccc1  cmp     [r8], ecx
0x18002ccc4  jnz     short loc_18002CCD8
0x18002ccc6  mov     r8, [r8+18h]; pCertId2
0x18002ccca  mov     rdx, [rdi+18h]; pCertId1
0x18002ccce  call    cs:__imp_CertCompareCertificate
0x18002ccd4  test    eax, eax
0x18002ccd6  jnz     short loc_18002CCE1
0x18002ccd8  mov     rsi, rbx
0x18002ccdb  mov     rbx, [rbx+8]
0x18002ccdf  jmp     short loc_18002CCB7
0x18002cce1  mov     rcx, [rbx]; pCertContext
0x18002cce4  mov     dword ptr [r14], 1
0x18002cceb  call    cs:__imp_CertFreeCertificateContext
0x18002ccf1  mov     rcx, rdi; pCertContext
0x18002ccf4  call    cs:__imp_CertDuplicateCertificateContext
0x18002ccfa  jmp     short loc_18002CD23
0x18002ccfc  mov     ecx, 10h; Size
0x18002cd01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cd06  mov     rbx, rax
0x18002cd09  test    rsi, rsi
0x18002cd0c  jnz     short loc_18002CD2A
0x18002cd0e  test    rax, rax
0x18002cd11  jz      short loc_18002CD33
0x18002cd13  mov     [r15], rax
0x18002cd16  mov     rcx, rdi; pCertContext
0x18002cd19  call    cs:__imp_CertDuplicateCertificateContext
0x18002cd1f  mov     [rbx+8], rbp
0x18002cd23  mov     [rbx], rax
0x18002cd26  mov     eax, ebp
0x18002cd28  jmp     short loc_18002CD3F
0x18002cd2a  mov     [rsi+8], rax
0x18002cd2e  test    rax, rax
0x18002cd31  jnz     short loc_18002CD16
0x18002cd33  mov     ebp, 8007000Eh
0x18002cd38  jmp     short loc_18002CD26
0x18002cd3a  mov     eax, 80070057h
0x18002cd3f  add     rsp, 28h
0x18002cd43  pop     r15
0x18002cd45  pop     r14
0x18002cd47  pop     rdi
0x18002cd48  pop     rsi
0x18002cd49  pop     rbp
0x18002cd4a  pop     rbx
0x18002cd4b  retn
```
