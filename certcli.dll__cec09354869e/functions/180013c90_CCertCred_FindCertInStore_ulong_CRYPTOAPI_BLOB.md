# CCertCred::FindCertInStore(ulong,_CRYPTOAPI_BLOB *)

- ea: `0x180013c90`
- end: `0x180013d47`
- name: `?FindCertInStore@CCertCred@@AEAAJKPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(CCertCred *this, DWORD, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013f70`

## callees

- `0x180013c90`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180013cb6`
- `CRYPT32!CertOpenStore` at `0x180013cb6`
- `CRYPT32!CertFreeCertificateContext` at `0x180013ce6`
- `CRYPT32!CertFreeCertificateContext` at `0x180013ce6`
- `CRYPT32!CertCloseStore` at `0x180013d36`
- `CRYPT32!CertCloseStore` at `0x180013d36`
- `CRYPT32!CertFindCertificateInStore` at `0x180013d0a`
- `CRYPT32!CertFindCertificateInStore` at `0x180013d0a`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x180013cc4`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x180013d19`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x180013cc4`
- `certca!__imp_?myHGetLastError@@YAJXZ` at `0x180013d19`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180013cd3`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180013d28`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180013cd3`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180013d28`

## pseudocode

```c
__int64 __fastcall CCertCred::FindCertInStore(CCertCred *this, DWORD a2, struct _CRYPTOAPI_BLOB *a3)
{
  HCERTSTORE v5; // rsi
  unsigned int Error; // ebx
  const CERT_CONTEXT *v7; // rcx
  PCCERT_CONTEXT CertificateInStore; // rax

  v5 = CertOpenStore((LPCSTR)0xA, 0, 0, a2, L"MY");
  if ( v5 )
  {
    v7 = (const CERT_CONTEXT *)*((_QWORD *)this + 1);
    Error = 0;
    if ( v7 )
    {
      CertFreeCertificateContext(v7);
      *((_QWORD *)this + 1) = 0;
    }
    CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0x10000u, a3, 0);
    *((_QWORD *)this + 1) = CertificateInStore;
    if ( !CertificateInStore )
    {
      Error = myHGetLastError();
      CSPrintErrorLineFile(0x1710BC0u, Error);
    }
    CertCloseStore(v5, 2u);
  }
  else
  {
    Error = myHGetLastError();
    CSPrintErrorLineFile(0x15E0BC0u, Error);
  }
  return Error;
}

```

## disassembly

```asm
0x180013c90  push    rbx
0x180013c92  push    rbp
0x180013c93  push    rsi
0x180013c94  push    rdi
0x180013c95  sub     rsp, 38h
0x180013c99  mov     r9d, edx; dwFlags
0x180013c9c  lea     rax, aMy; "MY"
0x180013ca3  xor     edx, edx; dwEncodingType
0x180013ca5  mov     [rsp+58h+pvPara], rax; pvPara
0x180013caa  mov     rbp, r8
0x180013cad  mov     rdi, rcx
0x180013cb0  xor     r8d, r8d; hCryptProv
0x180013cb3  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180013cb6  call    cs:__imp_CertOpenStore
0x180013cbc  mov     rsi, rax
0x180013cbf  test    rax, rax
0x180013cc2  jnz     short loc_180013CDB
0x180013cc4  call    cs:__imp_?myHGetLastError@@YAJXZ; myHGetLastError(void)
0x180013cca  mov     edx, eax
0x180013ccc  mov     ecx, 15E0BC0h
0x180013cd1  mov     ebx, eax
0x180013cd3  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180013cd9  jmp     short loc_180013D3C
0x180013cdb  mov     rcx, [rdi+8]; pCertContext
0x180013cdf  xor     ebx, ebx
0x180013ce1  test    rcx, rcx
0x180013ce4  jz      short loc_180013CF0
0x180013ce6  call    cs:__imp_CertFreeCertificateContext
0x180013cec  mov     [rdi+8], rbx
0x180013cf0  mov     r9d, 10000h; dwFindType
0x180013cf6  mov     [rsp+58h+pPrevCertContext], rbx; pPrevCertContext
0x180013cfb  xor     r8d, r8d; dwFindFlags
0x180013cfe  mov     [rsp+58h+pvPara], rbp; pvFindPara
0x180013d03  mov     rcx, rsi; hCertStore
0x180013d06  lea     edx, [r9+1]; dwCertEncodingType
0x180013d0a  call    cs:__imp_CertFindCertificateInStore
0x180013d10  mov     [rdi+8], rax
0x180013d14  test    rax, rax
0x180013d17  jnz     short loc_180013D2E
0x180013d19  call    cs:__imp_?myHGetLastError@@YAJXZ; myHGetLastError(void)
0x180013d1f  mov     edx, eax
0x180013d21  mov     ecx, 1710BC0h
0x180013d26  mov     ebx, eax
0x180013d28  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180013d2e  mov     edx, 2; dwFlags
0x180013d33  mov     rcx, rsi; hCertStore
0x180013d36  call    cs:__imp_CertCloseStore
0x180013d3c  mov     eax, ebx
0x180013d3e  add     rsp, 38h
0x180013d42  pop     rdi
0x180013d43  pop     rsi
0x180013d44  pop     rbp
0x180013d45  pop     rbx
0x180013d46  retn
```
