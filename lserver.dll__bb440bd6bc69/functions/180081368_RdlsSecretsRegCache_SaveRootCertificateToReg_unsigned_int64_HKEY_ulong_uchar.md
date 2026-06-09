# RdlsSecretsRegCache::SaveRootCertificateToReg(unsigned __int64,HKEY__ *,ulong,uchar *)

- ea: `0x180081368`
- end: `0x180081434`
- name: `?SaveRootCertificateToReg@RdlsSecretsRegCache@@AEAAK_KPEAUHKEY__@@KPEAE@Z`
- size: `204`
- prototype: `unsigned int(RdlsSecretsRegCache *__hidden this, unsigned __int64, HKEY, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180080e30`

## callees

- `0x180081368`

## import_xrefs

- `CRYPT32!CertAddCertificateContextToStore` at `0x1800813e0`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800813e0`
- `CRYPT32!CertOpenStore` at `0x180081390`
- `CRYPT32!CertOpenStore` at `0x180081390`
- `CRYPT32!CertCreateCertificateContext` at `0x1800813b8`
- `CRYPT32!CertCreateCertificateContext` at `0x1800813b8`
- `CRYPT32!CertFreeCertificateContext` at `0x180081401`
- `CRYPT32!CertFreeCertificateContext` at `0x180081401`
- `CRYPT32!CertCloseStore` at `0x180081415`
- `CRYPT32!CertCloseStore` at `0x180081415`
- `KERNEL32!GetLastError` at `0x1800813f0`
- `KERNEL32!GetLastError` at `0x1800813f0`

## pseudocode

```c
__int64 __fastcall RdlsSecretsRegCache::SaveRootCertificateToReg(
        RdlsSecretsRegCache *this,
        HCRYPTPROV_LEGACY a2,
        HKEY pvPara,
        DWORD a4,
        unsigned __int8 *pbCertEncoded)
{
  DWORD LastError; // ebx
  HCERTSTORE v7; // rsi
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v9; // rdi

  LastError = 0;
  v7 = CertOpenStore((LPCSTR)4, 0x10001u, a2, 1u, pvPara);
  if ( v7 )
  {
    CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, a4);
    v9 = CertificateContext;
    if ( CertificateContext )
    {
      if ( !CertAddCertificateContextToStore(v7, CertificateContext, 3u, 0) )
        LastError = GetLastError();
      CertFreeCertificateContext(v9);
    }
    else
    {
      LastError = -1073676256;
    }
    CertCloseStore(v7, 1u);
  }
  else
  {
    return (DWORD)-1073676256;
  }
  return LastError;
}

```

## disassembly

```asm
0x180081368  mov     [rsp+arg_0], rbx
0x18008136d  mov     [rsp+arg_8], rsi
0x180081372  push    rdi
0x180081373  sub     rsp, 30h
0x180081377  xor     ebx, ebx
0x180081379  mov     [rsp+38h+pvPara], r8; pvPara
0x18008137e  mov     edi, r9d
0x180081381  mov     r8, rdx; hCryptProv
0x180081384  mov     edx, 10001h; dwEncodingType
0x180081389  lea     r9d, [rbx+1]; dwFlags
0x18008138d  lea     ecx, [rbx+4]; lpszStoreProvider
0x180081390  call    cs:__imp_CertOpenStore
0x180081397  nop     dword ptr [rax+rax+00h]
0x18008139c  mov     rsi, rax
0x18008139f  test    rax, rax
0x1800813a2  jnz     short loc_1800813AB
0x1800813a4  mov     ebx, 0C0010020h
0x1800813a9  jmp     short loc_180081421
0x1800813ab  mov     rdx, [rsp+38h+pbCertEncoded]; pbCertEncoded
0x1800813b0  mov     r8d, edi; cbCertEncoded
0x1800813b3  mov     ecx, 1; dwCertEncodingType
0x1800813b8  call    cs:__imp_CertCreateCertificateContext
0x1800813bf  nop     dword ptr [rax+rax+00h]
0x1800813c4  mov     rdi, rax
0x1800813c7  test    rax, rax
0x1800813ca  jnz     short loc_1800813D3
0x1800813cc  mov     ebx, 0C0010020h
0x1800813d1  jmp     short loc_18008140D
0x1800813d3  xor     r9d, r9d; ppStoreContext
0x1800813d6  mov     rdx, rdi; pCertContext
0x1800813d9  mov     rcx, rsi; hCertStore
0x1800813dc  lea     r8d, [r9+3]; dwAddDisposition
0x1800813e0  call    cs:__imp_CertAddCertificateContextToStore
0x1800813e7  nop     dword ptr [rax+rax+00h]
0x1800813ec  test    eax, eax
0x1800813ee  jnz     short loc_1800813FE
0x1800813f0  call    cs:__imp_GetLastError
0x1800813f7  nop     dword ptr [rax+rax+00h]
0x1800813fc  mov     ebx, eax
0x1800813fe  mov     rcx, rdi; pCertContext
0x180081401  call    cs:__imp_CertFreeCertificateContext
0x180081408  nop     dword ptr [rax+rax+00h]
0x18008140d  mov     edx, 1; dwFlags
0x180081412  mov     rcx, rsi; hCertStore
0x180081415  call    cs:__imp_CertCloseStore
0x18008141c  nop     dword ptr [rax+rax+00h]
0x180081421  mov     rsi, [rsp+38h+arg_8]
0x180081426  mov     eax, ebx
0x180081428  mov     rbx, [rsp+38h+arg_0]
0x18008142d  add     rsp, 30h
0x180081431  pop     rdi
0x180081432  retn
```
