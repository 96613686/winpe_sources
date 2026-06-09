# FindIssuerCertInDefaultStores

- ea: `0x180010de0`
- end: `0x180010e79`
- name: `FindIssuerCertInDefaultStores`
- size: `153`
- prototype: `const struct _CERT_CONTEXT *__fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f140`

## callees

- `0x180010d50`
- `0x180010de0`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x180010e50`
- `CRYPT32!CertCloseStore` at `0x180010e50`
- `CRYPT32!CertOpenStore` at `0x180010e23`
- `CRYPT32!CertOpenStore` at `0x180010e23`

## pseudocode

```c
const struct _CERT_CONTEXT *__fastcall FindIssuerCertInDefaultStores(PCCERT_CONTEXT pCertContext)
{
  unsigned int i; // ebx
  void *v3; // rbp
  const struct _CERT_CONTEXT *IssuerCertInStores; // rdi
  void *v6; // [rsp+58h] [rbp+10h] BYREF

  for ( i = 0; i < 3; ++i )
  {
    v6 = CertOpenStore((LPCSTR)0xA, 0, 0, *((_DWORD *)&off_180032070 + 4 * i + 2) | 0x8000u, (&off_180032070)[2 * i]);
    v3 = v6;
    if ( v6 )
    {
      IssuerCertInStores = FindIssuerCertInStores(pCertContext, 1u, &v6);
      CertCloseStore(v3, 0);
      if ( IssuerCertInStores )
        return IssuerCertInStores;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010de0  mov     [rsp+arg_0], rbx
0x180010de5  mov     [rsp+arg_10], rbp
0x180010dea  push    rsi
0x180010deb  push    rdi
0x180010dec  push    r14
0x180010dee  sub     rsp, 30h
0x180010df2  mov     rsi, rcx
0x180010df5  lea     r14, off_180032070; "CA"
0x180010dfc  xor     ebx, ebx
0x180010dfe  cmp     ebx, 3
0x180010e01  jnb     short loc_180010E64
0x180010e03  xor     edx, edx; dwEncodingType
0x180010e05  mov     eax, ebx
0x180010e07  add     rax, rax
0x180010e0a  xor     r8d, r8d; hCryptProv
0x180010e0d  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180010e10  mov     r9d, [r14+rax*8+8]
0x180010e15  mov     rax, [r14+rax*8]
0x180010e19  bts     r9d, 0Fh; dwFlags
0x180010e1e  mov     [rsp+48h+pvPara], rax; pvPara
0x180010e23  call    cs:__imp_CertOpenStore
0x180010e29  mov     [rsp+48h+arg_8], rax
0x180010e2e  mov     rbp, rax
0x180010e31  test    rax, rax
0x180010e34  jz      short loc_180010E5B
0x180010e36  lea     r8, [rsp+48h+arg_8]; void **
0x180010e3b  mov     edx, 1; unsigned int
0x180010e40  mov     rcx, rsi; pCertContext
0x180010e43  call    ?FindIssuerCertInStores@@YAPEBU_CERT_CONTEXT@@PEBU1@KQEAPEAX@Z; FindIssuerCertInStores(_CERT_CONTEXT const *,ulong,void * * const)
0x180010e48  xor     edx, edx; dwFlags
0x180010e4a  mov     rcx, rbp; hCertStore
0x180010e4d  mov     rdi, rax
0x180010e50  call    cs:__imp_CertCloseStore
0x180010e56  test    rdi, rdi
0x180010e59  jnz     short loc_180010E5F
0x180010e5b  inc     ebx
0x180010e5d  jmp     short loc_180010DFE
0x180010e5f  mov     rax, rdi
0x180010e62  jmp     short loc_180010E66
0x180010e64  xor     eax, eax
0x180010e66  mov     rbx, [rsp+48h+arg_0]
0x180010e6b  mov     rbp, [rsp+48h+arg_10]
0x180010e70  add     rsp, 30h
0x180010e74  pop     r14
0x180010e76  pop     rdi
0x180010e77  pop     rsi
0x180010e78  retn
```
