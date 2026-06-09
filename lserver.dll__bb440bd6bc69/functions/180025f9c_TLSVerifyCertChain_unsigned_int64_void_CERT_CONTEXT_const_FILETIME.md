# TLSVerifyCertChain(unsigned __int64,void *,_CERT_CONTEXT const *,_FILETIME *)

- ea: `0x180025f9c`
- end: `0x18002606d`
- name: `?TLSVerifyCertChain@@YAK_KPEAXPEBU_CERT_CONTEXT@@PEAU_FILETIME@@@Z`
- size: `209`
- prototype: `unsigned int(unsigned __int64, void *, const struct _CERT_CONTEXT *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026074`
- `0x180026ac4`

## callees

- `0x180025e00`
- `0x180025f9c`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x180025fb9`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180025fb9`
- `CRYPT32!CertFreeCertificateContext` at `0x180025ffb`
- `CRYPT32!CertFreeCertificateContext` at `0x18002603b`
- `CRYPT32!CertFreeCertificateContext` at `0x180025ffb`
- `CRYPT32!CertFreeCertificateContext` at `0x18002603b`
- `KERNEL32!CompareFileTime` at `0x180025fd8`
- `KERNEL32!CompareFileTime` at `0x180025fd8`
- `KERNEL32!GetLastError` at `0x18002601d`
- `KERNEL32!GetLastError` at `0x18002601d`
- `KERNEL32!SetLastError` at `0x180026049`
- `KERNEL32!SetLastError` at `0x180026049`

## pseudocode

```c
__int64 __fastcall TLSVerifyCertChain(__int64 a1, void *a2, const struct _CERT_CONTEXT *a3, struct _FILETIME *a4)
{
  const CERT_CONTEXT *v6; // rbx
  int v7; // r8d
  const CERT_CONTEXT *i; // rdx
  const struct _CERT_CONTEXT *IssuerCertificateFromStore; // rax
  const struct _CERT_CONTEXT *v10; // rdi
  DWORD LastError; // eax
  DWORD v12; // edi

  v6 = CertDuplicateCertificateContext(a3);
  for ( i = v6; ; i = v10 )
  {
    IssuerCertificateFromStore = GetIssuerCertificateFromStore(a2, i, v7);
    v10 = IssuerCertificateFromStore;
    if ( !IssuerCertificateFromStore )
      break;
    if ( CompareFileTime(a4, &IssuerCertificateFromStore->pCertInfo->NotAfter) > 0 )
      *a4 = v10->pCertInfo->NotAfter;
    if ( v6 )
      CertFreeCertificateContext(v6);
    v6 = v10;
  }
  LastError = GetLastError();
  v12 = 0;
  if ( LastError != -2146885625 )
    v12 = LastError;
  if ( v6 )
    CertFreeCertificateContext(v6);
  SetLastError(v12);
  return v12;
}

```

## disassembly

```asm
0x180025f9c  mov     [rsp+arg_0], rbx
0x180025fa1  mov     [rsp+arg_8], rbp
0x180025fa6  mov     [rsp+arg_10], rsi
0x180025fab  push    rdi
0x180025fac  sub     rsp, 20h
0x180025fb0  mov     rcx, r8; pCertContext
0x180025fb3  mov     rsi, r9
0x180025fb6  mov     rbp, rdx
0x180025fb9  call    cs:__imp_CertDuplicateCertificateContext
0x180025fc0  nop     dword ptr [rax+rax+00h]
0x180025fc5  mov     rbx, rax
0x180025fc8  mov     rdx, rax
0x180025fcb  jmp     short loc_18002600D
0x180025fcd  mov     rdx, [rdi+18h]
0x180025fd1  mov     rcx, rsi; lpFileTime1
0x180025fd4  add     rdx, 48h ; 'H'; lpFileTime2
0x180025fd8  call    cs:__imp_CompareFileTime
0x180025fdf  nop     dword ptr [rax+rax+00h]
0x180025fe4  test    eax, eax
0x180025fe6  jle     short loc_180025FF3
0x180025fe8  mov     rax, [rdi+18h]
0x180025fec  mov     rcx, [rax+48h]
0x180025ff0  mov     [rsi], rcx
0x180025ff3  test    rbx, rbx
0x180025ff6  jz      short loc_180026007
0x180025ff8  mov     rcx, rbx; pCertContext
0x180025ffb  call    cs:__imp_CertFreeCertificateContext
0x180026002  nop     dword ptr [rax+rax+00h]
0x180026007  mov     rbx, rdi
0x18002600a  mov     rdx, rdi; pSubjectContext
0x18002600d  mov     rcx, rbp; hCertStore
0x180026010  call    ?GetIssuerCertificateFromStore@@YAPEBU_CERT_CONTEXT@@PEAXPEBU1@H@Z; GetIssuerCertificateFromStore(void *,_CERT_CONTEXT const *,int)
0x180026015  mov     rdi, rax
0x180026018  test    rax, rax
0x18002601b  jnz     short loc_180025FCD
0x18002601d  call    cs:__imp_GetLastError
0x180026024  nop     dword ptr [rax+rax+00h]
0x180026029  xor     edi, edi
0x18002602b  cmp     eax, 80092007h
0x180026030  cmovnz  edi, eax
0x180026033  test    rbx, rbx
0x180026036  jz      short loc_180026047
0x180026038  mov     rcx, rbx; pCertContext
0x18002603b  call    cs:__imp_CertFreeCertificateContext
0x180026042  nop     dword ptr [rax+rax+00h]
0x180026047  mov     ecx, edi; dwErrCode
0x180026049  call    cs:__imp_SetLastError
0x180026050  nop     dword ptr [rax+rax+00h]
0x180026055  mov     rbx, [rsp+28h+arg_0]
0x18002605a  mov     eax, edi
0x18002605c  mov     rbp, [rsp+28h+arg_8]
0x180026061  mov     rsi, [rsp+28h+arg_10]
0x180026066  add     rsp, 20h
0x18002606a  pop     rdi
0x18002606b  retn
```
